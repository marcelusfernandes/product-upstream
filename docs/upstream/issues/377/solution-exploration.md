# Solution exploration — Issue 377

## Objetivo da intervenção

Aplicar de maneira consistente a identidade **assistente de compras com IA do Zé Delivery**, sem o assistente se identificar como o próprio Zé, e estabelecer limites de tom verificáveis. A intervenção não deve se apresentar como solução para falhas de memória, catálogo, carrinho ou PII (problem-framing.md).

## Constraints

- D-003 prevalece sobre o exemplo antigo de Ética.
- Transparência sobre IA deve ser clara ao longo da interação; não basta uma abertura isolada (E-005).
- Segurança, consumo responsável, privacidade e fatos confirmados precedem tom/humor (E-004, E-005).
- Não alegar impacto quantitativo; o sucesso inicial é aderência verificável (D-004).
- As superfícies atuais são distribuídas: coordinator, persona/security prompt, small_talk, agente ReAct e guardrails (E-007, E-014).

## Alternativas

| Opção | Mecanismo | Por que ataca / não ataca o problema | Trade-offs | Reversibilidade |
|---|---|---|---|---|
| A. Troca pontual de cópia | Alterar apenas a mensagem inicial. | Corrige a primeira apresentação, mas não impede autorreferência como “Zé” em prompts, small talk ou recuperação de guardrail. Não atende transparência contínua. | Rápida, porém alta chance de inconsistência. | Alta. |
| B. Contrato de identidade transversal | Definir uma política canônica de identidade/tom e aplicá-la às superfícies de abertura, geração e recuperação; criar critérios de avaliação por jornada. | Ataca a origem da inconsistência distribuída e torna D-003 verificável. | Exige mapeamento de superfícies e testes/avaliações; não resolve problemas operacionais adjacentes. | Média-alta, com rollout controlado. |
| C. Reescrita final obrigatória | Inserir uma camada pós-geração que reescreva autorreferências e tom antes do envio. | Pode conter parte dos desvios, mas recebe pouco contexto e pode degradar clareza, ferramentas ou respostas de segurança. Não governa a abertura determinística. | Menor alteração nos prompts; maior risco de efeitos colaterais e custo/latência. | Média. |
| D. Apenas disclosure de canal | Exibir identificação de IA na abertura/UI e manter a persona existente. | Ajuda na transparência inicial, mas preserva a personificação como “Zé” e conflitos nas jornadas seguintes. | Simples; insuficiente para D-003. | Alta. |

## Alternativas descartadas nesta fase

- **A e D isoladas:** não cobrem as superfícies em que o comportamento atual se distribui (E-007).
- **C como mecanismo principal:** desloca a política para uma transformação tardia, com risco de modificar respostas de segurança ou contexto; pode ser avaliada como fallback posterior, não como fonte de verdade.

## Direção recomendada para shape

**B — contrato de identidade transversal**, com uma fonte de verdade de política e critérios de conformidade por jornada. A decisão de adotá-la ainda não foi tomada; a próxima etapa precisa detalhar mecanismo, estados, regras, fallbacks e avaliações sem implementar produto.

## Estado da Solution

| Definition | Knowledge | Estado | Evidências |
|---|---|---|---|
| vague | unknown | Explore | E-004, E-005, E-007, E-014, D-003, D-004 |

## Assumptions críticas a validar se B for escolhida

1. Uma política compartilhada alcança todas as superfícies que podem autorreferenciar o assistente.
2. A transparência contínua pode ser mantida sem repetição intrusiva em cada turno.
3. Os critérios de conformidade podem ser automatizados nos evals existentes sem degradar segurança, factualidade ou latência.
4. Brand Core, Ética e Jurídico aprovarão a redação e os limites operacionais derivados de D-003.
