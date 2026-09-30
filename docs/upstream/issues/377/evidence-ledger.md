# Evidence ledger — Issue 377

## Pergunta que a evidência precisa responder

Que comportamento conversacional está desalinhado da identidade esperada do Zé Delivery, para quais pessoas e em quais jornadas, e quais limites de Marketing, Ética e Jurídico são mandatórios para qualquer mudança?

---

```yaml
id: E-001
claim: "A Issue 377 foi aberta para melhorar o tom de voz e reduzir o uso de 'mano'."
kind: fact
source:
  type: github
  uri: "https://github.com/ab-inbev-ze-company/ze-consumer-whatsapp-orchestrator-app/issues/377"
  retrieved_at: "2026-09-30"
scope:
  population: "Não especificada na Issue"
  time_window: "Não especificada na Issue"
freshness: unknown
relationship: supports
criticality: supporting
status: evidenced
limitations:
  - "Não identifica mensagens, jornadas, segmentos, frequência ou impacto."
  - "Não demonstra que o uso de 'mano' é a causa principal de estranheza."
```

```yaml
id: E-002
claim: "O assistente deve se identificar como 'assistente de compras com IA do Zé Delivery', e não como o próprio Zé."
kind: fact
source:
  type: interview
  uri: "Stakeholder input registrado na conversa de intake"
  retrieved_at: "2026-09-30"
scope:
  population: "Todas as interações em que o assistente se apresenta ou é percebido como identidade do produto"
  time_window: "A confirmar no material do time de Ética"
freshness: current
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "Evidencia que o requisito foi comunicado pelo stakeholder; não substitui a recomendação/documento de Ética que o fundamenta."
  - "Ainda não define redação, canais, exceções ou critérios de conformidade."
```

```yaml
id: E-003
claim: "A construção e validação do branding de tom de voz dependem de informações a levantar com Marketing."
kind: fact
source:
  type: github
  uri: "https://github.com/ab-inbev-ze-company/ze-consumer-whatsapp-orchestrator-app/issues/377#issuecomment-5027733565"
  retrieved_at: "2026-09-30"
scope:
  population: "Iniciativa da Issue 377"
  time_window: "Comentário publicado em 2026-07-20"
freshness: unknown
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "Não contém o guia, os critérios de aprovação nem uma decisão de Marketing."
```

```yaml
id: U-001
claim: "Quais mensagens, jornadas, segmentos e circunstâncias produzem estranheza ou desalinhamento de identidade?"
kind: unknown
source:
  type: observation
  uri: "A levantar por meio de exemplos de conversa, feedback e/ou dados de produto"
  retrieved_at: "2026-09-30"
scope:
  population: "Usuários do assistente de compras com IA do Zé Delivery"
  time_window: "A definir"
freshness: unknown
relationship: does-not-resolve
criticality: critical
status: unverified
limitations:
  - "Sem esta evidência não é possível medir severidade, priorizar fluxos ou formular um problema concreto."
```

```yaml
id: U-002
claim: "Quais regras de Marketing, Ética e Jurídico são mandatórias, quais admitem contexto e como serão avaliadas?"
kind: unknown
source:
  type: repository
  uri: "docs/upstream/issues/377/ (materiais de contexto ainda indisponíveis no worktree)"
  retrieved_at: "2026-09-30"
scope:
  population: "Conteúdo e comportamento conversacional cobertos pela iniciativa"
  time_window: "A confirmar"
freshness: unknown
relationship: does-not-resolve
criticality: critical
status: unverified
limitations:
  - "Sem os documentos-fonte, não é seguro inferir regras, exceções ou aprovações."
```

## O que estas evidências não permitem concluir

- Que existe um único problema de tom de voz, ou que ele é causado pelo vocabulário informal.
- Que uma alteração editorial isolada resolverá a estranheza percebida.
- Que a diretriz de identidade já está operacionalizada ou aprovada nos materiais de Marketing, Jurídico e Ética.

## Próxima evidência discriminante

Vincular e ler os guias de Marketing e as recomendações de Ética, depois contrastá-los com exemplos reais de conversas. Isso diferencia regras mandatórias de preferências e mostra se o problema é de identidade, conteúdo, fluxo, contexto ou combinação desses fatores.

## Atualização após revisão das fontes — 2026-09-30

`U-002` está resolvido como disponibilidade de fonte. Os materiais foram localizados no worktree da Issue 377 do repositório WhatsApp, em `docs/upstream/issue-377-melhoria-tom-de-voz/`. Eles permanecem não versionados naquele worktree e não foram copiados para este repositório por conterem conteúdo marcado como sensível.

```yaml
id: E-004
claim: "O guia de Marketing define o produto como assistente de compras no WhatsApp e prioriza segurança, fatos confirmados e clareza acima de tom e humor."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/docs/upstream/issue-377-melhoria-tom-de-voz/guias-mkt/guia-mestre-content-whatsapp-ze-delivery.md"
  retrieved_at: "2026-09-30"
scope:
  population: "Respostas do assistente de compras do Zé Delivery no WhatsApp"
  time_window: "Guia copiado como vigente em 2026-09-29"
freshness: current
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "O guia é normativo; não demonstra por si só a incidência dos comportamentos atuais."
  - "O próprio arquivo está marcado como draft-for-brand-core-review; ele não é aprovação final de Brand Core."
```

```yaml
id: E-005
claim: "A recomendação de Ética exige que o caráter automatizado do chatbot permaneça claro durante toda a interação e veda antropomorfização que induza a pessoa a acreditar que fala com um humano."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/docs/upstream/issue-377-melhoria-tom-de-voz/guias-juridico/recomendacoes-etica-digital.md"
  retrieved_at: "2026-09-30"
scope:
  population: "Pessoas que interagem com o chatbot no WhatsApp antes de disponibilização pública"
  time_window: "Não especificada no documento"
freshness: unknown
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "O documento inclui recomendações de fluxo, privacidade e segurança além do escopo de tom."
  - "O documento recomenda transparência contínua e não antropomorfização, mas seu exemplo de abertura usa 'Sou o Zé, assistente virtual'; isso conflita com o requisito de não se identificar como o próprio Zé (E-002) e exige reconciliação formal."
```

```yaml
id: E-006
claim: "Nos traces analisados, respostas genéricas, oferta alcoólica antes de intenção, bordões/emoji recorrentes, personalização inesperada e perda de contexto coincidem com correções, cobranças ou retomadas feitas pelas pessoas usuárias."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/docs/discovery/melhoria-tom-de-voz/relatorio-traces-tom-de-voz.md"
  retrieved_at: "2026-09-30"
scope:
  population: "109 pares resposta anterior do assistente → turno seguinte da pessoa, em 45 conversas do export analisado"
  time_window: "Primeiro teste de produção; janela de coleta não documentada"
freshness: unknown
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "O export não contém transcript completo, rótulos de satisfação, abandono, tenant ou janela de coleta."
  - "Pares observados não provam causalidade nem prevalência na população total."
```

```yaml
id: U-003
claim: "Quais padrões observados continuam ativos, em quais jornadas ocorrem e qual é sua frequência/impacto relativo?"
kind: unknown
source:
  type: observation
  uri: "A validar com reconciliação entre export histórico, recorte recente de LLM Observability e definição da coorte de decisão"
  retrieved_at: "2026-09-30"
scope:
  population: "Usuários atuais do assistente de compras com IA do Zé Delivery"
  time_window: "A definir"
freshness: unknown
relationship: does-not-resolve
criticality: critical
status: unverified
limitations:
  - "O export histórico e a consulta recente cobrem populações e janelas diferentes (E-009, E-010); não permitem estimar prevalência atual ou impacto causal."
  - "A data informada no intake (23/07) conflita com a faixa técnica de 05–16/06/2026 derivada dos trace IDs do export histórico (E-010)."
```

```yaml
id: E-007
claim: "A identidade e o tom atuais são definidos em múltiplas superfícies de execução: abertura do coordinator, prompt de segurança/persona, small_talk e prompt do agente ReAct."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/src/{coordinator,orchestration}/"
  retrieved_at: "2026-09-30"
scope:
  population: "Código no commit 85c6f036e8829060a2ff1eadd66be633942562c1"
  time_window: "Estado do worktree no momento da leitura"
freshness: unknown
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "Não confirma que este commit corresponde ao deploy atual."
  - "Não mede a incidência de cada caminho em conversas reais."
```

```yaml
id: E-008
claim: "A suíte de avaliações cobre segurança, classificação, tools, correctness, helpfulness e hallucination; não foi encontrado teste executável explicitamente destinado a tom de voz, transparência de IA ou não antropomorfização."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/tests/node_harness/"
  retrieved_at: "2026-09-30"
scope:
  population: "Arquivos de teste e avaliação presentes no worktree"
  time_window: "Estado do worktree no momento da leitura"
freshness: unknown
relationship: supports
criticality: supporting
status: evidenced
limitations:
  - "Uma busca de código não prova ausência de verificação manual ou externa ao repositório."
```

```yaml
id: E-009
claim: "No recorte de 2026-07-23 a 2026-09-30, o LLM Observability retornou quatro workflows raiz whatsapp_message, de duas sessões, todos com tag env:prod; os quatro outputs cobrem small_talk (2), address (1) e commerce (1)."
kind: fact
source:
  type: observability
  uri: "Datadog LLM Observability: search_llmobs_spans(ml_app=ze-consumer-whatsapp-orchestrator, span_kind=workflow, span_name=whatsapp_message, root_spans_only=true); search de output_guardrails"
  retrieved_at: "2026-09-30"
scope:
  population: "Workflows raiz indexados e acessíveis com os filtros especificados"
  time_window: "2026-07-23 a 2026-09-30"
freshness: current
relationship: constrains
criticality: critical
status: evidenced
limitations:
  - "A amostra contém quatro turnos de duas sessões; é evidência de continuidade de superfícies/jornadas, não de frequência na população."
  - "As consultas iniciais filtradas como span_kind=agent e root_spans_only retornaram vazio porque a raiz instrumentada é workflow, não agent."
```

```yaml
id: E-010
claim: "O dataset versionado prod_search_inputs.jsonl contém 129 registros e 129 trace IDs distintos de source datadog_llmobs, associados a 56 conversation_ids distintos; a faixa técnica derivada dos trace IDs é 2026-06-05 a 2026-06-16 (UTC)."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/tests/search_evals/datasets/prod_search_inputs.jsonl"
  retrieved_at: "2026-09-30"
scope:
  population: "Registros preservados no dataset de inputs de busca de produção"
  time_window: "2026-06-05 a 2026-06-16, inferido do componente temporal dos trace IDs"
freshness: stale
relationship: contradicts
criticality: critical
status: evidenced
limitations:
  - "O arquivo não inclui timestamp de turno, ambiente, tenant, critério de exportação ou transcript completo; a janela é uma inferência técnica dos IDs."
  - "Os 129 traces não equivalem a 129 conversas; a contagem observada de conversation_id é 56."
  - "A faixa técnica antecede o disparo confirmado em 24/07/2026 (E-011); este export não deve ser tratado como a coorte do teste da Issue 377."
```

```yaml
id: E-011
claim: "O disparo do teste em escopo ocorreu em 24/07/2026; uma busca ampla no LLM Observability entre 24 e 31/07 não retornou spans para ml_app=ze-consumer-whatsapp-orchestrator."
kind: fact
source:
  type: interview+observability
  uri: "Confirmação do stakeholder no intake; Datadog LLM Observability search_llmobs_spans sem filtro de tipo/raiz"
  retrieved_at: "2026-09-30"
scope:
  population: "Coorte do teste disparado em 24/07/2026 e spans atualmente acessíveis no Datadog"
  time_window: "2026-07-24 a 2026-07-31"
freshness: current
relationship: constrains
criticality: critical
status: evidenced
limitations:
  - "Resultado vazio não demonstra ausência de tráfego no teste; pode refletir retenção, tenant, identificador de aplicação, permissões ou caminho de instrumentação distintos."
  - "A data do disparo é fato informado pelo stakeholder; a fonte operacional do export original ainda não foi localizada."
```

```yaml
id: D-001
claim: "O stakeholder aprovou usar o dataset de junho como baseline histórico complementar na investigação da Issue 377."
kind: decision
source:
  type: interview
  uri: "Decisão registrada na conversa de intake"
  retrieved_at: "2026-09-30"
scope:
  population: "Análise de Problem da Issue 377"
  time_window: "Baseline de 2026-06-05 a 2026-06-16; sem inferência de prevalência atual"
freshness: current
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "A decisão autoriza o uso complementar do baseline, mas não converte a coorte de junho na coorte do teste de 24/07."
  - "Prevalência e impacto atual permanecem em U-003 até nova evidência ou aceitação explícita do risco."
```

```yaml
id: E-012
claim: "Nas 109 respostas anteriores presentes em 45 conversas do baseline de junho, 'mano' ocorre 0 vezes; 'Bora' ocorre 12 vezes, 'Zé resolve' 3 vezes e não há apresentação explícita como 'assistente de compras com IA'."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/tests/search_evals/datasets/prod_search_inputs.jsonl"
  retrieved_at: "2026-09-30"
scope:
  population: "109 respostas anteriores não vazias, em 45 conversation_ids, no baseline histórico"
  time_window: "2026-06-05 a 2026-06-16, inferido dos trace IDs"
freshness: stale
relationship: contradicts
criticality: critical
status: evidenced
limitations:
  - "A ausência no campo prev_assistant não demonstra ausência nas aberturas ou em outros caminhos; o dataset é voltado a inputs de busca e não é transcript completo."
  - "As contagens não medem satisfação, causalidade, prevalência após 24/07 ou aderência a toda a experiência."
```

```yaml
id: D-002
claim: "O stakeholder autorizou continuar o upstream usando os traces disponíveis e encerrar a investigação adicional em logs."
kind: decision
source:
  type: interview
  uri: "Decisão registrada na conversa de intake"
  retrieved_at: "2026-09-30"
scope:
  population: "Formulação e priorização qualitativa do Problem da Issue 377"
  time_window: "Baseline histórico de junho e amostra recente de julho-setembro"
freshness: current
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "A decisão não converte as amostras em medida de prevalência, satisfação ou impacto atual."
  - "Métricas de sucesso da solução não podem alegar baseline quantitativo de incidência com base nesses traces."
```

```yaml
id: E-013
claim: "A busca no worktree WhatsApp não localizou outro export bruto de traces do teste de 24/07: os candidatos encontrados são evidência de pytest local de observability e uma captura de fluxo de debug datada de 28/07."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/{artifacts/evidencia-testes-datadog-llmobs.txt,whatsapp-flow-full-conversation-20260728.png}"
  retrieved_at: "2026-09-30"
scope:
  population: "Arquivos rastreados, não rastreados e ignorados do worktree, filtrados por nomes ligados a trace/export/Datadog"
  time_window: "Estado do worktree no momento da busca"
freshness: current
relationship: constrains
criticality: supporting
status: evidenced
limitations:
  - "A ausência de arquivo neste worktree não prova que o export não exista em outro ambiente, máquina, conta ou sistema."
  - "A captura de debug não é evidência de tráfego de produção nem de prevalência."
```

```yaml
id: U-004
claim: "Qual redação e regra de precedência aprovadas definem a identidade do assistente: o exemplo de Ética 'Sou o Zé, assistente virtual' ou o requisito de se apresentar como assistente de compras com IA do Zé Delivery, sem se identificar como o próprio Zé?"
kind: unknown
source:
  type: observation
  uri: "Contradição entre E-002 e E-005"
  retrieved_at: "2026-09-30"
scope:
  population: "Toda apresentação e autorreferência do assistente no WhatsApp"
  time_window: "Regra de lançamento e critérios de aceitação"
freshness: current
relationship: does-not-resolve
criticality: critical
status: unverified
limitations:
  - "Sem uma regra de precedência aprovada, não é possível transformar a identidade em critério de aceitação ou validar uma solução."
```

```yaml
id: D-003
claim: "A regra prevalente da Issue 377 é apresentar a experiência como 'assistente de compras com IA do Zé Delivery', sem se identificar como o próprio Zé."
kind: decision
source:
  type: interview
  uri: "Confirmação explícita do stakeholder no intake"
  retrieved_at: "2026-09-30"
scope:
  population: "Todas as apresentações, autorreferências e critérios de aceitação de identidade no WhatsApp"
  time_window: "Vigente para a definição da Issue 377"
freshness: current
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "A decisão prevalece para esta iniciativa sobre o exemplo de redação em E-005; a atualização ou aprovação formal do documento de Ética continua necessária antes do lançamento."
  - "Ela não substitui aprovações finais de Brand Core, Ética e Jurídico."
```

```yaml
id: E-014
claim: "A amostra recente de produção contém workflows com env:prod e git.commit.sha 85c6f036e8829060a2ff1eadd66be633942562c1, o mesmo commit do código analisado; ao menos uma sessão traz a abertura 'Zé no Zap' e a apresentação de endereço antes da interação subsequente."
kind: fact
source:
  type: observability
  uri: "Datadog LLM Observability, amostra de workflows whatsapp_message consultada em 2026-09-30"
  retrieved_at: "2026-09-30"
scope:
  population: "Uma sessão dentro dos quatro workflows recentes indexados"
  time_window: "2026-09-15 a 2026-09-23"
freshness: current
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "Demonstra que ao menos uma superfície atual usa o commit analisado; não mede incidência em toda a população."
  - "O conteúdo conversacional e qualquer dado pessoal da sessão não foram reproduzidos neste repositório."
```

## Atualização de identidade — 2026-09-30

`U-004` está resolvida para a definição da Issue por D-003. O exemplo “Sou o Zé, assistente virtual” em E-005 permanece como contradição documental a atualizar pelas áreas responsáveis, mas não define mais a regra de produto desta iniciativa.

## Atualização da lacuna de produção — 2026-09-30

O recorte recente confirma que as jornadas e as superfícies de resposta continuam instrumentadas em produção (E-009), mas é pequeno demais para estimar prevalência. O export histórico oferece profundidade de traces (E-010), mas antecede o teste de 24/07 e não declara sua consulta de origem. O Datadog acessível hoje não retorna a semana do disparo (E-011). `U-003` permanece crítico até que o export/consulta original do teste seja recuperado ou a ausência de prevalência seja aceita explicitamente como risco.
