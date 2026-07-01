---
marp: true
theme: default
paginate: true
backgroundColor: #00000a
color: #ffffff
html: true
---

<style>
/* Global */
section { color: #ffffff; }

/* Títulos */
h1 { color: #e0d0ff; }
h2, h3 { color: #c8b8ff; }

/* Tabelas */
table { border-collapse: collapse; width: 100%; }
th { background-color: #1a1a3a; color: #b090ff; border: 1px solid #333366; }
td { color: #1a1a2e; border: 1px solid #ccccdd; }
tr:nth-child(even) td { background-color: #f0f0f8; }

/* Blockquotes */
blockquote {
  border-left: 4px solid #7755cc;
  color: #aaaacc;
  background-color: #0d0d1f;
  padding: 10px 16px;
  margin: 16px 0;
}

/* Paginação */
section::after { color: #444466; }

/* Listas */
ul li, ol li { color: #e8e8ff; }

/* Negrito */
strong { color: #d0b8ff; }

/* Cover — logo grande posicionado à direita */
.logo-right {
  position: absolute;
  right: 40px;
  top: 50%;
  transform: translateY(-50%);
  text-align: right;
  width: 480px;
}

/* Mini-logo nos slides internos */
.mini-logo {
  position: absolute;
  top: 8px;
  right: 8px;
  width: 155px;
  text-align: right;
}

.mini-logo p { margin: 0; line-height: 1; }

.mini-logo span {
  color: #ffffff;
  font-size: 12px;
  letter-spacing: 2px;
  display: block;
}
</style>

<!-- _header: "" -->

<div class="logo-right">

![w:460](images/nebula-forge-logo.png)

<span style="font-size: 52px; letter-spacing: 3px; display: block; margin-top: 6px; margin-right: 15px;">QA🔬</span>

</div>

<p style="font-size: 16px; margin: 160px 0 12px 0; letter-spacing: 1px;">Revisão de Qualidade & Plano de Ação</p>

# Nebula Drift v1.2.3

<p style="font-size: 15px; margin: 0;">Lucas Jacques — QA Lead</p>

<p style="font-size: 13px; color: #666688; margin: 6px 0 0 0;">P1–P7 fazem referência às perguntas do desafio técnico</p>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# O cenário em números *(P1)*

<div style="display:flex; align-items:center; justify-content:center; gap:60px; margin-top:10px;">

<div style="text-align:center;">

<svg width="170" height="170" viewBox="0 0 180 180">
  <circle cx="90" cy="90" r="70" fill="none" stroke="#4a4a7a" stroke-width="24" />
  <circle cx="90" cy="90" r="70" fill="none" stroke="#ff5577" stroke-width="24"
    stroke-dasharray="141.4 439.8" stroke-linecap="round"
    transform="rotate(-90 90 90)" />
  <text x="90" y="84" text-anchor="middle" font-size="32" font-weight="bold" fill="#ffffff">9</text>
  <text x="90" y="106" text-anchor="middle" font-size="12" fill="#aaaacc">de 28 (32%)</text>
</svg>

<p style="font-size:13px; margin:8px 0 0 0; text-align:left; display:inline-block;">
<span style="color:#4a4a7a;">●</span> 28 críticos após freeze<br>
<span style="color:#ff5577;">●</span> 9 escaparam para produção
</p>

</div>

<div style="display:flex; flex-direction:column; gap:14px;">

<div style="border-left:6px solid #ffcc55; padding:6px 16px; background:#12122a;">
<span style="font-size:26px; font-weight:bold; color:#ffcc55;">40%</span><br>
<span style="font-size:13px;">dos bugs detectados próximo ao release</span>
</div>

<div style="border-left:6px solid #55ccff; padding:6px 16px; background:#12122a;">
<span style="font-size:26px; font-weight:bold; color:#55ccff;">3 dias</span><br>
<span style="font-size:13px;">tempo médio de correção</span>
</div>

</div>

</div>

<br>

> O time está testando tarde demais, sem cobertura estruturada.

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# O que precisa mudar *(P1)*

1. **Ausência de suíte de regressão** — sem baseline, não há como detectar sistematicamente o que quebrou entre builds
2. **Detecção tardia** — 40% dos bugs encontrados próximo ao release; 28 críticos identificados somente após freeze
3. **Alta taxa de escape** — 9 de 28 bugs críticos (≈32%) chegaram aos jogadores

<span style="color:red">**[RASCUNHO — considerar ícones ou imagem de "bug reaching players"]**</span>

---

<!-- _class: lead -->

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# 🚨 Bug crítico na v1.2.3
### Decisão imediata necessária *(P7)*

1 bug crítico · afeta 20% dos jogadores · correção: 2 dias · release: amanhã

<span style="color:red">**[RASCUNHO — considerar visual de semáforo vermelho ou "game over" como fundo]**</span>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# 🚨 Bug crítico: como estamos respondendo *(P7)*

**Decisão: adiar o release 2 dias para corrigir. *(Opção A)*.**

- 20% dos jogadores afetados = impacto direto em retenção
- 2 dias de atraso é controlado e justificável frente ao risco de churn
- Lançar com bug crítico conhecido contradiz nosso compromisso com o jogador

**Opções consideradas e apresentadas ao PO e Dev Lead:**

| | |
|---|---|
| ✅ **Opção A** *(escolhida)* | Adiar 2 dias, corrigir e revalidar |
| ⚠️ **Opção B** | Lançar com workaround documentado, se existir |
| 🧪 **Opção C** | Soft launch para fatia menor da base, se a infra suportar |

> Este tipo de escape é exatamente o que o nosso plano a seguir vai endereçar.

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Como vamos testar *(P2)*

| Tipo | Quando | Foco |
|---|---|---|
| 🔥 **Smoke** | Após cada build semanal | Fluxos críticos: pagamento, progressão (~30 min) |
| 🔁 **Regressão** | Antes do freeze trimestral | Funcionalidades já validadas + os 9 escapes mapeados |
| 🔍 **Exploratório** | Durante o sprint | Áreas alteradas e de maior risco, sem script rígido |

<br>

**O que NÃO testar agora:** textos de NPC · arte cosmética · tutoriais opcionais · edge cases de hardware raros

<span style="color:red">**[RASCUNHO — considerar imagem de gameplay como fundo ou ícones de games]**</span>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Antecipando bugs: novo fluxo *(P3)*

**De:** tudo testado no final → **Para:** validação distribuída na sprint

<br>

- 🗓️ **Início da sprint** — QA no refinamento, revisando critérios de aceite
- 💻 **Durante o desenvolvimento** — QA testa features conforme ficam prontas
- 🏗️ **Build semanal** — smoke obrigatório; falhou = não avança
- 🔒 **Pré-freeze** — regressão com devs ainda disponíveis para corrigir

<br>

> Meta: reduzir os 40% de bugs tardios antecipando a detecção para quando o custo de correção ainda é baixo

<span style="color:red">**[RASCUNHO — candidato a virar uma linha do tempo visual horizontal]**</span>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# QA no ciclo de produção *(P4)*

| Fase | Responsabilidade |
|---|---|
| 📋 Refinamento | Revisar critérios de aceite, levantar edge cases |
| 💻 Desenvolvimento | Testar features conforme prontas na branch |
| 🏗️ Build semanal | Smoke test — build que falha não avança |
| ⚠️ Pré-freeze | Regressão completa |
| 🔒 Freeze | Exploratório focado em risco |
| 🚀 Pós-release | Monitorar reports; validar hotfixes |

<span style="color:red">**[RASCUNHO — candidato a virar linha do tempo com fases do ciclo de desenvolvimento de um game]**</span>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Como vamos trabalhar *(P5)*

**Maria e José — execução:**
- Smoke tests semanais (após alinhamento inicial sobre critérios)
- Regressão em áreas estáveis e já mapeadas
- Reporte de bugs com template padronizado

**QA Lead — revisão e suporte:**
- Definir e priorizar o plano de testes a cada sprint
- Pair testing nas áreas críticas (pagamento, progressão)
- Interface com o time de desenvolvimento
- Sempre disponível para dúvidas — vocês não estão sozinhos nesse processo

<span style="color:red">**[RASCUNHO — considerar visual com dois "lados" ou organograma simples]**</span>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Desenvolvendo o time *(P6)*

| Semanas | Iniciativa |
|---|---|
| **1–2** | Diagnóstico: entender nível e lacunas de cada um no trabalho real |
| **3–4** | Pair testing nas áreas críticas — decisões discutidas em tempo real |
| **5–6** | Maria e José lideram o plano de testes de uma feature *(com revisão do Lead)* |
| **7–8** | Retrospectiva: o que melhorou, próximos objetivos |

<br>

**Métrica de sucesso:** redução de bugs encontrados no pré-freeze que deveriam ter sido capturados durante a sprint

<span style="color:red">**[RASCUNHO — considerar visual de progressão / level up como referência de games]**</span>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Plano de ação: próximas 2 semanas *(P1)*

1. **Regressão mínima baseada nos escapes** — mapear os 9 bugs que chegaram à produção, transformá-los em casos de teste e executar nas próximas builds semanais
2. **Shift-left no processo de sprint** — QA revisa critérios de aceite no início de cada sprint, antes do desenvolvimento começar
3. **Definition of done** — smoke pass + regressão mínima aprovada antes do freeze

<br>

> Pequenas mudanças, aplicadas de forma consistente, são o que vai transformar os números desta versão nas próximas.

<span style="color:red">**[RASCUNHO — considerar visual de roadmap ou checklist das 2 semanas]**</span>
