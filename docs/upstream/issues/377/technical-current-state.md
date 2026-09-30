# Estado técnico atual — repo WhatsApp

## Escopo e proveniência

Leitura realizada em 2026-09-30 no worktree da Issue 377 do repositório `ze-consumer-whatsapp-orchestrator-app`, em `/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz`.

O worktree está no commit `85c6f036e8829060a2ff1eadd66be633942562c1`; a relação desse commit com o deploy atual não foi verificada. Os guias de Marketing, Ética e os relatórios de discovery estão não versionados nesse worktree.

## Como a conversa funciona hoje

```text
Webhook Meta → MessageCoordinator → autenticação + sessão + abertura/endereço
→ LangGraph: memória → guardrails de entrada → classificador
→ [small_talk | agente ReAct] → guardrails de saída → envio WhatsApp
```

- O `MessageCoordinator` prepara uma abertura de sessão e pode exibir endereços salvos antes da resposta do agente.
- O LangGraph usa memória, guardrails de entrada, gray zone, classificador, `small_talk`, agente ReAct, moderador/template e guardrails de saída.
- `small_talk` é um nó separado, sem tools; commerce, ocasião e desambiguação são tratados pelo agente ReAct único.
- O agente monta um prompt estático mais contexto dinâmico de sessão, resumo, buscas anteriores, desambiguação, endereço ativo, perfil e autenticação.

## Tools disponíveis ao agente

- Catálogo: `search_products`, `browse_category`, `get_product_details`, `get_offers`, `get_recommendations`.
- Compra: `cart`, `cart_bulk_add`, `cart_bulk_mutate`, `create_pending_basket`.
- Contexto operacional: `get_order_history` e, condicionalmente, `logout_user`.

Preço, disponibilidade e mutações de carrinho têm contratos de tool e validações específicas; o agente não deveria afirmar ou montar produto sem resultado de ferramenta.

## Controles existentes

- Entrada: mascaramento/bloqueio de PII, detecção de prompt injection, classificação de temas e gray zone.
- Saída: normalização para pt-BR, mascaramento de PII, remoção/rewrite de marca proibida, verificação de preço e checagem LLM de segurança.
- Sensíveis: regras para menores, saúde, dados de terceiros, política, identidade e manipulação de prompt.

Esses controles não formam hoje uma camada de avaliação de voz/identidade: eles não verificam de modo explícito a apresentação como assistente com IA, a não antropomorfização, o uso contextual de humor ou a oferta comercial antes da intenção.

## Divergências observáveis com as novas fontes

| Superfície atual | Comportamento observado no código | Relação com o novo requisito |
|---|---|---|
| Prompt de segurança/persona | Define “o Zé” como amigo espirituoso; fornece “Bora?”, “Partiu?”, “Gelada trincando” e “Zé salva” como vocabulário. | Conflita com a diretriz de o produto não se identificar como o próprio Zé. |
| `small_talk` | Inicia como “Você é o Zé, assistente do Zé Delivery” e herda a mesma persona. | O caminho de saudação precisa entrar no mesmo escopo de identidade. |
| Prompt do agente ReAct | Importa a mesma persona estática e trata humor/emoji como recursos de venda. | Não traduz a prioridade nova de clareza e transparência sobre IA. |
| Abertura no coordinator | Envia “você chegou no Zé no Zap”, oferta de cerveja/destilado e emoji; também pode mostrar endereço salvo. | Reúne os gatilhos de estranheza descritos nos traces e merece validação separada. |
| Guardrails de saída | Protegem PII, preço, concorrentes e temas, mas não impõem a identidade “assistente de compras com IA”. | A nova regra não é verificável como invariant no pipeline atual. |
| Evals | A suíte mede classificação, guardrails, tools, correctness, helpfulness e hallucination. Não foi encontrado teste executável explicitamente voltado a tom, transparência de IA ou não antropomorfização. | A futura mudança precisará de critérios e casos de avaliação próprios. |

## O que isso permite concluir — e o que não permite

Permite concluir que a voz atual é uma propriedade distribuída entre coordinator, prompts, nós e guardrails; portanto, trocar apenas um prompt não basta para afirmar aderência.

Não permite concluir que todos esses comportamentos estão ativos no deploy atual, nem estimar sua prevalência, impacto causal ou a ordem correta de mudança. Isso permanece em `U-003`.

## Fontes técnicas

- `src/coordinator/message_coordinator.py`
- `src/orchestration/graph.py`
- `src/orchestration/nodes/{agent,small_talk,input_guardrails,output_guardrails}.py`
- `src/orchestration/prompts/{security,system,agent,session_opening,guardrails}.py`
- `src/orchestration/tools/{README.md,__init__.py}`
- `src/modules/conversation/domain/{input_guardrails,output_guardrails,gray_zone}.py`
- `tests/node_harness/` e relatórios de discovery da Issue 377.
