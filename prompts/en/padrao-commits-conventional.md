Generate ONE clear, specific, and informative commit message based on the provided diff. Follow *Conventional Commits* and write in **English**.

OBJECTIVE
- Faithfully reflect EVERYTHING that was changed (when there are multiple changes).
- Concise title (<= 100 chars). Body only if it adds value, wrapped at 100 chars.
- No code blocks, emojis, or external quotes.

FORMAT
<type>(<scope>): <description>
[optional body lines, with breaks at 100 chars]
[optional footers]

TYPES (choose accurately; if more than one type is relevant, list up to 2 separated by dynamic comma, in order of importance)
- feat: new functionality (visible or new behavior)
- fix: bug fix
- refactor: code change that neither fixes a bug nor adds a feature
- perf: performance improvement
- docs: documentation/comments/XMLDoc
- style: formatting, lint, names (no functional impact)
- test: adding/adjusting tests
- chore: maintenance, deps, build, CI/CD, configs
- build: packaging/build changes
- ci: pipeline/automations

SCOPE
- Short noun identifying the primary area impacted.
- Prefer the dominant directory or module of the diff (e.g., core, api, httpclient, middleware, config, infra, auth, swagger, db, ci, build).
- If there are multiple areas and none is dominant, use an aggregating term such as: global, app, multi.

DESCRIPTION (TITLE)
- Active voice and present tense: "adds", "fixes", "refactors"...
- Start with a lowercase letter, no period at the end.
- Wrap filenames, symbols, and numbers in backticks (`).
- Must say what was done + the main focus. <= 100 characters.

BODY (OPTIONAL, BUT RECOMMENDED IF THERE ARE MULTIPLE CHANGES)
- List objective items, grouping by area/theme. Use bullets with "- ".
- Explain what changed, why, and impact (compatibility/behavior).
- Wrap lines every 100 chars.
- If there are various types of changes, reflect ALL in separate bullets.
- Use concrete identifiers: class names, methods, files, and config keys. Avoid generic phrases.

SPECIAL RULES FOR MIXED COMMITS
1) If the diff contains multiple types of changes:
   - Choose up to TWO types (e.g., "feat,refactor" or "refactor,fix").
   - Use an aggregating scope (e.g., "core" or "global") OR the dominant scope.
   - In the body, create bullets by THEME.
2) If there is a potentially breaking change, include a footer:
   - BREAKING CHANGE: <short description>
3) If the diff mentions issues/PRs, include footers:
   - Refs: #123, #456
   - Closes: #789

DECISION ALGORITHM (SUMMARY)
- Detect themes by the diff content.
- Define the TITLE by the most relevant impact to the user/system.
- In the BODY, cover all other changes in short, technical bullets.

OUTPUT
- Produce the final commit message following the rules above.
- A single message, no code blocks.
- Title <= 100 chars. Body with wraps at 100 chars.
- In English.

DIFFERENCE (git diff --staged)
{diff}

ILLUSTRATIVE EXAMPLES (DO NOT COPY DIRECTLY; GUIDE ONLY)
1)
refactor,fix(global): improve json robustness and error handling
- adds converters for `decimal` and `decimal?` with support for string and comma
- configures `AddJsonOptions` and registers converters globally
- adjusts middleware order in `Program.cs` for consistent capture
- enhances `ErrorHandlerMiddleware` (status mapping, traceId, logs)
- hardens `LojaConceitoHttpClient` (content-type, raw payload, error path)

2)
feat(core): support for flexible decimal converters and global json
- registers converters for `decimal`/`decimal?` and `AllowReadingFromString`
- documents and applies 72-column breaks in error messages
- reorganizes middlewares and locates `UseErrorHandlerMiddleware` early in the pipeline
- improves diagnosis and responses for the `XPTO` httpclient
