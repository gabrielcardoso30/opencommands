# 🚀 Prompts para Devs & PMs

> Uma coleção curada de prompts para auxiliar Desenvolvedores, Engenheiros de Software e Gerentes de Produto a extraírem o máximo de IAs generativas (Gemini, ChatGPT, Claude).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

## 📋 Sobre o Projeto

Este repositório serve como uma **biblioteca centralizada de comandos (prompts)** testados e refinados para otimizar o fluxo de trabalho em desenvolvimento de software e gestão de projetos.

O objetivo é reduzir o tempo gasto na criação de contextos complexos e fornecer templates que geram respostas de alta qualidade.

---

## 🌐 Interface Web (Liquid Glass)

Recentemente, o projeto ganhou uma **interface web modernizada** utilizando a estética *Liquid Glass*. Além de navegar pelos prompts, a interface agora conta com monitoramento via **Google Analytics** para entender as demandas da comunidade e melhorar continuamente os conteúdos disponibilizados.

🚀 **Acesse aqui:** [opencommands.com](https://opencommands.com/)

---

## 🌎 Suporte Global (Internationalization)

O OpenCommands agora é **global**! A plataforma suporta automaticamente 5 idiomas:
- 🇧🇷 Português (Brasil)
- 🇺🇸 English
- 🇪🇸 Español
- 🇷🇺 Русский
- 🇨🇳 中文

A interface detecta seu idioma automaticamente, mas você também pode alternar manualmente usando o seletor no topo da página.

---

## ❤️ Por que criamos isso?

Sabe aquela sensação de olhar para uma tela em branco às 18h de uma sexta-feira, precisando escrever uma documentação técnica perfeita? Ou o peso de herdar um código legado sem nenhum comentário, que parece uma bomba-relógio prestes a explodir na sua mão?

Nós conhecemos essa dor.

Criamos este projeto porque cansamos de ver desenvolvedores brilhantes perdendo horas em tarefas repetitivas, lutando contra o bloqueio criativo ou se sentindo sobrecarregados pela complexidade crescente do software moderno.

Acreditamos que a programação é uma **arte**, e que você deveria gastar sua energia resolvendo problemas complexos de arquitetura, e não formatando strings ou escrevendo *boilerplate*.

Estes prompts não são apenas "comandos para o ChatGPT". São **ferramentas de sobrevivência**. São atalhos mentais que transformam ansiedade em produtividade. Cada prompt aqui foi refinado depois de muitas frustrações reais, bugs em produção e reuniões intermináveis.

Queremos que você termine seu trabalho mais cedo. Queremos que você sinta orgulho do código que entrega. Queremos que você tenha um "Senior Partner" disponível 24/7 para te ajudar a pensar.

É por isso que estamos aqui.

---

## 📂 Catálogo de Prompts (PT-BR)

Aqui você encontra os prompts originais em Português. Para outras línguas, utilize a interface web.

### 🛠️ Desenvolvimento & Engenharia de Software

| Arquivo | Atuação (Persona) | O que faz? |
| :--- | :--- | :--- |
| [**Code Review & Segurança**](./prompts/pt-BR/revisao-codigo-seguranca.md) | Senior Code Reviewer | Analisa código em busca de erros lógicos, falhas de segurança (OWASP), *bad smells* e violações de SOLID. |
| [**Performance .NET**](./prompts/pt-BR/revisao-performance-dotnet.md) | Engenheiro de Performance | Focado em otimização de C#: LINQ, `AsNoTracking`, alocação de memória e *async/await*. |
| [**Documentação Técnica**](./prompts/pt-BR/gerador-documentacao-csharp.md) | Tech Lead & Mentor | Gera documentação didática e XML Docs (`///`) profissionais para métodos e classes. |
| [**Execução de Demandas**](./prompts/pt-BR/fluxo-implementacao-feature.md) | Arquiteto de Soluções | Cria um plano detalhado de implementação para novas features, com checklist e *rollback plan*. |
| [**Padrão de Commits**](./prompts/pt-BR/padrao-commits-conventional.md) | DevOps Engineer | Gera mensagens de commit padronizadas baseadas no diff, seguindo Conventional Commits. |

### 📊 Gestão de Produto & Empreendedorismo

| Arquivo | Atuação (Persona) | O que faz? |
| :--- | :--- | :--- |
| [**Análise Técnica de PDF**](./prompts/pt-BR/analise_pdf_projeto_sistema_super_detalhado.md) | Arquiteto de Soluções | Realiza análise profunda de PDFs de sistemas, extraindo visão, requisitos, riscos e backlog com estimativas. |
| [**Especificação de Tarefas**](./prompts/pt-BR/gerador-especificacao-tarefas.md) | PM & Analista de Requisitos | Transforma solicitações vagas em *User Stories* completas com Critérios de Aceite e Gherkin. |
| [**Co-Fundador Técnico**](./prompts/pt-BR/cofundador-tecnico-virtual.md) | CTO / Co-founder | Guia você desde a ideia ("Tenho um app em mente") até o MVP, passando por descoberta e planejamento. |

---

## 🛠 Como Utilizar

1. **Escolha o Prompt**: Navegue pela tabela acima e clique no link do arquivo desejado.
2. **Copie o Conteúdo**: Copie todo o texto do arquivo `.md`.
3. **Preencha os Placeholders**: Procure por campos como `{{COLE_SEU_CODIGO_AQUI}}` ou `[Descreva sua ideia]` e substitua pelo seu contexto.
4. **Execute na IA**: Cole o prompt final na sua IA de preferência (Gemini, ChatGPT, Claude).

---

## 🤝 Como Contribuir

Contribuições são o que fazem a comunidade open source um lugar incrível! Sinta-se à vontade para enviar seus melhores prompts.

1. Faça um Fork do projeto.
2. Crie uma Branch para sua Feature (`git checkout -b feature/NovoPromptIncrivel`).
3. Adicione seu prompt seguindo o padrão dos existentes.
4. Faça o Commit (`git commit -m 'feat: adicionar prompt de arquitetura'`).
5. Faça o Push (`git push origin feature/NovoPromptIncrivel`).
6. Abra um Pull Request.

---

## 📝 Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

---

<p align="center">
  Feito com 💜 por <a href="https://github.com/gabrielcardoso30">Gabriel Cardoso</a>
</p>