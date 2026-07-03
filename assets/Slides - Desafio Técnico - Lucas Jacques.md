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

<div style="display:flex; align-items:center; gap:12px; margin-top:4px;">

<img src="images/ljacques-profile.png" style="height:56px; width:auto;" />

<p style="font-size: 15px; margin: 0;">Lucas Jacques — QA Lead</p>

</div>

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

<div style="display:flex; align-items:center; gap:40px; margin-top:14px;">

<svg width="150" height="140" viewBox="0 0 220 140" style="flex-shrink:0;">
  <defs>
    <marker id="arrowhead" markerWidth="8" markerHeight="8" refX="6" refY="3" orient="auto">
      <path d="M0,0 L6,3 L0,6 Z" fill="#aaaacc" />
    </marker>
  </defs>
  <line x1="22" y1="45" x2="10" y2="33" stroke="#ff5577" stroke-width="3" stroke-linecap="round"/>
  <line x1="58" y1="45" x2="70" y2="33" stroke="#ff5577" stroke-width="3" stroke-linecap="round"/>
  <line x1="18" y1="60" x2="2" y2="55" stroke="#ff5577" stroke-width="3" stroke-linecap="round"/>
  <line x1="18" y1="72" x2="2" y2="72" stroke="#ff5577" stroke-width="3" stroke-linecap="round"/>
  <line x1="18" y1="84" x2="2" y2="89" stroke="#ff5577" stroke-width="3" stroke-linecap="round"/>
  <line x1="62" y1="60" x2="78" y2="55" stroke="#ff5577" stroke-width="3" stroke-linecap="round"/>
  <line x1="62" y1="72" x2="78" y2="72" stroke="#ff5577" stroke-width="3" stroke-linecap="round"/>
  <line x1="62" y1="84" x2="78" y2="89" stroke="#ff5577" stroke-width="3" stroke-linecap="round"/>
  <ellipse cx="40" cy="75" rx="22" ry="30" fill="#ff5577" opacity="0.9"/>
  <line x1="40" y1="52" x2="40" y2="98" stroke="#aa2244" stroke-width="2"/>
  <path d="M95 75 L150 75" stroke="#aaaacc" stroke-width="2.5" stroke-dasharray="5 5" marker-end="url(#arrowhead)"/>
  <rect x="152" y="58" width="60" height="34" rx="16" fill="none" stroke="#55ccff" stroke-width="3"/>
  <line x1="168" y1="70" x2="168" y2="80" stroke="#55ccff" stroke-width="2.5" stroke-linecap="round"/>
  <line x1="163" y1="75" x2="173" y2="75" stroke="#55ccff" stroke-width="2.5" stroke-linecap="round"/>
  <circle cx="192" cy="70" r="3.5" fill="#55ccff"/>
  <circle cx="200" cy="78" r="3.5" fill="#55ccff"/>
  <text x="182" y="118" text-anchor="middle" font-size="12" fill="#aaaacc">jogador</text>
</svg>

<ol style="margin:0; padding-left:22px;">
<li style="margin-bottom:12px;"><strong>Ausência de suíte de regressão</strong><br><span style="font-size:13px; color:#aaaacc;">sem baseline, não há como detectar sistematicamente o que quebrou entre builds</span></li>
<li style="margin-bottom:12px;"><strong>Detecção tardia</strong><br><span style="font-size:13px; color:#aaaacc;">40% dos bugs encontrados próximo ao release; 28 críticos identificados somente após freeze</span></li>
<li><strong>Alta taxa de escape</strong><br><span style="font-size:13px; color:#aaaacc;">9 de 28 bugs críticos (≈32%) chegaram aos jogadores</span></li>
</ol>

</div>

---

<!-- _class: lead -->
<!-- _backgroundColor: #1a0508 -->

<div class="mini-logo">

<img src="images/nebula-forge-logo.png" style="width:150px; filter: hue-rotate(90deg) saturate(0); brightness(0.6); mix-blend-mode: screen;" />

<span>QA🔬</span>

</div>

<div style="display:flex; justify-content:center;">

<svg width="90" height="90" viewBox="0 0 90 90">
  <defs>
    <radialGradient id="alertGlow" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#ff3355" stop-opacity="1"/>
      <stop offset="55%" stop-color="#ff3355" stop-opacity="0.45"/>
      <stop offset="100%" stop-color="#ff3355" stop-opacity="0"/>
    </radialGradient>
  </defs>
  <circle cx="45" cy="45" r="45" fill="url(#alertGlow)"/>
  <circle cx="45" cy="45" r="18" fill="#ff2244"/>
</svg>

</div>

# 🚨 Bug crítico na v1.2.3
### Decisão imediata necessária *(P7)*

<div style="display:flex; justify-content:center; gap:16px; margin-top:36px; flex-wrap:wrap; width:100%;">

<div style="border:1px solid #ff3355; color:#ff8899; padding:8px 22px; border-radius:24px; font-size:18px;">1 bug crítico</div>

<div style="border:1px solid #ff3355; color:#ff8899; padding:8px 22px; border-radius:24px; font-size:18px;">20% dos jogadores</div>

<div style="border:1px solid #ff3355; color:#ff8899; padding:8px 22px; border-radius:24px; font-size:18px;">correção: 2 dias</div>

<div style="border:1px solid #ff3355; color:#ff8899; padding:8px 22px; border-radius:24px; font-size:18px;">release: amanhã</div>

</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# 🚨 Bug crítico: como estamos respondendo *(P7)*

<div style="display:flex; align-items:center; gap:14px; margin-bottom:8px;">

<svg width="40" height="40" viewBox="0 0 48 48">
  <rect x="6" y="6" width="26" height="34" rx="2" fill="#f5f0ff" stroke="#8866cc" stroke-width="2"/>
  <line x1="11" y1="15" x2="27" y2="15" stroke="#6a4fa8" stroke-width="1.5" opacity="0.8"/>
  <line x1="11" y1="21" x2="27" y2="21" stroke="#6a4fa8" stroke-width="1.5" opacity="0.8"/>
  <line x1="11" y1="27" x2="21" y2="27" stroke="#6a4fa8" stroke-width="1.5" opacity="0.8"/>
  <line x1="22" y1="40" x2="40" y2="22" stroke="#ffcc55" stroke-width="4" stroke-linecap="round"/>
  <circle cx="22" cy="40" r="3" fill="#ff8899"/>
  <circle cx="40" cy="22" r="1.6" fill="#2a2a3a"/>
</svg>

<div style="font-size:20px; font-weight:bold; color:#d0b8ff;">Decisão: adiar o release 2 dias para corrigir. <em>(Opção A)</em>.</div>

</div>

- 20% dos jogadores afetados = impacto direto em retenção
- 2 dias de atraso é controlado e justificável frente ao risco de churn
- Lançar com bug crítico conhecido contradiz nosso compromisso com o jogador

> Este tipo de escape é exatamente o que o nosso plano a seguir vai endereçar.

---

<!-- _class: lead -->

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Como vamos testar *(P2)*

<div style="display:flex; justify-content:center; gap:70px; margin-top:20px; width:100%;">

<div style="text-align:center;">
<div style="font-size:64px;">🔥</div>
<div style="font-weight:bold; font-size:24px; color:#ffcc55; margin-top:10px;">Smoke</div>
</div>

<div style="text-align:center;">
<div style="font-size:64px;">🔁</div>
<div style="font-weight:bold; font-size:24px; color:#55ccff; margin-top:10px;">Regressão</div>
</div>

<div style="text-align:center;">
<div style="font-size:64px;">🔍</div>
<div style="font-weight:bold; font-size:24px; color:#b090ff; margin-top:10px;">Exploratório</div>
</div>

</div>

<div style="text-align:center; margin-top:36px; font-size:15px; color:#aaaacc; width:100%;">
3 camadas complementares — cada uma com seu momento certo no ciclo
</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Smoke, regressão e exploratório *(P2)*

<div style="display:flex; gap:18px; margin-top:16px; width:100%;">

<div style="flex:1; border-top:4px solid #ffcc55; background:#12122a; padding:16px 18px;">
<div style="font-size:28px;">🔥</div>
<div style="font-weight:bold; font-size:17px; color:#ffcc55; margin-top:4px;">Smoke</div>
<div style="font-size:12px; color:#aaaacc; margin-top:2px;">Após cada build semanal</div>
<div style="font-size:13px; margin-top:10px;">Fluxos críticos: pagamento, progressão (~30 min)</div>
</div>

<div style="flex:1; border-top:4px solid #55ccff; background:#12122a; padding:16px 18px;">
<div style="font-size:28px;">🔁</div>
<div style="font-weight:bold; font-size:17px; color:#55ccff; margin-top:4px;">Regressão</div>
<div style="font-size:12px; color:#aaaacc; margin-top:2px;">Antes do freeze trimestral</div>
<div style="font-size:13px; margin-top:10px;">Funcionalidades já validadas + os 9 escapes mapeados</div>
</div>

<div style="flex:1; border-top:4px solid #b090ff; background:#12122a; padding:16px 18px;">
<div style="font-size:28px;">🔍</div>
<div style="font-weight:bold; font-size:17px; color:#b090ff; margin-top:4px;">Exploratório</div>
<div style="font-size:12px; color:#aaaacc; margin-top:2px;">Durante o sprint</div>
<div style="font-size:13px; margin-top:10px;">Áreas alteradas e de maior risco, sem script rígido</div>
</div>

</div>

<div style="margin-top:24px; font-size:14px;">
<strong>O que NÃO testar agora:</strong> textos de NPC · arte cosmética · tutoriais opcionais · edge cases de hardware específicos
</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Antecipando bugs: novo fluxo *(P3)*

**De:** tudo testado no final → **Para:** validação distribuída na sprint

<div style="position:relative; margin-top:50px; width:100%;">

<div style="position:absolute; top:24px; left:6%; right:6%; height:2px; background:#333366;"></div>

<div style="display:flex; position:relative; width:100%;">

<div style="flex:1; text-align:center; padding:0 8px;">
<div style="width:48px; height:48px; border-radius:50%; background:#12122a; border:2px solid #ffcc55; display:flex; align-items:center; justify-content:center; font-size:22px; margin:0 auto;">🗓️</div>
<div style="font-size:14px; font-weight:bold; color:#ffcc55; margin-top:10px;">Início da sprint</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">QA no refinamento, revisando critérios de aceite</div>
</div>

<div style="flex:1; text-align:center; padding:0 8px;">
<div style="width:48px; height:48px; border-radius:50%; background:#12122a; border:2px solid #55ccff; display:flex; align-items:center; justify-content:center; font-size:22px; margin:0 auto;">💻</div>
<div style="font-size:14px; font-weight:bold; color:#55ccff; margin-top:10px;">Durante o desenvolvimento</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">QA testa features conforme ficam prontas</div>
</div>

<div style="flex:1; text-align:center; padding:0 8px;">
<div style="width:48px; height:48px; border-radius:50%; background:#12122a; border:2px solid #ff8855; display:flex; align-items:center; justify-content:center; font-size:22px; margin:0 auto;">🏗️</div>
<div style="font-size:14px; font-weight:bold; color:#ff8855; margin-top:10px;">Build semanal</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">Smoke obrigatório; falhou = não avança</div>
</div>

<div style="flex:1; text-align:center; padding:0 8px;">
<div style="width:48px; height:48px; border-radius:50%; background:#12122a; border:2px solid #ff5577; display:flex; align-items:center; justify-content:center; font-size:22px; margin:0 auto;">⚠️</div>
<div style="font-size:14px; font-weight:bold; color:#ff5577; margin-top:10px;">Pré-freeze</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">Regressão com devs ainda disponíveis para corrigir</div>
</div>

</div>

</div>

<div style="margin-top:34px; border-left:4px solid #7755cc; background:#0d0d1f; padding:10px 16px; font-size:14px; color:#aaaacc;">
Meta: reduzir os 40% de bugs tardios antecipando a detecção para quando o custo de correção ainda é baixo
</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# QA no ciclo de produção *(P4)*
### Ciclo da Sprint

<div style="position:relative; width:700px; height:400px; margin:0 auto;">

<svg width="700" height="400" viewBox="0 0 700 400" style="position:absolute; top:0; left:0;">
  <defs>
    <marker id="sprintCycleArrow" markerWidth="12" markerHeight="12" refX="9" refY="4.5" orient="auto">
      <path d="M0,0 L9,4.5 L0,9 Z" fill="#8888c0" />
    </marker>
  </defs>
  <path d="M350,62 Q500,149.5 531.85,227.56" fill="none" stroke="#8888c0" stroke-width="2.5" marker-end="url(#sprintCycleArrow)"/>
  <path d="M550,272 Q350,307 197.3,280.28" fill="none" stroke="#8888c0" stroke-width="2.5" marker-end="url(#sprintCycleArrow)"/>
  <path d="M150,272 Q200,149.5 308.54,86.19" fill="none" stroke="#8888c0" stroke-width="2.5" marker-end="url(#sprintCycleArrow)"/>
</svg>

<div style="position:absolute; top:230px; left:150px; transform:translateX(-50%); width:210px; text-align:center;">
<div style="width:84px; height:84px; border-radius:50%; background:#12122a; border:3px solid #ffcc55; display:flex; align-items:center; justify-content:center; font-size:34px; margin:0 auto;">📋</div>
<div style="font-size:17px; font-weight:bold; color:#ffcc55; margin-top:8px;">Refinamento</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">Revisar critérios de aceite, levantar edge cases</div>
</div>

<div style="position:absolute; top:20px; left:350px; transform:translateX(-50%); width:210px; text-align:center;">
<div style="width:84px; height:84px; border-radius:50%; background:#12122a; border:3px solid #55ccff; display:flex; align-items:center; justify-content:center; font-size:34px; margin:0 auto;">💻</div>
<div style="font-size:17px; font-weight:bold; color:#55ccff; margin-top:8px;">Desenvolvimento</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">Testar features conforme ficam prontas na branch</div>
</div>

<div style="position:absolute; top:230px; left:550px; transform:translateX(-50%); width:210px; text-align:center;">
<div style="width:84px; height:84px; border-radius:50%; background:#12122a; border:3px solid #ff8855; display:flex; align-items:center; justify-content:center; font-size:34px; margin:0 auto;">🏗️</div>
<div style="font-size:17px; font-weight:bold; color:#ff8855; margin-top:8px;">Build semanal</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">Smoke test — build que falha não avança</div>
</div>

</div>

<div style="text-align:center; font-size:12px; color:#666688; margin-top:6px;">repete a cada sprint semanal</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# QA no ciclo de produção *(P4)*
### Ciclo de Release

<div style="position:relative; width:700px; height:400px; margin:0 auto;">

<svg width="700" height="400" viewBox="0 0 700 400" style="position:absolute; top:0; left:0;">
  <defs>
    <marker id="releaseCycleArrow" markerWidth="12" markerHeight="12" refX="9" refY="4.5" orient="auto">
      <path d="M0,0 L9,4.5 L0,9 Z" fill="#8888c0" />
    </marker>
  </defs>
  <path d="M350,62 Q500,149.5 531.85,227.56" fill="none" stroke="#8888c0" stroke-width="2.5" marker-end="url(#releaseCycleArrow)"/>
  <path d="M550,272 Q350,307 197.3,280.28" fill="none" stroke="#8888c0" stroke-width="2.5" marker-end="url(#releaseCycleArrow)"/>
  <path d="M150,272 Q200,149.5 308.54,86.19" fill="none" stroke="#8888c0" stroke-width="2.5" marker-end="url(#releaseCycleArrow)"/>
</svg>

<div style="position:absolute; top:230px; left:150px; transform:translateX(-50%); width:210px; text-align:center;">
<div style="width:84px; height:84px; border-radius:50%; background:#12122a; border:3px solid #ff5577; display:flex; align-items:center; justify-content:center; font-size:34px; margin:0 auto;">⚠️</div>
<div style="font-size:17px; font-weight:bold; color:#ff5577; margin-top:8px;">Pré-freeze</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">Regressão completa</div>
</div>

<div style="position:absolute; top:20px; left:350px; transform:translateX(-50%); width:210px; text-align:center;">
<div style="width:84px; height:84px; border-radius:50%; background:#12122a; border:3px solid #b090ff; display:flex; align-items:center; justify-content:center; font-size:34px; margin:0 auto;">🔒</div>
<div style="font-size:17px; font-weight:bold; color:#b090ff; margin-top:8px;">Freeze</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">Exploratório focado em risco</div>
</div>

<div style="position:absolute; top:230px; left:550px; transform:translateX(-50%); width:210px; text-align:center;">
<div style="width:84px; height:84px; border-radius:50%; background:#12122a; border:3px solid #66ddaa; display:flex; align-items:center; justify-content:center; font-size:34px; margin:0 auto;">🚀</div>
<div style="font-size:17px; font-weight:bold; color:#66ddaa; margin-top:8px;">Pós-release</div>
<div style="font-size:12px; color:#aaaacc; margin-top:4px;">Monitorar reports; validar hotfixes</div>
</div>

</div>

<div style="text-align:center; font-size:12px; color:#666688; margin-top:6px;">repete a cada release trimestral</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Como vamos trabalhar *(P5)*

<div style="display:flex; gap:14px; margin-top:20px; width:100%; align-items:stretch;">

<div style="flex:1; background:#12122a; border-top:4px solid #7755cc; padding:18px 20px;">
<div style="display:flex; gap:10px; align-items:flex-end; height:90px;">
<img src="images/maria-profile.png" style="height:90px; width:auto;" />
<img src="images/jose-profile.png" style="height:90px; width:auto;" />
</div>
<div style="font-weight:bold; font-size:17px; color:#c8b8ff; margin-top:8px;">Maria e José — execução</div>
<ul style="margin-top:10px; padding-left:20px; font-size:13px;">
<li>Smoke tests semanais (após alinhamento inicial sobre critérios)</li>
<li>Regressão em áreas estáveis e já mapeadas</li>
<li>Reporte de bugs com template padronizado</li>
</ul>
</div>

<div style="flex:1; background:#12122a; border-top:4px solid #7755cc; padding:18px 20px;">
<div style="display:flex; align-items:flex-end; height:90px;">
<img src="images/ljacques-profile.png" style="height:90px; width:auto;" />
</div>
<div style="font-weight:bold; font-size:17px; color:#c8b8ff; margin-top:8px;">L. Jacques — revisão e suporte</div>
<ul style="margin-top:10px; padding-left:20px; font-size:13px;">
<li>Definir e priorizar o plano de testes a cada sprint</li>
<li>Pair testing nas áreas críticas (pagamento, progressão)</li>
<li>Interface com o time de desenvolvimento</li>
<li>Início da automação de testes, conforme a stack do jogo</li>
<li>Sempre disponível para dúvidas</li>
</ul>
</div>

</div>

<div style="margin-top:20px; text-align:center; font-size:13px; color:#aaaacc; width:100%;">Responsabilidades diferentes, mas juntos com um mesmo objetivo.</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Desenvolvendo o time *(P6)*

<div style="position:relative; margin-top:44px; width:100%;">

<div style="position:absolute; top:28px; left:3%; width:78%; height:6px; border-radius:3px; background:linear-gradient(90deg, #55ccff, #b090ff, #ff8855, #ffcc55);"></div>

<div style="display:flex; position:relative; width:100%;">

<div style="flex:1; text-align:center; padding:0 6px;">
<div style="width:56px; height:56px; border-radius:50%; background:#12122a; border:3px solid #55ccff; display:flex; flex-direction:column; align-items:center; justify-content:center; margin:0 auto;">
<div style="font-size:9px; color:#55ccff; line-height:1;">LV</div>
<div style="font-size:20px; font-weight:bold; color:#55ccff; line-height:1.2;">1</div>
</div>
<div style="font-size:11px; color:#666688; margin-top:6px;">semanas 1–2</div>
<div style="font-size:14px; font-weight:bold; color:#55ccff; margin-top:2px;">Diagnóstico</div>
<div style="font-size:11px; color:#aaaacc; margin-top:4px;">Entender nível e lacunas de cada um no trabalho real</div>
</div>

<div style="flex:1; text-align:center; padding:0 6px;">
<div style="width:56px; height:56px; border-radius:50%; background:#12122a; border:3px solid #b090ff; display:flex; flex-direction:column; align-items:center; justify-content:center; margin:0 auto;">
<div style="font-size:9px; color:#b090ff; line-height:1;">LV</div>
<div style="font-size:20px; font-weight:bold; color:#b090ff; line-height:1.2;">2</div>
</div>
<div style="font-size:11px; color:#666688; margin-top:6px;">semanas 3–4</div>
<div style="font-size:14px; font-weight:bold; color:#b090ff; margin-top:2px;">Pair testing</div>
<div style="font-size:11px; color:#aaaacc; margin-top:4px;">Decisões discutidas em tempo real nas áreas críticas</div>
</div>

<div style="flex:1; text-align:center; padding:0 6px;">
<div style="width:56px; height:56px; border-radius:50%; background:#12122a; border:3px solid #ff8855; display:flex; flex-direction:column; align-items:center; justify-content:center; margin:0 auto;">
<div style="font-size:9px; color:#ff8855; line-height:1;">LV</div>
<div style="font-size:20px; font-weight:bold; color:#ff8855; line-height:1.2;">3</div>
</div>
<div style="font-size:11px; color:#666688; margin-top:6px;">semanas 5–6</div>
<div style="font-size:14px; font-weight:bold; color:#ff8855; margin-top:2px;">Ownership</div>
<div style="font-size:11px; color:#aaaacc; margin-top:4px;">Maria e José lideram o plano de testes de uma feature <em>(com revisão do L. Jacques)</em></div>
</div>

<div style="flex:1; text-align:center; padding:0 6px;">
<div style="width:56px; height:56px; border-radius:50%; background:#12122a; border:3px solid #ffcc55; display:flex; flex-direction:column; align-items:center; justify-content:center; margin:0 auto;">
<div style="font-size:9px; color:#ffcc55; line-height:1;">LV</div>
<div style="font-size:20px; font-weight:bold; color:#ffcc55; line-height:1.2;">4</div>
</div>
<div style="font-size:11px; color:#666688; margin-top:6px;">semanas 7–8</div>
<div style="font-size:14px; font-weight:bold; color:#ffcc55; margin-top:2px;">Retrospectiva</div>
<div style="font-size:11px; color:#aaaacc; margin-top:4px;">O que melhorou + início da automação (conforme stack do jogo)</div>
</div>

<div style="flex:0 0 70px; text-align:center; padding:0 6px;">
<div style="font-size:34px; line-height:56px;">🏆</div>
<div style="font-size:11px; font-weight:bold; color:#ffcc55; margin-top:6px;">Level up!</div>
</div>

</div>

</div>

<div style="margin-top:30px; border-left:4px solid #7755cc; background:#0d0d1f; padding:10px 16px; font-size:14px;">
<strong>Métrica de sucesso:</strong> redução de bugs encontrados no pré-freeze que deveriam ter sido capturados durante a sprint
</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>QA🔬</span>

</div>

# Plano de ação: próximas 2 semanas *(P1)*

<div style="display:flex; gap:18px; margin-top:20px; width:100%;">

<div style="flex:1; background:#12122a; border-top:4px solid #ffcc55; padding:16px 18px;">
<div style="font-size:26px;">🎯</div>
<div style="font-weight:bold; font-size:15px; color:#ffcc55; margin-top:6px;">Regressão mínima baseada nos escapes</div>
<div style="font-size:12px; color:#aaaacc; margin-top:8px;">Mapear os 9 bugs que chegaram à produção, transformá-los em casos de teste e executar nas próximas builds semanais</div>
</div>

<div style="flex:1; background:#12122a; border-top:4px solid #55ccff; padding:16px 18px;">
<div style="font-size:26px;">🎯</div>
<div style="font-weight:bold; font-size:15px; color:#55ccff; margin-top:6px;">Shift-left no processo de sprint</div>
<div style="font-size:12px; color:#aaaacc; margin-top:8px;">QA revisa critérios de aceite no início de cada sprint, antes do desenvolvimento começar</div>
</div>

<div style="flex:1; background:#12122a; border-top:4px solid #b090ff; padding:16px 18px;">
<div style="font-size:26px;">🎯</div>
<div style="font-weight:bold; font-size:15px; color:#b090ff; margin-top:6px;">Definition of done</div>
<div style="font-size:12px; color:#aaaacc; margin-top:8px;">Smoke pass + regressão mínima aprovada antes do freeze</div>
</div>

</div>

<div style="margin-top:26px; border-left:4px solid #7755cc; background:#0d0d1f; padding:12px 18px; font-size:15px; color:#aaaacc; text-align:center;">
Pequenas mudanças, aplicadas de forma consistente, são o que vai melhorar os números das próximas versões.
</div>
