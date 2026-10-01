# Framing de Problem — identidade e transparência

**Modo:** `problem-work / frame`  
**Evidências:** E-005, E-006, E-007 e E-008

## Problem statement

Na revisão de código `85c6f036e8829060a2ff1eadd66be633942562c1`, as superfícies
observadas de abertura e de persona apresentam o assistente como “Zé” e a
abertura não declara que se trata de um assistente de compras com IA. Isso não
está alinhado à restrição de escopo E-007 e não demonstra a transparência
contínua requerida em E-006.

## Estado atual observável

- A abertura de sessão é uma mensagem estática enviada diretamente e chama a
  experiência de “Zé no Zap”, introduzindo cerveja e destilado.
- Os prompts de agente, guardrails e moderator usam a persona “Você é o Zé”.
- As fontes de Marketing e Ética tratam segurança, clareza e transparência como
  prioridades anteriores a tom e humor.

## Estado desejado / outcome

Nas superfícies de apresentação e geração que forem confirmadas no escopo, a
identidade deve respeitar E-007: o produto se apresenta como assistente de
compras com IA do Zé Delivery, sem se passar pelo próprio Zé. A transparência
sobre automação deve obedecer à orientação de Ética aplicável, sem antecipar
redação final ou aprovação de release.

## População e contexto

O escopo observado é limitado a pessoas que recebem a abertura de sessão ou
respostas produzidas pelos caminhos que consomem as superfícies do commit E-008.
Não se afirma que esse commit esteja em produção, que todas as superfícies
cheguem a clientes ou qual é sua frequência.

## Gap observável

| Regra / restrição | Evidência de estado atual | Gap |
| --- | --- | --- |
| E-007 — não se identificar como o próprio Zé | abertura “Zé no Zap” e prompts “Você é o Zé” (E-008) | A identificação atual não explicita o assistente de compras com IA e usa a persona do próprio Zé. |
| E-006 — automação clara ao longo da interação | a abertura estática observada não informa IA (E-008) | Não há demonstração de transparência na abertura nem de cobertura nas demais superfícies. |
| E-005 — não presumir bebida em pedidos de ocasião | a abertura introduz cerveja e destilado antes de intenção (E-008) | A abertura pode antecipar uma categoria regulada sem o contexto da pessoa. |

## Impacto

Há risco de não conformidade com a restrição de escopo e com as diretrizes
aplicáveis. Não há evidência para quantificar impacto em confiança, satisfação,
abandono, conversão, prevalência ou severidade em produção.

## Escopo

Inclui: apresentação, autodefinição de persona e transparência de IA nas
superfícies que vierem a ser confirmadas como alcançando a pessoa usuária.

Não inclui, neste framing: memória e continuidade de contexto, catálogo,
checkout, endereço, personalização, pesquisa de satisfação, nem uma reescrita
de tom em geral. Eles permanecem candidatos separados até evidência própria.

## Hipóteses concorrentes e exceções

- A revisão implantada pode ser diferente de E-008.
- Os prompts podem ser interceptados ou modificados por outra camada antes da
  entrega; por isso sua redação não é, isoladamente, prova de mensagem enviada.
- A abertura estática pode estar condicionada a um fluxo que ainda precisa ser
  mapeado.
- A recomendação de bebida na abertura pode ser tratada por outra regra de
  produto; este framing só registra o conflito com E-005, não define a correção.

## Gates após framing

- **Problem Definition → Concrete:** candidato a `met`, sujeito a revisão
  independente. Current state, população/contexto limitado, gap, outcome,
  escopo e fontes estão explicitados.
- **Problem Knowledge → Known:** `not-met`. Permanecem U-001 (reconciliação
  formal de identidade/transparência), U-002 (recência/prevalência/impacto),
  U-003 (se outros candidatos têm relação causal) e U-004 (deploy/superfícies
  efetivas).

## Próximo gap crítico

Confirmar, de forma independente, que o framing não transforma o texto de um
prompt em comportamento de produção e que o escopo está corretamente limitado
à correção mandatória de identidade/transparência.
