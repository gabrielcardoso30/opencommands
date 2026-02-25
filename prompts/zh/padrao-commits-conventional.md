依据提供的 diff 生成一条清晰、具体且包含丰富信息的 commit 信息。请遵循 *Conventional Commits* 标准并使用 **中文** 书写。

目标
- 忠实反映所有变更内容（当存在多项变更时）。
- 标题简洁（<= 100 字符）。仅在能增加价值时提供正文，正文每行 100 字符换行。
- 禁止使用代码块、表情符号 (emojis) 或外部引号。

格式
<类型>(<范围>): <描述>
[可选的正文行，每行 100 字符换行]
[可选的页脚]

类型（请精准选择；若有多个相关类型，按重要程度列出最多 2 个，中间用逗号分隔）
- feat: 新功能（可见的功能或新行为）
- fix: 修补 bug
- refactor: 代码重构（既不修复 bug 也不添加功能的代码更改）
- perf: 性能优化
- docs: 文档/注释/XMLDoc 变更
- style: 格式、lint、命名变更（不影响功能）
- test: 添加/调整测试
- chore: 维护、依赖、构建、CI/CD、配置变更
- build: 打包/构建系统变更
- ci: 流水线/自动化变更

范围 (Scope)
- 使用短名词标识主要受影响的区域。
- 优先选择 diff 中占主导地位的目录或模块（如：core, api, httpclient, middleware, config, infra, auth, swagger, db, ci, build）。
- 若涉及多个区域且无主导区域，请使用聚合词，如：global, app, multi。

描述（标题）
- 使用动词且不加句号。
- 文件名、符号和数字请用反引号 (`) 包围。
- 必须说明做了什么 + 主要核心点。<= 100 字符。

正文（可选，但若存在多项变更则强烈建议提供）
- 列出客观项，按区域/主题分组。使用 "- " 作为列表符。
- 解释更改了什么、原因以及影响（兼容性/行为）。
- 每 100 字符换行。
- 若包含不同性质的更改，请在不同的要点中全部体现。
- 使用具体的标识符：类名、方法名、文件名和配置键。避免泛泛而谈。

混合提交的特殊规则
1) 若 diff 包含多种性质的更改：
   - 最多选择两个类型（如 "feat,refactor" 或 "refactor,fix"）。
   - 使用聚合范围（如 "core" 或 "global"）或主导范围。
   - 在正文中按主题创建要点。
2) 若包含潜在的破坏性变更，请包含页脚：
   - BREAKING CHANGE: <简短描述>
3) 若 diff 提及 issue/PR，请包含页脚：
   - Refs: #123, #456
   - Closes: #789

决策算法（摘要）
- 通过 diff 内容识别主题。
- 根据对用户/系统最相关的影响来定义标题。
- 在正文中，用简短的技术要点涵盖所有其他更改。

输出
- 按照上述规则生成最终的 commit 信息。
- 仅提供信息内容，不要放入代码块。
- 标题 <= 100 字符。正文每行 100 字符换行。
- 使用中文。

差异列表 (git diff --staged)
{diff}

示例参考（请勿直接复制；仅作为指南）
1)
refactor,fix(global): 增强 json 健壮性及错误处理
- 为 `decimal` 和 `decimal?` 添加支持字符串和逗号的转换器
- 配置 `AddJsonOptions` 并全局注册转换器
- 调整 `Program.cs` 中的中间件顺序以实现一致的捕获
- 增强 `ErrorHandlerMiddleware` (状态映射, traceId, 日志)
- 强化 `LojaConceitoHttpClient` (content-type, 原始 payload, 错误路径)

2)
feat(core): 支持灵活的 decimal 转换器和全局 json
- 为 `decimal`/`decimal?` 注册转换器及 `AllowReadingFromString`
- 在错误信息中记录并应用 72 列换行
- 重组中间件并将 `UseErrorHandlerMiddleware` 置于流水线前端
- 改进 `XPTO` httpclient 的诊断和响应
