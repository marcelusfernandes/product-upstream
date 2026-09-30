# Revisão adversarial — shape da Solution

- **Revisor:** agente Codex independente, somente leitura, em 2026-09-30.
- **Veredito inicial:** fail para `Solution = Validate`.

## Lacunas encontradas

1. O contrato não definia owner, formato conceitual, precedência, enforcement ou fail-safe.
2. Estados de falha para injection, gray zone, moderador/template, tool failure, PII, sessão e renderizadores determinísticos não estavam definidos.
3. Transparência contínua não tinha gatilhos operacionais.
4. Avaliações não tinham cobertura, thresholds, tratamento de falso positivo/negativo, regressão ou limite de latência.
5. Assumptions tinham método, mas não protocolo de validação.

## Encaminhamento aplicado

`solution-shape.md` foi expandido para explicitar essas lacunas. Uma nova revisão adversarial é necessária antes da transição para `Solution = Validate`.

## Reavaliação após expansão

- **Veredito:** pass para `Solution: Explore → Validate`.
- **Gates satisfeitos:** mecanismo, owner conceitual, formato de contrato, precedência, enforcement, falhas, transparência, avaliações, observabilidade, fronteiras e protocolos de validação.
- **Sem bloqueio para Validate:** o formato executável e os adaptadores são decisões de delivery; as aprovações cross-functional e nomeação formal de owner são gates de handoff/release.
- **Limites:** Solution Knowledge continua unknown até execução do protocolo; não declarar release antes de `approval_refs`, não regressão, inventário de cobertura e piloto controlado passarem.
