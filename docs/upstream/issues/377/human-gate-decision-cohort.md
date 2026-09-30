## Human gate — coorte de decisão para U-003

**Status: decisão de escopo resolvida em 2026-09-30; recuperação da coorte de 24/07 permanece como lacuna de evidência.**

### Contexto

Há duas evidências com escopos diferentes:

1. O dataset versionado `prod_search_inputs.jsonl` contém 129 traces e 56 `conversation_id`s distintos. O componente temporal dos trace IDs indica 05–16/06/2026 (UTC). O arquivo não declara janela, ambiente ou consulta de exportação e antecede o teste em escopo.
2. A consulta ao Datadog LLM Observability de 23/07–30/09 encontrou quatro workflows `whatsapp_message`, em duas sessões e com `env:prod`; eles cobrem `small_talk`, `address` e `commerce`.
3. O stakeholder confirmou que o disparo ocorreu em 24/07/2026. Uma consulta ampla ao LLM Observability entre 24 e 31/07 não encontrou spans para o `ml_app` conhecido.

Os quatro workflows recentes não são base suficiente para estimar frequência ou impacto. O Datadog acessível hoje não oferece a coorte do disparo; o resultado vazio pode refletir retenção, tenant, identificador, permissões ou instrumentação distintos.

### Question

Onde está o export ou a consulta Datadog original do teste disparado em 24/07/2026?

### Options

1. Indicar/localizar o export anonimizado do teste.
2. Indicar tenant, `ml_app`, ambiente ou query de origem.
3. Usar junho para mapear padrões e aceitar explicitamente a ausência de prevalência atual como risco.

### Recommendation

Opção 1 ou 2. Até que ela exista, usar a amostra de junho apenas como evidência histórica de padrões; usar o recorte recente somente para confirmar que as jornadas/superfícies ainda estão ativas.

### Decision

O stakeholder aprovou o uso da amostra de junho como baseline histórico complementar (D-001). A amostra não substitui a coorte do disparo de 24/07 nem autoriza inferência de prevalência atual.

### Impact

Sem a decisão, não é possível ordenar as jornadas por frequência/impacto atual. `Problem` fica em `Investigate` e `Solution` em `Explore`.

### Blocks

- `Problem = Ready`;
- métricas e critérios de sucesso;
- seleção responsável de uma intervenção de solução.
