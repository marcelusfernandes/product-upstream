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
