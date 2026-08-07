# Projeto: Angel AI Operating System


**Objetivo:** Projetar uma metodologia de trabalho com IA que seja eficiente, consistente e escalável, utilizando principalmente ChatGPT + Notion + Google Agenda.

---

# Sprint 0 — Problem Framing

---

# Sprint 0.5 — AI Behavior Specification

# O objetivo da Sprint 0.5

Especificar **como a Alice trabalha**.

Não o que ela sabe.

Não quais ferramentas usa.

Mas como ela toma decisões.

Na engenharia de software, isso equivale a escrever uma especificação antes da implementação.

---

# O entregável da Sprint 0.5

Será um único documento.

> **Alice Operational Specification v1.0**
> 

Este documento será tão importante quanto o Project Charter.

---

## Sprint 0.6 — Knowledge Architecture

*angel-ai-operating-system

```jsx
angel-ai-operating-system/

│
├── README.md
│
├── docs/
│
│   ├── architecture/
│   │      aos-overview.md
│   │      system-architecture.md
│   │
│   ├── specifications/
│   │      ABRS-v1.0.md
│   │      AOS-v1.0.md
│   │
│   ├── protocols/
│   │      collaboration.md
│   │      prompting.md
│   │      planning.md
│   │
│   ├── patterns/
│   │      elicitation.md
│   │      teaching.md
│   │      code-review.md
│   │      research.md
│   │
│   ├── templates/
│   │      project-template.md
│   │      poc-template.md
│   │
│   └── decisions/
│          ADR-001.md
│          ADR-002.md
│
├── examples/
│
├── assets/
│
└── CHANGELOG.md
```

Objetivo:

> Transformar a ABRS em um conjunto de artefatos versionados de engenharia que servirão como base permanente do Angel AI Operating System.
> 

As entregas seriam:

1. Estrutura do repositório GitHub.
2. `README.md` do projeto.
3. `CONTRIBUTING.md` (mesmo sendo um projeto inicialmente individual, ele define o processo de evolução).
4. `docs/architecture/angel-ai-operating-system.md`.
5. `docs/specifications/ABRS-v1.0.md`.
6. `docs/specifications/AOS-v1.0.md`.
7. `CHANGELOG.md`.
8. Diretório `docs/adr/` com os primeiros Architecture Decision Records.

---

# Sprint 1 — Descoberta (Discovery)

**Objetivo:** compreender completamente o sistema atual antes de modificá-lo.

Esta sprint terá **3 entregáveis**.

---

# Entregável 1 — Pesquisa

**Responsável:** Alice

**Objetivo**

Responder:

> "Como usuários avançados organizam seu trabalho com o ChatGPT em 2026?"
> 

**Produto esperado**

Um relatório contendo:

- melhores práticas da OpenAI;
- limitações dos Projetos;
- uso de Project Instructions;
- memória;
- bibliotecas de prompts;
- GPTs;
- Skills;
- agentes;
- Spec-Driven Development;
- padrões encontrados.

---

### O que preciso de você

Nada.

Eu mesma vou escrever o prompt da pesquisa.

---

# Entregável 2 — Diagnóstico

Aqui entra a tua ideia, que considero excelente.

Cada Projeto será analisado usando exatamente o mesmo protocolo.

---

### O que preciso de você

Somente isto:

Abrir cada Projeto.

Criar uma nova conversa chamada

```
Architecture Diagnosis
```

Copiar o prompt que construiremos.

Me devolver o relatório.

Nada mais.

---

# Entregável 3 — Inventário

Depois dos diagnósticos eu monto uma matriz.

Algo como:

| Projeto | Tipo | Contexto Persistente? | Recomendação |
| --- | --- | --- | --- |
| LICA | Domínio | ✅ | manter |
| Git | Conhecimento | ⚠️ | avaliar fusão |
| ColmeIA | Produto | ✅ | manter |
| ... | ... | ... | ... |

Essa tabela vai orientar todas as decisões seguintes.

---

# Sprint 2

Só começa depois.

Nela construiremos:

## Angel AI Framework

Aqui nascerão os componentes reutilizáveis.

Por exemplo.

```
Research

Reviewer

PM

Tutor

Writer

Executive Assistant

Decision Support

...
```

Cada capability terá:

- missão;
- checklist;
- protocolo;
- prompt-base;
- formato de saída.

---

# Sprint 3

Somente depois.

Reescreveremos todos os Projetos.

Mas agora com base em evidências.

Não em opiniões.

---

# Sprint 4

Escreveremos

> Angel AI Operating Manual v1.0
>