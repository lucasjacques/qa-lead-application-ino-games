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

<span style="font-size: 52px; letter-spacing: 3px; display: block; margin-top: 6px; margin-right: 15px;">DEV 👾</span>

</div>

<div style="max-width:640px; margin-top:160px;">

<p style="font-size: 16px; margin: 0 0 12px 0; letter-spacing: 1px;">Subtítulo do slide de capa</p>

# Apresentação de Template - DEV

<div style="display:flex; align-items:center; gap:12px; margin-top:4px;">

<img src="images/template-profile.png" style="height:56px; width:auto;" />

<p style="font-size: 15px; margin: 0;">Nome Sobrenome — Cargo</p>

</div>

<p style="font-size: 13px; color: #666688; margin: 6px 0 0 0;">Nota de rodapé opcional da capa</p>

</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>DEV 👾</span>

</div>

# Lorem Ipsum Dolor Sit Amet

<div style="display:flex; align-items:center; justify-content:center; gap:60px; margin-top:10px;">

<div style="text-align:center;">

<svg width="170" height="170" viewBox="0 0 180 180">
  <circle cx="90" cy="90" r="70" fill="none" stroke="#4a4a7a" stroke-width="24" />
  <circle cx="90" cy="90" r="70" fill="none" stroke="#ff5577" stroke-width="24"
    stroke-dasharray="141.4 439.8" stroke-linecap="round"
    transform="rotate(-90 90 90)" />
  <text x="90" y="84" text-anchor="middle" font-size="32" font-weight="bold" fill="#ffffff">X</text>
  <text x="90" y="106" text-anchor="middle" font-size="12" fill="#aaaacc">de Y (Z%)</text>
</svg>

<p style="font-size:13px; margin:8px 0 0 0; text-align:left; display:inline-block;">
<span style="color:#4a4a7a;">●</span> Lorem ipsum dolor sit<br>
<span style="color:#ff5577;">●</span> Consectetur adipiscing elit
</p>

</div>

<div style="display:flex; flex-direction:column; gap:14px;">

<div style="border-left:6px solid #ffcc55; padding:6px 16px; background:#12122a;">
<span style="font-size:26px; font-weight:bold; color:#ffcc55;">NN%</span><br>
<span style="font-size:13px;">Lorem ipsum dolor sit amet</span>
</div>

<div style="border-left:6px solid #55ccff; padding:6px 16px; background:#12122a;">
<span style="font-size:26px; font-weight:bold; color:#55ccff;">N dias</span><br>
<span style="font-size:13px;">Consectetur adipiscing elit</span>
</div>

</div>

</div>

<br>

> Lorem ipsum dolor sit amet, consectetur adipiscing elit sed do eiusmod.

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>DEV 👾</span>

</div>

# Consectetur Adipiscing Elit

<div style="display:flex; gap:18px; margin-top:20px; width:100%;">

<div style="flex:1; background:#12122a; border-top:4px solid #ffcc55; padding:16px 18px;">
<div style="font-size:26px; color:#ffcc55;">●</div>
<div style="font-weight:bold; font-size:15px; color:#ffcc55; margin-top:6px;">Lorem Ipsum</div>
<div style="font-size:12px; color:#aaaacc; margin-top:8px;">Lorem ipsum dolor sit amet, consectetur adipiscing elit</div>
</div>

<div style="flex:1; background:#12122a; border-top:4px solid #55ccff; padding:16px 18px;">
<div style="font-size:26px; color:#55ccff;">●</div>
<div style="font-weight:bold; font-size:15px; color:#55ccff; margin-top:6px;">Dolor Sit Amet</div>
<div style="font-size:12px; color:#aaaacc; margin-top:8px;">Sed do eiusmod tempor incididunt ut labore et dolore</div>
</div>

<div style="flex:1; background:#12122a; border-top:4px solid #b090ff; padding:16px 18px;">
<div style="font-size:26px; color:#b090ff;">●</div>
<div style="font-weight:bold; font-size:15px; color:#b090ff; margin-top:6px;">Consectetur</div>
<div style="font-size:12px; color:#aaaacc; margin-top:8px;">Ut enim ad minim veniam, quis nostrud exercitation</div>
</div>

</div>

<div style="margin-top:26px; border-left:4px solid #7755cc; background:#0d0d1f; padding:12px 18px; font-size:15px; color:#aaaacc; text-align:center;">
Lorem ipsum dolor sit amet, consectetur adipiscing elit.
</div>

---

<div class="mini-logo">

![w:150](images/nebula-forge-logo.png)

<span>DEV 👾</span>

</div>

# Sed Do Eiusmod Tempor

<div style="position:relative; margin-top:56px; width:100%;">

<div style="position:absolute; top:24px; left:4%; right:4%; height:2px; background:#333366;"></div>

<div style="display:flex; position:relative; width:100%;">

<div style="flex:1; text-align:center; padding:0 6px;">
<div style="width:48px; height:48px; border-radius:50%; background:#12122a; border:2px solid #ffcc55; display:flex; align-items:center; justify-content:center; font-size:18px; font-weight:bold; color:#ffcc55; margin:0 auto;">1</div>
<div style="font-size:14px; font-weight:bold; color:#ffcc55; margin-top:8px;">Lorem</div>
<div style="font-size:11px; color:#aaaacc; margin-top:4px;">Ipsum dolor sit amet consectetur</div>
</div>

<div style="flex:1; text-align:center; padding:0 6px;">
<div style="width:48px; height:48px; border-radius:50%; background:#12122a; border:2px solid #55ccff; display:flex; align-items:center; justify-content:center; font-size:18px; font-weight:bold; color:#55ccff; margin:0 auto;">2</div>
<div style="font-size:14px; font-weight:bold; color:#55ccff; margin-top:8px;">Ipsum</div>
<div style="font-size:11px; color:#aaaacc; margin-top:4px;">Dolor sit amet consectetur adipiscing</div>
</div>

<div style="flex:1; text-align:center; padding:0 6px;">
<div style="width:48px; height:48px; border-radius:50%; background:#12122a; border:2px solid #ff8855; display:flex; align-items:center; justify-content:center; font-size:18px; font-weight:bold; color:#ff8855; margin:0 auto;">3</div>
<div style="font-size:14px; font-weight:bold; color:#ff8855; margin-top:8px;">Dolor</div>
<div style="font-size:11px; color:#aaaacc; margin-top:4px;">Sit amet consectetur adipiscing elit</div>
</div>

<div style="flex:1; text-align:center; padding:0 6px;">
<div style="width:48px; height:48px; border-radius:50%; background:#12122a; border:2px solid #b090ff; display:flex; align-items:center; justify-content:center; font-size:18px; font-weight:bold; color:#b090ff; margin:0 auto;">4</div>
<div style="font-size:14px; font-weight:bold; color:#b090ff; margin-top:8px;">Sit Amet</div>
<div style="font-size:11px; color:#aaaacc; margin-top:4px;">Consectetur adipiscing elit sed do</div>
</div>

</div>

</div>

<div style="margin-top:34px; border-left:4px solid #7755cc; background:#0d0d1f; padding:10px 16px; font-size:14px; color:#aaaacc;">
Lorem ipsum dolor sit amet, consectetur adipiscing elit sed do eiusmod tempor.
</div>
