# CLAUDE.md — Vibcode Documentation Kit

Este repositório é um **kit de templates** para documentação técnica e boas práticas de agente AI em projetos de software. Não é um projeto de produto — é um ambiente de configuração reutilizável.

## O que é este repositório

Conjunto de arquivos prontos para copiar em um novo projeto, adaptando os campos marcados com `[COMO PREENCHER]`. O objetivo é que todo projeto novo parta com:
- Contrato de comportamento do agente já estabelecido
- Estrutura de documentação Obsidian pré-definida
- Ferramentas de audit (DRY, dead code, performance, separação de concerns) prontas para uso

## Estrutura dos arquivos

```
ai-best-practices.md          → contrato de comportamento do agente (obrigatório ler por sessão)
obsidian-documentation.md     → como documentar no vault Obsidian do projeto
obsidian-documentation.skill  → skill instalável para Claude Code (invoca as convenções automaticamente)
ferramentas/
├── coding-conventions.md     → padrões de nomenclatura, estrutura, stack
├── dry-refactoring.md        → protocolo DRY: extração e rastreamento de utils compartilhados
├── separation-of-concerns.md → padrão container/presentational e audit arquitetural
├── dead-code-audit.md        → protocolo de identificação e remoção de código morto
└── performance-audit.md      → checklist de otimizações e registro de resultados
```

## Como usar este kit em um projeto novo

1. Copie todos os arquivos para a pasta de instruções do projeto (ex: `vault/{instructions}/`)
2. Em cada arquivo, busque por `[COMO PREENCHER]` e siga as instruções de preenchimento
3. Substitua `[NOME DO PROJETO]` pelo nome real em todos os frontmatters
4. Atualize a estrutura de pastas em `obsidian-documentation.md` (seção 3)
5. Defina a stack técnica real em `coding-conventions.md`
6. Adicione o `ai-best-practices.md` ao contexto de cada sessão do agente
7. Instale a skill: `claude plugin install obsidian-documentation.skill` — habilita invocação automática das convenções Obsidian pelo agente

## Comportamento do agente neste repositório

Quando o agente está operando **dentro deste kit** (não em um projeto derivado):

- **Objetivo**: manter os templates genéricos, sem informações específicas de projeto
- **Não preencher** os campos `[COMO PREENCHER]` — eles são instruções para o usuário do kit
- **Não adicionar** exemplos com dados reais de projeto (nomes de arquivos, componentes, paths específicos)
- **Sim sugerir** melhorias nos templates quando identificar lacunas de cobertura

## Convenções deste repositório

- Campos a preencher: `[TEXTO EM MAIÚSCULAS ENTRE COLCHETES]`
- Blocos de instrução: `> **[COMO PREENCHER]** ...` — devem ser removidos após uso
- Placeholders de data: `YYYY-MM-DD` — substituir pela data real ao iniciar uso no projeto
- Wikilinks `[[nome]]` — apontam para notas que o usuário deve criar no vault do projeto

## Fluxo de sessão neste repositório

Ao receber uma tarefa neste repositório:

1. Verificar se a mudança mantém os arquivos genéricos (sem info específica de projeto)
2. Verificar se os blocos `[COMO PREENCHER]` estão presentes e corretos onde necessário
3. Não executar código — este repositório contém apenas documentação
4. Para adicionar nova ferramenta/template: seguir o padrão dos arquivos existentes em `ferramentas/`
