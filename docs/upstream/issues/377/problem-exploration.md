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

## Checagem do sinal original no baseline histórico

O sinal original menciona reduzir o uso de “mano”. A análise agregada das 109 respostas anteriores disponíveis no baseline não encontrou nenhuma ocorrência do termo (E-012). Portanto, reduzir “mano” não é um problema mensurável nessa amostra e não deve ser usado como proxy do desalinhamento.

No mesmo recorte, “Bora” aparece 12 vezes e “Zé resolve” três. Também não há apresentação explícita como **assistente de compras com IA do Zé Delivery** no campo analisado (E-012). Isso apoia investigar identidade e padrões de linguagem, mas não prova ausência dessa identificação nas aberturas, pois o dataset não é transcript completo.

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

Os traces dão exemplos e sinais, mas não revelam recência, prevalência, causalidade, satisfação, abandono ou a distribuição dos padrões por jornada. O dataset histórico contém 129 traces em 56 conversas na faixa técnica de 05–16/06/2026 (E-010); ele antecede o disparo confirmado do teste em 24/07/2026 (E-011). O recorte recente de 23/07–30/09 retorna quatro workflows em duas sessões, cobrindo small_talk, address e commerce (E-009), enquanto a consulta ampla da semana do disparo não retorna spans (E-011). A segunda amostra confirma continuidade de jornadas, mas não mede sua frequência. A coorte original do teste deve ser recuperada antes de usar dados para priorização. A incógnita `U-003` pode mudar a priorização e a formulação de impacto.

### Estados derivados

| Objeto | Definition | Knowledge | Estado | Evidências |
|---|---|---|---|---|
| Problem | concrete | unknown | Investigate | E-001–E-006, U-003 |
| Solution | vague | unknown | Explore | E-004, E-005, E-006, U-003 |

## Único gap crítico seguinte

**U-003: validar em recorte atual quais padrões continuam ativos, em quais jornadas e com qual frequência/impacto.** Isso separa defeitos históricos de comportamentos atuais e permite priorizar o problema sem confundir tom com falhas de contexto, segurança ou dados.

### Re-assessment após baseline complementar

- O baseline histórico está autorizado como fonte complementar (D-001), mas antecede o teste em escopo e não resolve `U-003`.
- A hipótese implícita de que “mano” é o padrão prioritário é contrariada no baseline (E-012).
- A formulação do problema continua concreta: identidade inadequadamente personificada, transparência insuficiente e linguagem/contexto que conflitam com Marketing e Ética são riscos observáveis (E-004–E-007, E-012).
- O worktree não contém outro export bruto da coorte de 24/07 (E-013). O stakeholder autorizou prosseguir com os traces disponíveis (D-002).
- **Problem Knowledge está pendente de revisão adversarial**: a limitação de prevalência atual foi explicitamente aceita para a formulação qualitativa do problema, mas não para alegações de impacto mensurável.

## Reframing após revisão adversarial

A revisão independente reprovou `Problem = Ready`: ela identificou que o framing anterior misturava problemas de identidade/tom com falhas de contexto, catálogo e privacidade, e que a regra de identidade tem fontes conflitantes. O problema foi decomposto em quatro dimensões (ver `problem-framing.md`).

Após a decomposição, **Problem Definition volta a met** para a dimensão em escopo da Issue: o assistente não possuía uma identidade conversacional única, aprovada e operacionalizada entre abertura, prompts e guardrails. O stakeholder resolveu `U-004` por D-003: a identidade prevalente é **assistente de compras com IA do Zé Delivery**, sem se identificar como o próprio Zé. A transição de Knowledge depende apenas da checagem adversarial final dessa decisão.

| Objeto | Definition | Knowledge | Estado | Evidências |
|---|---|---|---|---|
| Problem | concrete | unknown | Investigate | E-002, E-004–E-007, E-009–E-013, U-004 |
| Solution | vague | unknown | Explore | E-004, E-005, U-004 |

## Reassess final da revisão adversarial

A checagem independente posterior a D-003 concluiu:

- **Problem Definition = met** para identidade/transparência;
- **Problem Knowledge = not-met** para priorização por prevalência, severidade ou impacto mensurável;
- E-014 confirma que ao menos uma sessão recente de produção usa o commit analisado e mantém a abertura “Zé no Zap”, mas não resolve frequência.

O único gate remanescente é decidir se a obrigatoriedade de identidade (D-003), somada à ocorrência atual observada (E-014), basta para avançar como correção de conformidade — com métricas de sucesso de aderência — apesar de U-003. Sem essa aceitação explícita, `Problem` permanece `Investigate`.

## Transição para Problem Ready

O stakeholder aceitou explicitamente U-003 como risco limitado para uma correção mandatória (D-004). Assim, a evidência é suficiente para decidir o problema em escopo — identidade e transparência — sem alegar prevalência ou impacto quantitativo.

| Objeto | Definition | Knowledge | Estado | Evidências |
|---|---|---|---|---|
| Problem | concrete | known | Ready | E-002, E-004–E-007, E-009–E-014, D-001–D-004 |
| Solution | vague | unknown | Explore | E-004, E-005, E-007, D-003, D-004 |

## Human gate — coorte de decisão para U-003

O dataset histórico antecede o teste confirmado de 24/07/2026, e a consulta ampla dessa semana está vazia no Datadog acessível hoje. O upstream não vai presumir que 129 traces de 05–16/06 representam o teste de julho, nem que quatro workflows recentes sejam suficientes para medir incidência.

- **Question:** onde está o export ou a consulta Datadog original do teste disparado em 24/07/2026?
- **Options:** (a) indicar/localizar o export anonimizado do teste; (b) indicar tenant, ml_app, ambiente ou query de origem; (c) aceitar explicitamente que a priorização use apenas evidência histórica e ausência de prevalência atual como risco.
- **Recommendation:** opção (a) ou (b); até lá, usar junho apenas como evidência histórica de padrões e o recorte recente apenas como evidência de que jornadas/superfícies seguem ativas.
- **Impact:** sem essa decisão, o upstream não pode ordenar jornadas por frequência/impacto atual; `Problem` permanece `Investigate` e `Solution` permanece `Explore`.
- **Blocks:** formulação de impacto mensurável, critérios de sucesso e qualquer transição para `Problem = Ready`.
