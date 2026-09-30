# Git/GitHub workflow do upstream

GitHub Issue é a superfície visível e o estado operacional do processo.

## Issue-first timeline

Cada iniciativa upstream não trivial começa ou é vinculada a **uma única Issue
canônica** no repositório de upstream. O corpo preserva o snapshot de intake;
a timeline de comentários é o registro cronológico de trabalho.

Registre como comentário, no momento em que ocorrer:

- sinal/intake e vínculo à origem;
- evidência relevante e suas limitações;
- decisões, recomendações e human gates;
- revisão adversarial e seu veredito;
- transições de `problem:*` e `solution:*`;
- aceite de risco, bloqueio, validação, readiness e handoff.

Documentos locais sintetizam e detalham o trabalho, mas não substituem a
timeline. Branch, commit e PR podem versionar esses documentos, porém não são
tracking de upstream: todo avanço material precisa aparecer também em comentário
na Issue. Não apague ou reescreva o sinal original para refletir conclusões
posteriores.

## Labels

Execução: use `state:*` do repositório.

Problem — exatamente um:
- `problem:explore`
- `problem:frame`
- `problem:investigate`
- `problem:ready`

Solution — exatamente um:
- `solution:explore`
- `solution:shape`
- `solution:validate`
- `solution:deliver`

Tipos sugeridos:
- `type:investigation`
- `type:framing`
- `type:design`
- `type:experiment`
- `type:decision`
- `epic`

## Transição

Toda troca `problem:*` ou `solution:*` recebe comentário usando
`templates/state-transition-comment.md`.

Além da transição, mantenha labels de tipo e `state:in-progress` compatíveis com
o estado da Issue. Se a iniciativa vier de outro repositório, a Issue upstream
deve linkar a Issue de origem e vice-versa; a Issue upstream é a timeline
canônica do processo.

## Milestone

Milestone upstream é PRD curto: objective, starting hypothesis, outcomes,
entry state, critical unknowns, scope/out-of-scope, gates e exit criteria.
Fecha pelo critério, não pela contagem de issues.

## Epic/subissues

Iniciativa grande vira epic; decisões globais ficam na mãe; subissues reduzem
gaps independentes; achado fora de escopo vira follow-up com origem.

## Handoff

`problem:ready + solution:deliver + readiness approved` gera delivery tracking.
A partir daí segue o workflow de implementação do repositório.
