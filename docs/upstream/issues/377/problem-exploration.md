# Exploração de Problem — novo ciclo da Issue 377

**Modo:** `problem-work / explore`  
**Base:** sinal de intake e E-TR-001 a E-TR-004 em `traces-context.md`

## Fenômenos observados e candidatos de problema

| Candidato | Observação que o origina | O que ainda não se sabe | Não confundir com |
| --- | --- | --- | --- |
| P-01 — Resposta pouco aderente ao contexto | E-TR-001 registra respostas genéricas, personalização inesperada e perda de contexto. | Em qual momento ocorre, para quem, qual a frequência e se resulta de memória, recuperação, interpretação, dados ou cópia. | Um problema comprovado de tom de voz. |
| P-02 — Recomendação antes da intenção explícita | E-TR-001 registra oferta alcoólica antes de intenção explícita. | Se o comportamento ocorre além da amostra, qual regra o governa e qual consequência causa. | Uma regra de segurança já definida ou uma solução de bloqueio. |
| P-03 — Expressão percebida como repetitiva | E-TR-001 registra bordões ou emoji recorrentes. | Se são percebidos como estranhos, em quais jornadas, sua incidência e relação com retorno/correção. | A causa dos demais padrões. |
| P-04 — Identidade e tom desalinhados | O sinal de intake pede refletir a identidade do Zé Delivery e evitar estranheza. | Qual identidade é esperada, qual comportamento atual a contradiz e se os traces mostram esse desvio. | Um requisito ou copy já aprovado. |

## Leitura da população e do contexto

- E-TR-001 descreve um export histórico de inputs de busca, não uma população
  definida de clientes nem uma coorte completa de conversa.
- E-TR-002 mostra que há ao menos três tipos de workflow recentes acessíveis,
  mas quatro turnos de duas sessões não permitem segmentação ou priorização.
- E-TR-003 impede usar a ausência de spans no recorte consultado como prova de
  ausência de tráfego ou de comportamento.

## Hipóteses concorrentes

- H-01: a estranheza mencionada no intake decorre principalmente de expressão
  repetitiva (P-03).
- H-02: ela decorre principalmente de baixa aderência ao contexto (P-01), e o
  tom é apenas seu sintoma perceptível.
- H-03: recomendações antes da intenção (P-02) são o fenômeno mais relevante,
  independentemente do tom.
- H-04: há um desalinhamento de identidade (P-04), mas os traces disponíveis
  não são suficientes para caracterizá-lo.

Nenhuma hipótese foi comprovada. Os candidatos podem coexistir e podem ter
causas diferentes.

## Impacto conhecido e desconhecido

Os traces registram correções, cobranças ou retomadas em torno de alguns
padrões observados. Isso é sinal qualitativo de atrito na amostra; não prova
causalidade, severidade, satisfação, abandono, conversão ou risco em produção.

## Evidência discriminante necessária

Para escolher um candidato como Problem, é necessário um recorte que relacione
o comportamento a uma jornada, intenção e resultado observável. O menor
recorte útil deve conter, para cada caso: jornada/entrada, histórico mínimo
necessário para interpretar contexto, resposta do assistente, resultado ou
correção subsequente, origem e janela.

Em paralelo, P-02 e P-04 exigem recuperar fontes normativas aplicáveis antes
de afirmar que um comportamento é proibido ou que uma identidade é exigida.

## Próximo gap crítico

Definir uma coorte e um método de classificação que permita distinguir P-01 a
P-04 sem usar o dataset de busca como se fosse transcript, nem transformar
ausência de dados em evidência negativa.
