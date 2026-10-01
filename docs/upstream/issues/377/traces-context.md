# Contexto de traces — Issue 377

Este é o único contexto de discovery preservado após o reinício de
2026-10-01. Não contém decisões, guias, leitura de código, hipóteses de
solução, aprovações ou conclusões do ciclo anterior.

## Pergunta que este contexto pode informar

Quais comportamentos conversacionais foram observados nas amostras disponíveis
e quais limites impedem inferir frequência, causalidade ou impacto atual?

## E-TR-001 — Export histórico de traces

```yaml
id: E-TR-001
claim: "O export histórico contém 129 registros com 129 trace IDs e 56 conversation_ids; há 109 respostas anteriores não vazias em 45 conversas."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/tests/search_evals/datasets/prod_search_inputs.jsonl"
  retrieved_at: "2026-09-30"
scope:
  population: "Registros preservados no dataset de inputs de busca de produção"
  time_window: "2026-06-05 a 2026-06-16 UTC, inferido do componente temporal dos trace IDs"
freshness: stale
relationship: supports
criticality: supporting
status: evidenced
limitations:
  - "Não é transcript completo e não contém timestamp de turno, ambiente, tenant, critério de exportação ou rótulos de resultado."
  - "Trace IDs não equivalem a conversas; não mede prevalência, satisfação, abandono ou causalidade."
```

Nas respostas e turnos seguintes observados, foram registrados: respostas
genéricas, oferta alcoólica antes de intenção explícita, bordões ou emoji
recorrentes, personalização inesperada e perda de contexto. Esses são padrões
da amostra, não uma estimativa de incidência na população.

## E-TR-002 — Observabilidade recente acessível

```yaml
id: E-TR-002
claim: "A consulta de LLM Observability retornou quatro workflows raiz whatsapp_message, de duas sessões, em env:prod; eles cobrem small_talk (2), address (1) e commerce (1)."
kind: fact
source:
  type: observability
  uri: "Datadog LLM Observability: search_llmobs_spans(ml_app=ze-consumer-whatsapp-orchestrator, span_kind=workflow, span_name=whatsapp_message, root_spans_only=true)"
  retrieved_at: "2026-09-30"
scope:
  population: "Workflows raiz indexados e acessíveis com os filtros especificados"
  time_window: "2026-07-23 a 2026-09-30"
freshness: current
relationship: supports
criticality: supporting
status: evidenced
limitations:
  - "Quatro turnos de duas sessões não estimam frequência, severidade, impacto ou cobertura de jornada."
  - "A disponibilidade depende de retenção, filtros, tenant, permissões e instrumentação."
```

## E-TR-004 — Estrutura do export histórico

```yaml
id: E-TR-004
claim: "Os 129 registros do export pertencem ao bucket prod_search_inputs: 60 search_direct, 50 search_multi_turn e 19 ocasiao. Cada registro contém mensagem, resposta anterior, conversation_id, trace_id e número de buscas; não contém transcript completo."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/tests/search_evals/datasets/prod_search_inputs.jsonl"
  retrieved_at: "2026-10-01"
scope:
  population: "Registros do export histórico E-TR-001"
  time_window: "2026-06-05 a 2026-06-16 UTC, inferido do componente temporal dos trace IDs"
freshness: stale
relationship: constrains
criticality: critical
status: evidenced
limitations:
  - "O formato permite observar uma mensagem e, quando houver, a resposta imediatamente anterior; não permite reconstituir a jornada ou os turnos posteriores."
  - "Os tipos de caso descrevem o dataset de busca, não categorias de problema, satisfação ou impacto."
```

## E-TR-003 — Lacuna da coorte de teste

```yaml
id: E-TR-003
claim: "Uma consulta ampla ao LLM Observability no período de 2026-07-24 a 2026-07-31 não retornou spans para ml_app=ze-consumer-whatsapp-orchestrator."
kind: fact
source:
  type: observability
  uri: "Datadog LLM Observability: busca ampla sem filtro de tipo ou raiz"
  retrieved_at: "2026-09-30"
scope:
  population: "Spans atualmente acessíveis com os filtros especificados"
  time_window: "2026-07-24 a 2026-07-31"
freshness: current
relationship: does-not-resolve
criticality: supporting
status: evidenced
limitations:
  - "Resultado vazio não demonstra ausência de tráfego; pode refletir retenção, identificador, permissões ou instrumentação."
```

## O que este contexto não permite concluir

- Qual é o problema prioritário, sua causa, prevalência, severidade ou impacto.
- Que qualquer padrão continua ativo fora das amostras descritas.
- Que uma intervenção específica, mudança de tom ou identidade resolverá os
  comportamentos observados.
