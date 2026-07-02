# Desafio Técnico QA Lead - Lucas Jacques

## 1. Quais são os 3 principais problemas de qualidade com base nos dados? O que você priorizaria nas próximas 2 semanas? (máx. 3 ações)

**Problemas identificados:**

- **Ausência de suíte de regressão** — sem baseline estruturada, não há como detectar sistematicamente o que quebrou entre builds
- **Detecção tardia** — 40% dos bugs encontrados próximo ao release; 28 críticos identificados somente após freeze
- **Alta taxa de escape para produção** — 9 de 28 bugs críticos (≈32%) chegaram aos jogadores; com tempo médio de correção de 3 dias, isso equivale a ≈27 dias-bug de exposição crítica acumulada em produção (9 × 3 dias) — custo alto em reputação e esforço reativo

**3 ações prioritárias (próximas 2 semanas):**

1. **Montar uma regressão mínima baseada nos escapes** — mapear os 9 bugs que chegaram à produção, transformá-los em casos de teste e executar nas próximas builds semanais; esforço baixo, retorno imediato
2. **Shift-left no processo de sprint** — envolver o QA na revisão dos critérios de aceite no início de cada sprint, antes do desenvolvimento começar; não impacta velocidade dos devs e antecipa a discussão de riscos
3. **Definir critério mínimo de qualidade antes do freeze** — estabelecer um "definition of done" simples: smoke pass + regressão mínima aprovada; torna o freeze mais previsível e reduz surpresas de última hora

## 2. Como você estruturaria Smoke test, regressão e testes exploratórios? O que você NÃO testaria agora?

- **Smoke test** — executado após cada build semanal; cobre os fluxos mínimos críticos (autenticação, compra com moeda real, compra com moeda do jogo, progressão de personagem); objetivo: confirmar que o build está estável o suficiente para continuar testando; duração ~30 min
- **Regressão** — executada antes do freeze trimestral; garante que funcionalidades que já funcionavam continuam funcionando, incluindo as críticas; inicialmente montada a partir dos 9 bugs que escaparam para produção + fluxos principais já mapeados; cresce incrementalmente a cada sprint
- **Exploratório** — realizado durante o sprint, sem script rígido, focado nas áreas alteradas ou de maior risco da entrega atual; aproveita o conhecimento de domínio do QA para encontrar comportamentos inesperados que casos de teste formais não cobririam

**O que NÃO testaria agora:**

- Conteúdo estático: textos de NPC, localização, arte e UI cosmética
- Edge cases de configurações de hardware com menos de 1% de base de jogadores
- Fluxos secundários sem alteração recente: customização de avatar, tutoriais opcionais, menus de configuração

## 3. Considerando que os bugs são encontrados tardiamente, qual mudança você faria no fluxo para antecipar bugs?

A mudança central é distribuir a validação ao longo de toda a sprint, em vez de concentrá-la no final:

- **Início da sprint**: QA participa do refinamento para revisar critérios de aceite e identificar riscos antes do desenvolvimento começar — bugs teóricos custam zero para corrigir
- **Durante o desenvolvimento**: QA testa features individualmente assim que ficam prontas, sem esperar o build consolidado semanal
- **Build semanal**: smoke obrigatório; build que falha smoke não avança para validação
- **Pré-freeze**: regressão com devs ainda disponíveis para correção

Resultado esperado: reduzir a concentração de 40% de bugs encontrados próximo ao release, antecipando a detecção para quando o custo de correção ainda é baixo.

## 4. Onde você alocaria o QA no ciclo de produção do jogo? Quais os momentos e responsabilidades?

QA presente em todas as fases, com responsabilidades distintas em cada uma:

| Fase                     | Responsabilidade do QA                                                                        |
| ------------------------ | --------------------------------------------------------------------------------------------- |
| Refinamento / design     | Revisar critérios de aceite, levantar edge cases, identificar riscos antes do desenvolvimento |
| Desenvolvimento (sprint) | Testar features conforme ficam prontas na branch; não acumular para o final                   |
| Build semanal            | Executar smoke test; build que falha não avança                                               |
| Pré-freeze               | Executar regressão completa com devs disponíveis para correção                                |
| Freeze                   | Testes exploratórios focados em risco; sem novas features entrando                            |
| Pós-release              | Monitorar reports de jogadores; validar hotfixes de forma ágil                                |

## 5. Considerando a estrutura do time, o que você delegaria e o que você faria?

**Delegaria aos 2 QAs juniores:**

- Execução dos smoke tests semanais (após alinhamento inicial sobre critérios)
- Execução da regressão em áreas estáveis e já mapeadas
- Reporte de bugs seguindo template padronizado

**Faria como QA Lead:**

- Definir e priorizar o plano de testes a cada sprint
- Construir e evoluir a suíte de regressão
- Pair testing com os juniores nas áreas críticas (pagamento, progressão)
- Ser o ponto de comunicação entre QA e time de desenvolvimento
- Participar do refinamento para revisar critérios de aceite

## 6. Que iniciativa você proporia para elevar o nível do time de QA ao longo do próximo ciclo de 8 semanas?

Programa de desenvolvimento integrado ao ritmo da sprint — sem criar carga extra fora do trabalho real:

| Semanas | Iniciativa |
|---|---|
| 1–2 | Diagnóstico individual: entender o nível e as lacunas de cada QA júnior através do trabalho do dia a dia |
| 3–4 | Pair testing nas áreas críticas comigo; discutir decisões em tempo real ("por que esse caso entra na regressão e não no smoke?") |
| 5–6 | Júniores assumem o planejamento de testes de uma feature com minha revisão; desenvolver ownership |
| 7–8 | Retrospectiva de qualidade: o que melhorou, o que ainda falha, definir próximos objetivos |

**Métrica de sucesso:** redução de bugs encontrados na fase de pré-freeze que deveriam ter sido capturados durante a sprint.

## 7. Durante freeze do release trimestral foi encontrado:

- 1 bug crítico encontrado
- Afeta 20% dos jogadores
- Correção: 2 dias
- Release planejado para amanhã

## a) Você bloquearia o release? Como comunica sua decisão (seja ela de bloquear ou não o release)?

**Decisão: bloquear.**

Justificativa baseada em dados:
- 20% dos jogadores afetados é impacto direto em retenção — 1 a cada 5 jogadores encontraria o problema
- Correção estimada em 2 dias: o atraso é controlado e justificável frente ao risco de churn
- Lançar com bug crítico conhecido contradiz o compromisso com experiência do jogador que a empresa assumiu

**Como comunicar:**

Comunicar imediatamente ao Product Owner e Dev Lead com impacto quantificado e opções claras:

- **Opção A (recomendada):** adiar o release 2 dias, corrigir e revalidar
- **Opção B:** lançar com workaround documentado e comunicado aos jogadores, se existir
- **Opção C:** lançar para uma fatia menor da base (soft launch) enquanto a correção é concluída, se a infraestrutura suportar

Registrar a decisão formalmente no canal do time e no ticket do bug. Após aprovação do bloqueio: acompanhar a correção, reexecutar o smoke na área afetada e confirmar o novo release.
