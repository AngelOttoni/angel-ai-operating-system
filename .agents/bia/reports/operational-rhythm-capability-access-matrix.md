# Operational Rhythm — Capability and Access Diagnosis

**Data:** 2026-09-09

**Standing:** diagnóstico experimental; aguardando Architectural Review da Alice e aprovação de Angel.

**Escopo:** capacidades observadas, limites e proposta de experimento; nenhuma transferência de responsabilidade ou implementação autorizada por este documento.

**Referência local:** commit `abccead`; working tree e index inicialmente limpos.

**Contratos correntes:** Angel Daily Brief **v0.3** e Bia Operational Handoff **v0.2**, resolvidos pelo README do experimento **v0.2**. Versões anteriores são históricas.

## 1. Executive Summary

H2 é plausível, mas ainda não demonstrada. A Bia verificou acesso direto, sem Angel transportando dados, a Calendar, Gmail, Notion, Drive, GitHub, GitLab e histórico selecionado de tarefas ChatGPT/Codex. A coleta dos 13 calendários descobertos retornou eventos de calendários secundários. Isso enfraquece a premissa de que a coleta dessas fontes precisa ficar exclusivamente na Alice.

Há, entretanto, um impedimento concreto à afirmação de cobertura suficiente: três operações ClickUp retornaram `INVALID_ARGUMENT`. Não foi possível confirmar descoberta do workspace nem leitura de tarefas pela Bia. No Pilot Day 2, Alice relatou consulta incompleta ao ClickUp, não indisponibilidade total. A mudança de executora pode, portanto, piorar essa superfície. A causa dos erros permanece desconhecida; não se conclui falta de permissão ou defeito do serviço.

Tampouco existe avaliação comparativa da síntese da Bia. Acesso ao histórico não equivale à memória seletiva da Alice, nem uma síntese convincente demonstra qualidade ou confiabilidade repetida. A falha de multicalendário relatada no Day 2 parece compatível com escopo de coleta insuficiente; trocar a executora sem controlar discovery pode reproduzi-la.

O contrato atual exige Alice como sintetizadora e coleta independente por Alice. B e C são alternativas para avaliação, não execuções conformes já autorizadas. A capacidade de raciocinar da Bia não implica autoridade para definir prioridades globais ou substituir a identidade da Alice. Uma eventual exceção experimental precisa ser delimitada e aprovada; este relatório não determina que uma mudança de ABRS seja necessária, nem que seja dispensável.

Recomenda-se um **ensaio pareado em shadow mode, com gate de cobertura e duas execuções prospectivas**, comparando A e B sob o mesmo contrato-base, janela e critérios de qualidade. Um único replay pode refutar uma alegação forte, mas não sustenta confiabilidade. C permanece alternativa condicionada à verificação de um ciclo de delegação à Alice e à definição de quando delegar. Nenhuma arquitetura definitiva é escolhida.

## 2. Evidence and Verification Method

### 2.1 Fontes de autoridade consultadas

- `AGENTS.md`, baseline global efetivamente lido e `.agents/bia/instructions/repository-policy.md`; inventário local mostrou essa política no diretório de instruções deste repositório.
- `experiments/operational_rhythm/README.md`, §§3–9; `angel-daily-brief-v0.3.md`, §§2–12; `bia-operational-handoff-v0.2.md`, Execution Contract e Collection Notes.
- `docs/project_charter_v2.0.md`, especialmente §§5–8 e 12; ADR-001 e ADR-002 em `docs/adr/`; `docs/architecture/aos-document-architecture-v1.0.md`; `docs/sprint_1_roles.md`.
- `docs/specifications/ABRS-v1.0.md`: missão e autoridade, RQ-005–RQ-009, RQ-014–RQ-016; julgamento, RQ-022–RQ-031; memória, RQ-043–RQ-047; evolução, RQ-048–RQ-050. `docs/specifications/AOS-v1.0.md`, capítulos 4–5 e 8–10, como especificação derivada, sem recertificar sua aprovação.
- `.agents/bia/README.md`, contexto e handoff de 08/09; `experiments/operational_rhythm/runs/2026-09-08/daily-brief-execution.md`; registry operacional local, inspecionado sem reproduzir seus valores de configuração.

A hierarquia é Charter → arquitetura → ADRs → ABRS → AOS → protocolos → padrões → templates. ABRS governa a identidade de Alice, não define automaticamente a identidade de Bia. Angel mantém autoridade final; Alice revisa arquitetura; Bia entrega diagnóstico e self-review. Documentos de memória descrevem comportamento desejado, não provam um mecanismo de memória instalado.

### 2.2 Classes de evidência

- **V — VERIFIED:** uma operação delimitada teve resposta observável bem-sucedida nesta sessão. Não certifica cobertura integral, continuidade do acesso ou qualidade do conteúdo.
- **F — falha verificada:** tentativa concreta falhou; a capacidade pretendida continua **UNKNOWN / NOT VERIFIED**.
- **D — documentado/relatado:** instrução, configuração ou relato histórico observável. A capacidade de execução subjacente é **UNKNOWN / NOT VERIFIED** quando não foi testada diretamente.
- **U — UNKNOWN / NOT VERIFIED:** não demonstrado; não significa impossível ou inexistente.

As células usam essas classes por dimensão. Permissão declarada pelo provedor é evidência de metadados, não teste de escrita. Nenhuma escrita externa foi realizada. Autorização para produzir este relatório não autoriza alterar fontes operacionais.

### 2.3 Registro dos probes

Verificações realizadas nesta sessão, até aproximadamente 11:21 no horário operacional do experimento. As janelas consultadas não representam uma execução do Daily Brief.

| ID | Operação e resultado observado | Limite da evidência |
| --- | --- | --- |
| E1 | Leitura local de README, contratos, governança, contexto, status e diffs; Git local acessível. README remoto lido por `github_fetch_file`, também aponta v0.3/v0.2. | Não houve fetch/pull; comparação remota limitada ao README, não certificação de todos os arquivos ou branches. |
| E2 | `google_calendar_list_calendars`: 13 calendários, sem próxima página. `search_events` nos 13, janela de 09/09 00h a 11/09 00h com offset explícito e timezone operacional: 31 registros, nenhuma próxima página. | Inclui primário, compartilhados e blocos; registros não são necessariamente 31 compromissos distintos de Angel. Cobertura fora da lista/conta e semântica de recorrência não certificadas. |
| E3 | `gmail_search_emails` nas três conexões enumeradas: uma mensagem em cada amostra de 08–09/09; `read_email(full)` de uma mensagem profissional retornou corpo MIME. | Busca amostral com paginação pendente, não coleta completa. Corpo nas outras duas conexões, anexos e threads completas não testados. |
| E4 | ClickUp: `get_workspace_hierarchy`, `search` por um item mencionado no Day 2 e `filter_tasks` por vencimentos 09–11/09 retornaram `INVALID_ARGUMENT`. | Parâmetros seguiram os schemas; workspace automático não resolvido com sucesso. Nenhum workspace ID foi inventado. Causa, autenticação e cobertura desconhecidas. |
| E5 | Notion `fetch(self)`, `search` por Minicurso e `fetch` da página encontrada: sucesso, conteúdo e última edição retornados. | `ai_search` exige plano; queries de data sources limitadas; consulta múltipla exige versão ampliada; meeting notes exige plano. Metadado nativo da página: unverified. Ausência de flags de truncamento não certifica todos os blocos. |
| E6 | Drive `search(AOS, best_effort_fetch=true, topn=2)` retornou dois documentos, metadados e texto. | Amostra de documentos derivados, não inventário completo. Documento mais recentemente acessado pode conter contexto histórico desatualizado. |
| E7 | GitHub `list_repositories`, `get_repo` do AOS e leitura do README remoto: sucesso. | Descoberta amostral, acesso não extrapolado a todos os repositórios privados. Metadados declaram permissões de escrita; escrita não testada nem autorizada. |
| E8 | Credencial GitLab existente identificada sem expor valores. GET de identidade e descoberta de projetos falharam com `URLError` no ambiente restrito; repetidos com aprovação de execução externa: HTTP 200, JSON válido e um projeto na página. | Descoberta com `membership=true`, uma amostra; MRs, pipelines, discussões e todos os projetos necessários não revalidados hoje. Restrição de rede exigiu intervenção humana. |
| E9 | `list_threads` e `read_thread` recuperaram tarefas ChatGPT “Angel Operational Rhythm — Daily Brief” e “Ampliar Daily Brief”, além da tarefa Codex “Revisar contratos do Rhythm”. | Histórico paginado e delimitado. Respostas de Alice são evidência de relato/artefato, não logs autenticados de suas consultas. Não se enviou mensagem nem se invocou Alice. |
| E10 | Registry local contém oito fontes habilitadas; teste de existência confirmou as oito raízes. Arquivos de contexto e handoff foram lidos no AOS. | Existência não comprova leitura de todos os conteúdos, Git válido, upstream atual ou permissões de escrita. Clones técnicos não foram varridos; registry não é autorização universal. |
| E11 | Arquivo deste relatório criado e relido; verificações de diff, escopo e higiene na entrega. | Prova de persistência deste relatório. Não houve criação de run, stage, commit, push ou teste de escrita em outros destinos. |

O inventário de ferramentas foi usado somente para escolher probes. Keep não apresentou ferramenta dedicada no inventário examinado. Isso não prova que toda alternativa de acesso inexista. Não foram testadas sessões de navegador ou exploradas credenciais alternativas. A skill Google Drive orientou sua descoberta. Orientação genérica de produto não foi usada como evidência de acesso real.

## 3. Source Capability/Access Matrix

**Direto** significa que o agente pode obter dados usando ferramenta/API/arquivo sem Angel copiá-los; há mediação técnica do conector. **Mediado** significa transporte por pessoa, handoff ou artefato derivado. Escritas externas são U e fora do escopo desta análise, mesmo quando ferramentas de escrita existem.

### 3.1 Bia / Codex local

| Superfície | Read | Write | Discovery | Freshness/current state | Direto ou mediado | Intervenção humana | Confiabilidade/limites | Relevância |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Google Calendar | V: eventos nos 13 calendários | U; E2 declara owner em 8 e reader em 5 | V: lista sem paginação restante | V: consulta da janela; latência do provedor U | Direto | Nenhuma nos probes | Não deduplicado; bloco de tempo não é tarefa; calendários fora da conexão U | Obrigatória; Today e Look Ahead |
| Gmail | V: busca nas 3 conexões e corpo em 1 | U; não testado | V: conexões enumeradas e mensagens encontradas | V: registros datados; estado de toda inbox U | Direto | Nenhuma nos probes | Paginação não esgotada, snippets insuficientes para ação; notificação não é estado atual da tarefa | Obrigatória; comunicação acionável |
| ClickUp | U/F: três erros | U | U/F: workspace não confirmado | U | Rota direta exposta, acesso não confirmado | Recuperação pode exigir Angel; necessidade exata U | Não confundir erro com lista vazia; possível regressão de cobertura | Obrigatória; estado LICA |
| Notion | V: página e metadados | U | V: busca direcionada | V: última edição retornada; atualidade factual U | Direto | Nenhuma no probe | Restrições de plano verificadas; página não verificada pelo Notion | Condicional; proposta acionada no Day 2 |
| Google Drive | V: 2 textos e metadados | U | V: busca amostral | V: timestamps; fatos históricos não reconfirmados | Direto | Nenhuma no probe | Cópias derivadas podem divergir do Git corrente | Condicional; documentação/contexto |
| Google Keep | U | U | U | U | Somente Capture é rota documental estabelecida | Sim se houver conteúdo relevante inacessível | Não consultado; não alegar integração | Fora das fontes acessíveis do contrato; Capture |
| GitHub | V: repo e README | U; permissões declaradas não bastam | V: amostra | V: README remoto; restante U | Direto | Nenhuma nos probes | Cobertura de privados/branches não certificada | Condicional; contratos e projetos |
| GitLab | V: identidade e projeto amostral | Não autorizado com a credencial; teste U | V: página de projetos membros | V para metadados amostrais; MRs/pipelines U hoje | Direto por API | Sim: aprovação de saída da restrição de rede | Sucesso histórico de MRs não prova estado atual; acesso por projeto varia | Condicional a gatilho técnico |
| Git local | V: AOS, status, diffs e documentos | U para Git mutation; proibida nesta tarefa | V: AOS e registry; inventário de clones U | V: checkout; igualdade remota integral U | Direto | Nenhuma para leitura AOS | Raiz existente não implica repo válido; sem fetch/pull | Condicional; estado técnico e contract discovery |
| Filesystem autorizado | V: documentos AOS; existência de 8 raízes | V: relatório; outros alvos U | V limitada a escopo inspecionado | V: bytes lidos; fatos descritos podem ser antigos | Direto | Nenhuma para leitura; restrições por destino | Acesso amplo não equivale a autorização ampla | Contexto técnico, registro de runs |
| Conversas/histórico | V: tarefas ChatGPT e Codex selecionadas | U: mensagens não enviadas | V: listagem limitada e títulos | V: turnos retornados; histórico é passado | Direto via app | Nenhuma para recuperação testada | Paginação, truncamento, seleção por título; não expõe todo contexto interno da Alice | Continuidade e evidências do piloto |
| Memória/contexto persistente | V: arquivos históricos; U: memória interna compartilhada | V: relatório apenas; memória automática U | V em arquivos/turnos selecionados | U para validade presente das lembranças | Direto para arquivos; mecanismo interno U | Angel confirma evolução quando material | Retenção, seleção e recuperação não certificadas | Objetivos e decisões contextuais |
| Contratos/AOS | V: fontes locais e ponteiro remoto | Não autorizado nesta tarefa | V: README resolve versões | V local e ponteiro remoto concordante | Direto | Revisão/decisão continuam humanas | Leitura não prova aderência futura; cópia no Drive não prevalece | Governa todo o workflow |
| Azure DevOps/Teams | U: acesso ao vivo | U | U | U | Contexto/handoff histórico | Necessária se lacuna material, rota direta U | EnergIA oficial não se confunde com GitLab interno | Condicional; acessos e trabalho oficial |
| Element e demandas não registradas | U: Element direto; V: declaração histórica de Angel | U em Element | U fora da conversa | U atual; Capture precisa ser renovado | Mediado por Angel; Gmail pode conter notificações | Sim para fatos fora das fontes | Notificação pode permanecer após resolução; ideia não é compromisso | Day 2 demonstrou correção relevante por Capture |

### 3.2 Alice / ChatGPT

Não houve execução de ferramentas dentro do runtime de Alice nesta análise. E9 verifica que seus relatos e outputs existem; não verifica as integrações subjacentes. Portanto, abaixo **D não é acesso confirmado**. Ferramentas da Bia não foram atribuídas a Alice por analogia.

| Superfície | Read | Write | Discovery | Freshness/current state | Direto ou mediado | Intervenção humana | Confiabilidade/limites | Relevância |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Calendar | D: leitura relatada Day 2; acesso atual U | U | D: descoberta de secundários relatada depois da omissão | D: bloco de estudos encontrado depois; U teste direto | Direto relatado | Angel apontou omissão | Cobertura inicial insuficiente relatada; não prova incapacidade de discovery | Obrigatória |
| Gmail | D: consultas relatadas; U teste direto | U | D: profissional/pessoal; demais U | D: mensagens citadas; cobertura U | Direto relatado | Correção de estado via Capture | Email sobre tarefa pode estar superado | Obrigatória |
| ClickUp | D: workspace e 1 tarefa relatados; U teste direto | U | D: workspace identificado | D: Alice classificou cobertura incompleta | Direto relatado | Investigação/correções podem exigir Angel | Não é baseline de cobertura completa | Obrigatória |
| Notion | D: conteúdo do minicurso no Brief; U teste direto | U | D: busca dirigida; filtro temporal limitado relatado | D: conteúdo usado; validade atual U | Direto relatado | Angel forneceu demanda | Restrição da conexão da Bia não prova mesma restrição em Alice | Condicional |
| Drive | U | U | U | U | Rota atual U; documentos compartilhados são possíveis, não comprovam conector | U | Anexo não prova acesso ao Drive | Condicional |
| Keep | U | U | U | U | Capture conforme contrato | Sim quando relevante | Nenhuma consulta direta demonstrada | Capture |
| GitHub | D: versão v0.3 e repo citados; U teste direto | U | D: URL fornecida por Angel | D: contrato corrente referido; mecanismo U | Consulta remota relatada | Angel forneceu URL na invocação observada | Bootstrap atualizado é relato de Angel, não configuração auditada | Contratos/projetos |
| GitLab | U direto; D: handoff histórico lido | U | U direto | D: falta de estado técnico atual declarada | Mediado por handoff no fluxo documentado | Sim para handoff quando necessário | Handoff anterior não certifica MRs atuais | Condicional |
| Git local | U direto; D: observações no handoff | U | U | U atual | Mediado por Bia | Sim no fluxo observado | Sem execução local de Alice demonstrada | Condicional |
| Filesystem autorizado | U direto; D: anexo recebido | U | U | U atual | Anexo/handoff | Sim no transporte observado | Receber arquivo não dá acesso ao filesystem de origem | Contexto e runs |
| Conversas/histórico | V: interação e Brief no chat observado; acesso cruzado U | V: respostas no próprio chat; outros chats U | U para busca transversal | V: mensagens datadas; fatos atuais U | Direto no chat observado | Angel invoca e fornece Capture | Contexto total e seleção não auditados | Continuidade |
| Memória persistente | D: papel especificado; mecanismo U | U | U | U | U; não presumir equivalência com arquivos | Angel pode corrigir contexto | Memória normativa não é prova de implementação | Qualidade cognitiva |
| Contratos/AOS | D: v0.3 aplicado/declarado; leitura integral U | U | D: ponteiro fornecido e versão reconhecida | U para bootstrap automático integral | Repo/chat relatados | URL e configuração mencionadas por Angel | Carregamento e aderência repetida U | Governança |
| Azure DevOps/Teams | U direto; D: contexto histórico | U | U | U | Handoff/Capture | Sim se informação material não acessível | Contexto de acessos antigos não prova acesso atual | Condicional |
| Element/não registrado | U direto; V: input de Angel no Day 2 | U em Element | U fora do Capture | V: declaração datada; não estado atual geral | Mediado por Angel | Sim | Preservar declaração como fonte humana | Capture |

### 3.3 Angel / intervenção humana

Autoridade final está documentada e o input do Day 2 é observável. Isso não comprova credenciais, papel administrativo ou acesso total de Angel em cada sistema.

| Superfície | Read | Write | Discovery | Freshness/current state | Direto ou mediado | Intervenção humana requerida no workflow | Limites | Relevância |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Calendar | D: Angel relata agendas vinculadas; teste U | U | D: identificou omissão | U para checagem completa | Interface relatada | Corrigir cobertura quando necessário | Não substituir discovery por inspeção diária manual | Obrigatória |
| Gmail | U | U | U | U | Acesso pessoal não testado | Só lacunas/decisões materiais | Conta conectada ao agente não prova sessão humana | Obrigatória |
| ClickUp | U | U | U | U | U | Pode esclarecer workspace/itens se necessário | Não transformar Angel em exportadora rotineira | Obrigatória |
| Notion | D: conhece proposta; teste U | U | D: identifica demanda | V: necessidade declarada Day 2 | Capture observado | Explicitar objetivo relevante | Demanda não prova estado integral da página | Condicional |
| Drive | U | U | U | U | U | Transporte pode ocorrer, não é requisito intrínseco | Permissões humanas não auditadas | Condicional |
| Keep | U | U | U | U | Capture previsto | Sim se informação relevante estiver ali | Nenhuma nota Keep foi acessada | Capture |
| GitHub | D: forneceu URL; teste U | U | D: identifica repo | U | Link observado | Aprovação de mudanças | Autoridade arquitetural não é permissão técnica | Contratos |
| GitLab | D: revisões anteriores no handoff; teste U | U atual | U | U | Histórico mediado | Aprovações/decisões e eventual liberação runtime | Nenhuma sessão humana auditada | Técnico |
| Git local | D: histórico de trabalho; teste U | U | U | U | U | Autorizar operações fora do escopo | Não presumir sincronização | Técnico |
| Filesystem | U técnico | U técnico | U | U | U | Autorizar destinos quando necessário | Autoridade sobre entrega não prova acesso ao dispositivo | Persistência |
| Conversas | V: mensagens, invocação e Capture | V: mensagens no histórico | V: contexto fornecido; inventário total U | V: declarações datadas | Direto | Invocação, Capture, feedback | Recordação e seleção humanas também são falíveis | Obrigatória para Capture |
| Memória/contexto | V: objetivos e correções explicitados; retenção total U | V: atualização declarativa; sistemas persistentes U | U para recordação completa | V: correção datada, não onisciência | Direto por diálogo | Confirmar mudanças materiais | Silêncio não significa ausência | Objetivos/valores |
| Contratos/AOS | V: instruções e decisão no histórico; leitura total U | D: autoridade final; operação técnica U | D: aponta repositório | U integral | Direto no pedido; execução por agentes | Architectural approval | Não precisa indicar versão em toda execução | Governança |
| Azure DevOps/Teams | D: acesso histórico em contexto; atual U | U | U | U | Contexto histórico | Sim se agentes não alcançarem fato material | Não confundir restauração histórica com estado presente | Condicional |
| Element/não registrado | V: declaração de resolução e nova demanda | D: resolução relatada, operação U | V: identifica input | V: declaração Day 2 | Direto por Capture | Sim | Agente não deve reinterpretar relato como leitura da aplicação | Capture |

## 4. Functional Capability Matrix

| Função | Bia observada | Alice observada/documentada | Papel de Angel / limite |
| --- | --- | --- | --- |
| Contract discovery | V: README → v0.3/v0.2; E1 | D: versão reconhecida com URL; bootstrap repetido U | Aprovar contrato; não servir de resolvedora de versão diária |
| Source discovery | V parcial: calendários, contas Gmail, documentos, repos e tarefas; ClickUp F | D: descoberta de secundários e workspace; completude U | Delimitar relevância quando fontes/contas forem ambíguas |
| Source collection | V amostral em várias fontes; insuficiente no ClickUp | D: coleta relatada, com falhas Day 1/2 | Não suprir silenciosamente toda fonte defeituosa |
| Multi-calendar discovery/collection | V: 13/13 na janela; deduplicação/seleção operacional não testadas | D: secundário encontrado após correção; primeira cobertura inadequada | Identifica omissão; valida relevância sem varredura humana diária |
| Normalization | V limitada: versões, estados de probe e cobertura tabulados aqui; workflow integral U | D: artefato integra horários e domínios | Validar significado; não inventar prazo a partir de texto vago |
| Provenance preservation | V neste relatório; D no handoff histórico | V: distingue input humano no output; rastreio por item completo U | Capture com fonte e natureza: ideia, demanda ou decisão |
| Reconciliation | V diagnóstica: relato ≠ acesso, contexto ≠ atualidade; Daily Brief B U | V: output reconhece divergência ClickUp/Gmail; correção factual integral U | Resolve conflitos de intenção; fontes mantêm autoridade |
| Stale/conflicting information | V: cópia Drive antiga, relatos e lacunas separados | V: output não presume handoff antigo atual | Confirma resolução/novas decisões; nenhum agente sabe tudo |
| Prioritization | U para Daily Brief avaliado; não executada | V: Focus e ordenação produzidos; qualidade independente U | Decisão final; prioridade não é só deadline |
| Bounded cognitive synthesis | U empiricamente e não atribuída a Bia no contrato corrente | V: síntese produzida; confiabilidade comparativa U | Aprovar limites do ensaio; julgar utilidade sem transferir agência |
| Angel Capture Check | Interface de diálogo presente; execução Daily Brief B U | V: pergunta, resposta explícita e incorporação Day 2 | Necessário; silêncio não completa check |
| Final Daily Brief | U: nenhum Brief B produzido/testado | V: output Day 2; aderência integral não certificada | Aceitar/rejeitar; falhas materiais devem permanecer visíveis |
| Persistence/versioning | V: leitura Git, histórico e relatório; run/commit não testados nesta sessão | V: chat persistido; escrita local de run U | Commit/push requerem autorização separada |
| Simple invocation | U: execução B completa sob frase curta; discovery local V | V: frase curta iniciou protocolo e Capture; cobertura falhou | Invocação inicia processo, não elimina Capture |
| Delegated cognition | U: ferramentas de envio existem, mas round-trip à Alice não testado | U: endpoint cognitivo com contexto garantido | Não houve envio; futura autorização e ensaio específicos |

Para testar bounded synthesis, é necessário delimitar uma interpretação experimental: relacionar compromissos, dependências, consequências e objetivos explícitos; recomendar Focus e ordenação como hipóteses fundamentadas; preservar incerteza e autoridade das fontes; não criar compromissos, executar ações ou redefinir objetivos. Essa delimitação é **proposta para revisão**, não nova regra adotada. O nome “Alice's Read” e a atribuição de autoria também precisam de decisão experimental explícita; não se deve representar texto da Bia como fala da Alice.

## 5. Human-Middleware Analysis

Há três custos distintos: **input humano legítimo** (Capture, objetivos, decisões), **governança** (aprovação/revisão) e **transporte operacional** (copiar handoff, indicar versões, relançar agentes, transmitir respostas). H2 pretende reduzir o terceiro, não eliminar os dois primeiros.

O histórico mostra Angel fornecendo URL do repositório, anexo de handoff, invocação, correção sobre agendas e nova demanda no Capture. Nem toda mensagem é desperdício: a nova demanda e a resolução informada no Day 2 eram inputs legítimos. A necessidade de handoff atual não atendida é evidência de fricção, mas não mede quantos minutos foram gastos nem prova que a mediação causou todas as omissões.

A Bia já recupera histórico e documentos sem cópia manual, o que reduz uma parte potencial do custo. A mesma recuperação pode diminuir atrito em A ou C; não é evidência exclusiva a favor de B. O envio de prompts à Alice está exposto no app, mas não foi exercido. Não está verificado que preserve instruções, memória, identidade, coleta independente, resposta estruturada, recuperação de falhas ou ausência de duplicação.

Neste diagnóstico, GitLab precisou de uma aprovação de rede. Em B, falha ClickUp pode exigir seleção de workspace, correção ou exportação humana; se isso se repetir, o custo removido do handoff reaparece na coleta. Qualquer comparação deve contar essas intervenções. Não há medição confiável do custo total atual, logo não se declara ganho percentual.

## 6. Architecture Comparison (A × B × C)

Em A, a seta simplificada Bia → Angel → Alice não representa todo o contrato: Alice também coleta Calendar, Gmail e ClickUp independentemente, faz Capture e usa Bia apenas sob gatilho. Sem gatilho técnico, não há handoff obrigatório nem custo que B possa alegar ter removido.

| Critério | A — split atual | B — Bia end-to-end | C — Bia orquestra, Alice sob condição |
| --- | --- | --- | --- |
| Source coverage | Combinação documentada ampla; Day 2 mostrou ClickUp incompleto, omissão de calendário e lacuna técnica | Calendar/Gmail/Notion/Drive/Git verificados parcialmente; ClickUp não confirmado; cobertura técnica completa U | União potencial; não comprovada. Delegação cognitiva não corrige fonte ausente automaticamente |
| Human coordination cost | Transporte quando há handoff; invocação e Capture sempre legítimos | Pode reduzir transporte; troubleshooting, autorizações e contexto podem compensar ganho | Baixo apenas com round-trip funcional; se Angel retransmite, benefício central desaparece |
| Contract fidelity | Estruturalmente conforme v0.3; execução já falhou | Não conforme atribuição atual; ensaio requer autorização delimitada; quatro fases devem continuar separadas | Não definido: contrato atribui síntese a Alice em toda execução, não só casos excepcionais |
| Freshness | Duas coletas podem ocorrer em tempos distintos; handoff envelhece | Menor intervalo potencial, mas mesma necessidade de timestamps/reconsulta | Espera pela delegação pode envelhecer snapshot; coletor deve distinguir resposta tardia |
| Failure modes | Coleta omitida, handoff ausente, perda no transporte, pressupostos entre agentes | Falha única afeta todo workflow; pontos cegos correlacionados; coleta longa consome contexto da síntese | Critério de delegação errado, timeout, contexto insuficiente, duplicação e retorno incompatível |
| Observability | Evidência distribuída entre chat e arquivo | Registro único é viável; não surge automaticamente nem prova raciocínio correto | Precisa registrar delegação, evidência enviada, retorno e decisão de reconciliação |
| Reproducibility | Requer contratos, handoff, fontes, Capture e contexto de ambos | Menos fronteiras, mas modelo e fontes variam; Git sozinho não congela dados remotos | Mais estados/versões; papel exato de Alice deve ser identificável |
| Governance | Preserva responsabilidades aprovadas e autoridade humana | Pode ser função delimitada sem equivaler a Alice; classificação arquitetural cabe a Alice/Angel | Nova responsabilidade de roteamento e critérios ainda não definidos; não assumir síntese opcional |
| Implementation complexity | Menor mudança; discovery e disciplina ainda precisam melhorar | Sem plataforma nova necessariamente, mas escopo, acesso e avaliação precisam ser resolvidos | Maior: transporte, contrato de chamada, contexto, timeout/retry e autoria; sem necessidade demonstrada de nova plataforma |
| Angel as middleware | Dependência observada quando há transferência; não universal | Menor potencial, ainda não medido | Removida somente se invocação/retorno direto funcionarem; U |

## 7. Critical Gaps

1. **ClickUp obrigatório não demonstrado na Bia.** Identificar workspace correto a partir de evidência existente e verificar leitura de uma tarefa material conhecida, depois cobertura delimitada. Não instalar integração, trocar configuração ou solicitar credenciais como parte deste diagnóstico. Se não for possível sem mudança, manter falha e submeter decisão.
2. **Qualidade cognitiva e repetibilidade não medidas.** Um relatório bem estruturado não é prova de boa priorização diária. Precisam ser avaliadas relações úteis, omissões, inferências indevidas e correções de Angel.
3. **Cobertura de contexto não equivalente.** Arquivos e turnos recuperáveis não demonstram acesso à memória de Alice. B pode perder contexto relevante ou importar conclusões antigas indevidamente.
4. **Escopo de contas/calendários ainda não formalizado no contrato.** O v0.3 exige Calendar, mas não especifica inventário de calendários relevantes. O mesmo vale para contas Gmail. Enumerar tudo indiscriminadamente pode adicionar ruído; consultar apenas primary pode omitir compromissos.
5. **GitLab técnico e fontes oficiais não integralmente revalidados.** E8 prova acesso básico, não cobertura de MRs/pipelines por projeto. Azure DevOps, Teams e Element continuam lacunas diretas; contexto local não as fecha.
6. **Critério de delegação C ausente.** “Quando o contrato exige julgamento” inclui Focus e Alice's Read em todo Brief corrente. Definir exceções cognitivas seria decisão nova; não basta acionar um modelo e chamá-lo de Alice.
7. **Persistência ainda parcial.** Day 2 está no histórico ChatGPT consultado; o diretório de runs inspecionado contém o registro de Day 1. Preservar chats não equivale a registrar cada run com fontes, versão e falhas.

## 8. Assumptions / Unknowns

Não foram verificados: escrita em fontes externas; acesso completo de Alice a cada conector; permissões humanas por sistema; mecanismos internos de memória; transporte de ida e volta para cognição delegada; execução integral de B por frase simples; acesso ao vivo a Keep/Element/Teams/Azure; cobertura de todos os projetos GitLab; leitura de todos os clones; tolerância a timeout, paginação longa e mudanças concorrentes; custo humano em minutos; qualidade comparativa de priorização.

Não se assume que “sem resultado” significa “sem atividade”, que timestamp de edição comprova validade factual, que permissão owner/admin autoriza esta tarefa a escrever, que endpoint publicado funciona, que ausência de ferramenta comprova impossibilidade, ou que dois agentes reduzem erros por independência: os erros podem ser compartilhados. Nenhuma garantia de determinismo foi demonstrada para A, B ou C.

Os relatos de Alice sobre bootstrap e capacidades são contexto, não configuração auditada. A especificação de memória no AOS não estabelece acesso de runtime. O sucesso de uma conexão da Bia não certifica outra conta, outro projeto ou a sessão de Alice. Não foi executado um Capture atual: este pedido é diagnóstico, não Daily Brief; o Capture histórico não pode ser reciclado como resposta de uma nova execução.

## 9. Findings relevant to H2

**Principal evidência favorável:** a Bia reúne, nesta mesma sessão, contract discovery local, coleta multicalendário, Gmail, documentos, leitura de histórico ChatGPT e acesso GitLab básico. Não precisou que Angel copiasse dados entre Alice e Bia para essas leituras. Isso demonstra que a separação de acesso não é absoluta e torna um ensaio de B tecnicamente plausível.

**Principal evidência contrária:** a fonte obrigatória ClickUp permanece sem leitura confirmada na Bia após três falhas, enquanto o Day 2 relata ao menos leitura parcial pela Alice. B não pode ser declarada substituta com cobertura preservada no estado observado. Esse é um falsificador concreto da versão forte “B resolve praticamente todas as falhas”. Não é prova de impossibilidade futura.

**Contraponto causal:** descoberta multicalendário pode corrigir a omissão tanto em A quanto em B. Melhorar o procedimento de coleta e trocar a sintetizadora ao mesmo tempo confundiria o experimento. A falha Day 1 também motivou evolução do contrato; não atribuir ganhos do v0.3 à executora nova.

**Contraponto cognitivo:** a integração entre demanda nova, reuniões e atividades futuras no Day 2 demonstra output cognitivo de Alice, mas sem avaliação independente de sua qualidade. Não existe output equivalente de B avaliado. Economizar coordenação com perda dessa integração refutaria H2 nos termos propostos, ainda que B coletasse mais dados.

**Conclusão diagnóstica:** há evidência para testar H2, não para aceitá-la. Preservar A por tradição e adotar B por conveniência seriam conclusões igualmente excessivas. A superioridade operacional de B permanece UNKNOWN / NOT VERIFIED.

## 10. Recommendation for the NEXT EXPERIMENT only

### 10.1 Menor ensaio informativo

Propor, após Architectural Review e aprovação de Angel, **um ensaio pareado A/B com duas janelas prospectivas**, sem plataforma nova, sem escrita nas fontes e sem promoção normativa. A continua referência operacional; B produz candidato shadow claramente atribuído à Bia. Não executar C agora: sua mecânica não está verificada e acrescentaria variável antes de medir B.

**Gate prévio de cobertura:** repetir discovery e uma leitura de ClickUp usando workspace/item identificados por evidência, com paginação apropriada. Uma tarefa conhecida não comprova toda cobertura; delimitar o conjunto relevante. Revalidar GitLab no escopo técnico acionado, incluindo eventual aprovação de rede no custo. Se uma fonte obrigatória/material continuar inacessível, registrar falha de prontidão de B. Um replay com dados fornecidos pode testar cognição, mas não conta como êxito end-to-end nem redução de middleware. Não “resolver” isso com Angel exportando diariamente.

**Protocolo do ensaio, para aprovação:**

1. Fixar contrato-base v0.3, referência Git, janela operacional, contas e calendários relevantes, gatilhos técnicos e critérios de avaliação. Registrar separadamente a exceção experimental de executor/autoria para B; não editar silenciosamente “Alice” no contrato. Alice/Angel decidem a suficiência dessa autorização e qualquer implicação superior.
2. Usar uma janela com demanda técnica e contexto cruzado, e outra sem gatilho técnico, se disponível. Se não houver diversidade, reconhecer que a repetição não cobre esses dois casos. Não fabricar compromissos reais para obter um teste.
3. Iniciar cada candidato com pedido curto equivalente. A faz sua coleta independente conforme contrato; B faz coleta própria. Nenhum recebe o Brief/priorização do outro antes de concluir. Ambas usam o mesmo escopo e cutoff; mudanças entre coletas são registradas, não tratadas como erro cognitivo.
4. Fazer um Capture explícito por janela e fornecer a mesma resposta aos candidatos. Contar o transporte adicional necessário ao ensaio separadamente; manter contabilizado no fluxo que dependeria dele em uso normal. Capture precisa terminar antes de reconciliação/síntese, podendo disparar coleta adicional.
5. Registrar fontes, identificadores não sensíveis, horários, limites/paginação, status por fonte, motivos de não consulta, conflitos, conclusão das fases e duração. Repetir seletivamente leituras materiais que envelheçam antes da entrega. Não guardar dados pessoais desnecessários nem configuração da máquina nos runs.
6. Congelar as duas saídas antes da comparação. Angel avalia, preferencialmente sem rótulo de executor, utilidade, omissões, prioridades, próximos passos e inferências. Alice faz revisão adversarial de contrato/proveniência; sua avaliação não deve ser o único juiz de qualidade por ser autora de A.
7. Usar os snapshots coletados para um replay de síntese apenas se houver diferença material: dar o mesmo pacote de evidências a ambos ajuda a distinguir falha de coleta de falha cognitiva. Esse replay é diagnóstico auxiliar e não uma execução A conforme coleta independente.

### 10.2 Métricas e critérios propostos

| Dimensão | Medida | Critério inicial proposto para aceitar apenas viabilidade do próximo passo |
| --- | --- | --- |
| Cobertura | Fontes exigidas/acionadas e itens materiais recuperados; gaps por conta/calendário | Nenhuma perda material exclusiva de B; fonte com erro nunca registrada como consultada |
| Fidelidade | Ordem das quatro fases, Capture, proveniência, status e limites | Zero violação crítica: síntese prematura, silêncio como Capture, inventar compromisso, esconder falha ou tratar passado como estado atual |
| Freshness | Momento da observação, última atualização e mudanças entre coletas | Nenhuma conclusão material baseada em estado superado conhecido sem ressalva; avaliar por fonte, sem TTL universal inventado |
| Qualidade cognitiva | Omissões relevantes, prioridades inadequadas, relações úteis e correções humanas | B sem perda material de qualidade na avaliação de Angel; discordância com Alice sozinha não é falha |
| Custo humano | Minutos ativos, transferências, reexplicações, relançamentos e aprovações | B reduz coordenação operacional em ambas as janelas, sem deslocá-la para exportação/troubleshooting; Capture e avaliação medidos separadamente |
| Execução | Duração total, tentativas, falhas e retomadas | Duas execuções completas rastreáveis ou falhas claramente identificadas; uma falha não deve ser ocultada por nova tentativa |

Os critérios são proposta do ensaio, não requisitos novos do AOS. Devem ser aprovados antes de observar os resultados. Se B perder um compromisso material, depender de transporte humano equivalente ao removido, degradar julgamento ou contornar o contrato, H2 não recebe suporte para expansão. Se A e B compartilharem a mesma lacuna material, o teste é inconclusivo quanto à cobertura suficiente, mesmo que B seja mais rápida.

Duas execuções não provam confiabilidade estatística nem decidem arquitetura definitiva. São o menor ensaio proposto que acrescenta uma repetição prospectiva, permite rejeitar erros grosseiros e mede coordenação real. Um resultado favorável justifica somente continuar o piloto; resultado misto orienta diagnóstico de coleta/contexto/cognição, podendo tornar C objeto de um teste futuro específico.

### Self-review e encerramento

- Versões resolvidas pelo README local e corroboradas pelo README remoto; contratos históricos preservados.
- Matrizes separam atores, leitura, escrita, descoberta, atualidade, mediação, intervenção, limites e nível de evidência.
- Nenhuma ferramenta ou credencial foi tratada como acesso confirmado por sua mera existência; falhas ClickUp e restrição GitLab permanecem visíveis.
- Relatos de Alice não foram promovidos a testes de seu runtime. Nenhuma declaração de superioridade cognitiva da Bia foi feita.
- Recommendation limitada ao próximo experimento, com falsificadores e separação entre mudança de coleta e mudança de síntese.
- Única alteração pretendida: este relatório. Contratos, documentação canônica, permissões, configuração e fontes operacionais não foram modificados; nenhum commit/push realizado.
- Relatório sem credenciais, identificadores de conexão, caminhos absolutos ou endereços de máquina. Referências de artefatos são relativas.

**Pendente:** Architectural Review da Alice e aprovação de Angel. Nenhuma execução shadow, delegação, implementação ou alteração de arquitetura foi iniciada por esta análise.
