## Human gate — coorte de decisão para U-003

**Status: aguardando confirmação do stakeholder/responsável operacional.**

### Contexto

Há duas evidências com escopos diferentes:

1. O dataset versionado `prod_search_inputs.jsonl` contém 129 traces e 56 `conversation_id`s distintos. O componente temporal dos trace IDs indica 05–16/06/2026 (UTC). O arquivo não declara janela, ambiente ou consulta de exportação.
2. A consulta ao Datadog LLM Observability de 23/07–30/09 encontrou quatro workflows `whatsapp_message`, em duas sessões e com `env:prod`; eles cobrem `small_talk`, `address` e `commerce`.

O intake informou que o teste ocorreu em 23/07. Isso conflita com a janela técnica do export histórico. Os quatro workflows recentes não são base suficiente para estimar frequência ou impacto.

### Question

Qual coorte deve embasar a priorização da Issue 377: o export histórico de 05–16/06, uma coorte ainda não localizada de 23/07 em diante, ou ambos com papéis distintos?

### Options

1. Confirmar que o export de junho é o teste em escopo.
2. Indicar/localizar o export de 23/07 ou a consulta Datadog correspondente.
3. Usar junho para mapear padrões e aceitar explicitamente a ausência de prevalência atual como risco.

### Recommendation

Opção 2. Até que ela exista, usar a amostra de junho apenas como evidência histórica de padrões; usar o recorte recente somente para confirmar que as jornadas/superfícies ainda estão ativas.

### Impact

Sem a decisão, não é possível ordenar as jornadas por frequência/impacto atual. `Problem` fica em `Investigate` e `Solution` em `Explore`.

### Blocks

- `Problem = Ready`;
- métricas e critérios de sucesso;
- seleção responsável de uma intervenção de solução.
