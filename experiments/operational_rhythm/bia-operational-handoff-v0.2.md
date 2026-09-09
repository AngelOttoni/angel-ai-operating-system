# Bia Operational Handoff

**Version:** 0.2
**Status:** Experimental
**Generated at:** YYYY-MM-DD HH:MM TZ
**Execution trigger:** <pedido, evidência ou necessidade operacional concreta>
**Mode:** incremental | baseline
**Comparison reference:** <handoff anterior adequado ou motivo para baseline>
**Period / observation window:** <período comparado ou janela de observação do baseline>
**Collection scope:** <fontes/projetos pertinentes ao gatilho>

## Execution Contract

Este handoff é executado on-demand / condition-triggered, sem obrigação de execução diária ou periódica. Gatilhos válidos incluem, sem limitar-se a:

- pedido explícito de Angel ou Alice;
- evidência ou suspeita razoável de alteração em GitLab ou no estado local;
- necessidade de revisão ou decisão técnica;
- necessidade de estabelecer estado técnico atual para o Angel Daily Brief.

Registre o motivo da execução e delimite a coleta proporcionalmente ao gatilho, dentro do escopo autorizado da Bia. Não é obrigatório varrer todas as fontes em toda execução. Para metadados GitLab necessários, use a API GitLab conforme as instruções aplicáveis; para código local, consulte o repositório autorizado.

Use modo incremental quando houver handoff anterior adequado e comparação confiável para o escopo observado. Identifique essa referência. Sem referência adequada ou comparação confiável, produza um baseline e registre o motivo. No baseline, descreva o estado observado sem presumir mudanças ou ausência de mudanças desde uma coleta anterior. Limites de comparação por fonte devem permanecer explícitos.

O handoff é uma observação técnica derivada, não uma determinação das prioridades globais de Angel. Registre referências e momentos de observação suficientes para Alice avaliar cobertura e atualidade. Um handoff anterior é contexto histórico, nunca evidência presumidamente atual. A ausência de coleta não demonstra ausência de mudanças.

Este contrato experimental substitui v0.1 para novas execuções e preserva o contrato anterior e registros do piloto como histórico. Não promove o experimento para arquitetura normativa.

## 1. Requires Angel's Attention

Itens que provavelmente exigem ação, decisão, revisão ou resposta da Angel.

### <Project> — <Item>

- Type:
- Status:
- Owner:
- What changed / baseline state:
- Why it matters:
- Expected Angel action:
- Source:
- Reference:
- Last update:

## 2. Waiting / Blocked

Itens relevantes que estão aguardando terceiros, dependências ou condições externas.

### <Project> — <Item>
- Waiting for:
- Since:
- Current state:
- Angel action now: none | <action>
- Source:
- Reference:

## 3. Relevant Changes

Mudanças desde o handoff de referência que alteram o estado conhecido de projetos,
mesmo que não exijam ação imediata. Em modo baseline, registre o estado relevante
observado e identifique que não há comparação confiável.

### <Project>
- Change / baseline state:
- Operational impact:
- Source:
- Reference:

## 4. Upcoming Technical Deadlines

Somente deadlines tecnicamente relevantes identificados nas fontes observadas.

- Date:
- Project:
- Item:
- Current risk:
- Source:

## 5. Open Technical Decisions

Decisões ainda não encerradas que podem demandar atenção da Angel.

### <Project> — <Decision>
- Current question:
- Known options:
- Current state:
- Decision needed by:
- Source:

## 6. No Relevant Changes

Somente projetos/fontes efetivamente consultados com comparação confiável e sem
alteração operacional relevante. Fontes não consultadas não pertencem a esta seção.
Em baseline, registre o estado observado nas categorias pertinentes e a ausência
de comparação nas notas de coleta.

- <project/source>

## 7. Collection Notes

Registre cobertura e limitações que afetem a interpretação do handoff. Distinga
fonte consultada sem mudança relevante de fonte não consultada, indisponível ou
com consulta incompleta. Não sugira cobertura além da coleta realizada.

- Sources consulted / observation time:
- Sources not consulted / reason (including outside trigger scope):
- Consultation incomplete:
- Comparison limitations:
- Source unavailable:
- Collection limitation:
- Possible stale information:
