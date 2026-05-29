---
title: DRY Refactoring — [NOME DO PROJETO]
date: YYYY-MM-DD
tags:
  - instructions
  - refactoring
  - dry
  - claude
aliases:
  - dry
  - duplications
---

# DRY Refactoring

> **Para Claude:** Nota especialista em identificar e eliminar código duplicado. Leia antes de qualquer sessão de refatoração por duplicação.

---

**Princípio DRY:** *Don't Repeat Yourself* — se código aparece em 2+ lugares, ele pertence a um lugar só.

> [!warning] Regra obrigatória
> Nunca executar refatoração sem aprovação. Apresentar análise, aguardar ok, executar em tiers pequenos com build entre cada um.

---

## Estrutura atual — atualizada em YYYY-MM-DD

> **[COMO PREENCHER]**
> Documente aqui a estrutura atual de utils, helpers e componentes compartilhados do projeto.
> Atualize esta seção sempre que uma extração for concluída.
> Use o formato abaixo como guia — adapte para a estrutura de pastas real do projeto.
> Marque arquivos removidos com `~~nome.ts~~` e a data de remoção.

```
[RAIZ DO PROJETO]/
├── [pasta de componentes compartilhados]/
│   ├── [ComponenteA].tsx          ← criado YYYY-MM-DD — [propósito]
│   └── [ComponenteB].tsx          ← criado YYYY-MM-DD — [propósito]
├── [pasta de utils]/
│   ├── [dominio]Utils.ts          ← criado YYYY-MM-DD — [lista de exports]
│   └── [outrodominio]Utils.ts     ← criado YYYY-MM-DD — [lista de exports]
```

**Instruções de preenchimento:**
- Liste cada arquivo de utils/helpers com seus exports principais
- Registre a data de criação para rastreabilidade
- Documente divergências intencionais entre utils de domínios diferentes (ver seção abaixo)

---

## Duplicações resolvidas

> **[COMO PREENCHER]**
> Registre aqui cada extração concluída, com data. Formato:
>
> ### [Data da extração]
>
> | Função/Constante/Componente | Arquivos originais (antes da extração) |
> |-----------------------------|-----------------------------------------|
> | `[nome]` | `[Arquivo1]`, `[Arquivo2]` |
>
> Manter este histórico permite entender POR QUE algo foi para um utils específico
> e evita regredir (mover de volta para os arquivos de origem).

---

## Divergências intencionais — NÃO compartilhadas

> **[COMO PREENCHER]**
> Documente aqui casos onde código PARECE duplicado mas é intencional manter separado.
> Isso evita que o agente "corrija" uma divergência que foi uma decisão deliberada.
>
> | Item | Arquivo divergente | Motivo da divergência |
> |------|--------------------|----------------------|
> | `[nome]` | `[arquivo]` | `[ex: threshold diferente, design distinto, tipo incompatível]` |

> [!note] Por que documentar divergências intencionais?
> Sem este registro, o agente (ou outro dev) pode tentar unificar código que parece duplicado mas tem diferenças sutis e intencionais. O registro protege decisões de design.

---

## Pendências de extração

> **[COMO PREENCHER]**
> Liste aqui duplicações identificadas mas ainda não extraídas, aguardando aprovação.
> Formato: o que está duplicado, onde, e o que impede a extração agora.

> [!note] Pendente
> `[Descreva a duplicação pendente]` — aguarda `[o que precisa acontecer antes de extrair]`.

---

## Prompt de audit periódico — DRY

```
Identifique padrões de código duplicados no projeto.
Procure por funções, componentes ou blocos de código que aparecem
em vários lugares, com pouca ou nenhuma alteração.

Sugira refatorações para criar componentes reutilizáveis, hooks
personalizados ou funções utilitárias — seguindo DRY.

Também revise organização de pastas e arquivos para estrutura profissional.
Não execute nada sem aprovação.
```

---

Ver também: [[dead-code-audit]] | [[coding-conventions]] | [[project-structure]]
