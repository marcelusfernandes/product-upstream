## Decision record — uso do baseline de junho

- **Date:** 2026-09-30
- **Origin:** human gate de coorte de evidência para U-003
- **Question:** o dataset de 05–16/06/2026 pode apoiar a investigação da Issue 377, embora anteceda o disparo confirmado em 24/07/2026?
- **Context:** o dataset contém 129 traces e 56 conversas distintas (E-010). A coorte de 24/07 não está acessível no Datadog consultado (E-011), enquanto a amostra recente contém quatro workflows e não mede incidência (E-009).
- **Options:** descartar junho; usar junho apenas como baseline histórico; tratá-lo indevidamente como a coorte de 24/07.
- **Recommendation:** usar junho apenas como baseline histórico complementar.
- **Decision:** aprovado pelo stakeholder usar o baseline de junho (D-001).
- **Why:** ele amplia a observação de padrões sem mascarar a ausência da coorte do teste de julho.
- **Accepted trade-offs:** a análise pode caracterizar padrões históricos e conflitos com as diretrizes, mas não estimar prevalência ou impacto atual.
- **Evidence IDs:** E-009, E-010, E-011, D-001.
- **Reversibility:** reversível; o baseline pode ser substituído ou complementado quando o export de julho for recuperado.
- **Affected artifacts:** evidence-ledger.md, problem-exploration.md, human-gate-decision-cohort.md.
- **Status:** approved.
- **Owner approval ref:** input explícito do stakeholder em 2026-09-30: "pode usar o de junho tbm, nao tem problema".

## Checkpoint posterior — continuidade com traces disponíveis

- **Date:** 2026-09-30
- **Decision:** o stakeholder autorizou continuar o upstream com os traces disponíveis e encerrar a busca adicional em logs (D-002).
- **Scope:** a autorização aceita o uso qualitativo do baseline de junho e da amostra recente; não aceita inferência de prevalência, satisfação ou impacto atual.
- **Impact:** a lacuna de prevalência deixa de bloquear a formulação do Problem, mas permanece como limitação para métricas de outcome da solução.
