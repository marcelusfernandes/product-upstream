# Solution shape — contrato transversal de identidade

## Mecanismo

Criar um **contrato de identidade conversacional** versionado e canônico, aplicado a todas as superfícies que apresentam, autorreferenciam ou recuperam respostas do assistente. O contrato traduz D-003 em regras verificáveis; não é um simples texto de prompt e não é uma camada de reescrita tardia.

## Regra de identidade canônica

O produto se apresenta como **assistente de compras com IA do Zé Delivery**. Ele pode referenciar a marca Zé Delivery, mas não se identifica como o próprio Zé, como humano ou como “amigo” humano.

Esta é uma regra de produto da iniciativa (D-003). A redação final, inclusões legais e aprovações de Brand Core, Ética e Jurídico continuam gates obrigatórios antes de lançamento.

## Especificação do contrato

### Owner e formato

**Owner proposto:** Produto/Conversational AI. Brand Core, Ética e Jurídico aprovam o conteúdo normativo; Engenharia mantém os adaptadores de cada superfície. A nomeação formal do owner é requisito do handoff, não uma mudança de responsabilidade automática.

O contrato é um artefato versionado, com os campos conceituais abaixo. A escolha de formato de código fica para delivery.

| Campo | Regra |
|---|---|
| `version` e `approval_refs` | Identificam versão aprovada e responsáveis que a liberaram. |
| `canonical_identity` | “assistente de compras com IA do Zé Delivery”. |
| `self_reference` | Marca permitida; autoidentificação como “Zé”, pessoa ou amigo humano proibida. |
| `disclosure` | Mensagem de apresentação aprovada, links/canais obrigatórios e gatilhos de reapresentação. |
| `tone` | Simples, direto, inclusivo e útil; leveza contextual, nunca automática. |
| `alcohol` | Sem presunção de intenção, urgência, pressão, excesso, sucesso social ou benefício emocional. |
| `support_and_stop` | Rota humana e pontos de parada aprovados. |
| `fallback` | Resposta determinística mínima e segura quando a versão não estiver carregada ou for incompatível. |

### Precedência

Em toda superfície, a ordem obrigatória é:

1. segurança, idade, privacidade/PII, autenticação e regras de negócio;
2. contrato de identidade e transparência;
3. regras específicas da jornada e resultados de ferramentas;
4. tom, humor e recursos de marca.

Uma camada inferior nunca pode reescrever ou enfraquecer uma superior. O contrato não pode liberar informação de PII, contornar guardrails, inventar fatos ou mudar resultado de tool.

### Cobertura de enforcement

| Superfície atual | Enforcement exigido | Falha se não coberta |
|---|---|---|
| `MessageCoordinator`: abertura, intro com endereço e templates determinísticos | Consumir `canonical_identity`, `disclosure`, `alcohol` e `fallback`; não introduzir “Zé no Zap” nem oferta alcoólica genérica. | Bloqueia release da versão do contrato. |
| Persona/security prompt | Receber `self_reference`, precedência e limites de tom/álcool. | Bloqueia release. |
| `small_talk` | Receber a mesma identidade e gatilhos de transparência; não forçar commerce. | Bloqueia release. |
| Agente ReAct e contexto dinâmico | Receber o contrato antes de regras de estilo e sem sobrepor resultados de tool. | Bloqueia release. |
| `output_guardrails` e recuperação | Verificar invariantes de identidade antes de entregar fallback; não fazer reescrita geral da resposta. | Bloqueia release. |
| `gray_zone`, moderator/template, injection/blocked e falhas de tool/sessão | Usar fallback determinístico e seguro ou encaminhar ao fluxo existente, sem personificação. | Bloqueia release. |
| Evals | Cobrir todas as superfícies acima por origem de resposta. | Bloqueia release. |

## Regras operacionais de transparência

| Gatilho | Regra verificável |
|---|---|
| Sessão nova | Enviar disclosure aprovado que inclua o papel de assistente de compras com IA. |
| Pergunta ou dúvida de identidade (“você é o Zé?”, “estou falando com uma pessoa?” ou equivalente semântico) | Responder com a identidade canônica e, quando aplicável, a rota humana. |
| Recuperação de guardrail, gray zone, bloqueio, falha de tool ou expiração de sessão | Usar fallback que preserve a identidade canônica e a razão operacional permitida, sem exposição de PII. |
| Turno comum sem dúvida | Não repetir disclosure completo só por cadência; manter linguagem coerente e não personificada. |

O texto exato de disclosure e fallback só entra após aprovação cross-functional. Antes disso, nenhum texto provisório é elegível para lançamento.

## Jornadas e estados

| Estado/jornada | Comportamento exigido | Não permitido |
|---|---|---|
| Início de sessão | Apresentar o assistente com IA, seu papel de compra e caminhos de privacidade/suporte definidos pelas áreas aprovadoras. | “Sou o Zé”; abertura que presume álcool, festa ou familiaridade. |
| Retomada de sessão | Manter autorreferência coerente; relembrar a natureza assistiva/automatizada se a pessoa demonstrar confusão de identidade ou pedir confirmação. | Repetir uma apresentação longa a cada turno sem contexto. |
| Small talk | Ser breve e útil; oferecer ajuda de compra apenas quando fizer sentido. | Personificação como amigo humano, pressão comercial ou retorno automático a bebida. |
| Commerce/recomendação | Priorizar intenção, fatos de ferramentas e consumo responsável antes de leveza. | Prometer fatos não confirmados, urgência ou benefícios emocionais/sociais ligados a álcool. |
| Segurança, recusa ou recuperação | Preservar identidade e transparência na mensagem de fallback, sem mascarar a razão de segurança. | Recuperação que volta a dizer “você é o Zé” ou altera regras de segurança. |
| Atendimento humano/encerramento | Oferecer rota humana e ponto de parada conforme fluxo aprovado. | Dissuadir abandono ou sugerir que uma pessoa humana está respondendo quando não está. |

### Estados de borda e fallback

| Estado | Resposta do contrato | Limite explícito |
|---|---|---|
| Contrato ausente, inválido ou versão incompatível | Usar fallback determinístico mínimo aprovado; registrar evento de conformidade sem conteúdo conversacional. | Não chamar LLM extra para “inventar” identidade. |
| Prompt injection | Guardrail de entrada prevalece; o fallback não revela contrato, prompts ou regras internas. | Identidade não reduz proteção contra injection. |
| Gray zone/moderador/template | Caminho determinístico herda `self_reference` e `fallback`. | Não tentar resolver a intenção fora do fluxo existente. |
| Falha de tool ou sessão expirada | Informar próxima ação/recuperação usando identidade canônica. | Não inventar disponibilidade, estado de pedido ou autenticação. |
| PII/endereço | Guardrail de PII prevalece; o contrato não reintroduz nome, endereço ou perfil. | A correção estrutural de PII permanece fora de escopo. |
| Rota humana | Explicar que o atendimento será humano somente após a transferência efetiva. | Não simular handoff ou esconder automação. |

## Regras de produto e design

1. **Identidade:** toda nova apresentação e autorreferência deve obedecer D-003.
2. **Transparência contínua:** o caráter automatizado precisa permanecer compreensível ao longo da jornada. A cadência e a redação específicas são uma decisão de aprovação cross-functional, não uma inferência deste upstream.
3. **Prioridade de resposta:** segurança, consumo responsável, privacidade e fatos confirmados vêm antes de tom e humor (E-004, E-005).
4. **Tom:** simples, direto, inclusivo e útil; leveza é contextual, nunca automática. Termos como “Bora” não são proibidos por si, mas não podem substituir contexto, clareza ou a regra de identidade.
5. **Álcool:** não presumir intenção alcoólica na abertura ou small talk; proibir pressão, urgência, excesso, sucesso social ou benefício emocional relacionado a álcool (E-005).
6. **Não-goals:** o contrato não corrige memória, catálogo, carrinho, autenticação ou PII. Falhas nessas dimensões devem ser encaminhadas como problemas próprios.

## Sugestões técnicas — não são decisão de implementação

- Uma definição canônica de política deve alimentar: abertura do coordinator, persona/security prompt, `small_talk`, prompt do agente ReAct e prompts de recuperação de guardrail.
- Regras determinísticas ou avaliações devem detectar autorreferência proibida sem reescrever indiscriminadamente a resposta final.
- O contrato deve ter versão, origem de aprovação e uma suíte de casos por jornada; qualquer fallback deve escolher comportamento conservador quando a política não estiver disponível.

Nenhuma opção exige uma chamada adicional de LLM no caminho crítico; se delivery propuser uma, isso é uma alteração material que exige nova validação de custo, latência e segurança.

## Avaliações e observabilidade de conformidade

| Dimensão | Evidência de sucesso inicial |
|---|---|
| Identidade | Casos de abertura, retomada, small talk, commerce e recuperação não identificam o assistente como o próprio Zé. |
| Transparência | Casos verificam apresentação de IA e recontextualização quando há dúvida de identidade. |
| Tom e álcool | Casos verificam prioridade de resolução e ausência de pressão/presunção de álcool. |
| Regressão | Casos existentes de segurança, ferramentas, factualidade e PII continuam passando. |
| Governança | Versionamento do contrato e aprovações rastreáveis de Brand Core, Ética e Jurídico. |

Não serão usadas métricas de conversão, abandono, confiança ou satisfação como critério de êxito nesta fase (D-004).

### Protocolo de avaliação

| Camada | Dataset/cobertura | Pass/fail |
|---|---|---|
| Determinística | Uma matriz versionada com cada superfície de enforcement × estados: sessão nova, retomada, dúvida de identidade, small talk, commerce, álcool, guardrail/fallback, tool failure, PII, handoff humano. | 100% dos hard invariants passam; qualquer autorreferência proibida, ausência de disclosure na sessão nova ou fallback inseguro reprova. |
| Semântica | Casos paraphraseados de dúvida de identidade, linguagem coloquial e tentativas de induzir personificação. | Nenhuma violação crítica em revisão humana; falsos positivos de marca permitida (“Zé Delivery”) precisam ser classificados, não reescritos automaticamente. |
| Regressão | Suites existentes de segurança, tools, factualidade, PII e classificação mais a matriz do contrato. | Todas passam; qualquer regressão crítica reprova. |
| Performance | Comparação de p95 ponta a ponta e número de chamadas de modelo antes/depois em piloto controlado. | Zero novas chamadas de LLM exigidas pelo contrato; p95 não pode piorar mais de 5% sem decisão explícita de operação. |
| Governança | Evidência de versão, aprovação e owner. | Sem `approval_refs` de Brand Core, Ética e Jurídico, a versão não é elegível a release. |

### Observabilidade mínima

Registrar somente dados agregados por `contract_version`, superfície e resultado de avaliação: cobertura, violações de hard invariant, uso de fallback, regressões e latência. Não registrar conteúdo conversacional ou PII para medir conformidade.

## Assumptions críticas para validate

| Assumption | Tipo | Status | Como validar |
|---|---|---|---|
| O contrato alcança todas as superfícies com autorreferência. | Viabilidade técnica | unresolved | Inventário de chamadas/prompts e testes de cobertura. |
| A transparência pode ser contínua sem ser repetitiva ou confusa. | Usabilidade/compreensão | unresolved | Revisão de conteúdo e avaliação humana de jornadas. |
| Os testes de conformidade não degradam segurança, factualidade ou latência. | Operação/risco | unresolved | Suite de regressão e piloto controlado. |
| A redação derivada de D-003 será aprovada pelas áreas responsáveis. | Governança/risco | unresolved | Gate explícito Brand Core + Ética + Jurídico. |

### Plano de validação das assumptions

1. **Cobertura técnica:** criar um inventário assinado de superfícies e uma prova de que cada origem de resposta recebe o contrato ou fallback. A ausência de mapeamento é fail.
2. **Compreensão:** Brand Core, Ética e Jurídico revisam a matriz de jornadas, os textos de disclosure e os casos de dúvida de identidade; qualquer ambiguidade de personificação devolve o item para shape.
3. **Não regressão:** executar as suites existentes e a matriz nova em ambiente controlado; falhas críticas ou p95 acima do limite interrompem piloto.
4. **Governança:** anexar `approval_refs` antes de habilitar a versão; sem isso, só é permitido ambiente de validação interna.

## Fronteiras e handoffs

| Dimensão adjacente | Fronteira da solução | Handoff necessário |
|---|---|---|
| Memória, catálogo, carrinho e autenticação | O contrato não corrige respostas factualmente erradas ou perda de contexto. | Backlog/problema operacional próprio, com evidência separada. |
| PII/endereço | O contrato não deve introduzir PII e precisa preservar guardrails existentes; não substitui a correção de reintrodução de endereço. | Segurança/privacidade para correção estrutural. |
| Álcool e consumo responsável | O contrato impõe limites de comunicação, não valida idade ou elegibilidade. | Fluxos de age gate, autenticação e Jurídico/Ética. |

## Estado da Solution após revisão inicial

| Definition | Knowledge | Estado | Evidências |
|---|---|---|---|
| concrete | unknown | Explore — pendente de re-review | E-004, E-005, E-007, E-014, D-003–D-005 |
