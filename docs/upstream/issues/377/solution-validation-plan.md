# Plano de validação — contrato transversal de identidade

## Objetivo

Resolver as assumptions críticas de `solution-shape.md` sem implementar produto no upstream. Evidência de ambiente, piloto ou aprovação deve ser adicionada pelo responsável apropriado; este plano define o protocolo e os critérios de decisão.

**Autorização atual:** validação interna aprovada por D-007. Piloto controlado com pessoas usuárias não está autorizado nesta fase.

| ID | Assumption | Evidência exigida | Pass | Falha / próximo passo | Owner proposto |
|---|---|---|---|---|---|
| V-001 | O contrato alcança todas as superfícies. | Inventário assinado que mapeie cada origem de resposta ao contrato ou fallback; teste de cobertura por superfície. | 100% das superfícies da tabela de enforcement mapeadas e cobertas. | Superfície sem adaptador/teste: retornar a shape/delivery. | Engenharia + Conversational AI. |
| V-002 | Transparência é compreensível sem repetição indevida. | Revisão humana estruturada de sessões nova, retomada, dúvida de identidade, small talk, commerce e fallback. | Brand Core, Ética e Jurídico aprovam disclosure, gatilhos e fallback sem ambiguidade de personificação. | Divergência de redação ou confusão: voltar a shape. | Brand Core + Ética + Jurídico. |
| V-003 | Não há regressão de segurança, factualidade, PII ou latência. | Execução da matriz determinística, suites de regressão existentes e piloto controlado com métricas agregadas. | Hard invariants 100%; sem regressão crítica; nenhuma chamada LLM nova; p95 até 5% pior que baseline. | Qualquer falha crítica ou p95 acima do limite: bloquear rollout e investigar. | Engenharia + Ops. |
| V-004 | A governança aprova a versão. | `approval_refs`, owner formal e versão de contrato aprovada. | Todas as referências e owner constam antes de release. | Ausência de aprovação: permitido só ambiente interno. | Produto/Conversational AI (owner D-006); Brand Core, Ética e Jurídico (aprovação). |

## Artefatos esperados

1. Matriz de conformidade versionada, sem conteúdo de conversas reais.
2. Inventário de superfícies com adaptador/fallback e cobertura.
3. Parecer de Brand Core, Ética e Jurídico sobre disclosure/fallback.
4. Resultado agregado de regressão e piloto com versão do contrato.
5. Registro de owner e `approval_refs`.

## Regra de saída

`Solution = Deliver` só é elegível quando V-001 a V-004 estiverem `supported` ou houver risco explicitamente aceito pelo stakeholder responsável. Ausência de dado não é aprovação.
