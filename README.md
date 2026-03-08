<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Sur-raaj · Suraj KC</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@400;700;900&family=IBM+Plex+Mono:ital,wght@0,300;0,400;0,600;1,300&display=swap" rel="stylesheet"/>
<style>

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }

body {
  background: #030912;
  font-family: 'IBM Plex Mono', monospace;
  font-size: 14px;
  line-height: 1.6;
  min-height: 100vh;
  overflow-x: hidden;
}

/* ══ TOPBAR ══ */
.topbar {
  position: sticky; top: 0; z-index: 300;
  background: rgba(3,9,18,0.97);
  backdrop-filter: blur(18px);
  border-bottom: 1px solid #0d1a26;
  display: flex; align-items: center;
  justify-content: space-between;
  padding: 0.78rem 2.5rem;
}
.brand {
  font-family: 'Orbitron', sans-serif;
  font-size: 0.82rem; font-weight: 700;
  letter-spacing: 0.1em;
}
.brand .cy  { color: #00d4ff; }
.brand .vs  { color: #1a3040; margin: 0 0.4em; font-weight: 400; }
.brand .hi  { color: #ff9500; }
.brand .sub { color: #1a3040; font-weight: 400; font-family: 'IBM Plex Mono', monospace; font-size: 0.76rem; letter-spacing: 0.04em; }

.nav-pills { display: flex; gap: 0.45rem; }
.pill {
  display: inline-flex; align-items: center; gap: 0.4rem;
  padding: 0.36rem 1.1rem; border-radius: 999px;
  border: 1px solid #162433; background: transparent;
  font-family: 'IBM Plex Mono', monospace; font-size: 0.71rem;
  cursor: pointer; color: #1e3a50; transition: all 0.2s; letter-spacing: 0.05em;
}
.pill:hover { color: #336688; border-color: #1e3a50; }
.pill.side   { color: #2a4a60; border-color: #162433; }
.pill.active { background: rgba(0,212,255,0.13); border-color: #00d4ff; color: #00d4ff; font-weight: 600; }
.pdot { width: 7px; height: 7px; border-radius: 50%; background: #00d4ff; box-shadow: 0 0 7px #00d4ff; flex-shrink: 0; }

/* ══ PAGE ══ */
.page { max-width: 880px; margin: 0 auto; padding: 2.5rem 1.5rem 5rem; }

.col-tag {
  display: block; text-align: center;
  font-family: 'Share Tech Mono', monospace;
  font-size: 0.6rem; letter-spacing: 0.25em; text-transform: uppercase;
  padding: 0.42rem 2rem; border-radius: 999px; margin-bottom: 1.8rem;
  background: rgba(0,212,255,0.05); color: #009bbb;
  border: 1px solid rgba(0,212,255,0.14);
}

/* ══ CARD ══ */
.card {
  background: #070f1c;
  border: 1px solid #0c1e30;
  border-radius: 14px;
  overflow: hidden;
  position: relative;
  box-shadow:
    0 0 55px rgba(0,212,255,0.06),
    0 0 120px rgba(0,80,160,0.04),
    0 28px 60px rgba(0,0,0,0.7);
  animation: rise 0.4s ease both;
}
@keyframes rise { from{opacity:0;transform:translateY(14px)} to{opacity:1;transform:translateY(0)} }

/* animated top border */
.card::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 2px;
  background: linear-gradient(90deg, transparent 0%, #00d4ff 30%, #0099cc 70%, transparent 100%);
  animation: topLine 4s ease-in-out infinite;
}
@keyframes topLine { 0%,100%{opacity:.3} 50%{opacity:1} }

/* corner accent */
.card::after {
  content: '';
  position: absolute; top: 0; right: 0;
  width: 60px; height: 60px;
  background: linear-gradient(225deg, rgba(0,212,255,0.07) 0%, transparent 60%);
  pointer-events: none;
}

/* ══ HEADER ══ */
.c-header {
  padding: 3.5rem 2rem 3rem;
  text-align: center;
  background: linear-gradient(180deg, #030f1e 0%, #050d1a 60%, #070f1c 100%);
  border-bottom: 1px solid #0a1e30;
  position: relative; overflow: hidden;
}
/* scanline texture */
.c-header::before {
  content: '';
  position: absolute; inset: 0;
  background: repeating-linear-gradient(0deg, transparent, transparent 3px, rgba(0,212,255,0.012) 3px, rgba(0,212,255,0.012) 4px);
  pointer-events: none;
}
/* faint binary watermark */
.c-header::after {
  content: '01001100 01001111 01000111 01001001 01001110';
  position: absolute; bottom: 5px; left: 0; right: 0;
  font-family: 'Share Tech Mono', monospace; font-size: 0.36rem;
  color: #020c18; letter-spacing: 0.18em; pointer-events: none;
}

.c-name {
  font-family: 'Orbitron', sans-serif;
  font-size: clamp(2.8rem, 6vw, 3.8rem);
  font-weight: 900;
  color: #00d4ff;
  letter-spacing: 0.14em;
  text-shadow:
    0 0 15px rgba(0,212,255,.8),
    0 0 40px rgba(0,212,255,.4),
    0 0 80px rgba(0,180,255,.18),
    0 0 140px rgba(0,150,255,.08);
  line-height: 1;
  position: relative; z-index: 1;
}

.c-sub {
  font-family: 'Share Tech Mono', monospace;
  font-size: 0.71rem; color: #004d6e;
  margin-top: 0.8rem; letter-spacing: 0.14em; line-height: 2;
  position: relative; z-index: 1;
}
.c-sub .hl { color: #0077aa; }

/* ══ TERMINAL ══ */
.c-terminal {
  margin: 1.8rem;
  background: #000508;
  border: 1px solid #061525;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 24px rgba(0,0,0,0.4), inset 0 0 40px rgba(0,0,0,0.3);
}

.ct-bar {
  background: #02080f;
  padding: 0.52rem 1.1rem;
  display: flex; align-items: center; gap: 0.45rem;
  border-bottom: 1px solid #061525;
}
.dot { width: 9px; height: 9px; border-radius: 50%; }
.dot.r { background: #2e0e0e; }
.dot.y { background: #2e2a0e; }
.dot.g { background: #0e2a0e; }
.ct-filename { font-size: 0.58rem; color: #082030; letter-spacing: 0.12em; margin-left: auto; font-family: 'Share Tech Mono', monospace; }

.ct-body {
  padding: 1.4rem 1.7rem;
  font-family: 'Share Tech Mono', monospace;
  font-size: 0.8rem; line-height: 2.1;
}
.tc { color: #0a2535; font-style: italic; }
.tk { color: #005f7a; }
.tv { color: #0099bb; }
.ts { color: #00c8ee; }
.tb { color: #003344; }
.tg { color: #00cc66; }
.td { color: #061822; }
.cursor {
  display: inline-block; width: 9px; height: 0.95em;
  background: #00d4ff; vertical-align: text-bottom;
  box-shadow: 0 0 8px #00d4ff;
  animation: blink 1s step-end infinite;
}
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

/* ══ SECTION LABEL ══ */
.sec-label {
  font-family: 'Share Tech Mono', monospace;
  font-size: 0.56rem; color: #082030;
  letter-spacing: 0.22em; text-transform: uppercase;
  margin: 0.2rem 0 0.6rem;
  display: flex; align-items: center; gap: 0.6rem;
}
.sec-label::before { content: '▸'; color: #041520; }
.sec-label::after  { content: ''; flex: 1; height: 1px; background: #051520; }

/* ══ BADGES ══ */
.c-badges { padding: 0 1.8rem 1.8rem; }
.badges { display: flex; flex-wrap: wrap; gap: 0.42rem; }

.badge {
  display: inline-flex; align-items: center; gap: 0.32rem;
  padding: 0.3rem 0.92rem; border-radius: 5px; border: 1px solid;
  font-family: 'Share Tech Mono', monospace; font-size: 0.64rem;
  letter-spacing: 0.06em; white-space: nowrap;
  cursor: default; transition: all 0.18s;
}
.badge:hover { transform: translateY(-1px); }
.bh  { background: rgba(0,212,255,.09); border-color: #063348; color: #00d4ff; }
.bh:hover { background: rgba(0,212,255,.16); border-color: #009bcc; box-shadow: 0 0 10px rgba(0,212,255,.15); }
.bm  { background: rgba(0,136,187,.06); border-color: #042030; color: #0099bb; }
.bm:hover { border-color: #007799; }
.bd  { background: rgba(0,70,110,.04);  border-color: #031525; color: #005577; }
.bq  { background: rgba(0,100,200,.07); border-color: #042040; color: #0077cc; }
.bq:hover { border-color: #0066bb; }

/* ══ STATS ROW ══ */
.c-stats {
  display: grid; grid-template-columns: repeat(3,1fr);
  gap: 0.7rem; margin: 0 1.8rem 1.8rem;
}
.stat {
  background: #030d18; border: 1px solid #051828;
  border-radius: 8px; padding: 0.9rem 0.8rem; text-align: center;
  transition: border-color 0.2s;
}
.stat:hover { border-color: #063348; }
.stat-val {
  font-family: 'Orbitron', sans-serif; font-size: 1.25rem;
  font-weight: 700; color: #00d4ff;
  text-shadow: 0 0 14px rgba(0,212,255,.4);
}
.stat-lbl { font-size: 0.55rem; color: #0a2535; letter-spacing: 0.12em; margin-top: 0.25rem; text-transform: uppercase; }

/* ══ PROJECTS ══ */
.c-projects { margin: 0 1.8rem 1.8rem; }
.proj {
  display: flex; align-items: center; gap: 0.8rem;
  padding: 0.65rem 1rem; border-radius: 7px;
  border: 1px solid #051525;
  background: rgba(0,12,25,.5); margin-bottom: 0.45rem;
  transition: all 0.18s; cursor: default;
}
.proj:hover { border-color: #0a2a40; background: rgba(0,18,35,.7); transform: translateX(3px); }
.proj-ico { font-size: 1rem; flex-shrink: 0; }
.proj-name { font-size: 0.68rem; color: #0099bb; font-family: 'Share Tech Mono', monospace; }
.proj-desc { font-size: 0.58rem; color: #042535; margin-top: 0.1rem; }
.proj-arr { margin-left: auto; color: #042030; font-size: 0.65rem; transition: color 0.2s; }
.proj:hover .proj-arr { color: #00d4ff; }

/* ══ ACTIVITY ══ */
.c-activity {
  margin: 0 1.8rem 1.8rem;
  background: #030d18; border: 1px solid #051828;
  border-radius: 9px; padding: 1rem 1.2rem;
}
.act-grid { display: flex; gap: 2px; flex-wrap: wrap; margin-top: 0.6rem; }
.ac {
  width: 11px; height: 11px; border-radius: 2px;
  background: #030d18; border: 1px solid #051525;
}
.ac.l1{background:#042030;border-color:#063040;}
.ac.l2{background:#06405a;border-color:#08506a;}
.ac.l3{background:#097080;border-color:#0b8090;}
.ac.l4{background:#00aabb;border-color:#00c4cc;}
.ac.l5{background:#00d4ff;border-color:#33ddff;box-shadow:0 0 4px rgba(0,212,255,.5);}

/* ══ OTW ══ */
.c-otw {
  margin: 0 1.8rem 1.8rem;
  border: 1px solid #063348; border-radius: 9px;
  padding: 1.1rem 1.4rem;
  display: flex; align-items: flex-start; gap: 1rem;
  background: linear-gradient(135deg, rgba(0,212,255,.03), rgba(0,80,160,.015));
  position: relative; overflow: hidden;
}
.c-otw::before {
  content: ''; position: absolute; left: 0; top: 0; bottom: 0; width: 3px;
  background: linear-gradient(180deg, #00d4ff 0%, #0044aa 100%);
}
.pulse {
  width: 11px; height: 11px; border-radius: 50%; flex-shrink: 0; margin-top: 3px;
  background: #00ff88;
  box-shadow: 0 0 12px #00ff88, 0 0 24px rgba(0,255,136,.3);
  animation: pulseAnim 1.6s ease infinite;
}
@keyframes pulseAnim { 0%,100%{transform:scale(1);opacity:1} 50%{transform:scale(.6);opacity:.3} }
.otw-t { font-family: 'Share Tech Mono', monospace; font-size: 0.73rem; color: #00d4ff; letter-spacing: 0.1em; }
.otw-s { font-size: 0.61rem; color: #052535; margin-top: 0.35rem; line-height: 1.9; }

/* ══ SOCIALS ══ */
.c-social { padding: 0 1.8rem 2rem; display: flex; flex-wrap: wrap; gap: 0.5rem; }
.soc {
  display: inline-flex; align-items: center; gap: 0.4rem;
  padding: 0.36rem 1rem; border-radius: 6px;
  border: 1px solid #061828; background: rgba(0,100,160,.04);
  font-family: 'Share Tech Mono', monospace; font-size: 0.63rem;
  color: #005f77; cursor: default; transition: all 0.18s; letter-spacing: 0.05em;
}
.soc:hover { border-color: #00d4ff; color: #00d4ff; background: rgba(0,212,255,.06); box-shadow: 0 0 10px rgba(0,212,255,.08); }

/* ══ FOOTER ══ */
.c-footer {
  padding: 1rem 1.8rem; border-top: 1px solid #061828;
  display: flex; align-items: center; justify-content: space-between;
  font-family: 'Share Tech Mono', monospace; font-size: 0.56rem;
  color: #041825; letter-spacing: 0.1em;
}
.c-footer .vbadge {
  background: rgba(0,212,255,.04); border: 1px solid #051828;
  padding: 0.22rem 0.7rem; border-radius: 4px; color: #004d66;
}

/* ══ QUOTE ══ */
.c-quote {
  margin: 0 1.8rem 1.8rem;
  background: #030d18; border: 1px solid #051828; border-radius: 9px;
  padding: 1rem 1.4rem;
  font-family: 'Share Tech Mono', monospace; font-size: 0.72rem;
  color: #004d66; line-height: 1.9; text-align: center; letter-spacing: 0.04em;
}

</style>
</head>
<body>

<!-- ══ TOPBAR ══ -->
<div class="topbar">
  <div class="brand">
    <span class="cy">CYBER</span><span class="vs">vs</span><span class="hi">HIMALAYAN</span>
    <span class="sub"> · Sur-raaj README Preview</span>
  </div>
  <div class="nav-pills">
    <button class="pill side" onclick="setSide()">Side by Side</button>
    <button class="pill active" id="btn-cyber">
      <span class="pdot"></span>Cyberpunk
    </button>
    <button class="pill" id="btn-himal" onclick="setHimal()" style="color:#3a2008;border-color:#1a0e05">
      <span style="width:7px;height:7px;border-radius:50%;background:#ff9500;box-shadow:0 0 7px #ff9500;flex-shrink:0"></span>Himalayan
    </button>
  </div>
</div>

<!-- ══ PAGE ══ -->
<div class="page">

  <span class="col-tag">DARK CYBERPUNK — FULL PREVIEW</span>

  <div class="card">

    <!-- HEADER -->
    <div class="c-header">
      <div class="c-name">SUR-RAAJ</div>
      <div class="c-sub">
        <span class="hl">&gt; SURAJ KC</span> // KATHMANDU, NEPAL 🏔️<br/>
        &gt; BACKEND DEV &nbsp;→&nbsp; AI/ML &nbsp;→&nbsp; QUANTUM COMPUTING
      </div>
    </div>

    <!-- TERMINAL -->
    <div class="c-terminal">
      <div class="ct-bar">
        <div class="dot r"></div>
        <div class="dot y"></div>
        <div class="dot g"></div>
        <div class="ct-filename">sur-raaj.profile.js</div>
      </div>
      <div class="ct-body">
        <span class="tc">// boot.sequence.init()</span><br/>
        <span class="tk">const</span> <span class="tv">surRaaj</span> <span class="td">= {</span><br/>
        &nbsp;&nbsp;<span class="tk">name</span><span class="td">:</span>     <span class="ts">"Suraj KC"</span><span class="td">,</span><br/>
        &nbsp;&nbsp;<span class="tk">origin</span><span class="td">:</span>   <span class="ts">"Kathmandu, Nepal 🇳🇵"</span><span class="td">,</span><br/>
        &nbsp;&nbsp;<span class="tk">focus</span><span class="td">:</span>    <span class="ts">"AI/ML → Quantum Computing"</span><span class="td">,</span><br/>
        &nbsp;&nbsp;<span class="tk">frontend</span><span class="td">:</span> <span class="tb">false</span><span class="td">,</span> <span class="tc">// never asked 😅</span><br/>
        &nbsp;&nbsp;<span class="tk">status</span><span class="td">:</span>   <span class="tg">"OPEN TO COLLABORATE 🟢"</span><br/>
        <span class="td">}</span><span class="cursor"></span>
      </div>
    </div>

    <!-- BADGES -->
    <div class="c-badges">
      <div class="sec-label">FULL STACK</div>
      <div class="badges">
        <span class="badge bh">🤖 AI/ML</span>
        <span class="badge bh">PyTorch</span>
        <span class="badge bh">TensorFlow</span>
        <span class="badge bq">⚛️ Qiskit</span>
        <span class="badge bm">HuggingFace</span>
        <span class="badge bd">Python</span>
        <span class="badge bd">Node.js</span>
        <span class="badge bd">FastAPI</span>
        <span class="badge bd">Docker</span>
        <span class="badge bd">AWS</span>
        <span class="badge bd">PostgreSQL</span>
      </div>
    </div>

    <!-- STATS -->
    <div class="c-stats">
      <div class="stat">
        <div class="stat-val">500+</div>
        <div class="stat-lbl">Commits</div>
      </div>
      <div class="stat">
        <div class="stat-val">🔥 —</div>
        <div class="stat-lbl">Day Streak</div>
      </div>
      <div class="stat">
        <div class="stat-val">NP 🏔️</div>
        <div class="stat-lbl">Origin</div>
      </div>
    </div>

    <!-- PROJECTS -->
    <div class="c-projects">
      <div class="sec-label">PINNED PROJECTS</div>
      <div class="proj">
        <span class="proj-ico">🤖</span>
        <div>
          <div class="proj-name">AI / ML Project Name</div>
          <div class="proj-desc">Add your project description · Python · PyTorch · FastAPI</div>
        </div>
        <span class="proj-arr">→</span>
      </div>
      <div class="proj">
        <span class="proj-ico">⚛️</span>
        <div>
          <div class="proj-name">Quantum Project Name</div>
          <div class="proj-desc">Add your project description · Qiskit · Python</div>
        </div>
        <span class="proj-arr">→</span>
      </div>
      <div class="proj">
        <span class="proj-ico">⚙️</span>
        <div>
          <div class="proj-name">Backend Project Name</div>
          <div class="proj-desc">Add your project description · Node.js · PostgreSQL</div>
        </div>
        <span class="proj-arr">→</span>
      </div>
      <div class="proj">
        <span class="proj-ico">🔬</span>
        <div>
          <div class="proj-name">Research Project Name</div>
          <div class="proj-desc">Add your project description · PyTorch · Docker</div>
        </div>
        <span class="proj-arr">→</span>
      </div>
    </div>

    <!-- ACTIVITY -->
    <div class="c-activity">
      <div class="sec-label">CONTRIBUTION GRAPH</div>
      <div class="act-grid" id="actGrid"></div>
    </div>

    <!-- OTW -->
    <div class="c-otw">
      <div class="pulse"></div>
      <div>
        <div class="otw-t">OPEN TO WORK &amp; COLLABORATIONS</div>
        <div class="otw-s">AI/ML &nbsp;·&nbsp; Quantum Research &nbsp;·&nbsp; Backend Systems &nbsp;·&nbsp; Open Source</div>
      </div>
    </div>

    <!-- QUOTE -->
    <div class="c-quote">
      "Build systems that outlive the hype." &nbsp;—&nbsp; Sur-raaj
    </div>

    <!-- SOCIALS -->
    <div class="c-social">
      <span class="soc">🔗 LinkedIn</span>
      <span class="soc">🐦 Twitter</span>
      <span class="soc">🌐 Portfolio</span>
      <span class="soc">✉️ Email</span>
    </div>

    <!-- FOOTER -->
    <div class="c-footer">
      <span>⚡ Engineered from Kathmandu, Nepal 🇳🇵 · @sur-raaj</span>
      <span class="vbadge">👁 PROFILE VIEWS: ——</span>
    </div>

  </div><!-- end card -->

</div><!-- end page -->

<script>
// Generate activity grid
const grid = document.getElementById('actGrid');
for (let i = 0; i < 196; i++) {
  const c = document.createElement('div');
  const r = Math.random();
  const l = r < .42 ? 0 : r < .58 ? 1 : r < .72 ? 2 : r < .84 ? 3 : r < .93 ? 4 : 5;
  c.className = 'ac' + (l ? ' l'+l : '');
  grid.appendChild(c);
}

function setSide() {
  alert('Both themes available — use the Cyberpunk & Himalayan buttons to switch.');
}
function setHimal() {
  alert('Himalayan theme: use README-himalayan.md from your downloads.');
}
</script>
</body>
</html>
