<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=1340"/>
<title>Kartik Agrawal</title>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@700;800;900&family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
body{background:#04080F;font-family:'Space Grotesk',sans-serif;}

:root{
  --c:#00C8FF;
  --dark:#04080F;
  --navy:#060C18;
  --muted:#8899AA;
  --dim:#2A4050;
}

.canvas{
  width:1340px;height:850px;
  position:relative;overflow:hidden;
  background:var(--dark);
}

/* ── BACKGROUND ── */
.bg-overlay{
  position:absolute;inset:0;pointer-events:none;z-index:0;
  background:
    radial-gradient(ellipse at 80% 5%, rgba(15,70,200,0.14) 0%, transparent 50%),
    radial-gradient(ellipse at 15% 85%, rgba(0,40,120,0.08) 0%, transparent 50%),
    radial-gradient(ellipse at 60% 50%, rgba(0,20,80,0.06) 0%, transparent 70%);
}

.mountains-svg{
  position:absolute;bottom:0;left:0;
  width:1340px;height:540px;
  pointer-events:none;z-index:1;
}

.fog-layer{
  position:absolute;bottom:0;left:0;right:0;height:220px;
  background:linear-gradient(to top,rgba(2,6,15,0.7) 0%,rgba(4,8,20,0.3) 60%,transparent 100%);
  pointer-events:none;z-index:2;
}

/* ── TOP NAV ── */
.top-nav{
  position:absolute;top:0;left:0;right:0;
  display:flex;align-items:flex-start;
  padding:28px 46px 0;z-index:20;
}

.terminal-id{
  font-family:'JetBrains Mono',monospace;
  font-size:12.5px;line-height:1.9;color:var(--dim);
}
.terminal-id .v{color:var(--c);font-weight:700;}

.nav-menu{
  flex:1;text-align:center;padding-top:6px;
  font-size:11px;font-weight:500;
  letter-spacing:0.28em;color:#1E3040;
  text-transform:uppercase;
}
.nav-menu .sep{color:#0F1E2E;margin:0 10px;}

.github-id{display:flex;align-items:center;gap:10px;}
.gh-circle{
  width:38px;height:38px;border-radius:50%;
  background:#080F1C;border:1px solid #182A3A;
  display:flex;align-items:center;justify-content:center;
}
.gh-text .gh-n{font-size:13px;font-weight:700;color:#C8D8E4;letter-spacing:0.05em;}
.gh-text .gh-s{font-size:10px;color:#2A3E50;letter-spacing:0.06em;margin-top:2px;}

/* ── LEFT IDENTITY ── */
.identity{
  position:absolute;left:46px;top:118px;
  width:530px;z-index:10;
}
.hi{font-size:22px;font-weight:300;color:#587080;margin-bottom:8px;letter-spacing:0.02em;}

.name-block{line-height:0.86;margin-bottom:16px;}
.nm{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:142px;display:block;letter-spacing:-0.015em;}
.nm-solid{color:#FFFFFF;}
.nm-outline{
  -webkit-text-stroke:2.5px #00C8FF;
  color:transparent;
  text-shadow:0 0 70px rgba(0,200,255,0.22),0 0 140px rgba(0,100,200,0.1);
}

.role-text{
  font-size:11.5px;font-weight:500;
  letter-spacing:0.24em;color:#1E3040;
  text-transform:uppercase;margin-bottom:20px;
}

.tagline{
  font-size:14px;color:#587080;line-height:1.65;
  border-left:3px solid var(--c);
  padding-left:14px;margin-bottom:24px;
  max-width:380px;
}

.skill-badges{display:flex;gap:8px;flex-wrap:wrap;}
.skill-badge{
  display:flex;align-items:center;gap:8px;
  border:1px solid rgba(0,200,255,0.13);
  background:rgba(0,200,255,0.03);
  border-radius:5px;padding:7px 15px;
  font-size:12px;font-weight:600;color:#587080;
  letter-spacing:0.04em;
}
.badge-ico{color:var(--c);font-size:14px;line-height:1;}

/* ── QUOTE ── */
.quote{
  position:absolute;bottom:46px;left:46px;
  z-index:10;width:340px;
}
.q-text{font-size:17px;font-style:italic;color:#3A5060;line-height:1.5;margin-bottom:6px;font-weight:300;}
.q-by{font-size:11.5px;color:#1E3040;font-style:italic;}

/* ── CENTER MONITOR ── */
.monitor-wrap{position:absolute;left:528px;top:108px;z-index:10;}

.monitor{
  width:325px;
  background:#07111E;
  border:1px solid #152535;
  border-radius:11px;overflow:hidden;
  box-shadow:
    0 0 0 1px rgba(0,200,255,0.04),
    0 28px 70px rgba(0,0,0,0.75),
    0 0 60px rgba(0,80,180,0.06);
}
.monitor-bar{
  background:#040D1A;padding:10px 16px;
  display:flex;align-items:center;gap:6px;
  border-bottom:1px solid #0D1D2D;
}
.dot2{width:9px;height:9px;border-radius:50%;}
.d-r{background:#FF5F57;}.d-y{background:#FFBD2E;}.d-g{background:#28C840;}
.monitor-title{flex:1;text-align:center;font-family:'JetBrains Mono',monospace;font-size:10.5px;color:#1E3A50;}

.monitor-body{padding:16px 20px;font-family:'JetBrains Mono',monospace;font-size:12px;}
.mb-flex{display:flex;gap:20px;}
.file-tree .ft{color:#00C8FF;font-weight:700;font-size:13.5px;margin-bottom:10px;}
.file-tree .di{color:#3A5A70;line-height:2.1;}
.file-tree .di::before{content:"▷ ";font-size:9px;color:#1E3A50;}
.file-tree .fi{color:#1E3040;line-height:2.1;}
.file-tree .fi::before{content:"📄 ";font-size:9px;}
.code-side{color:#1E3A50;font-size:12px;line-height:2.1;margin-top:2px;}
.code-side .cm{color:#1A3A52;}
.code-side .cmh{color:#00C8FF;font-weight:700;}
.div-line{margin-top:12px;border-top:1px solid #0A1A28;padding-top:10px;}
.arrow-line{font-size:11px;letter-spacing:0.1em;color:#1A3040;}
.arrow-line .al{color:#1E4060;}.arrow-line .av{color:#1E3A50;}

/* KEYBOARD */
.keyboard-wrap{margin-top:10px;perspective:280px;}
.keyboard{
  background:#04090F;
  border:1px solid #0A1822;
  border-radius:8px;padding:10px 14px;
  transform:rotateX(28deg);transform-origin:top center;
  box-shadow:0 22px 50px rgba(0,0,0,0.85),0 0 30px rgba(0,100,200,0.04);
}
.key-row{display:flex;gap:4px;margin-bottom:4px;justify-content:center;}
.key{
  width:24px;height:18px;
  background:#06101A;border:1px solid #0D1C2A;
  border-radius:3px;border-bottom:2px solid #020608;
  font-family:'JetBrains Mono',monospace;
  font-size:6.5px;color:#152232;
  display:flex;align-items:center;justify-content:center;
}
.key.lit{
  background:#07162A;border-color:rgba(0,200,255,0.22);
  color:rgba(0,200,255,0.45);box-shadow:0 0 5px rgba(0,200,255,0.12);
}
.key.space{width:110px;}
.mouse-pad{
  margin-top:8px;
  width:50px;height:30px;
  background:#04080E;border:1px solid #0A1820;
  border-radius:20px;margin-left:auto;margin-right:auto;
  box-shadow:0 0 8px rgba(0,100,200,0.06);
}

/* ── WATERMARK ── */
.watermark{
  position:absolute;bottom:95px;left:50%;
  transform:translateX(-50%);
  font-size:9.5px;font-weight:500;
  letter-spacing:0.48em;color:#0D1A24;
  text-transform:uppercase;white-space:nowrap;
  z-index:5;
}

/* ── KORTEX PANEL ── */
.kortex-panel{
  position:absolute;right:28px;top:58px;
  width:455px;height:490px;z-index:10;
}

.flabel{
  position:absolute;
  font-family:'Space Grotesk',sans-serif;
  font-size:10px;font-weight:700;
  letter-spacing:0.2em;color:#3A5870;
  background:rgba(4,8,15,0.82);
  border:1px solid #152535;
  border-radius:4px;padding:4px 12px;
  text-transform:uppercase;white-space:nowrap;
}
.fl-a{top:78px;left:8px;}
.fl-t{top:18px;right:88px;}
.fl-d{top:98px;right:8px;}
.fl-m{top:238px;right:12px;}

.conn-svg{position:absolute;inset:0;width:100%;height:100%;pointer-events:none;}

/* 3D CUBE */
.cube-wrap{
  position:absolute;top:42px;right:78px;
  width:215px;height:215px;perspective:900px;
}
.cube3d{
  width:215px;height:215px;
  position:relative;transform-style:preserve-3d;
  transform:rotateX(-22deg) rotateY(36deg);
  animation:cf 7s ease-in-out infinite;
}
@keyframes cf{
  0%,100%{transform:rotateX(-22deg) rotateY(36deg) translateY(0);}
  50%{transform:rotateX(-22deg) rotateY(36deg) translateY(-13px);}
}
.cface{
  position:absolute;width:215px;height:215px;
  border:1px solid rgba(0,200,255,0.2);
  backface-visibility:visible;
}
.cface.cf{transform:translateZ(107px);background:linear-gradient(145deg,#07183A 0%,#030A18 100%);box-shadow:inset 0 0 40px rgba(0,200,255,0.06);display:flex;align-items:center;justify-content:center;}
.cface.cb{transform:rotateY(180deg) translateZ(107px);background:#010308;}
.cface.cl{transform:rotateY(-90deg) translateZ(107px);background:linear-gradient(160deg,#040F26 0%,#020608 100%);}
.cface.cr{transform:rotateY(90deg) translateZ(107px);background:linear-gradient(160deg,#05102A 0%,#030910 100%);}
.cface.ct{transform:rotateX(90deg) translateZ(107px);background:linear-gradient(145deg,#0C2646 0%,#061835 100%);box-shadow:0 0 60px rgba(0,200,255,0.1);}
.cface.cbo{transform:rotateX(-90deg) translateZ(107px);background:#010205;}

.k-letter{
  font-family:'Barlow Condensed',sans-serif;
  font-weight:900;font-size:105px;color:#00C8FF;
  text-shadow:
    0 0 12px rgba(0,200,255,1),
    0 0 35px rgba(0,200,255,0.6),
    0 0 70px rgba(0,150,230,0.35),
    0 0 130px rgba(0,100,200,0.2);
  line-height:1;user-select:none;
}

/* platform glow below cube */
.platform{
  position:absolute;top:265px;right:68px;
  width:235px;height:8px;
  background:linear-gradient(to bottom,rgba(0,200,255,0.45),transparent);
  filter:blur(5px);
  animation:rp 3s ease-in-out infinite;
}
@keyframes rp{0%,100%{opacity:0.5;}50%{opacity:1;}}

/* side stripes for 3D platform look */
.platform-plate{
  position:absolute;top:259px;right:68px;
  width:235px;height:4px;
  background:linear-gradient(to right,transparent,rgba(0,200,255,0.3),rgba(0,200,255,0.5),rgba(0,200,255,0.3),transparent);
}

/* KORTEX neon text */
.kortex-neon-wrap{
  position:absolute;bottom:28px;
  left:50%;transform:translateX(-50%);
  text-align:center;white-space:nowrap;
}
.kortex-neon-text{
  font-family:'Barlow Condensed',sans-serif;
  font-weight:900;font-size:55px;
  letter-spacing:0.16em;color:#00C8FF;
  text-shadow:
    0 0 8px rgba(0,200,255,1),
    0 0 22px rgba(0,200,255,0.85),
    0 0 50px rgba(0,200,255,0.55),
    0 0 100px rgba(0,140,230,0.3);
  animation:np 3s ease-in-out infinite;
}
@keyframes np{
  0%,100%{text-shadow:0 0 8px rgba(0,200,255,1),0 0 22px rgba(0,200,255,0.85),0 0 50px rgba(0,200,255,0.55);}
  50%{text-shadow:0 0 12px rgba(0,200,255,1),0 0 35px rgba(0,200,255,0.9),0 0 80px rgba(0,200,255,0.65),0 0 150px rgba(0,140,220,0.35);}
}
.kortex-sub{
  font-family:'Space Grotesk',sans-serif;
  font-size:10px;letter-spacing:0.3em;
  color:#1A3048;text-transform:uppercase;margin-top:4px;
}

/* ── COLLABORATE ── */
.collab{position:absolute;bottom:46px;right:46px;z-index:10;text-align:right;}
.collab-sl{font-family:'JetBrains Mono',monospace;font-size:10.5px;color:#152535;margin-bottom:5px;}
.collab-t{font-family:'Space Grotesk',sans-serif;font-size:11px;letter-spacing:0.22em;color:#1E3040;text-transform:uppercase;line-height:1.8;}
.collab-rule{width:190px;height:1px;background:linear-gradient(to left,#152535,transparent);margin-left:auto;margin-top:10px;}
</style>
</head>
<body>
<div class="canvas">

<!-- BG -->
<div class="bg-overlay"></div>

<!-- MOUNTAINS -->
<svg class="mountains-svg" viewBox="0 0 1340 540" preserveAspectRatio="xMidYMax meet" xmlns="http://www.w3.org/2000/svg">
  <!-- Moon halo right -->
  <radialGradient id="rg1" cx="82%" cy="8%" r="42%">
    <stop offset="0%" stop-color="#0C3070" stop-opacity="0.3"/>
    <stop offset="100%" stop-color="#04080F" stop-opacity="0"/>
  </radialGradient>
  <rect width="1340" height="540" fill="url(#rg1)"/>

  <!-- Water/valley glow bottom center -->
  <radialGradient id="rg2" cx="50%" cy="108%" r="40%">
    <stop offset="0%" stop-color="#06203C" stop-opacity="0.55"/>
    <stop offset="100%" stop-color="#04080F" stop-opacity="0"/>
  </radialGradient>
  <rect width="1340" height="540" fill="url(#rg2)"/>

  <!-- Farthest mountains - lightest blue cast -->
  <path d="M0 430 L70 330 L150 375 L240 275 L340 335 L440 235 L555 305 L665 215 L780 285 L890 195 L1000 260 L1100 178 L1200 240 L1280 188 L1340 220 L1340 540 L0 540Z" fill="#05101E" opacity="0.55"/>

  <!-- Mid mountains -->
  <path d="M0 455 L90 385 L190 415 L300 340 L410 390 L520 308 L640 368 L755 282 L870 348 L980 268 L1085 322 L1185 258 L1280 298 L1340 272 L1340 540 L0 540Z" fill="#040C16" opacity="0.8"/>

  <!-- Near mountains -->
  <path d="M0 482 L110 428 L220 460 L340 398 L455 448 L575 378 L695 432 L815 360 L935 418 L1055 350 L1155 400 L1260 355 L1340 380 L1340 540 L0 540Z" fill="#03090F" opacity="0.95"/>

  <!-- Ground line -->
  <path d="M0 515 L180 500 L400 514 L650 496 L900 510 L1150 498 L1340 508 L1340 540 L0 540Z" fill="#020608"/>

  <!-- Subtle moonlight shimmer on water at valley bottom -->
  <linearGradient id="water" x1="0" y1="0" x2="0" y2="1">
    <stop offset="0%" stop-color="#06243C" stop-opacity="0"/>
    <stop offset="100%" stop-color="#081830" stop-opacity="0.45"/>
  </linearGradient>
  <ellipse cx="670" cy="530" rx="380" ry="40" fill="url(#water)"/>
</svg>

<div class="fog-layer"></div>

<!-- ══ TOP NAV ══ -->
<nav class="top-nav">
  <div class="terminal-id">
    <div>&gt; whoami</div>
    <div class="v">Kartik Agrawal</div>
    <div style="margin-top:5px">&gt; status</div>
    <div class="v">Building... ⌛</div>
  </div>

  <div class="nav-menu">
    AUTOMATE<span class="sep">/</span>BUILD<span class="sep">/</span>LEARN<span class="sep">/</span>IMPROVE
  </div>

  <div class="github-id">
    <div class="gh-circle">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="#3A5870">
        <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/>
      </svg>
    </div>
    <div class="gh-text">
      <div class="gh-n">Kagrawal11</div>
      <div class="gh-s">Code · Automate · Innovate</div>
    </div>
  </div>
</nav>

<!-- ══ LEFT IDENTITY ══ -->
<div class="identity">
  <div class="hi">Hi, I'm</div>
  <div class="name-block">
    <span class="nm nm-solid">KARTIK</span>
    <span class="nm nm-outline">AGRAWAL</span>
  </div>
  <div class="role-text">Software Engineer &nbsp;|&nbsp; Automation Enthusiast</div>
  <div class="tagline">
    Building practical solutions for real-world problems.<br/>
    Focused on automation, backend engineering<br/>and developer productivity.
  </div>
  <div class="skill-badges">
    <div class="skill-badge">
      <span class="badge-ico" style="font-family:monospace;font-size:11px;">&lt;/&gt;</span>
      Clean Code
    </div>
    <div class="skill-badge">
      <svg class="badge-ico" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#00C8FF" stroke-width="2" stroke-linecap="round">
        <circle cx="12" cy="12" r="3"/><path d="M12 2v2M12 20v2M2 12h2M20 12h2M4.93 4.93l1.41 1.41M17.66 17.66l1.41 1.41M4.93 19.07l1.41-1.41M17.66 6.34l1.41-1.41"/>
      </svg>
      Automate
    </div>
    <div class="skill-badge">
      <svg class="badge-ico" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#00C8FF" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
        <rect x="3" y="3" width="4" height="18" rx="1"/><rect x="10" y="8" width="4" height="13" rx="1"/><rect x="17" y="13" width="4" height="8" rx="1"/>
      </svg>
      Solve
    </div>
    <div class="skill-badge">
      <svg class="badge-ico" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#00C8FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M9 18h6M10 22h4M12 2a7 7 0 017 7c0 2.38-1.19 4.47-3 5.74V17H8v-2.26C6.19 13.47 5 11.38 5 9a7 7 0 017-7z"/>
      </svg>
      Grow
    </div>
  </div>
</div>

<!-- ══ QUOTE ══ -->
<div class="quote">
  <div class="q-text">"Build systems<br/>that give you back time."</div>
  <div class="q-by">— Kartik Agrawal</div>
</div>

<!-- ══ CENTER MONITOR ══ -->
<div class="monitor-wrap">
  <div class="monitor">
    <div class="monitor-bar">
      <div class="dot2 d-r"></div>
      <div class="dot2 d-y"></div>
      <div class="dot2 d-g"></div>
      <div class="monitor-title">KORTEX — workspace</div>
    </div>
    <div class="monitor-body">
      <div class="mb-flex">
        <div class="file-tree">
          <div class="ft">KORTEX</div>
          <div class="di">backend/</div>
          <div class="di">frontend/</div>
          <div class="di">automation/</div>
          <div class="di">docs/</div>
          <div class="fi">README.md</div>
        </div>
        <div class="code-side">
          <div style="height:22px"></div>
          <div style="height:22px"></div>
          <div class="cm">// Automate today.</div>
          <div class="cm">// Scale tomorrow.</div>
          <div class="cmh">// KORTEX</div>
        </div>
      </div>
      <div class="div-line">
        <div class="arrow-line">
          <span class="al">IDEAS </span>
          <span style="color:#0F2030"> ──► </span>
          <span class="av">IMPACT</span>
        </div>
      </div>
    </div>
  </div>

  <div class="keyboard-wrap">
    <div class="keyboard">
      <div class="key-row">
        <div class="key">Q</div><div class="key lit">W</div><div class="key">E</div>
        <div class="key lit">R</div><div class="key">T</div><div class="key">Y</div>
        <div class="key lit">U</div><div class="key">I</div><div class="key">O</div>
        <div class="key">P</div>
      </div>
      <div class="key-row">
        <div class="key">A</div><div class="key">S</div><div class="key lit">D</div>
        <div class="key">F</div><div class="key lit">G</div><div class="key">H</div>
        <div class="key">J</div><div class="key lit">K</div><div class="key">L</div>
      </div>
      <div class="key-row">
        <div class="key">Z</div><div class="key lit">X</div><div class="key">C</div>
        <div class="key">V</div><div class="key lit">B</div><div class="key">N</div>
        <div class="key">M</div>
      </div>
      <div class="key-row"><div class="key space"></div></div>
    </div>
  </div>
  <div class="mouse-pad"></div>
</div>

<!-- WATERMARK -->
<div class="watermark">D I S C I P L I N E &nbsp;&nbsp; C O M P O U N D S &nbsp;&nbsp; R E S U L T S</div>

<!-- ══ KORTEX 3D PANEL ══ -->
<div class="kortex-panel">

  <!-- Labels -->
  <div class="flabel fl-a">AUTOMATE</div>
  <div class="flabel fl-t">TEST</div>
  <div class="flabel fl-d">DEPLOY</div>
  <div class="flabel fl-m">MONITOR</div>

  <!-- Connector lines -->
  <svg class="conn-svg" viewBox="0 0 455 490" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <marker id="dm" viewBox="0 0 6 6" refX="3" refY="3" markerWidth="3" markerHeight="3" orient="auto">
        <circle cx="3" cy="3" r="2.5" fill="rgba(0,200,255,0.4)"/>
      </marker>
    </defs>
    <line x1="105" y1="90" x2="222" y2="162" stroke="rgba(0,200,255,0.18)" stroke-width="1" stroke-dasharray="5 3" marker-end="url(#dm)"/>
    <line x1="355" y1="30" x2="276" y2="148" stroke="rgba(0,200,255,0.14)" stroke-width="1" stroke-dasharray="5 3" marker-end="url(#dm)"/>
    <line x1="440" y1="110" x2="338" y2="175" stroke="rgba(0,200,255,0.14)" stroke-width="1" stroke-dasharray="5 3" marker-end="url(#dm)"/>
    <line x1="440" y1="250" x2="350" y2="228" stroke="rgba(0,200,255,0.12)" stroke-width="1" stroke-dasharray="5 3" marker-end="url(#dm)"/>
  </svg>

  <!-- Cube -->
  <div class="cube-wrap">
    <div class="cube3d">
      <div class="cface cf"><span class="k-letter">K</span></div>
      <div class="cface cb"></div>
      <div class="cface cl"></div>
      <div class="cface cr"></div>
      <div class="cface ct"></div>
      <div class="cface cbo"></div>
    </div>
  </div>

  <!-- Platform glow -->
  <div class="platform-plate"></div>
  <div class="platform"></div>

  <!-- KORTEX neon text -->
  <div class="kortex-neon-wrap">
    <div class="kortex-neon-text">KORTEX</div>
    <div class="kortex-sub">From Manual to Meaningful</div>
  </div>

</div>

<!-- ══ COLLABORATE ══ -->
<div class="collab">
  <div class="collab-sl">// &gt;</div>
  <div class="collab-t">Open to collaborate<br/>on interesting problems.</div>
  <div class="collab-rule"></div>
</div>

</div>
</body>
</html>
