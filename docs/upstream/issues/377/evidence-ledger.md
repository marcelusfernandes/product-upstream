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
  - "A redação operacional exata de identificação do assistente requer confirmação das áreas responsáveis."
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
  uri: "A validar com recorte atual de traces, telemetria e revisão de fluxos"
  retrieved_at: "2026-09-30"
scope:
  population: "Usuários atuais do assistente de compras com IA do Zé Delivery"
  time_window: "A definir"
freshness: unknown
relationship: does-not-resolve
criticality: critical
status: unverified
limitations:
  - "Sem esta verificação, não é possível decidir quais jornadas devem ser alteradas primeiro ou atribuir efeito a uma mudança de tom."
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
