# Problem framing — identidade conversacional da Issue 377

## Sinal original preservado

> Melhor tom de voz para refletir a identidade do Zé Delivery, definir nova identidade do Zé no Zap e se adequar a alinhamentos jurídicos e evitar estranheza nas respostas.

## Problem statement

O assistente de compras no WhatsApp não possui uma identidade conversacional única, aprovada e aplicada de modo consistente. A implementação atual se apresenta e se comporta como “Zé” em algumas superfícies, enquanto Marketing enquadra o produto como assistente de compras e Ética exige transparência contínua sobre a automação. A regra de precedência entre essas formulações não está resolvida (U-004).

Isso impede avaliar de forma consistente se uma resposta representa corretamente o produto e aumenta o risco de comunicações pouco claras ou antropomorfizadas. Esse risco é uma inferência de E-004, E-005 e E-007; não é uma medida causal de confiança ou satisfação.

## Estado atual observável

- A abertura, os prompts de persona, `small_talk` e o agente ReAct usam formulações de “Zé” e tom coloquial em superfícies distintas (E-007).
- No baseline histórico, “mano” não ocorre nas 109 respostas anteriores analisadas; “Bora” ocorre 12 vezes e “Zé resolve” três (E-012). Logo, “reduzir mano” não representa o gap demonstrado nessa amostra.
- O guia de Marketing chama o produto de assistente de compras, mas está em rascunho para revisão de Brand Core (E-004).
- Ética exige deixar claro o caráter automatizado durante toda a interação e evitar antropomorfização, mas sugere uma abertura que começa com “Sou o Zé” (E-005).

## Estado desejado

Pessoas usuárias devem receber uma apresentação e uma autorreferência consistentes, transparentes sobre IA e compatíveis com os limites de Marketing, Ética e Jurídico aprovados. O assistente deve ajudar a compra com clareza e usar leveza apenas quando não comprometer fatos, segurança ou entendimento (E-004, E-005).

## População e contexto

Pessoas que usam o assistente de compras no WhatsApp. A evidência histórica disponível cobre 109 pares de turnos de 45 conversas entre 05 e 16/06/2026; a evidência recente cobre quatro workflows de duas sessões entre 23/07 e 30/09/2026. Essas amostras não estimam prevalência nem impacto atual (E-009–E-013).

## Dimensões separadas

| Dimensão | Evidência | Relação com a Issue |
|---|---|---|
| Identidade e transparência | E-002, E-004, E-005, E-007, U-004 | Núcleo da Issue; precisa regra aprovada. |
| Tom comercial e álcool | E-004, E-005, E-006, E-007, E-012 | Em escopo somente quando expressa a identidade aprovada ou conflita com limites éticos. |
| Continuidade/contexto e catálogo | E-006, E-007 | Evidência de estranheza, mas causa operacional separada; não será tratada como problema de tom. |
| Privacidade e exposição de endereço | E-005, E-006, E-007 | Risco crítico separado; não será resolvido por uma mudança editorial. |

## Escopo

- Definir a regra de identidade e transparência conversacional do assistente.
- Definir os limites de tom ligados a essa identidade, consumo responsável e clareza.
- Estabelecer critérios qualitativos verificáveis para apresentações, autorreferências e respostas dentro do escopo.

## Fora de escopo

- Corrigir memória, catálogo, carrinho, autenticação ou tools.
- Corrigir a exposição de PII/endereço, exceto declarar que não é uma solução de tom.
- Alegar redução de abandono, aumento de confiança ou frequência de falhas sem nova medição.

## Hipóteses concorrentes

1. A estranheza percebida decorre principalmente da identidade personificada e da transparência insuficiente.
2. A estranheza decorre principalmente de falhas de continuidade/contexto; uma mudança de tom não a resolveria.
3. As duas dimensões coexistem, mas requerem intervenções e métricas independentes.

## Único gap crítico

**U-004:** reconciliação formal da identidade. Sem ela, não há critério de aceitação nem base para decidir solução.
