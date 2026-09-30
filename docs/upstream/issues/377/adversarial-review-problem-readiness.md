# Revisão adversarial — readiness de Problem

- **Revisor:** agente Codex independente, somente leitura, em 2026-09-30.
- **Artefatos revisados:** evidence-ledger.md, problem-exploration.md, technical-current-state.md, decision-use-june-baseline.md e human-gate-decision-cohort.md.
- **Veredito:** fail para `Problem = Ready`.

## Gates

- **Problem Definition:** reprovado no framing anterior porque ele misturava identidade/tom, contexto/memória, catálogo e privacidade.
- **Problem Knowledge:** reprovado porque os traces não medem prevalência atual e havia contradição não resolvida na identidade.
- **Solution:** não avaliada; permanece independente.

## Achados relevantes

1. D-002 autoriza continuidade qualitativa, não resolve prevalência ou causalidade.
2. O guia de Marketing está em `draft-for-brand-core-review`.
3. Ética exige transparência e não antropomorfização, mas o exemplo de abertura usa “Sou o Zé, assistente virtual”, em conflito com E-002.
4. O framing anterior fazia inferências de confiança/risco e agregava falhas operacionais fora do escopo de tom.

## Encaminhamento aplicado

O framing foi decomposto em `problem-framing.md`. A definição da dimensão em escopo é agora concreta, mas U-004 bloqueia Knowledge e qualquer transição para Ready.

## Checagem após D-003

- **Veredito:** `Problem Definition = pass`; `Problem Knowledge = fail`.
- **Razão:** D-003 resolve a precedência de identidade para a iniciativa. Entretanto, U-003 permanece: os traces não permitem estimar prevalência, jornada dominante, severidade, satisfação ou impacto atual.
- **Evidência adicional:** E-014 conecta uma sessão recente `env:prod` ao commit analisado e à abertura “Zé no Zap”, mas tem escopo de uma sessão.
- **Recomendação:** manter `Problem = Investigate` até o stakeholder aceitar explicitamente U-003 como risco para uma correção mandatória de conformidade, com métricas de aderência em vez de métricas de impacto.

### Condição satisfeita

O stakeholder aceitou U-003 nos termos recomendados (D-004). O veredito condicional permite a transição para `Problem = Ready`; a limitação permanece obrigatória nos critérios e na leitura de resultados.
