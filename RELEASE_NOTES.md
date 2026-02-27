# Notas de Lançamento (Release Notes)

Este arquivo documenta todas as mudanças notáveis feitas neste projeto.

## Padrão de Versionamento
Este projeto utiliza o padrão **Semantic Versioning (SemVer)** (Versionamento Semântico).

### Por que SemVer?
Escolhemos o **SemVer** (`MAJOR.MINOR.PATCH`) por ser o padrão mais eficiente e amplamente adotado na indústria de software por diversos motivos:
1.  **Clareza de Impacto:** Permite entender instantaneamente se uma atualização traz quebras de compatibilidade (MAJOR), novas funcionalidades (MINOR) ou apenas correções (PATCH).
2.  **Previsibilidade:** Ajuda tanto quem desenvolve quanto quem consome a ferramenta a planejar atualizações com segurança.
3.  **Automação:** Facilita a integração com ferramentas de automação de build e deploy.

---

## [1.5.0] - 2026-02-27

### Adicionado
- **Novo Prompt:** "Inserir Logs Estruturados" adicionado à categoria de Desenvolvimento & Engenharia de Software, na subcategoria Observabilidade & Debugging.
- **Tradução de Conteúdo:** O novo prompt foi traduzido para os 4 idiomas adicionais suportados (EN, ES, RU, ZH).

---

## [1.4.0] - 2026-02-24

### Adicionado
- **Suporte Multilíngue (i18n):** Implementação de suporte para 5 idiomas (PT-BR, EN, ES, RU, ZH).
- **Tradução de Conteúdo:** Todos os 8 prompts originais foram traduzidos para as 4 novas línguas suportadas.
- **Seletor de Idiomas:** Novo componente de UI premium para alternância manual de idiomas.
- **Detecção Automática:** Sistema inteligente que detecta o idioma do navegador e a localização do usuário.
- **Estrutura de Pastas:** Reorganização dos prompts em diretórios específicos por idioma (`/prompts/en/`, `/prompts/es/`, etc.).

## [1.3.0] - 2026-02-24

### Alterado
- **Domínio Principal:** Migração do domínio de `prompts.datalin.com.br` para `opencommands.com`.
- **SEO & Metadados:** Atualização de todas as URLs canônicas, metadados Open Graph e Twitter para o novo domínio.
- **Documentação:** Atualização de links e referências no `README.md`.

---

## [1.2.0] - 2026-02-21

### Adicionado
- **Google Analytics:** Integração com gtag.js para monitoramento de tráfego e análise de uso.
- **Domínio Customizado:** Padronização de todas as URLs internas e metadados para `opencommands.com`.

---

## [1.1.0] - 2026-02-21

### Adicionado
- **Novo Prompt:** "Análise Técnica Completa de Projetos de Software via PDF" adicionado à categoria de Gestão & Planejamento.

---

## [1.0.0] - 2026-02-21

Esta é a versão inicial do projeto, consolidando todas as funcionalidades desenvolvidas até o momento.

### Adicionado
- **Interface Liquid Glass:** Design moderno com efeitos de vidro, desfoque e animações de blobs de fundo.
- **Biblioteca de Prompts:** Coleção inicial de prompts curados para Desenvolvedores e Product Managers.
- **Sistema de Categorias:** Navegação intuitiva por abas (Desktop) e dropdown (Mobile).
- **Visualização de Prompts:** Modal interativo com suporte a Markdown (via Marked.js) e botão de "Copiar Prompt".
- **Sistema de Feedback:** Integração com GitHub Issues para reporte de bugs e sugestões diretamente da interface.
- **SEO & Social:** Meta tags otimizadas para motores de busca e compartilhamento em redes sociais (Open Graph/Twitter).
- **Responsividade:** Layout adaptável para dispositivos móveis, tablets e desktops.
- **Release Notes:** Implementação do histórico de versões e exibição no rodapé.
