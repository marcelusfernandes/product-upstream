# Problem exploration — Issue 377

## Fenômeno relatado

O sinal de intake pede um tom de voz que reflita a identidade do Zé Delivery, uma nova identidade para a experiência antes chamada de “Zé no Zap”, aderência a alinhamentos jurídicos e menos estranheza nas respostas.

O único requisito já explícito como mandatário é que a experiência se apresente como **assistente de compras com IA do Zé Delivery**, e não como o próprio Zé (E-002).

## O que é observável hoje

Ainda não há exemplos de conversas, fluxos, segmentos, frequência, métricas, reclamações ou resultados de pesquisa anexados ao worktree. Portanto, não há evidência suficiente para declarar um estado atual observável além do próprio pedido (E-001–E-003).

## Candidatos de problema — ainda não validados

| ID | Candidato | O que o sustentaria | O que poderia refutá-lo |
|---|---|---|---|
| H-001 | O registro linguístico das mensagens não representa a identidade esperada do Zé Delivery. | Guia de Marketing + exemplos recorrentes de mensagens desalinhadas. | Exemplos aprovados mostram que o registro atual já é adequado. |
| H-002 | A apresentação como o próprio Zé gera confusão de identidade e/ou viola um guardrail ético. | Recomendação de Ética + mensagens que personificam o assistente. | A documentação permite explicitamente essa personificação em todos os contextos. |
| H-003 | Restrições jurídicas e éticas não estão traduzidas em regras de comportamento conversacional. | Requisitos normativos + lacunas identificadas em respostas atuais. | As regras já estão implementadas e a estranheza decorre de outra causa. |
| H-004 | A inconsistência entre jornadas causa respostas percebidas como estranhas. | Comparação entre saudações, recomendações, recusas e recuperações. | As jornadas analisadas são coerentes e a estranheza tem outra origem. |

## Impactos a verificar

- Compreensão de que a pessoa está interagindo com um assistente de compras com IA do Zé Delivery.
- Aderência à identidade de marca.
- Segurança ética e jurídica das interações.
- Confiança e continuidade na jornada de compra.

Esses impactos são hipóteses de investigação, não resultados comprovados.

## Lacuna crítica única

**U-002: recuperar os materiais-fonte de Marketing e Ética e confrontá-los com exemplos concretos de conversa.** Sem isso, não é possível transformar o sinal em problem statement nem distinguir uma regra mandatória de uma preferência de linguagem.

## Estado após a exploração inicial

| Objeto | Definition | Knowledge | Estado | Evidências |
|---|---|---|---|---|
| Problem | vague | unknown | Explore | E-001, E-002, E-003, U-001, U-002 |
| Solution | vague | unknown | Explore | E-001, E-002, E-003, U-002 |

## Re-assessment após fontes de Marketing, Ética e traces

### Problem Definition — met

- **Estado atual observável:** o relatório de traces registra aberturas genéricas, oferta alcoólica antes de intenção, repetição de bordões/emoji, personalização não solicitada e perda de contexto em respostas do assistente (E-006).
- **População e contexto:** 109 pares de turnos em 45 conversas de um export descrito como tráfego de produção; a janela e a representatividade são limitadas (E-006).
- **Gap observável:** esses comportamentos conflitam com as prioridades de clareza, segurança e resolução do guia de Marketing (E-004) e aumentam o risco ético de antropomorfização e baixa transparência sobre IA (E-005).
- **Outcome desejado:** a pessoa deve reconhecer que fala com o assistente de compras com IA do Zé Delivery, receber respostas claras, contextuais e verificáveis, e encontrar leveza apenas quando ela não comprometer segurança ou confiança (E-004, E-005).
- **Escopo:** identidade verbal, apresentação, tom e comportamento conversacional relacionados aos padrões observados. Não cobre a reescrita integral de fluxos de segurança, privacidade ou commerce.

### Problem Knowledge — not-met

Os traces dão exemplos e sinais, mas não revelam recência, prevalência, causalidade, satisfação, abandono ou a distribuição dos padrões por jornada. A incógnita `U-003` pode mudar a priorização e a formulação de impacto.

### Estados derivados

| Objeto | Definition | Knowledge | Estado | Evidências |
|---|---|---|---|---|
| Problem | concrete | unknown | Investigate | E-001–E-006, U-003 |
| Solution | vague | unknown | Explore | E-004, E-005, E-006, U-003 |

## Único gap crítico seguinte

**U-003: validar em recorte atual quais padrões continuam ativos, em quais jornadas e com qual frequência/impacto.** Isso separa defeitos históricos de comportamentos atuais e permite priorizar o problema sem confundir tom com falhas de contexto, segurança ou dados.
