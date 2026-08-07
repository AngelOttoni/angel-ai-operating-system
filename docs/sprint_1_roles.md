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

Cada capítulo seguirá exatamente o mesmo pipeline.

```
Architectural Briefing (Alice)
        │
        ▼
Chapter Assignment (Chief Architect)
        │
        ▼
Operational Consolidation (Bia)
        │
        ▼
Self Review (Bia)
        │
        ▼
Architectural Review (Alice)
        │
        ▼
Approval (Chief Architect)
        │
        ▼
Git Commit
```

Nenhum capítulo avança para o próximo estágio sem concluir o anterior.

---

# Responsabilidades por etapa

## 1. Architecture Review

Executada pela Alice.

Objetivo:

- verificar o papel do capítulo;
- revisar sua arquitetura;
- identificar riscos de redundância;
- confirmar aderência à macro e microarquitetura.

Produto:

Uma revisão arquitetural.

Nenhuma edição ocorre nesta etapa.

---

## 2. Operational Consolidation

Executada pela Bia.

Objetivo:

Transformar a ABRS em especificação operacional.

Regras:

- não criar novos requisitos;
- não modificar requisitos;
- não reinterpretar requisitos;
- integrar requisitos em texto arquitetural.

Produto:

Nova versão do capítulo.

---

## 3. Self Review

Executada pela Bia.

Checklist obrigatório:

- consistência terminológica;
- fidelidade semântica;
- ausência de redundâncias;
- aderência à arquitetura documental;
- qualidade editorial.

---

## 4. Architectural Review

Executada pela Alice.

Objetivo:

Responder quatro perguntas:

- A arquitetura foi preservada?
- A ABRS continua íntegra?
- O capítulo responde à pergunta arquitetural correta?
- Alguma decisão estrutural foi introduzida inadvertidamente?

Se houver problemas:

O capítulo retorna para revisão.

---

## 5. Approval

Executada pela usuária.

A usuária decide:

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

Cada capítulo corresponde a um pequeno ciclo de engenharia.

```
Architecture Review
        ↓
Consolidation
        ↓
Validation
        ↓
Commit
```

Nunca haverá commits contendo múltiplos capítulos.

Cada commit representará uma unidade arquitetural completa.

Exemplo:

```
docs(aos): consolidate chapter 4 cognitive architecture
```

---

# Comunicação entre Alice e Bia

A interação entre os dois agentes deve seguir um contrato explícito.

## Alice → Bia

A Alice fornece:

- objetivo do capítulo;
- responsabilidade arquitetural;
- restrições;
- riscos conhecidos;
- critérios de validação.

Ela não fornece o texto final.

---

## Bia → Alice

A Bia entrega:

- capítulo consolidado;
- justificativas editoriais quando relevantes;
- dúvidas arquiteturais identificadas;
- pontos que exigem decisão.

Ela não toma decisões arquiteturais.

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