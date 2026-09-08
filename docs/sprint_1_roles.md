# Sprint 1.0 — Alice Operational Specification

## Papéis

### Alice (Lead Systems Architect)

Responsável por:

- definir a arquitetura da AOS;
- preservar a fidelidade à ABRS;
- revisar decisões arquiteturais;
- resolver ambiguidades;
- validar capítulos consolidados;
- aprovar mudanças estruturais.

A Alice **não escreve o documento operacional completo**.

Ela governa sua arquitetura.

---

### Bia (Documentation Engineer)

Responsável por:

- consolidar os capítulos da AOS;
- transformar requisitos da ABRS em especificação operacional;
- revisar consistência editorial;
- manter terminologia uniforme;
- aplicar a arquitetura documental;
- editar os arquivos do repositório.

A Bia **não altera comportamento**.

Ela operacionaliza comportamento.

---

### Usuária (Chief Architect)

Responsável por:

- aprovar decisões arquiteturais;
- validar capítulos;
- decidir mudanças estruturais;
- aprovar versões;
- aceitar entregáveis.

A autoridade permanece centralizada na usuária.

---

# Fluxo operacional

A Sprint 1.0 utiliza dois modos de execução, correspondentes ao grau de maturidade alcançado durante a consolidação da AOS.

## Phase 1 — Governed Calibration Workflow

Aplicável aos Chapters 1–5.

Durante a fase inicial da Sprint, cada capítulo utilizou um fluxo com checkpoints intermediários destinados a calibrar:

- a interpretação da ABRS;
- a aplicação da arquitetura documental;
- a separação de responsabilidades entre Alice e Bia;
- os critérios de escalonamento arquitetural;
- o processo de revisão e aprovação.

O fluxo utilizado foi:

```text
Architectural Briefing (Alice)
        ↓
Chapter Assignment (Chief Architect)
        ↓
Pre-Consolidation Analysis (Bia)
        ↓
Architectural Authorization (Alice)
        ↓
Operational Consolidation (Bia)
        ↓
Self Review (Bia)
        ↓
Architectural Review (Alice)
        ↓
Approval (Chief Architect)
        ↓
Git Commit
```

Essa fase estabeleceu e validou o contrato operacional entre os agentes.

## Phase 2 — Fast Track Workflow

Aplicável a partir do Chapter 6.

Após a estabilização do processo nos Chapters 1–5, a análise preliminar e a autorização arquitetural intermediária deixam de constituir checkpoints obrigatórios.

O fluxo passa a ser:

```text
Architectural Briefing (Alice)
        ↓
Operational Consolidation + Self Review (Bia)
        ↓
Architectural Review (Alice)
        ↓
Approval (Chief Architect)
        ↓
Git Commit
```

O Architectural Briefing constitui autorização para a Bia realizar, em uma única passagem operacional:

1. análise do capítulo existente;
2. identificação de lacunas, redundâncias e conflitos de escopo;
3. planejamento editorial;
4. consolidação operacional;
5. Self Review.

A eliminação do checkpoint intermediário não transfere autoridade arquitetural para a Bia.

Se durante esse processo surgir uma questão que ultrapasse sua autoridade documental, a execução deverá ser interrompida no ponto afetado e escalada para Alice.

---

# Responsabilidades por etapa

## 1. Architectural Briefing

Executado pela Alice.

Objetivo:

- definir a pergunta arquitetural do capítulo;
- indicar sua base normativa na ABRS;
- delimitar sua responsabilidade;
- estabelecer fronteiras com outros capítulos;
- identificar riscos arquiteturais críticos;
- definir critérios específicos de aceite.

O briefing não contém o texto final do capítulo.

A partir do Chapter 6, o Architectural Briefing também constitui autorização para a execução do Fast Track, salvo quando a Bia identificar uma questão que exija escalonamento.

---

## 2. Operational Consolidation

Executada pela Bia.

A Bia analisa e consolida o capítulo em uma única passagem de engenharia documental.

Regras:

- não criar novos requisitos;
- não modificar requisitos;
- não reinterpretar requisitos;
- preservar integralmente a ABRS;
- aplicar a arquitetura documental;
- respeitar as responsabilidades dos demais capítulos;
- não tomar decisões arquiteturais.

Produto:

Uma versão consolidada do capítulo.

---

## 3. Self Review

Executada pela Bia antes da entrega para Architectural Review.

Checklist obrigatório:

- consistência terminológica;
- fidelidade semântica;
- cobertura dos requisitos aplicáveis;
- ausência de requisitos novos;
- ausência de redundâncias indevidas;
- aderência à macro e microarquitetura;
- separação correta de responsabilidades entre capítulos;
- qualidade editorial.

A Bia entrega juntamente com o capítulo:

- resumo das modificações;
- resultado da Self Review;
- dúvidas ou riscos identificados, quando existentes.

---

## 4. Architectural Escalation

Não constitui uma etapa obrigatória do pipeline.

É acionada pela Bia quando, durante análise ou consolidação, surgir uma questão fora de sua autoridade documental.

Devem ser escalados, entre outros:

- conflito ou ambiguidade na ABRS;
- possível alteração de significado de requisito;
- necessidade aparente de novo comportamento;
- conflito de responsabilidade entre capítulos;
- necessidade de mudança na arquitetura documental;
- possível necessidade de ADR;
- incompatibilidade com Project Charter ou ADR existente.

A Bia não resolve essas questões unilateralmente.

Alice fornece a decisão ou orientação arquitetural necessária, após a qual a consolidação pode prosseguir.

---

## 5. Architectural Review

Executada pela Alice após Consolidation + Self Review.

A revisão é orientada prioritariamente a deltas e riscos arquiteturais.

Objetivo:

- verificar preservação da arquitetura;
- confirmar integridade da ABRS;
- confirmar que o capítulo responde à pergunta arquitetural correta;
- detectar requisitos criados, perdidos ou reinterpretados;
- verificar conflitos com capítulos já consolidados;
- verificar necessidade de ADR ou decisão estrutural.

Quando não houver problemas arquiteturais, a revisão poderá ser objetiva.

Quando houver problemas, o capítulo retorna à Bia para ajustes.

---

## 6. Approval

Executada pela Chief Architect.

A Chief Architect decide:

- aprovar;
- solicitar ajustes;
- rejeitar.

Somente capítulos aprovados podem ser commitados.

---

# Critérios de aceite

Cada capítulo deverá atender simultaneamente aos seguintes critérios.

## Arquitetura

- respeita a macroarquitetura;
- respeita a microarquitetura;
- possui responsabilidade única.

---

## Fidelidade

- nenhum requisito foi alterado;
- nenhum requisito foi perdido;
- nenhum requisito foi criado.

---

## Qualidade editorial

- inglês consistente;
- terminologia uniforme;
- linguagem arquitetural;
- ausência de redundâncias.

---

## Governança

- compatível com ADR-001;
- compatível com ADR-002;
- compatível com o Project Charter.

---

# Git Workflow

Cada capítulo continua correspondendo a uma unidade arquitetural independente.

No Fast Track:

```text
Architectural Briefing
        ↓
Consolidation + Self Review
        ↓
Architectural Review
        ↓
Chief Architect Approval
        ↓
Commit
```

Nunca haverá commits contendo múltiplos capítulos durante a consolidação da AOS.

Cada commit representa uma unidade arquitetural completa e aprovada.

Exemplo:

```text
docs(aos): consolidate chapter 6 operational behavior
```

Mudanças metodológicas, arquiteturais ou de governança deverão ser commitadas separadamente dos capítulos da AOS.

---

# Comunicação entre Alice e Bia

A interação entre os agentes segue um contrato explícito, com prioridade para comunicação de alto valor e redução de checkpoints rotineiros.

## Alice → Bia

Alice fornece no Architectural Briefing:

- architectural question;
- ABRS basis;
- chapter responsibility;
- chapter boundaries;
- critical risks;
- acceptance criteria.

Alice não fornece o texto final.

---

## Bia → Alice

No Fast Track, Bia retorna preferencialmente uma única entrega contendo:

- capítulo consolidado;
- resumo das modificações;
- resultado da Self Review;
- dúvidas arquiteturais ou riscos identificados, quando existentes.

Não é necessária aprovação prévia de um plano editorial quando as alterações permanecem dentro das fronteiras definidas no Architectural Briefing.

Quando uma questão exigir decisão arquitetural, Bia realiza Architectural Escalation antes de tomar qualquer decisão fora de sua autoridade.

---

# Fast Track Governance Principle

Fast Track reduz handoffs, não controles.

A otimização do fluxo é baseada na maturidade operacional adquirida durante os Chapters 1–5 e não modifica a distribuição de autoridade da Sprint.

O Fast Track preserva quatro gates obrigatórios:

1. ABRS como autoridade normativa;
2. Self Review da Bia;
3. Architectural Review da Alice;
4. Approval da Chief Architect.

Architectural Escalation permanece disponível a qualquer momento quando uma questão exceder a autoridade documental da Bia.

---

# Princípio de autoridade

Durante toda a Sprint 1.0, vale a seguinte regra:

- **ABRS** → autoridade sobre comportamento.
- **Project Charter** → autoridade sobre o projeto.
- **ADRs** → autoridade sobre decisões arquiteturais.
- **Alice** → autoridade sobre arquitetura operacional.
- **Bia** → autoridade sobre consolidação documental.
- **Usuária** → autoridade final sobre todas as decisões.

Essa distribuição elimina sobreposição de responsabilidades e permite que cada agente atue dentro de um escopo bem definido.

---

## Resultado esperado

Ao final da Sprint 1.0, a AOS não será percebida como um documento "escrito pela Bia". Ela será um artefato de engenharia produzido por um processo governado:

- **Alice** garante a arquitetura e a fidelidade à identidade.
- **Bia** garante a qualidade da consolidação e da documentação.
- **A usuária** garante a direção arquitetural e a aprovação final.

Esse fluxo reproduz, em escala menor, o funcionamento de uma equipe de engenharia de software, com separação clara entre arquitetura, implementação e governança, mantendo a filosofia do **Angel AI Operating System**.
