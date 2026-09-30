## Decision record — mecanismo de contrato transversal

- **Date:** 2026-09-30
- **Origin:** exploração de solução da Issue 377.
- **Question:** qual mecanismo impede a identidade definida por D-003 de divergir entre as superfícies do assistente?
- **Context:** a identidade está distribuída entre abertura, persona/prompt, small talk, agente ReAct e recuperação de guardrails (E-007). Trocas pontuais não cobrem todas essas superfícies.
- **Options:** troca pontual de cópia; contrato transversal; reescrita final obrigatória; disclosure apenas na abertura/UI.
- **Recommendation:** contrato transversal de identidade.
- **Decision:** aprovado pelo stakeholder (D-005).
- **Why:** ele cria uma fonte de verdade e critérios verificáveis para todas as superfícies, sem assumir que uma mudança de texto resolve problemas operacionais adjacentes.
- **Accepted trade-offs:** maior escopo de mapeamento e avaliação; redação final e aprovações cross-functional continuam pendentes.
- **Evidence IDs:** E-004, E-005, E-007, E-014, D-003, D-004, D-005.
- **Reversibility:** o contrato e suas regras podem evoluir por versão; não deve haver mudança de redação sem nova aprovação.
- **Affected artifacts:** prompts, coordinator, guardrails de recuperação, avaliações e guias aprovados.
- **Status:** approved for solution shape.
- **Owner approval ref:** input explícito do stakeholder em 2026-09-30: “pode seguir com a opcao 2”.
