# Evidence ledger — novo ciclo da Issue 377

Este ledger foi criado após o reset de 2026-10-01. Ele não reutiliza decisões,
conclusões, cópias, soluções ou gates do ciclo anterior.

## Pergunta de evidência atual

Quais regras aplicáveis ajudam a distinguir comportamentos observados nos
traces de preferências editoriais, sem inferir aprovação final ou solução?

## E-TR-001 a E-TR-004 — Contexto observacional

Os quatro registros de traces estão preservados em `traces-context.md` e são
parte deste ledger. Eles informam candidatos de problema, com limitações de
amostra, janela e transcript explicitadas naquele arquivo.

## E-005 — Guia de Marketing

```yaml
id: E-005
claim: "O guia de Marketing posiciona o canal como assistente de compras e ordena segurança, consumo responsável, privacidade e políticas; fatos confirmados; clareza; e somente depois tom e humor. Ele orienta não presumir bebida, pessoas, orçamento ou evento em pedidos de ocasião."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/docs/upstream/issue-377-melhoria-tom-de-voz/guias-mkt/guia-mestre-content-whatsapp-ze-delivery.md"
  retrieved_at: "2026-10-01"
scope:
  population: "Respostas do assistente de compras do Zé Delivery no WhatsApp"
  time_window: "Documento atualizado em 2026-09-29"
freshness: current
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "O arquivo está marcado como draft-for-brand-core-review; não é evidência de aprovação final de Brand Core."
  - "É uma diretriz normativa e não mede incidência, severidade ou impacto dos comportamentos atuais."
```

## E-006 — Recomendações de Ética Digital

```yaml
id: E-006
claim: "As recomendações de Ética Digital exigem que o caráter automatizado permaneça claro durante a interação e que sejam evitados elementos de antropomorfização que induzam a pessoa a acreditar que fala com um humano. Também vedam urgência artificial, pressão de compra e personalização persuasiva de bebidas alcoólicas baseada em vulnerabilidades ou histórico individual."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/docs/upstream/issue-377-melhoria-tom-de-voz/guias-juridico/recomendacoes-etica-digital.md"
  retrieved_at: "2026-10-01"
scope:
  population: "Interações do Zé no Zap antes de disponibilização pública"
  time_window: "Não especificada no documento"
freshness: unknown
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "O documento condiciona a disponibilização pública à implementação das mitigações; não comprova que elas existam hoje."
  - "A abertura sugerida no próprio documento usa 'Sou o Zé, assistente virtual', o que exige reconciliação com qualquer regra de identidade antes de virar comportamento de produto."
```

## E-007 — Restrição de escopo do stakeholder

```yaml
id: E-007
claim: "Para esta iniciativa, o assistente deve se apresentar como 'assistente de compras com IA do Zé Delivery' e não como o próprio Zé."
kind: fact
source:
  type: interview
  uri: "Instrução explícita do stakeholder no intake desta iniciativa"
  retrieved_at: "2026-09-30"
scope:
  population: "Interações em que o assistente se apresenta ou é percebido como a identidade do produto"
  time_window: "Vigente para este ciclo, salvo nova orientação explícita do stakeholder"
freshness: current
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "É uma restrição de escopo comunicada pelo stakeholder; não substitui aprovação formal de Brand Core, Ética ou Jurídico."
  - "Não define por si só gatilhos, redação completa, exceções ou critérios de release."
```

## E-008 — Estado técnico observado

```yaml
id: E-008
claim: "No commit 85c6f036e8829060a2ff1eadd66be633942562c1, a abertura de sessão emitida diretamente diz 'você chegou no Zé no Zap' e lista cerveja e destilado; os prompts de agente, guardrails e moderator também definem a persona como 'Você é o Zé'."
kind: fact
source:
  type: repository
  uri: "/Users/bruno.segantin/orca/workspaces/ze-consumer-whatsapp-orchestrator-app/melhoria-tom-de-voz/src/{coordinator/message_coordinator.py,orchestration/prompts/{agent.py,guardrails.py,moderator.py}}"
  retrieved_at: "2026-10-01"
scope:
  population: "Aberturas de sessão e respostas geradas pelos caminhos que consomem essas constantes/prompts na revisão de código observada"
  time_window: "Estado do worktree no momento da leitura"
freshness: unknown
relationship: supports
criticality: critical
status: evidenced
limitations:
  - "A leitura prova o comportamento definido neste commit, não que ele esteja em produção nem a frequência de cada caminho."
  - "Uma instrução interna de prompt pode afetar a saída, mas não prova isoladamente a redação de cada mensagem gerada."
```

## Contradição e unknowns vigentes

- **U-001:** como operacionalizar a transparência de E-006 junto à restrição de
  identidade E-007 em apresentação e retomadas. O exemplo de abertura de
  E-006 não prevalece sobre a restrição de escopo e requer reconciliação formal
  para aprovação/release.
- **U-002:** quais padrões dos traces continuam ativos, em quais jornadas e com
  qual frequência, severidade ou impacto.
- **U-003:** se P-01 a P-04 da exploração descrevem problemas separados,
  sintomas de um mesmo problema ou casos fora de escopo.
- **U-004:** qual revisão está efetivamente em produção e quais superfícies de
  identidade alcançam pessoas usuárias em cada jornada.

## O que este ledger não permite concluir

- Que o guia de Marketing foi aprovado de forma final.
- Que qualquer frase sugerida pelos documentos deve ser implementada.
- Que a amostra de traces é representativa ou que uma regra normativa é a causa
  de uma reação de pessoa usuária.
