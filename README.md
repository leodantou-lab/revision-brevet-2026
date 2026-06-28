<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nocturne — Réviser le Brevet</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,500;0,9..144,600;0,9..144,700;1,9..144,500&family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
/* ===================== TOKENS ===================== */
:root{
  --ink: #0A0D13;
  --ink-2: #0F131B;
  --card: #131722;
  --card-hover: #161B27;
  --line: #232a38;
  --line-soft: #1a202c;
  --text: #ECEEF2;
  --text-dim: #9099AC;
  --text-faint: #5B6478;

  --histoire: #FF6B5B;
  --histoire-dim: #4a2c28;
  --geo: #3DDC8C;
  --geo-dim: #1f3c2e;
  --svt: #22D3EE;
  --svt-dim: #173a42;
  --physique: #B794F6;
  --physique-dim: #332a4a;
  --maths: #FBBF24;
  --maths-dim: #423420;
  --francais: #F472B6;
  --francais-dim: #422a3a;
  --brevet: #ffffff;

  --accent: var(--maths);
  --accent-dim: var(--maths-dim);

  --radius-lg: 24px;
  --radius-md: 16px;
  --radius-sm: 10px;
  --shadow-card: 0 1px 0 rgba(255,255,255,0.03) inset, 0 20px 40px -24px rgba(0,0,0,0.6);
  --ease: cubic-bezier(.16,1,.3,1);
}

*{box-sizing:border-box; max-width:100%;}
html,body{margin:0;padding:0; width:100%; overflow-x:hidden;}
html{color-scheme: dark;}
body{
  background: radial-gradient(ellipse 1200px 800px at 20% -10%, #161c2a 0%, var(--ink) 55%), var(--ink);
  color:var(--text) !important;
  font-family:'Inter', -apple-system, sans-serif;
  min-height:100vh;
  -webkit-font-smoothing:antialiased;
  overflow-x:hidden;
  width:100%;
}
h1,h2,h3,h4,h5,h6,p,span,div,button,a,li{ color:inherit; }
.display{font-family:'Fraunces', serif;}
.mono{font-family:'JetBrains Mono', monospace;}

a{color:inherit; text-decoration:none;}
button{font-family:inherit; cursor:pointer;}
::selection{background:var(--maths); color:#1a1a1a;}

/* Subtle noise / grain texture */
.grain{
  position:fixed; inset:0; pointer-events:none; z-index:1; opacity:0.035; mix-blend-mode:overlay;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='160' height='160'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
}

/* Reduced motion */
@media (prefers-reduced-motion: reduce){
  *{animation-duration:0.001ms !important; transition-duration:0.001ms !important;}
}

/* Focus visibility */
:focus-visible{outline:2px solid var(--maths); outline-offset:3px; border-radius:6px;}

/* ===================== LAYOUT SHELLS ===================== */
.app{position:relative; z-index:2; max-width:1180px; width:100%; margin:0 auto; padding: 28px 24px 80px;}

.top-row{display:flex; align-items:center; justify-content:space-between; margin-bottom:48px; gap:20px;}
.brand{display:flex; align-items:center; gap:12px;}
.brand-mark{
  width:38px; height:38px; border-radius:11px;
  background: linear-gradient(150deg, #232a3a, #11151e);
  border:1px solid var(--line);
  display:flex; align-items:center; justify-content:center;
  font-family:'Fraunces',serif; font-weight:700; font-size:18px; color:var(--maths);
  box-shadow: 0 0 0 1px rgba(255,255,255,0.02) inset, 0 8px 20px -8px rgba(0,0,0,0.7);
}
.brand-name{font-family:'Fraunces',serif; font-weight:600; font-size:19px; letter-spacing:0.2px; color:var(--text);}
.brand-sub{font-size:11px; color:var(--text-faint); letter-spacing:0.08em; text-transform:uppercase; margin-top:1px;}

.streak-pill{
  display:flex; align-items:center; gap:8px;
  background:var(--card); border:1px solid var(--line);
  padding:8px 16px 8px 12px; border-radius:100px;
  font-family:'JetBrains Mono', monospace; font-size:13px; color:var(--text-dim);
}
.streak-flame{font-size:15px; filter: drop-shadow(0 0 6px rgba(251,191,36,0.5));}
.streak-num{color:var(--text); font-weight:600;}

/* ===================== HERO ===================== */
.hero{margin-bottom:64px; padding-top:8px;}
.hero-eyebrow{
  display:inline-flex; align-items:center; gap:8px;
  font-family:'JetBrains Mono',monospace; font-size:12px; letter-spacing:0.1em; text-transform:uppercase;
  color:var(--text-faint); margin-bottom:20px;
}
.hero-eyebrow::before{content:''; width:6px; height:6px; border-radius:50%; background:var(--maths); box-shadow:0 0 12px var(--maths);}
.hero h1{
  font-family:'Fraunces', serif; font-weight:600; font-size:clamp(34px, 5.2vw, 58px);
  line-height:1.04; margin:0 0 18px; letter-spacing:-0.01em; max-width:780px; color:var(--text);
}
.hero h1 em{font-style:italic; font-weight:500; color:var(--maths);}
.hero p{font-size:16.5px; color:var(--text-dim); max-width:560px; line-height:1.6; margin:0;}

/* ===================== SUBJECT GRID ===================== */
.section-label{
  display:flex; align-items:baseline; gap:14px; margin: 56px 0 22px;
}
.section-label h2{font-family:'Fraunces',serif; font-weight:600; font-size:22px; margin:0; color:var(--text);}
.section-label .count{font-family:'JetBrains Mono',monospace; font-size:12px; color:var(--text-faint);}
.section-label .rule{flex:1; height:1px; background:linear-gradient(to right, var(--line), transparent);}

.subject-grid{
  display:grid; grid-template-columns:repeat(3, 1fr); gap:16px;
}
@media (max-width: 920px){ .subject-grid{grid-template-columns:repeat(2,1fr);} }
@media (max-width: 600px){ .subject-grid{grid-template-columns:1fr;} }

.subject-card{
  position:relative; background:var(--card); border:1px solid var(--line);
  border-radius:var(--radius-md); padding:24px;
  display:flex; flex-direction:column; gap:14px;
  transition: transform .35s var(--ease), border-color .35s var(--ease), background .35s var(--ease);
  overflow:hidden;
  box-shadow: var(--shadow-card);
}
.subject-card::before{
  content:''; position:absolute; top:0; left:0; right:0; height:2px;
  background:var(--accent); opacity:0.85;
}
.subject-card::after{
  content:''; position:absolute; top:-40%; right:-30%; width:220px; height:220px; border-radius:50%;
  background:var(--accent); opacity:0; filter:blur(60px); transition:opacity .4s var(--ease);
}
.subject-card:hover{ transform:translateY(-4px); border-color: color-mix(in srgb, var(--accent) 35%, var(--line)); background:var(--card-hover);}
.subject-card:hover::after{opacity:0.18;}

.subject-top{display:flex; align-items:flex-start; justify-content:space-between; gap:10px;}
.subject-icon{
  width:42px; height:42px; border-radius:11px; display:flex; align-items:center; justify-content:center;
  font-size:19px; background:var(--accent-dim); color:var(--accent); flex:none;
  border:1px solid color-mix(in srgb, var(--accent) 28%, transparent);
}
.subject-qcount{font-family:'JetBrains Mono',monospace; font-size:11px; color:var(--text-faint); padding-top:4px; white-space:nowrap;}
.subject-name{font-family:'Fraunces',serif; font-weight:600; font-size:19px; line-height:1.25; margin:0; color:var(--text);}
.subject-desc{font-size:13.5px; color:var(--text-dim); line-height:1.5; margin:0; flex:1;}
.subject-foot{display:flex; align-items:center; justify-content:space-between; margin-top:4px;}
.subject-cta{
  font-family:'JetBrains Mono',monospace; font-size:12.5px; font-weight:500; color:var(--accent);
  display:flex; align-items:center; gap:6px;
}
.subject-cta svg{transition: transform .3s var(--ease);}
.subject-card:hover .subject-cta svg{transform:translateX(4px);}
.subject-best{font-size:11px; color:var(--text-faint); font-family:'JetBrains Mono',monospace;}

.subject-card{border:1px solid var(--line); cursor:pointer;}
.subject-card:focus-visible{outline:2px solid var(--accent);}

/* difficulty badge */
.diff-badge{
  position:absolute; top:14px; right:14px; font-family:'JetBrains Mono',monospace; font-size:9.5px;
  letter-spacing:0.06em; text-transform:uppercase; color:var(--text-faint); opacity:0.7;
}

/* ===================== FOOTER NOTE ===================== */
.footnote{margin-top:70px; padding-top:28px; border-top:1px solid var(--line-soft); display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:12px;}
.footnote p{font-size:12.5px; color:var(--text-faint); margin:0;}
.footnote .reset-btn{
  font-family:'JetBrains Mono',monospace; font-size:12px; color:var(--text-faint); background:none; border:1px solid var(--line);
  padding:7px 14px; border-radius:8px; transition:all .2s;
}
.footnote .reset-btn:hover{color:var(--text); border-color:var(--text-faint);}

/* =====================================================
   QUIZ VIEW
===================================================== */
.quiz-view{display:none; min-height:100vh;}
.quiz-view.active{display:block;}
.home-view.hidden{display:none;}

.quiz-shell{max-width:760px; width:100%; margin:0 auto; padding: 24px 24px 60px;}

.quiz-top{display:flex; align-items:center; justify-content:space-between; margin-bottom:28px; gap:12px; flex-wrap:wrap;}
.back-btn{
  display:flex; align-items:center; gap:8px; font-family:'JetBrains Mono',monospace; font-size:13px;
  color:var(--text-dim); background:var(--card); border:1px solid var(--line); padding:9px 14px 9px 10px; border-radius:10px;
  transition: all .2s;
}
.back-btn:hover{color:var(--text); border-color:var(--text-faint);}

.quiz-meta{display:flex; align-items:center; gap:16px;}
.quiz-subject-tag{
  display:flex; align-items:center; gap:7px; font-family:'JetBrains Mono',monospace; font-size:12px; color:var(--accent);
  background:var(--accent-dim); border:1px solid color-mix(in srgb, var(--accent) 30%, transparent); padding:6px 12px; border-radius:100px;
}
.quiz-subject-tag .dot{width:6px; height:6px; border-radius:50%; background:var(--accent);}

.progress-track{
  position:relative; height:6px; background:var(--line-soft); border-radius:100px; overflow:hidden; margin-bottom:36px;
}
.progress-fill{
  position:absolute; left:0; top:0; height:100%; border-radius:100px;
  background: linear-gradient(90deg, color-mix(in srgb, var(--accent) 60%, white 0%), var(--accent));
  transition: width .5s var(--ease);
  box-shadow: 0 0 14px var(--accent);
}

.q-counter{font-family:'JetBrains Mono',monospace; font-size:12.5px; color:var(--text-faint); margin-bottom:10px; display:flex; gap:10px; align-items:center;}
.q-counter .type-pill{
  background:var(--line-soft); padding:2px 9px; border-radius:6px; color:var(--text-dim); font-size:10.5px; text-transform:uppercase; letter-spacing:0.05em;
}

.q-card{
  background:var(--card); border:1px solid var(--line); border-radius:var(--radius-lg); padding:38px 36px;
  box-shadow:var(--shadow-card);
  animation: cardIn .45s var(--ease);
}
@keyframes cardIn{from{opacity:0; transform:translateY(10px);} to{opacity:1; transform:translateY(0);}}

.q-text{font-family:'Fraunces',serif; font-weight:500; font-size:clamp(20px,2.6vw,25px); line-height:1.4; margin:0 0 30px; color:var(--text);}

.choices{display:flex; flex-direction:column; gap:10px;}
.choice{
  display:flex; align-items:center; gap:14px; text-align:left;
  background:var(--ink-2); border:1px solid var(--line); border-radius:var(--radius-sm);
  padding:16px 18px; font-size:15px; color:var(--text); width:100%;
  transition: all .18s var(--ease); position:relative; overflow:hidden;
}
.choice .letter{
  width:26px; height:26px; border-radius:7px; background:var(--line-soft); color:var(--text-dim);
  font-family:'JetBrains Mono',monospace; font-size:12px; display:flex; align-items:center; justify-content:center; flex:none;
  transition: all .18s;
}
.choice:hover:not(.disabled){border-color: color-mix(in srgb, var(--accent) 45%, var(--line)); background:var(--card-hover); transform:translateX(3px);}
.choice:hover:not(.disabled) .letter{background:var(--accent-dim); color:var(--accent);}
.choice.disabled{cursor:default;}

.choice.correct{
  border-color: var(--geo); background: linear-gradient(90deg, color-mix(in srgb, var(--geo) 14%, var(--ink-2)), var(--ink-2));
  animation: pulseGood .5s var(--ease);
}
.choice.correct .letter{background:var(--geo); color:#06140d;}
.choice.wrong{
  border-color: var(--histoire); background: linear-gradient(90deg, color-mix(in srgb, var(--histoire) 14%, var(--ink-2)), var(--ink-2));
  animation: shakeBad .4s var(--ease);
}
.choice.wrong .letter{background:var(--histoire); color:#1a0a08;}
.choice.faded{opacity:0.4;}

@keyframes pulseGood{0%{transform:scale(1);} 40%{transform:scale(1.015);} 100%{transform:scale(1);}}
@keyframes shakeBad{0%,100%{transform:translateX(0);} 25%{transform:translateX(-5px);} 75%{transform:translateX(5px);}}

.choice .check-icon{margin-left:auto; flex:none; opacity:0; transition:opacity .2s;}
.choice.correct .check-icon, .choice.wrong .check-icon{opacity:1;}

/* True/False layout */
.vf-row{display:grid; grid-template-columns:1fr 1fr; gap:14px;}
.vf-btn{
  display:flex; flex-direction:column; align-items:center; gap:8px; padding:30px 20px;
  background:var(--ink-2); border:1px solid var(--line); border-radius:var(--radius-md);
  transition:all .18s var(--ease);
}
.vf-btn .vf-label{font-family:'Fraunces',serif; font-size:19px; font-weight:600; color:var(--text);}
.vf-btn:hover:not(.disabled){transform:translateY(-3px); border-color:color-mix(in srgb, var(--accent) 45%, var(--line));}
.vf-btn.correct{border-color:var(--geo); background:color-mix(in srgb, var(--geo) 12%, var(--ink-2)); animation: pulseGood .5s var(--ease);}
.vf-btn.wrong{border-color:var(--histoire); background:color-mix(in srgb, var(--histoire) 12%, var(--ink-2)); animation: shakeBad .4s var(--ease);}
.vf-btn.faded{opacity:0.4;}
.vf-icon{font-size:22px;}

/* Feedback panel */
.feedback{
  margin-top:24px; padding:20px 22px; border-radius:var(--radius-md); border:1px solid var(--line);
  display:none; animation: feedIn .35s var(--ease);
}
.feedback.show{display:block;}
@keyframes feedIn{from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);}}
.feedback.is-correct{background: color-mix(in srgb, var(--geo) 8%, var(--card)); border-color: color-mix(in srgb, var(--geo) 35%, var(--line));}
.feedback.is-wrong{background: color-mix(in srgb, var(--histoire) 8%, var(--card)); border-color: color-mix(in srgb, var(--histoire) 35%, var(--line));}
.feedback-title{display:flex; align-items:center; gap:8px; font-family:'JetBrains Mono',monospace; font-size:12.5px; font-weight:600; letter-spacing:0.04em; text-transform:uppercase; margin-bottom:8px;}
.feedback.is-correct .feedback-title{color:var(--geo);}
.feedback.is-wrong .feedback-title{color:var(--histoire);}
.feedback-text{font-size:14.5px; color:var(--text-dim); line-height:1.6; margin:0;}
.feedback-text strong{color:var(--text); font-weight:600;}

.next-row{display:flex; justify-content:flex-end; margin-top:26px;}
.next-btn{
  font-family:'JetBrains Mono',monospace; font-size:13.5px; font-weight:600; color:#0c0e13;
  background:var(--accent); border:none; padding:13px 24px; border-radius:10px;
  display:flex; align-items:center; gap:8px; opacity:0; pointer-events:none;
  transition: all .25s var(--ease); transform:translateY(4px);
}
.next-btn.show{opacity:1; pointer-events:auto; transform:translateY(0);}
.next-btn:hover{filter:brightness(1.08); transform:translateY(-1px);}
.next-btn:active{transform:translateY(0px) scale(0.98);}

/* ===================== RESULTS VIEW ===================== */
.results-view{display:none;}
.results-view.active{display:block;}
.results-card{
  background:var(--card); border:1px solid var(--line); border-radius:var(--radius-lg); padding:50px 40px;
  text-align:center; box-shadow:var(--shadow-card); animation: cardIn .5s var(--ease);
}
.results-ring{width:160px; height:160px; margin:0 auto 28px; position:relative;}
.results-ring svg{transform:rotate(-90deg);}
.results-ring .ring-bg{fill:none; stroke:var(--line-soft); stroke-width:10;}
.results-ring .ring-fg{fill:none; stroke:var(--accent); stroke-width:10; stroke-linecap:round; transition: stroke-dashoffset 1.2s var(--ease); filter:drop-shadow(0 0 10px var(--accent));}
.results-score{position:absolute; inset:0; display:flex; flex-direction:column; align-items:center; justify-content:center;}
.results-score .num{font-family:'Fraunces',serif; font-size:40px; font-weight:600; line-height:1;}
.results-score .denom{font-family:'JetBrains Mono',monospace; font-size:12px; color:var(--text-faint); margin-top:2px;}

.results-title{font-family:'Fraunces',serif; font-size:26px; font-weight:600; margin:0 0 10px; color:var(--text);}
.results-sub{color:var(--text-dim); font-size:15px; margin:0 0 32px; max-width:420px; margin-left:auto; margin-right:auto; line-height:1.6;}

.results-stats{display:flex; justify-content:center; gap:36px; margin-bottom:36px; flex-wrap:wrap;}
.rstat{text-align:center;}
.rstat .v{font-family:'JetBrains Mono',monospace; font-size:20px; font-weight:600; color:var(--text);}
.rstat .l{font-size:11px; color:var(--text-faint); text-transform:uppercase; letter-spacing:0.06em; margin-top:4px;}

.results-actions{display:flex; gap:12px; justify-content:center; flex-wrap:wrap;}
.btn-primary, .btn-ghost{
  font-family:'JetBrains Mono',monospace; font-size:13.5px; font-weight:600; padding:13px 22px; border-radius:10px;
  display:inline-flex; align-items:center; gap:8px; transition:all .2s var(--ease);
}
.btn-primary{background:var(--accent); color:#0c0e13; border:none;}
.btn-primary:hover{filter:brightness(1.08); transform:translateY(-1px);}
.btn-ghost{background:transparent; color:var(--text-dim); border:1px solid var(--line);}
.btn-ghost:hover{color:var(--text); border-color:var(--text-faint);}

.missed-review{margin-top:40px; text-align:left; border-top:1px solid var(--line-soft); padding-top:28px;}
.missed-review h3{font-family:'Fraunces',serif; font-size:16px; font-weight:600; margin:0 0 16px; color:var(--text-dim);}
.missed-item{padding:14px 0; border-bottom:1px solid var(--line-soft);}
.missed-item:last-child{border-bottom:none;}
.missed-q{font-size:14px; color:var(--text); margin:0 0 6px; font-weight:500;}
.missed-a{font-size:13px; color:var(--text-dim); margin:0;}
.missed-a strong{color:var(--geo);}

@media (max-width: 600px){
  .q-card{padding:26px 22px;}
  .results-card{padding:36px 22px;}
  .vf-row{grid-template-columns:1fr;}
  .quiz-shell{padding:16px 14px 50px;}
  .q-counter{flex-wrap:wrap;}
}
</style>
</head>
<body>
<div class="grain"></div>

<!-- ===================== HOME VIEW ===================== -->
<div class="home-view" id="homeView">
  <div class="app">

    <div class="top-row">
      <div class="brand">
        <div class="brand-mark">N</div>
        <div>
          <div class="brand-name">Nocturne</div>
          <div class="brand-sub">Révisions Brevet</div>
        </div>
      </div>
      <div class="streak-pill">
        <span class="streak-flame">🔥</span>
        <span>Série : <span class="streak-num" id="globalStreak">0</span></span>
      </div>
    </div>

    <div class="hero">
      <div class="hero-eyebrow">Session 3e · Diplôme National du Brevet</div>
      <h1>Réviser <em>tard le soir</em>,<br>réussir le grand jour.</h1>
      <p>Six matières, plus de 300 questions calibrées difficiles, correction immédiate et explication à chaque réponse. Choisis ta matière, le reste suit.</p>
    </div>

    <div class="section-label">
      <h2>Choisir une matière</h2>
      <div class="rule"></div>
      <span class="count" id="totalQCount">— questions au total</span>
    </div>

    <div class="subject-grid" id="subjectGrid"></div>

    <div class="footnote">
      <p>Ta progression est conservée sur cet appareil. Les questions sont mélangées à chaque tentative.</p>
      <button class="reset-btn" id="resetProgressBtn">Réinitialiser ma progression</button>
    </div>
  </div>
</div>

<!-- ===================== QUIZ VIEW ===================== -->
<div class="quiz-view" id="quizView">
  <div class="quiz-shell">
    <div class="quiz-top">
      <button class="back-btn" id="backBtn">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><path d="M15 18l-6-6 6-6"/></svg>
        Quitter
      </button>
      <div class="quiz-meta">
        <div class="quiz-subject-tag" id="quizSubjectTag"><span class="dot"></span><span id="quizSubjectName"></span></div>
      </div>
    </div>

    <div class="progress-track"><div class="progress-fill" id="progressFill" style="width:0%"></div></div>

    <div class="q-counter">
      <span id="qCounterText">Question 1 / 50</span>
      <span class="type-pill" id="qTypePill">QCM</span>
    </div>

    <div class="q-card" id="qCard">
      <p class="q-text" id="qText"></p>
      <div class="choices" id="choicesContainer"></div>
      <div class="vf-row" id="vfContainer" style="display:none;"></div>

      <div class="feedback" id="feedbackPanel">
        <div class="feedback-title" id="feedbackTitle"></div>
        <p class="feedback-text" id="feedbackText"></p>
      </div>

      <div class="next-row">
        <button class="next-btn" id="nextBtn">
          <span id="nextBtnLabel">Question suivante</span>
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round"><path d="M9 6l6 6-6 6"/></svg>
        </button>
      </div>
    </div>
  </div>
</div>

<!-- ===================== RESULTS VIEW ===================== -->
<div class="results-view" id="resultsView">
  <div class="quiz-shell">
    <div class="results-card">
      <div class="results-ring">
        <svg width="160" height="160" viewBox="0 0 160 160">
          <circle class="ring-bg" cx="80" cy="80" r="70"></circle>
          <circle class="ring-fg" id="ringFg" cx="80" cy="80" r="70" stroke-dasharray="439.8" stroke-dashoffset="439.8"></circle>
        </svg>
        <div class="results-score">
          <div class="num" id="resultPercent">0%</div>
          <div class="denom" id="resultFraction">0 / 0</div>
        </div>
      </div>
      <h2 class="results-title" id="resultsTitle">Bilan</h2>
      <p class="results-sub" id="resultsSub"></p>

      <div class="results-stats">
        <div class="rstat"><div class="v" id="statCorrect">0</div><div class="l">Bonnes</div></div>
        <div class="rstat"><div class="v" id="statWrong">0</div><div class="l">Erreurs</div></div>
        <div class="rstat"><div class="v" id="statBestStreak">0</div><div class="l">Meilleure série</div></div>
      </div>

      <div class="results-actions">
        <button class="btn-primary" id="retryBtn">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><path d="M3 12a9 9 0 1 0 3-6.7M3 3v6h6"/></svg>
          Refaire cette matière
        </button>
        <button class="btn-ghost" id="homeBtn">Retour à l'accueil</button>
      </div>

      <div class="missed-review" id="missedReview" style="display:none;">
        <h3>À revoir</h3>
        <div id="missedList"></div>
      </div>
    </div>
  </div>
</div>

<script>

// ===== data_histoire.js =====
const QUESTIONS_HISTOIRE = [
  { q: "En quelle année éclate la Première Guerre mondiale ?", type: "qcm", choices: ["1912", "1914", "1916", "1918"], correct: 1, exp: "L'attentat de Sarajevo (28 juin 1914) déclenche l'engrenage des alliances et le début du conflit." },
  { q: "Le système des tranchées illustre avant tout :", type: "qcm", choices: ["Une guerre de mouvement rapide", "Une guerre d'usure et de position", "L'absence d'artillerie", "Une guerre exclusivement navale"], correct: 1, exp: "Dès 1914-1915, le front se fige : les armées s'enterrent et la guerre devient une guerre de position, très coûteuse en vies." },
  { q: "La bataille de Verdun (1916) est restée dans les mémoires comme :", type: "qcm", choices: ["Une victoire éclair allemande", "Le symbole de la résistance et du sacrifice français", "Le premier usage de l'arme nucléaire", "Une bataille uniquement navale"], correct: 1, exp: "Verdun symbolise l'acharnement des deux armées et l'ampleur des pertes humaines (environ 300 000 morts)." },
  { q: "Le génocide des Arméniens est perpétré pendant la Première Guerre mondiale par :", type: "qcm", choices: ["L'Empire russe", "L'Empire ottoman", "L'Empire austro-hongrois", "Le Royaume-Uni"], correct: 1, exp: "À partir de 1915, les autorités ottomanes organisent la déportation et l'extermination de la population arménienne." },
  { q: "Le traité de Versailles (1919) impose à l'Allemagne :", type: "qcm", choices: ["Une augmentation de son territoire", "Des réparations financières et une réduction de son armée", "Une alliance militaire avec la France", "L'annexion de l'Alsace-Lorraine"], correct: 1, exp: "L'Allemagne perd des territoires, doit payer de lourdes réparations et voit son armée strictement limitée." },
  { q: "Vrai ou faux : la Première Guerre mondiale a mobilisé des soldats venus des colonies françaises.", type: "vf", correct: true, exp: "Des tirailleurs sénégalais, des soldats nord-africains et indochinois ont combattu pour la France, preuve de l'ampleur impériale du conflit." },
  { q: "Quel évènement de 1917 affaiblit durablement l'effort de guerre russe ?", type: "qcm", choices: ["La révolution bolchevique", "L'entrée en guerre des États-Unis", "La bataille de la Marne", "Le traité de Brest-Litovsk seul"], correct: 0, exp: "La révolution d'octobre 1917 porte les bolcheviks au pouvoir ; ils négocient ensuite la paix séparée de Brest-Litovsk en 1918." },
  { q: "La crise économique de 1929 trouve son origine principale dans :", type: "qcm", choices: ["Le krach boursier de Wall Street", "Une famine en Europe", "Une guerre commerciale franco-allemande", "La chute du mur de Berlin"], correct: 0, exp: "Le krach d'octobre 1929 à New York déclenche une crise bancaire et industrielle qui se propage au monde entier." },
  { q: "Vrai ou faux : la crise de 1929 reste cantonnée aux États-Unis et n'a aucun effet en Europe.", type: "vf", correct: false, exp: "Faux : la crise se mondialise rapidement, provoquant chômage massif et instabilité politique en Europe, notamment en Allemagne." },
  { q: "Quel régime profite particulièrement de la crise économique pour s'imposer en Allemagne ?", type: "qcm", choices: ["Le parti communiste", "Le NSDAP (parti nazi) d'Hitler", "Le parti monarchiste", "Le parti social-démocrate seul"], correct: 1, exp: "Le chômage massif et la défiance envers la République de Weimar profitent à la propagande nazie, qui arrive au pouvoir en 1933." },
  { q: "Le terme 'totalitarisme' désigne un régime qui :", type: "qcm", choices: ["Organise des élections libres régulières", "Contrôle tous les aspects de la société et écrase les libertés", "Laisse une presse totalement indépendante", "Limite son pouvoir au seul domaine économique"], correct: 1, exp: "Un État totalitaire fusionne parti unique et État, utilise la propagande, la terreur et encadre la totalité de la vie sociale." },
  { q: "Staline met en place en URSS un système économique fondé sur :", type: "qcm", choices: ["Le libre marché", "La planification et la collectivisation forcée", "La propriété privée généralisée", "Le système féodal"], correct: 1, exp: "Les plans quinquennaux et la collectivisation des terres (kolkhozes) caractérisent l'économie stalinienne, au prix de famines et de répression." },
  { q: "Vrai ou faux : les démocraties européennes de l'entre-deux-guerres sont restées toutes stables face à la crise.", type: "vf", correct: false, exp: "Faux : plusieurs démocraties (Allemagne, Italie, Espagne) basculent vers des régimes autoritaires ou totalitaires." },
  { q: "La guerre civile espagnole (1936-1939) oppose principalement :", type: "qcm", choices: ["Les nationalistes de Franco aux républicains", "La France à l'Espagne", "Le Portugal à l'Espagne", "Les monarchistes aux colons"], correct: 0, exp: "Le coup d'État militaire de Franco en 1936 déclenche une guerre civile contre le gouvernement républicain, jusqu'à la victoire franquiste en 1939." },
  { q: "Pendant la guerre d'Espagne, les puissances étrangères qui soutiennent Franco sont :", type: "qcm", choices: ["L'URSS et le Mexique", "L'Allemagne nazie et l'Italie fasciste", "Le Royaume-Uni et les États-Unis", "La France et la Belgique"], correct: 1, exp: "Hitler et Mussolini fournissent armes, troupes et soutien aérien aux nationalistes espagnols." },
  { q: "Le bombardement de Guernica (1937) est devenu un symbole de :", type: "qcm", choices: ["La victoire républicaine", "La violence de guerre contre les civils", "La paix négociée", "La neutralité espagnole"], correct: 1, exp: "Ce bombardement, immortalisé par Picasso, illustre les souffrances infligées aux populations civiles pendant le conflit." },
  { q: "Vrai ou faux : la Seconde Guerre mondiale débute par l'invasion de la Pologne par l'Allemagne en septembre 1939.", type: "vf", correct: true, exp: "Le 1er septembre 1939, l'Allemagne envahit la Pologne ; la France et le Royaume-Uni déclarent la guerre à l'Allemagne deux jours plus tard." },
  { q: "On qualifie la Seconde Guerre mondiale de 'guerre d'anéantissement' car :", type: "qcm", choices: ["Elle ne touche que les militaires", "Elle vise la destruction totale de l'adversaire, y compris des civils", "Elle se limite à l'Europe", "Elle dure moins d'un an"], correct: 1, exp: "Bombardements de villes, sièges, famines organisées et génocides montrent une volonté d'anéantir totalement l'ennemi, civils compris." },
  { q: "La Shoah désigne :", type: "qcm", choices: ["La déportation des prisonniers de guerre", "L'extermination systématique des Juifs d'Europe par les nazis", "La famine en Ukraine", "Les bombardements alliés sur l'Allemagne"], correct: 1, exp: "Politique d'extermination planifiée, la Shoah a causé la mort de six millions de Juifs européens." },
  { q: "Le siège de Leningrad (1941-1944) illustre :", type: "qcm", choices: ["Une victoire allemande rapide", "Les souffrances extrêmes infligées à la population civile", "Une trêve entre Allemands et Soviétiques", "Une bataille exclusivement navale"], correct: 1, exp: "Ce siège de plus de 800 jours provoque la mort d'environ un million de civils par la faim, le froid et les bombardements." },
  { q: "Vrai ou faux : les camps de concentration et les camps d'extermination nazis ont la même fonction.", type: "vf", correct: false, exp: "Faux : les camps de concentration servent à l'enfermement et au travail forcé, tandis que les camps d'extermination (comme Auschwitz-Birkenau) sont conçus pour tuer massivement." },
  { q: "En juin 1940, la France signe l'armistice avec l'Allemagne ; le pays est alors :", type: "qcm", choices: ["Totalement libre et indépendant", "Divisé entre zone occupée et zone libre sous Vichy", "Annexé entièrement par l'Italie", "Gouverné depuis Londres"], correct: 1, exp: "La France est coupée en deux : le nord et la côte atlantique sont occupés, le sud est administré par le régime de Vichy dirigé par Pétain." },
  { q: "Le régime de Vichy pratique une politique de collaboration qui inclut :", type: "qcm", choices: ["La protection systématique de tous les citoyens", "La participation à la persécution des Juifs de France", "Le refus total de coopérer avec l'occupant", "L'indépendance totale vis-à-vis de l'Allemagne"], correct: 1, exp: "Vichy collabore activement, notamment via le statut des Juifs (1940) et la participation aux rafles, comme celle du Vél' d'Hiv en 1942." },
  { q: "L'appel du 18 juin 1940 est lancé par :", type: "qcm", choices: ["Philippe Pétain", "Charles de Gaulle", "Jean Moulin", "Pierre Laval"], correct: 1, exp: "Depuis Londres, de Gaulle appelle les Français à poursuivre le combat et refuse la défaite, fondant la France libre." },
  { q: "Vrai ou faux : la Résistance française est un mouvement unifié dès 1940, sans aucune divergence interne.", type: "vf", correct: false, exp: "Faux : la Résistance regroupe des mouvements divers (gaullistes, communistes, etc.) qui ne s'unifient que progressivement, notamment avec le CNR en 1943." },
  { q: "Jean Moulin joue un rôle clé dans la Résistance car il :", type: "qcm", choices: ["Dirige l'armée allemande en France", "Unifie les mouvements de résistance au sein du CNR", "Signe l'armistice de 1940", "Préside le régime de Vichy"], correct: 1, exp: "Envoyé par de Gaulle, Jean Moulin parvient à fédérer les différents réseaux de résistance dans le Conseil national de la Résistance (1943)." },
  { q: "Le débarquement de Normandie a lieu le :", type: "qcm", choices: ["8 mai 1945", "6 juin 1944", "1er septembre 1939", "11 novembre 1918"], correct: 1, exp: "Le 6 juin 1944, les Alliés débarquent sur les côtes normandes, ouvrant un second front décisif à l'ouest." },
  { q: "La capitulation de l'Allemagne nazie est signée le :", type: "qcm", choices: ["6 juin 1944", "8 mai 1945", "2 septembre 1945", "11 novembre 1918"], correct: 1, exp: "Le 8 mai 1945 marque la fin des combats en Europe, après la chute de Berlin." },
  { q: "Les bombes atomiques sur Hiroshima et Nagasaki sont larguées en :", type: "qcm", choices: ["Juin 1944", "Mai 1945", "Août 1945", "Septembre 1945"], correct: 2, exp: "Les 6 et 9 août 1945, les États-Unis larguent deux bombes atomiques, précipitant la capitulation japonaise le 2 septembre 1945." },
  { q: "Vrai ou faux : le bilan humain de la Seconde Guerre mondiale est principalement militaire, les civils étant peu touchés.", type: "vf", correct: false, exp: "Faux : les pertes civiles, dues aux bombardements, génocides et famines, dépassent largement les pertes militaires dans ce conflit." },
  { q: "La décolonisation de l'Inde en 1947 s'accompagne :", type: "qcm", choices: ["D'une unification pacifique totale", "D'une partition violente entre Inde et Pakistan", "Du maintien du Raj britannique", "D'une guerre avec la Chine"], correct: 1, exp: "L'indépendance de 1947 entraîne la partition entre l'Inde et le Pakistan, provoquant des déplacements de population massifs et des violences intercommunautaires." },
  { q: "La guerre d'Algérie (1954-1962) se termine par :", type: "qcm", choices: ["Le maintien de l'Algérie française", "Les accords d'Évian et l'indépendance algérienne", "Une annexion par le Maroc", "Une victoire militaire totale de la France"], correct: 1, exp: "Les accords d'Évian de mars 1962 actent la fin de la guerre et l'indépendance de l'Algérie, proclamée en juillet 1962." },
  { q: "Vrai ou faux : la décolonisation s'est toujours faite de manière pacifique et négociée.", type: "vf", correct: false, exp: "Faux : si certaines décolonisations sont négociées (Maroc, Tunisie), d'autres se font dans la violence (Algérie, Indochine)." },
  { q: "La conférence de Bandung (1955) marque :", type: "qcm", choices: ["La création de l'ONU", "L'émergence du mouvement des pays non-alignés", "La fin de la guerre froide", "La création de l'Union européenne"], correct: 1, exp: "Réunissant des pays d'Asie et d'Afrique, cette conférence affirme la volonté de ne pas choisir entre les deux blocs de la guerre froide." },
  { q: "Le terme 'guerre froide' désigne :", type: "qcm", choices: ["Un conflit armé direct entre États-Unis et URSS", "Un affrontement indirect entre deux blocs idéologiques rivaux", "Une guerre climatique", "Un conflit en Antarctique"], correct: 1, exp: "Les deux superpuissances s'affrontent sans jamais se combattre directement, via la propagande, la course aux armements et des conflits par procuration." },
  { q: "Le mur de Berlin est construit en :", type: "qcm", choices: ["1949", "1961", "1975", "1989"], correct: 1, exp: "Construit en août 1961 par la RDA, le mur symbolise la division de l'Europe et de l'Allemagne pendant la guerre froide." },
  { q: "Vrai ou faux : la crise de Cuba en 1962 a fait craindre une guerre nucléaire directe entre les deux blocs.", type: "vf", correct: true, exp: "L'installation de missiles soviétiques à Cuba provoque une crise majeure, résolue par des négociations évitant un conflit ouvert." },
  { q: "La chute du mur de Berlin a lieu en :", type: "qcm", choices: ["1985", "1989", "1991", "1995"], correct: 1, exp: "Le 9 novembre 1989, le mur tombe, symbole de la fin de la guerre froide et de la réunification allemande à venir." },
  { q: "La construction européenne après 1945 vise avant tout à :", type: "qcm", choices: ["Renforcer le colonialisme", "Garantir la paix et la coopération économique entre États européens", "Créer une armée unique mondiale", "Réduire le nombre de pays membres de l'ONU"], correct: 1, exp: "Né de la volonté d'éviter un nouveau conflit, le projet européen débute par la CECA (1951) pour lier les économies française et allemande." },
  { q: "Le traité de Rome (1957) crée :", type: "qcm", choices: ["L'ONU", "La Communauté économique européenne (CEE)", "L'OTAN", "Le Conseil de l'Europe"], correct: 1, exp: "Ce traité fondateur établit un marché commun entre six États européens, base de la future Union européenne." },
  { q: "Vrai ou faux : l'euro est devenu la monnaie de tous les pays membres de l'Union européenne dès sa création.", type: "vf", correct: false, exp: "Faux : tous les États membres n'ont pas adopté l'euro (par exemple, certains pays ont conservé leur propre monnaie)." },
  { q: "Le traité de Maastricht (1992) a notamment pour conséquence :", type: "qcm", choices: ["La dissolution de l'Union européenne", "La création de l'Union européenne et les bases de la monnaie unique", "Le retrait du Royaume-Uni", "La fin de la libre circulation"], correct: 1, exp: "Ce traité transforme la CEE en Union européenne et prépare l'instauration de l'euro." },
  { q: "Les attentats du 11 septembre 2001 visent notamment :", type: "qcm", choices: ["Le Kremlin à Moscou", "Le World Trade Center et le Pentagone aux États-Unis", "La tour Eiffel à Paris", "Le palais de Buckingham à Londres"], correct: 1, exp: "Ces attentats, perpétrés par Al-Qaïda, marquent un tournant dans la perception du terrorisme international." },
  { q: "Vrai ou faux : la fin de la guerre froide a mis fin à toute forme de tension internationale dans le monde.", type: "vf", correct: false, exp: "Faux : de nouvelles tensions apparaissent (terrorisme, conflits régionaux, montée de puissances émergentes)." },
  { q: "L'ONU a été créée en :", type: "qcm", choices: ["1919", "1945", "1957", "1991"], correct: 1, exp: "Créée après la Seconde Guerre mondiale, l'ONU vise à maintenir la paix et la sécurité internationales." },
  { q: "Le génocide au Rwanda a eu lieu en :", type: "qcm", choices: ["1985", "1994", "2001", "2010"], correct: 1, exp: "En 1994, l'extermination des Tutsi par des extrémistes hutu fait environ 800 000 morts en quelques mois." },
  { q: "Vrai ou faux : depuis 1989, le monde est devenu totalement unipolaire et stable, sans nouvelles puissances émergentes.", type: "vf", correct: false, exp: "Faux : de nouvelles puissances (Chine, Inde, etc.) émergent et le monde devient plus multipolaire au fil du temps." },
  { q: "La construction européenne après 1989 s'élargit principalement vers :", type: "qcm", choices: ["L'Amérique du Sud", "Les anciens pays du bloc communiste d'Europe de l'Est", "L'Afrique du Nord", "L'Asie du Sud-Est"], correct: 1, exp: "Après la chute du communisme, plusieurs pays d'Europe de l'Est rejoignent l'Union européenne (élargissements de 2004 et suivants)." },
  { q: "La laïcité en France repose sur le principe de :", type: "qcm", choices: ["L'interdiction de toute religion", "La séparation des Églises et de l'État, garantissant la liberté de conscience", "L'imposition d'une religion d'État", "La suppression de la liberté de culte"], correct: 1, exp: "La loi de 1905 instaure la neutralité de l'État, qui garantit en retour la liberté de croire ou de ne pas croire." },
  { q: "Vrai ou faux : la loi de séparation des Églises et de l'État date de 1905.", type: "vf", correct: true, exp: "Cette loi fondatrice établit la laïcité en France, séparant le pouvoir politique des institutions religieuses." },
  { q: "Le 'devoir de mémoire' désigne :", type: "qcm", choices: ["L'oubli volontaire des conflits passés", "La transmission et la commémoration des évènements tragiques de l'histoire", "Un examen scolaire annuel", "Une loi sur l'économie"], correct: 1, exp: "Il s'agit de préserver la mémoire des victimes (guerres, génocides) pour en tirer des leçons collectives." },
  { q: "Le procès de Nuremberg (1945-1946) juge :", type: "qcm", choices: ["Les criminels de guerre nazis pour crimes contre l'humanité", "Les dirigeants soviétiques", "Les responsables de la guerre d'Algérie", "Les chefs d'État alliés"], correct: 0, exp: "Ce procès international établit pour la première fois la notion juridique de crime contre l'humanité." }
];


// ===== data_geographie.js =====
const QUESTIONS_GEOGRAPHIE = [
  { q: "Une 'aire urbaine' désigne :", type: "qcm", choices: ["Un pôle urbain et sa couronne périurbaine liés par les déplacements domicile-travail", "Une zone strictement rurale", "Un département entier", "Une zone exclusivement industrielle"], correct: 0, exp: "L'aire urbaine regroupe une ville-centre, ses banlieues et les communes périurbaines dont une part importante des actifs travaille dans le pôle." },
  { q: "La métropolisation désigne :", type: "qcm", choices: ["Le déclin des grandes villes", "La concentration croissante des populations et activités dans les grandes villes", "L'abandon des campagnes par tous les habitants", "La disparition des banlieues"], correct: 1, exp: "Ce phénomène mondial concentre pouvoir économique, population et fonctions de commandement dans un nombre restreint de grandes métropoles." },
  { q: "Vrai ou faux : en France, la majorité de la population vit aujourd'hui dans des espaces urbains.", type: "vf", correct: true, exp: "Plus de 80% de la population française vit dans une aire urbaine, preuve de l'intensité de l'urbanisation du territoire." },
  { q: "L'étalement urbain a pour conséquence principale :", type: "qcm", choices: ["La densification du centre-ville uniquement", "L'extension des espaces périurbains et l'artificialisation des sols", "La disparition totale des villes", "La baisse de la consommation d'espace"], correct: 1, exp: "Les villes s'étendent sur les espaces ruraux environnants, consommant des terres agricoles et naturelles, ce qui pose des enjeux environnementaux." },
  { q: "La gentrification d'un quartier urbain désigne :", type: "qcm", choices: ["L'arrivée de populations plus aisées remplaçant progressivement les habitants populaires", "Le départ de tous les habitants vers la campagne", "La construction exclusive de logements sociaux", "L'abandon total du quartier"], correct: 0, exp: "Ce processus de réhabilitation s'accompagne souvent d'une hausse des prix qui repousse les populations les plus modestes." },
  { q: "Vrai ou faux : les espaces de faible densité en France sont uniquement des espaces en déclin, sans aucun dynamisme.", type: "vf", correct: false, exp: "Faux : certains espaces ruraux connaissent un regain démographique et économique (tourisme, énergies renouvelables, agriculture spécialisée)." },
  { q: "Parmi les atouts des espaces de faible densité, on trouve :", type: "qcm", choices: ["La saturation des transports", "Le cadre de vie, le patrimoine naturel et le potentiel touristique", "La densité de population très élevée", "L'absence totale d'activité économique"], correct: 1, exp: "Ces espaces valorisent souvent leur cadre naturel, leur patrimoine et développent des activités touristiques, agricoles ou énergétiques spécifiques." },
  { q: "La 'diagonale des faibles densités' en France traverse principalement :", type: "qcm", choices: ["L'Île-de-France et la Côte d'Azur", "Le centre du pays, des Ardennes aux Landes", "Uniquement les littoraux", "La région parisienne"], correct: 1, exp: "Cette diagonale rurale, peu peuplée, s'étend du nord-est au sud-ouest de la France métropolitaine." },
  { q: "Vrai ou faux : aménager un territoire signifie uniquement construire des routes.", type: "vf", correct: false, exp: "Faux : l'aménagement du territoire englobe aussi les transports, l'urbanisme, les équipements publics, l'environnement et le développement économique." },
  { q: "Les politiques d'aménagement du territoire visent notamment à :", type: "qcm", choices: ["Accentuer les inégalités entre régions", "Réduire les inégalités territoriales et favoriser un développement équilibré", "Supprimer les services publics ruraux", "Concentrer toute l'activité dans une seule ville"], correct: 1, exp: "L'État et les collectivités cherchent à corriger les déséquilibres entre territoires dynamiques et territoires en difficulté." },
  { q: "Les DROM (Départements et Régions d'Outre-Mer) ont pour particularité :", type: "qcm", choices: ["De ne pas appartenir à la République française", "D'avoir le même statut juridique que les régions métropolitaines, avec des spécificités", "D'utiliser une monnaie différente de l'euro", "De ne pas être représentés au Parlement"], correct: 1, exp: "Les DROM (Guadeloupe, Martinique, Guyane, La Réunion, Mayotte) sont pleinement intégrés à la République et à l'Union européenne, tout en bénéficiant d'adaptations législatives." },
  { q: "Vrai ou faux : les COM (collectivités d'outre-mer) ont exactement le même statut que les DROM.", type: "vf", correct: false, exp: "Faux : les COM (comme la Polynésie française) disposent d'une autonomie plus large que les DROM, notamment en matière législative." },
  { q: "La principale différence entre les DROM et les COM réside dans :", type: "qcm", choices: ["Le climat", "Le degré d'autonomie politique et législative", "La langue parlée", "La taille du territoire"], correct: 1, exp: "Les COM disposent d'une autonomie politique plus importante que les DROM, qui appliquent en principe le droit commun français." },
  { q: "Les territoires ultramarins français sont stratégiques car ils offrent à la France :", type: "qcm", choices: ["Une absence totale d'enjeux maritimes", "La plus grande zone économique exclusive (ZEE) du monde", "Un accès limité aux océans", "Une frontière unique avec l'Allemagne"], correct: 1, exp: "Grâce à ses outre-mer, la France dispose de la deuxième ZEE mondiale, riche en ressources marines et stratégiques." },
  { q: "Vrai ou faux : les territoires ultramarins ne connaissent aucun risque naturel particulier.", type: "vf", correct: false, exp: "Faux : cyclones, éruptions volcaniques (Réunion), séismes (Antilles) exposent fortement ces territoires aux risques naturels." },
  { q: "L'Union européenne constitue pour la France un espace de référence car :", type: "qcm", choices: ["Elle n'a aucune influence sur l'économie française", "Elle structure les échanges économiques, les politiques régionales et la mobilité des citoyens", "Elle impose une seule langue officielle", "Elle remplace entièrement les régions françaises"], correct: 1, exp: "L'UE influence fortement les politiques régionales, le commerce, l'agriculture (PAC) et la libre circulation des personnes et des biens." },
  { q: "La PAC (Politique Agricole Commune) vise principalement à :", type: "qcm", choices: ["Réduire la production agricole en Europe", "Soutenir les agriculteurs et réguler les marchés agricoles européens", "Interdire les exportations agricoles", "Supprimer toute aide aux agriculteurs"], correct: 1, exp: "La PAC est une politique européenne majeure de soutien financier et de régulation au secteur agricole des États membres." },
  { q: "Vrai ou faux : la France est le premier pays bénéficiaire de la PAC en valeur absolue parmi les États membres.", type: "vf", correct: true, exp: "Grâce à l'importance de son secteur agricole, la France perçoit historiquement la plus grande part des aides de la PAC." },
  { q: "Les fonds européens régionaux (FEDER) financent principalement :", type: "qcm", choices: ["Les dépenses militaires", "Des projets de développement économique et de réduction des inégalités régionales", "Les retraites des fonctionnaires", "Le budget des partis politiques"], correct: 1, exp: "Le FEDER aide au développement des infrastructures et à la réduction des écarts économiques entre régions européennes." },
  { q: "Une métropole se distingue d'une ville moyenne par :", type: "qcm", choices: ["Une absence totale d'activité économique", "Une concentration de fonctions de commandement (finance, recherche, décision politique)", "Une population strictement rurale", "L'absence de transports en commun"], correct: 1, exp: "Les métropoles concentrent les sièges sociaux, universités, centres de recherche et institutions, ce qui les distingue des villes moyennes." },
  { q: "Vrai ou faux : toutes les métropoles françaises connaissent une croissance démographique identique.", type: "vf", correct: false, exp: "Faux : certaines métropoles (Bordeaux, Toulouse) croissent fortement, d'autres connaissent une croissance plus modérée voire un déclin relatif." },
  { q: "Le périurbain se caractérise principalement par :", type: "qcm", choices: ["Une forte densité comparable au centre-ville", "Une dominante pavillonnaire et une dépendance à l'automobile", "L'absence totale d'habitants", "Des immeubles de plus de 50 étages"], correct: 1, exp: "Les espaces périurbains, souvent composés de maisons individuelles, dépendent fortement de la voiture pour les déplacements quotidiens." },
  { q: "La mondialisation se traduit dans les territoires français notamment par :", type: "qcm", choices: ["L'isolement total des régions françaises", "Le développement des grands ports, aéroports et zones logistiques connectés au monde", "La disparition de tout commerce extérieur", "La fermeture des frontières"], correct: 1, exp: "Les grands ports (Le Havre, Marseille) et hubs aéroportuaires (Roissy) intègrent la France dans les flux économiques mondiaux." },
  { q: "Vrai ou faux : le port du Havre fait partie des grandes portes d'entrée maritimes de la France dans la mondialisation.", type: "vf", correct: true, exp: "Le Havre, avec Marseille et Dunkerque, constitue l'une des principales façades maritimes françaises connectées aux échanges mondiaux." },
  { q: "Les espaces productifs agricoles français se transforment notamment sous l'effet :", type: "qcm", choices: ["De la disparition totale de l'agriculture", "De la mécanisation, de la spécialisation régionale et des normes environnementales", "De l'absence de toute exportation", "D'une interdiction des cultures céréalières"], correct: 1, exp: "L'agriculture française se modernise, se spécialise par région (céréales dans le Bassin parisien, élevage dans le Massif central) et doit répondre à des exigences environnementales croissantes." },
  { q: "Vrai ou faux : la France métropolitaine ne possède qu'une seule façade maritime.", type: "vf", correct: false, exp: "Faux : la France métropolitaine possède plusieurs façades maritimes (Manche, Atlantique, Méditerranée)." },
  { q: "Le tourisme dans les espaces de faible densité contribue à :", type: "qcm", choices: ["L'abandon total de ces territoires", "Une diversification économique et au maintien des populations locales", "La disparition des emplois locaux", "L'interdiction des activités agricoles"], correct: 1, exp: "Le tourisme rural ou de montagne crée des emplois, valorise le patrimoine et participe au maintien d'une activité économique locale." },
  { q: "Les espaces productifs industriels en France ont connu depuis les années 1970 :", type: "qcm", choices: ["Une croissance ininterrompue dans toutes les régions", "Une désindustrialisation marquée dans certaines régions et une reconversion partielle", "La disparition totale de l'industrie", "Une stabilité parfaite sans aucun changement"], correct: 1, exp: "Certaines régions industrielles traditionnelles (Nord, Lorraine) ont connu un fort déclin, tandis que de nouvelles filières (aéronautique, high-tech) se sont développées ailleurs." },
  { q: "Vrai ou faux : Toulouse est un pôle majeur de l'industrie aéronautique en France.", type: "vf", correct: true, exp: "Toulouse, siège d'Airbus, constitue l'un des principaux pôles aéronautiques mondiaux." },
  { q: "Un 'territoire' en géographie désigne :", type: "qcm", choices: ["Une simple surface vide d'habitants", "Un espace approprié et aménagé par une société humaine", "Uniquement une zone militaire", "Un espace exclusivement naturel sans aucune intervention humaine"], correct: 1, exp: "Le territoire est un espace que les sociétés humaines occupent, organisent, aménagent et auquel elles donnent du sens." },
  { q: "Vrai ou faux : la croissance urbaine se traduit uniquement par l'extension horizontale des villes.", type: "vf", correct: false, exp: "Faux : la croissance urbaine peut aussi se faire par densification verticale (immeubles plus hauts) en plus de l'étalement horizontal." },
  { q: "Le réseau de transport à grande vitesse (TGV) en France a pour objectif principal :", type: "qcm", choices: ["De relier uniquement les zones rurales isolées", "De connecter rapidement les grandes métropoles entre elles et à Paris", "De remplacer totalement les transports aériens", "De desservir exclusivement les zones frontalières"], correct: 1, exp: "Le réseau TGV structure le territoire en reliant rapidement les principales métropoles françaises, renforçant souvent la centralité parisienne." },
  { q: "L'effet tunnel du TGV désigne :", type: "qcm", choices: ["Le fait que toutes les villes profitent également du TGV", "Le fait que les territoires traversés mais non desservis par une gare ne profitent pas de la grande vitesse", "Une innovation technique du train", "Un problème de signalisation ferroviaire"], correct: 1, exp: "Les territoires traversés sans gare TGV ne bénéficient pas des effets positifs de la grande vitesse, créant des inégalités territoriales." },
  { q: "Vrai ou faux : les littoraux français sont parmi les espaces les plus attractifs du territoire.", type: "vf", correct: true, exp: "Tourisme, activités économiques et qualité de vie rendent les littoraux français très attractifs, entraînant une forte pression démographique et environnementale." },
  { q: "La littoralisation des activités économiques désigne :", type: "qcm", choices: ["Le déplacement des activités vers l'intérieur des terres", "La concentration croissante des populations et activités sur les littoraux", "La disparition de toute activité portuaire", "Un phénomène propre à l'agriculture uniquement"], correct: 1, exp: "Ports, tourisme et industries se concentrent de plus en plus sur les façades maritimes, accentuant les pressions sur ces espaces." },
  { q: "Vrai ou faux : l'aménagement du territoire en France relève uniquement de la responsabilité de l'État, sans aucune intervention des collectivités locales.", type: "vf", correct: false, exp: "Faux : les régions, départements et communes jouent un rôle croissant dans l'aménagement du territoire, en complément de l'État." },
  { q: "La revitalisation des centres-villes moyens vise à lutter contre :", type: "qcm", choices: ["La sur-densité urbaine", "La désertification commerciale et le déclin démographique des centres", "L'excès de transports en commun", "La pollution de l'air uniquement"], correct: 1, exp: "Certains centres-villes de villes moyennes connaissent une fermeture de commerces et une baisse de population, ce qui justifie des politiques de revitalisation." },
  { q: "Le programme 'Action cœur de ville' en France a pour objectif de :", type: "qcm", choices: ["Développer exclusivement les très grandes métropoles", "Redynamiser les villes moyennes et leurs centres", "Supprimer les services publics ruraux", "Encourager l'étalement urbain"], correct: 1, exp: "Ce dispositif national vise à revitaliser le commerce, l'habitat et les services dans les villes moyennes françaises." },
  { q: "Vrai ou faux : les espaces de montagne en France ne connaissent aucune activité économique notable.", type: "vf", correct: false, exp: "Faux : tourisme (ski), élevage, sylviculture et énergies renouvelables (hydroélectricité) animent fortement les espaces de montagne." },
  { q: "L'agriculture intensive en zones de grande culture (Bassin parisien) repose sur :", type: "qcm", choices: ["De petites parcelles non mécanisées", "De grandes exploitations mécanisées et fortement productives", "L'absence totale d'engrais", "Des cultures exclusivement biologiques"], correct: 1, exp: "Le Bassin parisien illustre une agriculture intensive, mécanisée, orientée vers les grandes cultures céréalières à haut rendement." },
  { q: "Vrai ou faux : la France est l'un des principaux pays exportateurs de produits agricoles au monde.", type: "vf", correct: true, exp: "Grâce à une agriculture performante et diversifiée, la France figure parmi les grandes puissances agricoles exportatrices mondiales." },
  { q: "Les espaces frontaliers français bénéficient souvent de :", type: "qcm", choices: ["Une absence totale d'échanges avec les pays voisins", "Une coopération transfrontalière en matière économique et de transports", "Un isolement complet du reste du territoire", "L'interdiction de circuler vers le pays voisin"], correct: 1, exp: "De nombreux espaces frontaliers développent des coopérations économiques, des bassins d'emploi communs et des infrastructures partagées avec les pays voisins." },
  { q: "Le concept de 'France des marges' désigne :", type: "qcm", choices: ["Les très grandes métropoles dynamiques", "Les territoires moins intégrés aux dynamiques de la mondialisation et de la métropolisation", "Uniquement les territoires d'outre-mer", "Les zones les plus riches du pays"], correct: 1, exp: "Certains territoires ruraux ou anciennement industriels restent moins connectés aux grands réseaux de la mondialisation, accentuant des inégalités territoriales." },
  { q: "Vrai ou faux : les zones rurales françaises sont systématiquement plus pauvres que les zones urbaines.", type: "vf", correct: false, exp: "Faux : certaines zones rurales sont dynamiques et prospères (agriculture spécialisée, tourisme), tandis que des poches de pauvreté existent aussi en milieu urbain." },
  { q: "Le développement durable appliqué à l'aménagement urbain vise notamment à :", type: "qcm", choices: ["Augmenter sans limite l'étalement urbain", "Concilier développement économique, justice sociale et préservation de l'environnement", "Supprimer toute construction nouvelle", "Favoriser uniquement les transports individuels polluants"], correct: 1, exp: "Les politiques urbaines durables cherchent un équilibre entre croissance, équité sociale et respect de l'environnement (mobilités douces, écoquartiers)." },
  { q: "Vrai ou faux : les écoquartiers visent à réduire l'empreinte écologique des nouveaux espaces urbains.", type: "vf", correct: true, exp: "Ces quartiers intègrent des normes environnementales strictes (énergie, mobilité douce, gestion de l'eau) pour limiter leur impact écologique." },
  { q: "La Guyane française se distingue des autres DROM notamment par :", type: "qcm", choices: ["Son insularité totale", "Sa forêt amazonienne et sa frontière terrestre avec le Brésil et le Suriname", "Son climat polaire", "L'absence de population"], correct: 1, exp: "Contrairement aux autres DROM insulaires, la Guyane est un territoire continental couvert majoritairement par la forêt amazonienne." },
  { q: "Mayotte est devenue département français en :", type: "qcm", choices: ["1946", "1981", "2011", "2020"], correct: 2, exp: "Mayotte devient le 101e département français en mars 2011, après un référendum local." },
  { q: "Vrai ou faux : la Polynésie française est une collectivité d'outre-mer (COM) disposant d'une large autonomie.", type: "vf", correct: true, exp: "La Polynésie française, COM depuis 2004, dispose d'une autonomie étendue dans de nombreux domaines, contrairement aux DROM." },
  { q: "Le rôle des métropoles régionales françaises (Lyon, Toulouse, Bordeaux...) est de :", type: "qcm", choices: ["Concurrencer uniquement Paris sans aucun rayonnement propre", "Structurer leur région et rayonner à l'échelle nationale et internationale", "Se limiter à une fonction agricole", "Disparaître au profit de Paris"], correct: 1, exp: "Ces métropoles concentrent des fonctions économiques, universitaires et culturelles qui structurent leur région et leur donnent un rayonnement propre." }
];


// ===== data_svt.js =====
const QUESTIONS_SVT = [
  { q: "L'ADN est principalement localisé dans :", type: "qcm", choices: ["Le cytoplasme uniquement", "Le noyau de la cellule", "La membrane plasmique", "Les ribosomes"], correct: 1, exp: "Chez les cellules eucaryotes, l'ADN est contenu dans le noyau, organisé en chromosomes." },
  { q: "Vrai ou faux : tous les individus d'une même espèce ont exactement le même ADN.", type: "vf", correct: false, exp: "Faux : chaque individu possède des variations génétiques qui le rendent unique, même au sein d'une même espèce." },
  { q: "Un gène correspond à :", type: "qcm", choices: ["Un fragment d'ADN portant une information héréditaire précise", "Une cellule entière", "Un organe complet", "Une protéine déjà formée"], correct: 0, exp: "Le gène est une séquence d'ADN qui contient l'information nécessaire à la fabrication d'une protéine ou à une fonction biologique." },
  { q: "La méiose est le processus qui permet de produire :", type: "qcm", choices: ["Des cellules somatiques identiques", "Des cellules reproductrices (gamètes) avec la moitié du nombre de chromosomes", "Des cellules cancéreuses", "Des cellules musculaires"], correct: 1, exp: "La méiose réduit de moitié le nombre de chromosomes pour former des gamètes, rétablissant le nombre normal lors de la fécondation." },
  { q: "Vrai ou faux : la fécondation rétablit le nombre normal de chromosomes de l'espèce.", type: "vf", correct: true, exp: "Lors de la fécondation, l'union d'un gamète mâle et d'un gamète femelle (chacun avec n chromosomes) restaure le nombre diploïde (2n)." },
  { q: "Le brassage génétique lors de la méiose explique principalement :", type: "qcm", choices: ["L'identité parfaite entre parents et enfants", "La diversité génétique des individus issus de la reproduction sexuée", "L'absence de variation entre frères et sœurs", "La disparition des chromosomes"], correct: 1, exp: "Le brassage des chromosomes pendant la méiose produit des combinaisons génétiques uniques, expliquant la diversité au sein d'une famille." },
  { q: "Vrai ou faux : une mutation génétique peut être à l'origine d'une maladie héréditaire.", type: "vf", correct: true, exp: "Certaines mutations modifient le fonctionnement d'un gène et peuvent provoquer des maladies génétiques transmissibles." },
  { q: "Le système nerveux central comprend :", type: "qcm", choices: ["Le cerveau et la moelle épinière", "Uniquement les nerfs périphériques", "Le cœur et les poumons", "Les muscles striés"], correct: 0, exp: "Le système nerveux central regroupe le cerveau et la moelle épinière, qui traitent les informations reçues par le corps." },
  { q: "Un réflexe myotatique (comme le réflexe rotulien) est :", type: "qcm", choices: ["Une réponse volontaire et consciente", "Une réponse motrice involontaire et rapide à un stimulus", "Une réaction strictement hormonale", "Un phénomène propre à la digestion"], correct: 1, exp: "Le réflexe est une réponse motrice automatique, rapide et involontaire, ne nécessitant pas l'intervention consciente du cerveau." },
  { q: "Vrai ou faux : la consommation d'alcool n'a aucun effet sur le système nerveux.", type: "vf", correct: false, exp: "Faux : l'alcool perturbe la transmission des messages nerveux, ralentit les réflexes et altère le jugement." },
  { q: "Le rôle du système immunitaire est principalement de :", type: "qcm", choices: ["Produire de l'énergie pour les muscles", "Défendre l'organisme contre les agents pathogènes", "Digérer les aliments", "Réguler la température corporelle uniquement"], correct: 1, exp: "Le système immunitaire protège l'organisme en reconnaissant et en éliminant les micro-organismes pathogènes (bactéries, virus...)." },
  { q: "Les anticorps sont produits par :", type: "qcm", choices: ["Les globules rouges", "Les lymphocytes B", "Les cellules musculaires", "Les neurones"], correct: 1, exp: "Les lymphocytes B, activés lors d'une infection, se différencient en plasmocytes produisant des anticorps spécifiques." },
  { q: "Vrai ou faux : la vaccination repose sur le principe de la mémoire immunitaire.", type: "vf", correct: true, exp: "Le vaccin permet au système immunitaire de 'mémoriser' un agent pathogène, accélérant la réponse en cas d'infection réelle ultérieure." },
  { q: "Le VIH, virus du sida, attaque principalement :", type: "qcm", choices: ["Les cellules osseuses", "Les lymphocytes T4 du système immunitaire", "Les cellules de la peau", "Les cellules nerveuses uniquement"], correct: 1, exp: "Le VIH détruit progressivement les lymphocytes T4, affaiblissant gravement les défenses immunitaires de l'organisme." },
  { q: "Vrai ou faux : les antibiotiques sont efficaces contre les infections virales comme la grippe.", type: "vf", correct: false, exp: "Faux : les antibiotiques agissent contre les bactéries, pas contre les virus." },
  { q: "La théorie de l'évolution proposée par Darwin repose principalement sur :", type: "qcm", choices: ["La génération spontanée des espèces", "La sélection naturelle des individus les mieux adaptés à leur milieu", "L'immutabilité totale des espèces", "L'absence de variation entre individus"], correct: 1, exp: "Darwin explique l'évolution des espèces par la sélection naturelle : les individus les mieux adaptés survivent et se reproduisent davantage." },
  { q: "Vrai ou faux : les fossiles apportent des preuves de l'évolution des espèces au cours du temps.", type: "vf", correct: true, exp: "L'étude des fossiles permet de retracer l'apparition, la transformation et la disparition des espèces au fil des ères géologiques." },
  { q: "L'ancêtre commun de l'Homme et du chimpanzé :", type: "qcm", choices: ["Était un chimpanzé moderne", "N'est ni l'Homme actuel ni le chimpanzé actuel, mais une espèce disparue", "Était un poisson", "N'a jamais existé"], correct: 1, exp: "L'Homme et le chimpanzé partagent un ancêtre commun disparu, distinct des deux espèces actuelles." },
  { q: "La photosynthèse permet aux plantes de produire de la matière organique grâce :", type: "qcm", choices: ["À l'oxygène et à l'obscurité totale", "À la lumière, au CO2 et à l'eau", "Uniquement à l'eau", "À la respiration cellulaire seule"], correct: 1, exp: "Grâce à la lumière, les plantes transforment le CO2 et l'eau en matière organique, libérant de l'oxygène (chlorophylle)." },
  { q: "Vrai ou faux : la respiration cellulaire libère de l'énergie à partir de matière organique et de dioxygène.", type: "vf", correct: true, exp: "La respiration cellulaire dégrade la matière organique en présence de dioxygène pour produire l'énergie nécessaire aux cellules." },
  { q: "Le réchauffement climatique actuel est principalement dû à :", type: "qcm", choices: ["L'augmentation de l'activité volcanique uniquement", "L'augmentation des gaz à effet de serre liée aux activités humaines", "La diminution de l'ensoleillement", "Un refroidissement naturel cyclique"], correct: 1, exp: "Les émissions de CO2 et d'autres gaz à effet de serre, liées aux activités humaines (combustibles fossiles, déforestation), renforcent l'effet de serre." },
  { q: "Vrai ou faux : l'effet de serre est, à l'origine, un phénomène naturel indispensable à la vie sur Terre.", type: "vf", correct: true, exp: "L'effet de serre naturel maintient une température permettant la vie ; le problème vient de son intensification par les activités humaines." },
  { q: "La biodiversité désigne :", type: "qcm", choices: ["Uniquement le nombre d'espèces animales", "La diversité du vivant à toutes les échelles (gènes, espèces, écosystèmes)", "La seule diversité des paysages", "L'absence de variation génétique"], correct: 1, exp: "La biodiversité englobe la diversité génétique au sein des espèces, la diversité des espèces et celle des écosystèmes." },
  { q: "Vrai ou faux : la déforestation contribue à la perte de biodiversité.", type: "vf", correct: true, exp: "La destruction des habitats naturels, comme les forêts, menace directement de nombreuses espèces animales et végétales." },
  { q: "Un écosystème est composé :", type: "qcm", choices: ["Uniquement d'êtres vivants sans relation entre eux", "D'un ensemble d'êtres vivants en interaction avec leur milieu", "Uniquement de roches et minéraux", "D'une seule espèce isolée"], correct: 1, exp: "Un écosystème associe une communauté d'organismes vivants (biocénose) et leur milieu physique (biotope), en interactions constantes." },
  { q: "Le rôle des décomposeurs dans un écosystème est de :", type: "qcm", choices: ["Produire de l'oxygène uniquement", "Dégrader la matière organique morte et recycler les nutriments", "Empêcher toute reproduction", "Produire de la lumière"], correct: 1, exp: "Bactéries et champignons décomposeurs transforment la matière organique morte en éléments minéraux réutilisables par les producteurs." },
  { q: "Vrai ou faux : dans une chaîne alimentaire, l'énergie se transmet intégralement d'un niveau trophique à l'autre.", type: "vf", correct: false, exp: "Faux : une grande partie de l'énergie est perdue (chaleur, respiration) à chaque niveau de la chaîne alimentaire." },
  { q: "Le cycle menstruel féminin est régulé principalement par :", type: "qcm", choices: ["Le système digestif", "Des hormones (œstrogènes et progestérone)", "La respiration cellulaire", "Le système osseux"], correct: 1, exp: "Les hormones ovariennes, sous contrôle du cerveau, régulent les différentes phases du cycle menstruel." },
  { q: "Vrai ou faux : la puberté est déclenchée par des modifications hormonales.", type: "vf", correct: true, exp: "L'augmentation de la production d'hormones sexuelles (testostérone, œstrogènes) déclenche les transformations physiques de la puberté." },
  { q: "La contraception hormonale agit principalement en :", type: "qcm", choices: ["Bloquant l'ovulation grâce à des hormones de synthèse", "Augmentant la fécondité", "Modifiant le système digestif", "Agissant sur le système osseux"], correct: 0, exp: "La pilule contraceptive, par exemple, bloque l'ovulation grâce à un apport hormonal régulé." },
  { q: "Vrai ou faux : les IST (infections sexuellement transmissibles) ne peuvent être évitées par aucun moyen.", type: "vf", correct: false, exp: "Faux : l'usage du préservatif réduit significativement les risques de transmission des IST." },
  { q: "Le sang est composé notamment de globules rouges dont le rôle est de :", type: "qcm", choices: ["Produire des anticorps", "Transporter le dioxygène dans tout l'organisme", "Digérer les aliments", "Réguler la température corporelle uniquement"], correct: 1, exp: "Les globules rouges, grâce à l'hémoglobine, transportent le dioxygène des poumons vers l'ensemble des cellules du corps." },
  { q: "Vrai ou faux : le tabagisme augmente significativement les risques de cancer du poumon.", type: "vf", correct: true, exp: "La fumée de tabac contient des substances cancérigènes qui endommagent les cellules pulmonaires et favorisent le développement de tumeurs." },
  { q: "Une cellule cancéreuse se caractérise par :", type: "qcm", choices: ["Une division cellulaire normale et contrôlée", "Une multiplication anarchique et incontrôlée", "Une absence totale de division", "Une transformation en cellule musculaire"], correct: 1, exp: "Le cancer résulte d'une perte de contrôle de la division cellulaire, conduisant à la formation de tumeurs." },
  { q: "Vrai ou faux : tous les facteurs de risque de cancer sont d'origine génétique uniquement.", type: "vf", correct: false, exp: "Faux : des facteurs environnementaux (tabac, UV, alimentation) jouent aussi un rôle majeur dans le développement de cancers." },
  { q: "Le rôle des reins dans l'organisme est principalement de :", type: "qcm", choices: ["Produire des globules blancs", "Filtrer le sang et éliminer les déchets sous forme d'urine", "Digérer les graisses", "Produire de l'insuline"], correct: 1, exp: "Les reins filtrent le sang en continu, éliminant les déchets métaboliques et régulant l'équilibre en eau et en sels minéraux." },
  { q: "Le diabète de type 1 est lié à :", type: "qcm", choices: ["Une production excessive d'insuline", "Une absence ou insuffisance de production d'insuline par le pancréas", "Un excès de globules rouges", "Une infection virale des poumons"], correct: 1, exp: "Dans le diabète de type 1, les cellules du pancréas productrices d'insuline sont détruites, empêchant la régulation normale de la glycémie." },
  { q: "Vrai ou faux : l'insuline a pour rôle de faire baisser le taux de sucre (glucose) dans le sang.", type: "vf", correct: true, exp: "L'insuline favorise l'entrée du glucose dans les cellules, ce qui diminue la glycémie après un repas." },
  { q: "La tectonique des plaques explique notamment :", type: "qcm", choices: ["L'absence totale de mouvement des continents", "Les séismes, le volcanisme et la formation des chaînes de montagnes", "L'augmentation de la masse de la Terre", "La disparition de l'atmosphère"], correct: 1, exp: "Les mouvements des plaques lithosphériques génèrent l'essentiel de l'activité sismique, volcanique et orogénique sur Terre." },
  { q: "Vrai ou faux : les séismes se produisent principalement aux frontières des plaques tectoniques.", type: "vf", correct: true, exp: "La majorité des séismes survient aux limites des plaques, où s'accumulent puis se libèrent les contraintes mécaniques." },
  { q: "Une espèce invasive est une espèce qui :", type: "qcm", choices: ["Disparaît rapidement dans son nouveau milieu", "S'implante dans un nouvel écosystème et perturbe son équilibre", "Ne se reproduit jamais", "Vit uniquement en milieu marin"], correct: 1, exp: "Introduite volontairement ou non, une espèce invasive peut menacer la biodiversité locale en concurrençant les espèces indigènes." },
  { q: "Vrai ou faux : la surpêche peut entraîner l'effondrement de populations de poissons.", type: "vf", correct: true, exp: "Une pêche excessive, supérieure à la capacité de renouvellement des populations, peut conduire à leur effondrement durable." },
  { q: "Les antibiotiques deviennent parfois inefficaces à cause :", type: "qcm", choices: ["D'une absence totale de bactéries", "De la résistance bactérienne due à une utilisation excessive ou inappropriée", "D'un excès de globules blancs", "D'une carence en vitamines"], correct: 1, exp: "L'usage répété et parfois inapproprié des antibiotiques favorise la sélection de bactéries résistantes, un enjeu de santé publique majeur." },
  { q: "Vrai ou faux : le système nerveux et le système hormonal communiquent et interagissent dans la régulation de l'organisme.", type: "vf", correct: true, exp: "Ces deux systèmes coopèrent étroitement, notamment via l'hypothalamus, pour réguler de nombreuses fonctions physiologiques." },
  { q: "Les cellules souches sont particulières car elles peuvent :", type: "qcm", choices: ["Uniquement mourir rapidement", "Se diviser et se différencier en différents types de cellules", "Exister uniquement chez les plantes", "Se transformer en virus"], correct: 1, exp: "Les cellules souches ont la capacité de se renouveler et de se spécialiser en divers types cellulaires, un enjeu majeur pour la recherche médicale." },
  { q: "Vrai ou faux : la consommation excessive de sucres et de graisses peut favoriser le développement de l'obésité.", type: "vf", correct: true, exp: "Un déséquilibre alimentaire associé à un manque d'activité physique constitue un facteur de risque majeur pour l'obésité." },
  { q: "Le rôle des poumons est principalement de permettre :", type: "qcm", choices: ["La digestion des aliments", "Les échanges gazeux entre l'air et le sang (O2/CO2)", "La filtration du sang", "La production d'hormones sexuelles"], correct: 1, exp: "Au niveau des alvéoles pulmonaires, le dioxygène passe dans le sang tandis que le dioxyde de carbone en est extrait." },
  { q: "Vrai ou faux : l'activité physique régulière contribue positivement à la santé cardiovasculaire.", type: "vf", correct: true, exp: "L'exercice physique régulier renforce le cœur, améliore la circulation sanguine et réduit les risques de maladies cardiovasculaires." },
  { q: "Le caryotype humain normal comporte :", type: "qcm", choices: ["23 chromosomes", "46 chromosomes", "92 chromosomes", "12 chromosomes"], correct: 1, exp: "Une cellule humaine normale (diploïde) possède 46 chromosomes, soit 23 paires." },
  { q: "Vrai ou faux : les organes du système digestif transforment les aliments pour permettre l'absorption des nutriments par l'organisme.", type: "vf", correct: true, exp: "La digestion décompose les aliments en nutriments simples, absorbés ensuite au niveau de l'intestin pour nourrir les cellules." }
];


// ===== data_physique.js =====
const QUESTIONS_PHYSIQUE = [
  { q: "La formule chimique de l'eau est :", type: "qcm", choices: ["CO2", "H2O", "O2", "NaCl"], correct: 1, exp: "L'eau est composée de deux atomes d'hydrogène et un atome d'oxygène, d'où la formule H2O." },
  { q: "Vrai ou faux : un atome est globalement neutre électriquement.", type: "vf", correct: true, exp: "Un atome possède autant de protons (charge positive) que d'électrons (charge négative), ce qui le rend neutre." },
  { q: "Le noyau d'un atome est composé de :", type: "qcm", choices: ["Protons et électrons", "Protons et neutrons", "Neutrons et électrons", "Uniquement d'électrons"], correct: 1, exp: "Le noyau atomique regroupe protons (charge +) et neutrons (sans charge), tandis que les électrons gravitent autour." },
  { q: "Vrai ou faux : au cours d'une réaction chimique, la masse totale des réactifs est égale à la masse totale des produits.", type: "vf", correct: true, exp: "C'est la loi de conservation de la masse (Lavoisier) : 'rien ne se crée, rien ne se perd, tout se transforme'." },
  { q: "La combustion du carbone dans le dioxygène produit principalement :", type: "qcm", choices: ["De l'eau uniquement", "Du dioxyde de carbone (CO2)", "De l'azote", "Du méthane"], correct: 1, exp: "La combustion complète du carbone avec le dioxygène produit du dioxyde de carbone (C + O2 → CO2)." },
  { q: "Vrai ou faux : un mélange homogène présente une composition uniforme à l'œil nu.", type: "vf", correct: true, exp: "Dans un mélange homogène, on ne distingue pas les différents composants, contrairement à un mélange hétérogène." },
  { q: "La vitesse moyenne se calcule par la formule :", type: "qcm", choices: ["v = m × a", "v = distance / temps", "v = masse / volume", "v = F / m"], correct: 1, exp: "La vitesse moyenne s'obtient en divisant la distance parcourue par la durée du trajet (v = d/t)." },
  { q: "Vrai ou faux : dans le Système International, la vitesse s'exprime en mètres par seconde (m/s).", type: "vf", correct: true, exp: "L'unité légale de vitesse dans le Système International est le mètre par seconde (m/s), même si le km/h est aussi très utilisé." },
  { q: "La deuxième loi de Newton relie la force, la masse et :", type: "qcm", choices: ["La température", "L'accélération", "Le volume", "La pression"], correct: 1, exp: "La relation fondamentale de la dynamique s'écrit F = m × a, reliant force, masse et accélération." },
  { q: "Vrai ou faux : le poids d'un objet est identique sur Terre et sur la Lune.", type: "vf", correct: false, exp: "Faux : le poids dépend de l'intensité de la gravité, qui est différente sur la Lune (plus faible) ; seule la masse reste constante." },
  { q: "L'unité de la force dans le Système International est :", type: "qcm", choices: ["Le watt", "Le newton (N)", "Le joule", "Le pascal"], correct: 1, exp: "La force se mesure en newtons (N), en hommage au physicien Isaac Newton." },
  { q: "Vrai ou faux : un objet immobile est nécessairement soumis à aucune force.", type: "vf", correct: false, exp: "Faux : un objet immobile peut être soumis à plusieurs forces qui se compensent exactement (équilibre des forces)." },
  { q: "La loi d'Ohm relie tension, intensité et :", type: "qcm", choices: ["La résistance", "La puissance uniquement", "La fréquence", "La masse"], correct: 0, exp: "La loi d'Ohm s'écrit U = R × I, reliant tension (U), résistance (R) et intensité (I)." },
  { q: "Vrai ou faux : dans un circuit en série, l'intensité du courant est la même en tout point du circuit.", type: "vf", correct: true, exp: "Dans un montage en série, le courant ne peut suivre qu'un seul chemin, donc l'intensité reste identique partout." },
  { q: "Dans un circuit en dérivation (parallèle), la tension aux bornes de chaque branche est :", type: "qcm", choices: ["Toujours différente", "La même pour chaque branche reliée aux mêmes nœuds", "Toujours nulle", "Égale à zéro uniquement"], correct: 1, exp: "Dans un circuit en dérivation, chaque branche reliée aux mêmes points reçoit la même tension." },
  { q: "Vrai ou faux : un court-circuit correspond à une résistance quasiment nulle qui provoque un courant très important.", type: "vf", correct: true, exp: "Un court-circuit relie directement deux points sans résistance significative, provoquant un courant dangereusement élevé." },
  { q: "L'énergie cinétique d'un objet dépend de :", type: "qcm", choices: ["Sa couleur et sa forme uniquement", "Sa masse et sa vitesse", "Sa température uniquement", "Son volume uniquement"], correct: 1, exp: "L'énergie cinétique se calcule par Ec = ½ × m × v², dépendant donc de la masse et du carré de la vitesse." },
  { q: "Vrai ou faux : l'énergie se conserve toujours au cours d'une transformation, même si elle peut changer de forme.", type: "vf", correct: true, exp: "Le principe de conservation de l'énergie stipule que l'énergie totale reste constante, bien qu'elle se transforme (mécanique, thermique, etc.)." },
  { q: "Une éclipse de Soleil se produit lorsque :", type: "qcm", choices: ["La Terre passe entre le Soleil et la Lune", "La Lune passe entre la Terre et le Soleil", "Le Soleil disparaît temporairement", "La Lune devient totalement invisible"], correct: 1, exp: "Lors d'une éclipse solaire, la Lune s'interpose entre la Terre et le Soleil, projetant son ombre sur une partie de la Terre." },
  { q: "Vrai ou faux : la lumière se propage plus rapidement dans le vide que dans l'eau.", type: "vf", correct: true, exp: "La lumière se déplace à environ 300 000 km/s dans le vide, une vitesse supérieure à celle qu'elle atteint dans des milieux comme l'eau ou le verre." },
  { q: "Le spectre de la lumière blanche, décomposé par un prisme, révèle :", type: "qcm", choices: ["Une seule couleur uniforme", "L'ensemble des couleurs de l'arc-en-ciel", "Uniquement du rouge et du bleu", "Aucune couleur visible"], correct: 1, exp: "La lumière blanche est composée de toutes les couleurs visibles, que le prisme permet de séparer en un spectre coloré." },
  { q: "Vrai ou faux : le son ne peut pas se propager dans le vide.", type: "vf", correct: true, exp: "Le son a besoin d'un milieu matériel (air, eau, solide) pour se propager ; il ne peut donc pas se déplacer dans le vide." },
  { q: "La fréquence d'un son est liée à :", type: "qcm", choices: ["Sa hauteur (aigu ou grave)", "Sa couleur", "Sa masse", "Sa température"], correct: 0, exp: "Plus la fréquence d'un son est élevée, plus le son perçu est aigu ; une fréquence basse correspond à un son grave." },
  { q: "Vrai ou faux : le pH d'une solution acide est inférieur à 7.", type: "vf", correct: true, exp: "Sur l'échelle de pH, les solutions acides ont un pH inférieur à 7, les solutions basiques un pH supérieur à 7, et 7 correspond à la neutralité." },
  { q: "Une réaction acido-basique se produit entre :", type: "qcm", choices: ["Un acide et une base", "Deux métaux uniquement", "Deux gaz inertes", "Deux solides non réactifs"], correct: 0, exp: "Lorsqu'un acide réagit avec une base, on parle de réaction acido-basique, pouvant produire de l'eau et un sel." },
  { q: "Vrai ou faux : l'électrolyse de l'eau permet de produire du dihydrogène et du dioxygène.", type: "vf", correct: true, exp: "En faisant passer un courant électrique dans l'eau, on décompose les molécules H2O en dihydrogène (H2) et dioxygène (O2)." },
  { q: "La masse volumique se calcule par la formule :", type: "qcm", choices: ["ρ = masse / volume", "ρ = volume / masse", "ρ = masse × volume", "ρ = masse + volume"], correct: 0, exp: "La masse volumique (ρ) s'obtient en divisant la masse d'un objet par son volume (ρ = m/V)." },
  { q: "Vrai ou faux : un objet flotte sur l'eau si sa masse volumique est inférieure à celle de l'eau.", type: "vf", correct: true, exp: "Un objet moins dense que l'eau (masse volumique inférieure à 1000 kg/m³) flotte à sa surface." },
  { q: "L'énergie potentielle de pesanteur d'un objet dépend de :", type: "qcm", choices: ["Sa couleur", "Sa masse et sa hauteur", "Sa vitesse uniquement", "Sa température uniquement"], correct: 1, exp: "L'énergie potentielle de pesanteur (Epp = m × g × h) dépend de la masse de l'objet et de sa hauteur par rapport à un référentiel." },
  { q: "Vrai ou faux : les panneaux solaires photovoltaïques transforment l'énergie lumineuse en énergie électrique.", type: "vf", correct: true, exp: "Les cellules photovoltaïques convertissent directement la lumière du soleil en électricité grâce à l'effet photoélectrique." },
  { q: "Une centrale nucléaire produit de l'électricité grâce à :", type: "qcm", choices: ["La combustion du charbon", "La fission nucléaire qui chauffe de l'eau pour produire de la vapeur", "L'énergie solaire uniquement", "La force du vent"], correct: 1, exp: "La fission des noyaux d'uranium libère de la chaleur, utilisée pour produire de la vapeur qui actionne des turbines reliées à des alternateurs." },
  { q: "Vrai ou faux : les énergies fossiles (charbon, pétrole, gaz) sont des ressources renouvelables.", type: "vf", correct: false, exp: "Faux : les énergies fossiles se forment sur des millions d'années et sont considérées comme non renouvelables à l'échelle humaine." },
  { q: "La conservation des éléments chimiques au cours d'une réaction signifie que :", type: "qcm", choices: ["Les atomes disparaissent", "Le nombre d'atomes de chaque élément reste identique avant et après la réaction", "De nouveaux atomes apparaissent", "La masse augmente toujours"], correct: 1, exp: "Au cours d'une réaction chimique, les atomes se réorganisent mais leur nombre total par élément ne change pas." },
  { q: "Vrai ou faux : équilibrer une équation chimique consiste à ajuster les nombres stœchiométriques pour respecter la conservation des atomes.", type: "vf", correct: true, exp: "On ajuste les coefficients devant chaque espèce chimique afin que le nombre d'atomes de chaque élément soit identique des deux côtés." },
  { q: "L'ion qu'on appelle 'cation' est :", type: "qcm", choices: ["Un ion chargé négativement", "Un ion chargé positivement", "Un atome neutre", "Une molécule complexe"], correct: 1, exp: "Un cation est un ion ayant perdu un ou plusieurs électrons, lui donnant une charge positive." },
  { q: "Vrai ou faux : l'eau pure est un bon conducteur électrique.", type: "vf", correct: false, exp: "Faux : l'eau pure conduit très mal l'électricité ; ce sont les ions dissous (sels minéraux) qui rendent l'eau conductrice." },
  { q: "Le principe de l'inertie énonce que :", type: "qcm", choices: ["Un objet accélère toujours sans raison", "Un objet conserve son état de mouvement (ou de repos) si aucune force ne s'y oppose", "Les forces n'existent pas", "Tous les objets tombent à des vitesses différentes selon leur masse, dans le vide"], correct: 1, exp: "Le principe d'inertie (première loi de Newton) stipule qu'un corps reste au repos ou en mouvement rectiligne uniforme tant qu'aucune force extérieure ne le perturbe." },
  { q: "Vrai ou faux : dans le vide, deux objets de masses différentes lâchés de la même hauteur tombent à la même vitesse.", type: "vf", correct: true, exp: "En l'absence de frottements (dans le vide), tous les objets, quelle que soit leur masse, tombent avec la même accélération de pesanteur." },
  { q: "La puissance électrique d'un appareil se calcule par :", type: "qcm", choices: ["P = U × I", "P = U / I", "P = U + I", "P = U - I"], correct: 0, exp: "La puissance électrique consommée par un appareil se calcule en multipliant la tension (U) par l'intensité (I) : P = U × I." },
  { q: "Vrai ou faux : le kilowattheure (kWh) est une unité d'énergie utilisée notamment pour la facturation électrique.", type: "vf", correct: true, exp: "Le kWh mesure la quantité d'énergie consommée ; c'est l'unité utilisée par les fournisseurs d'électricité pour facturer la consommation." },
  { q: "Un système optique convergent (lentille convergente) peut :", type: "qcm", choices: ["Disperser uniquement la lumière sans la concentrer", "Faire converger les rayons lumineux vers un point appelé foyer", "Bloquer totalement la lumière", "Inverser les couleurs"], correct: 1, exp: "Une lentille convergente rapproche les rayons lumineux parallèles vers un point focal, utile notamment dans les loupes et appareils photo." },
  { q: "Vrai ou faux : l'œil humain fonctionne comme un système optique convergent avec une lentille (le cristallin).", type: "vf", correct: true, exp: "Le cristallin de l'œil agit comme une lentille convergente qui forme une image sur la rétine." },
  { q: "La dilatation d'un gaz lorsqu'on augmente sa température, à pression constante, entraîne :", type: "qcm", choices: ["Une diminution de son volume", "Une augmentation de son volume", "Aucun changement de volume", "Une disparition du gaz"], correct: 1, exp: "À pression constante, un gaz chauffé voit ses molécules s'agiter davantage, ce qui augmente son volume (loi de Charles)." },
  { q: "Vrai ou faux : la chaleur se propage toujours d'un corps chaud vers un corps froid.", type: "vf", correct: true, exp: "Selon le second principe de la thermodynamique, la chaleur se transmet naturellement du corps le plus chaud vers le plus froid." },
  { q: "Le symbole chimique du fer est :", type: "qcm", choices: ["Fe", "F", "Fr", "Fer"], correct: 0, exp: "Le symbole chimique du fer, issu du latin 'ferrum', est Fe." },
  { q: "Vrai ou faux : la rouille est le résultat d'une réaction chimique entre le fer, l'eau et le dioxygène.", type: "vf", correct: true, exp: "La rouille (oxyde de fer hydraté) se forme lorsque le fer réagit avec l'humidité et l'oxygène de l'air." },
  { q: "L'unité de mesure de l'énergie dans le Système International est :", type: "qcm", choices: ["Le watt", "Le joule (J)", "Le newton", "L'ampère"], correct: 1, exp: "Le joule (J) est l'unité officielle d'énergie dans le Système International, qu'il s'agisse d'énergie mécanique, thermique ou électrique." },
  { q: "Vrai ou faux : un courant électrique alternatif change périodiquement de sens, contrairement au courant continu.", type: "vf", correct: true, exp: "Le courant alternatif (utilisé dans les habitations) inverse périodiquement son sens, alors que le courant continu (piles) circule toujours dans le même sens." },
  { q: "La concentration molaire d'une solution se calcule par le rapport :", type: "qcm", choices: ["Volume / quantité de matière", "Quantité de matière / volume de solution", "Masse / masse molaire uniquement", "Température / pression"], correct: 1, exp: "La concentration molaire C = n/V, où n est la quantité de matière (en mol) et V le volume de solution (en L)." },
  { q: "Vrai ou faux : plus la résistance d'un conducteur est grande, plus l'intensité du courant qui le traverse est faible, à tension constante.", type: "vf", correct: true, exp: "D'après la loi d'Ohm (U=RI), pour une tension fixée, une résistance plus grande entraîne une intensité plus faible." }
];


// ===== data_maths.js =====
const QUESTIONS_MATHS = [
  { q: "Quelle est la valeur de (-3) × (-4) ?", type: "qcm", choices: ["-12", "12", "-7", "7"], correct: 1, exp: "Le produit de deux nombres négatifs est positif : (-3) × (-4) = 12." },
  { q: "Vrai ou faux : la racine carrée de 49 est 7.", type: "vf", correct: true, exp: "7 × 7 = 49, donc √49 = 7." },
  { q: "Le théorème de Pythagore s'applique dans :", type: "qcm", choices: ["Tout triangle", "Un triangle rectangle uniquement", "Un triangle équilatéral uniquement", "Un quadrilatère"], correct: 1, exp: "Le théorème de Pythagore relie les côtés d'un triangle rectangle : le carré de l'hypoténuse égale la somme des carrés des deux autres côtés." },
  { q: "Dans un triangle rectangle de côtés 3 cm et 4 cm, l'hypoténuse mesure :", type: "qcm", choices: ["5 cm", "7 cm", "6 cm", "12 cm"], correct: 0, exp: "D'après Pythagore : hyp² = 3² + 4² = 9 + 16 = 25, donc hyp = √25 = 5 cm." },
  { q: "Vrai ou faux : le théorème de Thalès permet de calculer des longueurs dans des configurations de triangles avec des droites parallèles.", type: "vf", correct: true, exp: "Le théorème de Thalès relie les longueurs de segments dans deux triangles formés par des droites parallèles." },
  { q: "La somme des angles d'un triangle est toujours égale à :", type: "qcm", choices: ["90°", "180°", "360°", "120°"], correct: 1, exp: "Dans tout triangle, la somme des trois angles intérieurs vaut 180°." },
  { q: "Vrai ou faux : un nombre est un multiple de 9 si la somme de ses chiffres est un multiple de 9.", type: "vf", correct: true, exp: "C'est un critère de divisibilité bien connu : par exemple, 729 → 7+2+9 = 18, multiple de 9, donc 729 est divisible par 9." },
  { q: "Quelle est la forme développée de (x + 3)² ?", type: "qcm", choices: ["x² + 9", "x² + 6x + 9", "x² + 3x + 9", "x² - 6x + 9"], correct: 1, exp: "(x+3)² = x² + 2×3×x + 3² = x² + 6x + 9, en utilisant l'identité remarquable (a+b)² = a² + 2ab + b²." },
  { q: "Vrai ou faux : (a - b)² = a² - b².", type: "vf", correct: false, exp: "Faux : (a-b)² = a² - 2ab + b², ce qui est différent de a² - b² (qui correspond à (a-b)(a+b))." },
  { q: "La factorisation de x² - 16 est :", type: "qcm", choices: ["(x-4)(x+4)", "(x-8)(x+2)", "(x-16)(x+1)", "Impossible à factoriser"], correct: 0, exp: "x² - 16 = x² - 4² = (x-4)(x+4), en utilisant l'identité remarquable a² - b² = (a-b)(a+b)." },
  { q: "Vrai ou faux : une fonction linéaire est représentée par une droite passant par l'origine.", type: "vf", correct: true, exp: "Une fonction linéaire s'écrit f(x) = ax et sa représentation graphique est une droite passant par le point (0,0)." },
  { q: "Une fonction affine f(x) = ax + b a pour représentation graphique :", type: "qcm", choices: ["Une parabole", "Une droite", "Un cercle", "Une courbe exponentielle"], correct: 1, exp: "Toute fonction affine de la forme f(x) = ax + b est représentée par une droite dans un repère." },
  { q: "Vrai ou faux : dans f(x) = ax + b, le coefficient 'a' représente le coefficient directeur (la pente) de la droite.", type: "vf", correct: true, exp: "Le coefficient 'a' indique la pente de la droite, tandis que 'b' est l'ordonnée à l'origine." },
  { q: "Pour résoudre l'équation 3x + 5 = 17, on obtient x = :", type: "qcm", choices: ["4", "6", "12", "22"], correct: 0, exp: "3x + 5 = 17 → 3x = 12 → x = 4." },
  { q: "Vrai ou faux : pour résoudre une inéquation, multiplier les deux membres par un nombre négatif inverse le sens de l'inégalité.", type: "vf", correct: true, exp: "Lorsqu'on multiplie ou divise une inéquation par un nombre négatif, le sens de l'inégalité doit être inversé." },
  { q: "La probabilité d'obtenir un nombre pair en lançant un dé à 6 faces est :", type: "qcm", choices: ["1/6", "1/3", "1/2", "2/3"], correct: 2, exp: "Il y a 3 nombres pairs (2, 4, 6) sur les 6 issues possibles, donc P = 3/6 = 1/2." },
  { q: "Vrai ou faux : la probabilité d'un événement est toujours comprise entre 0 et 1.", type: "vf", correct: true, exp: "Par définition, une probabilité vaut au minimum 0 (impossible) et au maximum 1 (certain)." },
  { q: "Le volume d'un cube de côté 4 cm est :", type: "qcm", choices: ["16 cm³", "48 cm³", "64 cm³", "12 cm³"], correct: 2, exp: "Le volume d'un cube se calcule par côté³ = 4³ = 4×4×4 = 64 cm³." },
  { q: "Vrai ou faux : le volume d'une boule se calcule par la formule V = (4/3) × π × r³.", type: "vf", correct: true, exp: "Cette formule classique permet de calculer le volume d'une sphère en fonction de son rayon r." },
  { q: "Dans un repère, la distance entre les points A(0,0) et B(3,4) est :", type: "qcm", choices: ["7", "5", "12", "25"], correct: 1, exp: "AB = √(3² + 4²) = √(9+16) = √25 = 5, en appliquant la formule de la distance dérivée de Pythagore." },
  { q: "Vrai ou faux : la médiane d'une série statistique sépare toujours la série en deux groupes de tailles égales en termes de valeurs.", type: "vf", correct: false, exp: "Faux : la médiane partage la série en deux groupes contenant le même nombre de valeurs (effectifs égaux), pas nécessairement des valeurs égales." },
  { q: "La moyenne des nombres 4, 8, 6, 10 et 12 est :", type: "qcm", choices: ["8", "9", "7", "10"], correct: 0, exp: "(4+8+6+10+12)/5 = 40/5 = 8." },
  { q: "Vrai ou faux : un nombre premier n'a que deux diviseurs : 1 et lui-même.", type: "vf", correct: true, exp: "Par définition, un nombre premier (comme 2, 3, 5, 7, 11...) n'admet que 1 et lui-même comme diviseurs." },
  { q: "Le PGCD de 24 et 36 est :", type: "qcm", choices: ["6", "12", "8", "18"], correct: 1, exp: "Les diviseurs communs de 24 et 36 incluent 12, qui est le plus grand commun diviseur (24=12×2 ; 36=12×3)." },
  { q: "Vrai ou faux : √2 est un nombre rationnel.", type: "vf", correct: false, exp: "Faux : √2 est un nombre irrationnel, il ne peut pas s'écrire comme une fraction de deux entiers." },
  { q: "L'écriture scientifique de 0,00045 est :", type: "qcm", choices: ["4,5 × 10⁻⁴", "4,5 × 10⁴", "45 × 10⁻⁵", "4,5 × 10⁻⁵"], correct: 0, exp: "0,00045 = 4,5 × 10⁻⁴, en déplaçant la virgule de 4 rangs vers la droite." },
  { q: "Vrai ou faux : (a×10ⁿ) × (b×10ᵐ) = (a×b) × 10^(n+m).", type: "vf", correct: true, exp: "Lors d'une multiplication en écriture scientifique, on multiplie les coefficients et on additionne les exposants de 10." },
  { q: "Dans un triangle, la médiane et la médiatrice d'un côté sont :", type: "qcm", choices: ["Toujours identiques", "Généralement différentes, sauf cas particuliers comme le triangle isocèle", "Toujours perpendiculaires entre elles", "Inexistantes dans un triangle"], correct: 1, exp: "La médiane relie un sommet au milieu du côté opposé, tandis que la médiatrice est perpendiculaire au côté en son milieu ; elles coïncident dans certains triangles particuliers (isocèle, équilatéral)." },
  { q: "Vrai ou faux : dans un triangle équilatéral, toutes les médianes, médiatrices, bissectrices et hauteurs sont confondues.", type: "vf", correct: true, exp: "Grâce à la symétrie parfaite du triangle équilatéral, ces quatre droites remarquables coïncident pour chaque sommet." },
  { q: "L'aire d'un disque de rayon 5 cm est (on prendra π ≈ 3,14) :", type: "qcm", choices: ["31,4 cm²", "78,5 cm²", "15,7 cm²", "50 cm²"], correct: 1, exp: "Aire = π × r² = 3,14 × 5² = 3,14 × 25 = 78,5 cm²." },
  { q: "Vrai ou faux : la formule du périmètre d'un cercle de rayon r est P = 2 × π × r.", type: "vf", correct: true, exp: "Le périmètre (circonférence) d'un cercle se calcule par 2πr, où r est le rayon." },
  { q: "L'expression -5 - (-3) est égale à :", type: "qcm", choices: ["-8", "-2", "2", "8"], correct: 1, exp: "-5 - (-3) = -5 + 3 = -2." },
  { q: "Vrai ou faux : pour résoudre un système de deux équations à deux inconnues, on peut utiliser la méthode de substitution.", type: "vf", correct: true, exp: "La méthode de substitution consiste à exprimer une inconnue en fonction de l'autre puis à remplacer dans la seconde équation." },
  { q: "Quel est le résultat de l'addition de fractions 1/3 + 1/4 ?", type: "qcm", choices: ["2/7", "7/12", "1/7", "5/12"], correct: 1, exp: "1/3 + 1/4 = 4/12 + 3/12 = 7/12, en réduisant au dénominateur commun 12." },
  { q: "Vrai ou faux : diviser par une fraction équivaut à multiplier par son inverse.", type: "vf", correct: true, exp: "Diviser par a/b équivaut à multiplier par b/a, l'inverse de la fraction." },
  { q: "Dans un repère orthonormé, le coefficient directeur d'une droite passant par A(1,2) et B(3,8) est :", type: "qcm", choices: ["2", "3", "4", "6"], correct: 1, exp: "Le coefficient directeur se calcule par (y_B - y_A)/(x_B - x_A) = (8-2)/(3-1) = 6/2 = 3." },
  { q: "Vrai ou faux : deux droites sont parallèles si elles ont le même coefficient directeur.", type: "vf", correct: true, exp: "Dans un repère, deux droites non confondues ayant le même coefficient directeur sont parallèles." },
  { q: "Le développement de (2x - 3)(x + 5) donne :", type: "qcm", choices: ["2x² + 7x - 15", "2x² - 7x - 15", "2x² + 7x + 15", "2x² - 7x + 15"], correct: 0, exp: "(2x-3)(x+5) = 2x² + 10x - 3x - 15 = 2x² + 7x - 15." },
  { q: "Vrai ou faux : tout nombre décimal est un nombre rationnel.", type: "vf", correct: false, exp: "Faux : un nombre décimal illimité non périodique (comme π) n'est pas rationnel ; seuls les décimaux finis ou périodiques le sont." },
  { q: "L'angle inscrit dans un demi-cercle (sous-tendu par un diamètre) mesure toujours :", type: "qcm", choices: ["45°", "60°", "90°", "180°"], correct: 2, exp: "D'après la propriété de l'angle inscrit, tout angle inscrit dans un demi-cercle, s'appuyant sur le diamètre, est un angle droit (90°)." },
  { q: "Vrai ou faux : la fonction f(x) = x² est une fonction croissante sur tout ℝ.", type: "vf", correct: false, exp: "Faux : f(x) = x² est décroissante sur les réels négatifs et croissante sur les réels positifs, formant une parabole." },
  { q: "Le pourcentage 25% correspond à la fraction :", type: "qcm", choices: ["1/2", "1/4", "1/5", "1/3"], correct: 1, exp: "25% = 25/100 = 1/4." },
  { q: "Vrai ou faux : augmenter un prix de 20% puis le diminuer de 20% redonne le prix initial.", type: "vf", correct: false, exp: "Faux : les pourcentages successifs ne s'annulent pas car ils s'appliquent à des bases différentes ; le prix final est inférieur au prix initial." },
  { q: "Le volume d'un cylindre de rayon 3 cm et de hauteur 10 cm est (π ≈ 3,14) :", type: "qcm", choices: ["94,2 cm³", "282,6 cm³", "188,4 cm³", "30 cm³"], correct: 1, exp: "Volume = π × r² × h = 3,14 × 9 × 10 = 282,6 cm³." },
  { q: "Vrai ou faux : la fonction trigonométrique cosinus d'un angle dans un triangle rectangle correspond au rapport (côté adjacent / hypoténuse).", type: "vf", correct: true, exp: "Dans un triangle rectangle, cos(angle) = côté adjacent / hypoténuse, l'une des trois formules trigonométriques de base avec sinus et tangente." },
  { q: "Une équation du second degré peut avoir au maximum :", type: "qcm", choices: ["1 solution", "2 solutions réelles", "3 solutions réelles", "4 solutions réelles"], correct: 1, exp: "Une équation du second degré (ax²+bx+c=0) admet au maximum deux solutions réelles, selon le signe du discriminant." },
  { q: "Vrai ou faux : si le discriminant d'une équation du second degré est négatif, l'équation n'a aucune solution réelle.", type: "vf", correct: true, exp: "Lorsque le discriminant (Δ = b² - 4ac) est négatif, l'équation n'admet pas de solution dans l'ensemble des nombres réels." },
  { q: "Dans un triangle ABC rectangle en A, le sinus de l'angle B est égal à :", type: "qcm", choices: ["AB / BC", "AC / BC", "AB / AC", "BC / AB"], correct: 1, exp: "sin(B) = côté opposé à B / hypoténuse = AC / BC." },
  { q: "Vrai ou faux : la somme des angles d'un quadrilatère est toujours égale à 360°.", type: "vf", correct: true, exp: "Tout quadrilatère peut être décomposé en deux triangles (180° chacun), donc la somme de ses angles vaut 360°." },
  { q: "Le résultat de l'opération 2³ × 2⁴ est :", type: "qcm", choices: ["2⁷", "2¹²", "4⁷", "2¹"], correct: 0, exp: "Lors d'une multiplication de puissances de même base, on additionne les exposants : 2³ × 2⁴ = 2^(3+4) = 2⁷." },
  { q: "Vrai ou faux : une fonction est dite croissante sur un intervalle si, lorsque x augmente, f(x) augmente également sur cet intervalle.", type: "vf", correct: true, exp: "C'est la définition même de la croissance d'une fonction : les images suivent le même sens de variation que les antécédents." }
];


// ===== data_francais.js =====
const QUESTIONS_FRANCAIS = [
  { q: "Dans la phrase 'Le chat dort paisiblement', le mot 'paisiblement' est :", type: "qcm", choices: ["Un adjectif", "Un adverbe", "Un nom", "Un verbe"], correct: 1, exp: "'Paisiblement' modifie le verbe 'dort' et indique la manière : c'est un adverbe." },
  { q: "Vrai ou faux : un complément d'objet direct (COD) répond à la question 'quoi ?' ou 'qui ?' posée après le verbe.", type: "vf", correct: true, exp: "Le COD se trouve en posant la question 'qui ?' ou 'quoi ?' directement après le verbe, sans préposition." },
  { q: "Le passé simple du verbe 'venir' à la 3e personne du singulier est :", type: "qcm", choices: ["Il vint", "Il venait", "Il vienne", "Il viendra"], correct: 0, exp: "Le passé simple de 'venir' à la 3e personne du singulier est 'il vint', un verbe irrégulier du 3e groupe." },
  { q: "Vrai ou faux : le COI (complément d'objet indirect) est toujours introduit par une préposition (à, de...).", type: "vf", correct: true, exp: "Le COI se distingue du COD car il est relié au verbe par une préposition, comme dans 'il pense à elle'." },
  { q: "Une métaphore est une figure de style qui consiste à :", type: "qcm", choices: ["Comparer deux éléments en utilisant 'comme' ou 'tel que'", "Établir un rapprochement entre deux éléments sans mot de comparaison", "Répéter le même mot plusieurs fois", "Exagérer une réalité"], correct: 1, exp: "Contrairement à la comparaison, la métaphore associe directement deux éléments sans outil de comparaison ('Cet homme est un lion')." },
  { q: "Vrai ou faux : une comparaison utilise toujours un outil de comparaison comme 'comme', 'ainsi que' ou 'semblable à'.", type: "vf", correct: true, exp: "La comparaison relie explicitement deux éléments à l'aide d'un mot-outil, contrairement à la métaphore qui les associe directement." },
  { q: "Dans un récit, un narrateur 'omniscient' est un narrateur qui :", type: "qcm", choices: ["Ne connaît que ses propres pensées", "Connaît tout, y compris les pensées de tous les personnages", "N'existe pas dans le récit", "Raconte uniquement à la première personne"], correct: 1, exp: "Le narrateur omniscient a un point de vue total : il connaît les pensées, sentiments et actions passées ou futures de tous les personnages." },
  { q: "Vrai ou faux : un récit à la première personne ('je') implique nécessairement que le narrateur est un personnage de l'histoire.", type: "vf", correct: true, exp: "Lorsque le narrateur dit 'je', il est impliqué dans l'histoire, qu'il en soit le héros ou un témoin." },
  { q: "Le futur antérieur exprime généralement :", type: "qcm", choices: ["Une action future antérieure à une autre action future", "Une action passée révolue", "Une action présente continue", "Un ordre direct"], correct: 0, exp: "Le futur antérieur ('quand j'aurai fini') marque une action future qui se termine avant une autre action future." },
  { q: "Vrai ou faux : le conditionnel peut exprimer une hypothèse ou un souhait.", type: "vf", correct: true, exp: "Le conditionnel s'utilise pour exprimer une hypothèse ('si j'avais le temps, je viendrais') ou un souhait poli ('je voudrais')." },
  { q: "Une antithèse est une figure de style qui :", type: "qcm", choices: ["Répète un même son", "Oppose deux idées ou mots de sens contraire", "Compare deux éléments avec 'comme'", "Atténue une réalité"], correct: 1, exp: "L'antithèse met en relief un contraste fort, par exemple : 'Je vis, je meurs ; je me brûle et me noie'." },
  { q: "Vrai ou faux : un euphémisme atténue la réalité d'un propos, contrairement à l'hyperbole qui l'exagère.", type: "vf", correct: true, exp: "L'euphémisme adoucit (par exemple 'il nous a quittés' pour 'il est mort'), tandis que l'hyperbole amplifie ('mourir de rire')." },
  { q: "Dans la phrase 'Bien qu'il pleuve, nous sortirons', la proposition subordonnée exprime :", type: "qcm", choices: ["La cause", "La concession (opposition)", "Le but", "La conséquence"], correct: 1, exp: "'Bien que' introduit une proposition subordonnée de concession, qui marque une opposition malgré un obstacle." },
  { q: "Vrai ou faux : une proposition subordonnée relative est introduite par un pronom relatif (qui, que, dont, où...).", type: "vf", correct: true, exp: "Les pronoms relatifs (qui, que, dont, où, lequel...) introduisent les propositions subordonnées relatives, qui complètent un nom." },
  { q: "Le registre de langue 'soutenu' se caractérise par :", type: "qcm", choices: ["Un vocabulaire familier et des phrases courtes", "Un vocabulaire recherché et une syntaxe complexe", "L'absence totale de grammaire", "Des phrases incomplètes uniquement"], correct: 1, exp: "Le registre soutenu emploie un vocabulaire riche, une syntaxe élaborée, souvent utilisé en littérature ou contextes formels." },
  { q: "Vrai ou faux : un sonnet est un poème à forme fixe composé de 14 vers.", type: "vf", correct: true, exp: "Le sonnet, forme poétique classique, comprend deux quatrains et deux tercets, soit 14 vers au total." },
  { q: "Un alexandrin est un vers de :", type: "qcm", choices: ["8 syllabes", "10 syllabes", "12 syllabes", "14 syllabes"], correct: 2, exp: "L'alexandrin, vers classique très utilisé en poésie française (notamment chez Racine ou Hugo), compte 12 syllabes." },
  { q: "Vrai ou faux : dans 'Le Malade imaginaire' de Molière, il s'agit d'une tragédie.", type: "vf", correct: false, exp: "Faux : 'Le Malade imaginaire' est une comédie (plus précisément une comédie-ballet), pas une tragédie." },
  { q: "L'argumentation directe consiste à :", type: "qcm", choices: ["Exposer explicitement une thèse et des arguments", "Critiquer indirectement par le récit ou la fiction", "Ne jamais exprimer d'opinion", "Utiliser uniquement le dialogue"], correct: 0, exp: "L'argumentation directe défend une thèse de façon explicite (essai, discours), contrairement à l'argumentation indirecte qui passe par la fiction (fable, conte philosophique)." },
  { q: "Vrai ou faux : une fable est souvent un exemple d'argumentation indirecte, car elle délivre une morale à travers un récit.", type: "vf", correct: true, exp: "Les fables, comme celles de La Fontaine, utilisent le récit et les personnages animaliers pour transmettre une leçon de manière indirecte." },
  { q: "Le mot 'autographe' contient le préfixe 'auto-' qui signifie :", type: "qcm", choices: ["Contre", "Soi-même", "Au-dessus", "Beaucoup"], correct: 1, exp: "Le préfixe grec 'auto-' signifie 'soi-même', comme dans autographe, autobiographie ou autonomie." },
  { q: "Vrai ou faux : le mot 'biographie' est composé des racines grecques 'bio' (vie) et 'graphie' (écriture).", type: "vf", correct: true, exp: "Une biographie est littéralement l'écriture de la vie d'une personne, en accord avec son étymologie grecque." },
  { q: "Dans une phrase complexe, une proposition subordonnée circonstancielle de but est introduite par :", type: "qcm", choices: ["'parce que'", "'afin que' ou 'pour que'", "'bien que'", "'si bien que'"], correct: 1, exp: "Les locutions 'afin que' et 'pour que' introduisent une subordonnée de but, exprimant l'objectif visé par l'action principale." },
  { q: "Vrai ou faux : 'parce que' introduit une proposition subordonnée de cause.", type: "vf", correct: true, exp: "'Parce que' exprime la cause d'un fait, répondant à la question 'pourquoi ?'." },
  { q: "L'accord du participe passé avec l'auxiliaire 'avoir' se fait avec le COD uniquement si :", type: "qcm", choices: ["Le COD est placé après le verbe", "Le COD est placé avant le verbe", "Il n'y a jamais d'accord avec avoir", "Le sujet est féminin"], correct: 1, exp: "Avec l'auxiliaire 'avoir', le participe passé s'accorde avec le COD seulement lorsque celui-ci est placé avant le verbe (ex : 'la lettre qu'il a écrite')." },
  { q: "Vrai ou faux : avec l'auxiliaire 'être', le participe passé s'accorde toujours avec le sujet.", type: "vf", correct: true, exp: "Avec 'être', le participe passé s'accorde en genre et en nombre avec le sujet du verbe (ex : 'elles sont parties')." },
  { q: "Le mot 'anticonstitutionnellement' est souvent cité comme exemple de :", type: "qcm", choices: ["Mot le plus court de la langue française", "Mot le plus long couramment utilisé en français", "Un verbe irrégulier", "Un nom propre"], correct: 1, exp: "Avec ses 25 lettres, 'anticonstitutionnellement' est souvent présenté comme l'un des mots les plus longs de la langue française." },
  { q: "Vrai ou faux : dans le théâtre, une 'didascalie' est une indication scénique donnée par l'auteur, non prononcée par les acteurs.", type: "vf", correct: true, exp: "Les didascalies (indications de jeu, de décor, de ton) guident la mise en scène sans être dites par les personnages." },
  { q: "Le mouvement littéraire des Lumières, au XVIIIe siècle, est associé notamment à :", type: "qcm", choices: ["Victor Hugo et le Romantisme", "Voltaire, Rousseau et la philosophie rationaliste", "Molière et la comédie classique", "Baudelaire et le symbolisme"], correct: 1, exp: "Le siècle des Lumières valorise la raison, la critique des injustices et le progrès, incarné notamment par Voltaire, Rousseau et Diderot." },
  { q: "Vrai ou faux : Victor Hugo est une figure majeure du mouvement romantique français.", type: "vf", correct: true, exp: "Victor Hugo, auteur des 'Misérables' et de nombreux poèmes, est l'une des figures les plus emblématiques du romantisme en France." },
  { q: "Une 'antiphrase' consiste à :", type: "qcm", choices: ["Dire l'inverse de ce qu'on pense, souvent par ironie", "Répéter plusieurs fois la même idée", "Utiliser un vocabulaire très simple", "Comparer deux objets différents"], correct: 0, exp: "L'antiphrase exprime ironiquement le contraire de ce que l'on veut réellement dire (ex : 'Quelle belle journée !' sous la pluie battante)." },
  { q: "Vrai ou faux : le champ lexical regroupe l'ensemble des mots se rapportant à un même thème dans un texte.", type: "vf", correct: true, exp: "Le champ lexical réunit les termes liés à une même idée ou un même thème (par exemple, le champ lexical de la guerre)." },
  { q: "Dans 'Le Petit Prince' de Saint-Exupéry, le narrateur principal est :", type: "qcm", choices: ["Le Petit Prince lui-même", "Un aviateur échoué dans le désert", "Le renard", "La rose"], correct: 1, exp: "Le récit est raconté par l'aviateur qui rencontre le Petit Prince après s'être écrasé dans le désert du Sahara." },
  { q: "Vrai ou faux : un texte argumentatif a pour but principal de convaincre ou persuader le lecteur.", type: "vf", correct: true, exp: "L'argumentation vise à défendre un point de vue en s'appuyant sur des arguments rationnels (convaincre) ou des émotions (persuader)." },
  { q: "Le mode subjonctif s'emploie souvent après des expressions comme :", type: "qcm", choices: ["'il est certain que'", "'il faut que' ou 'je doute que'", "'il est évident que'", "'je suis sûr que'"], correct: 1, exp: "Le subjonctif exprime souvent le doute, la nécessité ou le souhait, employé après des locutions comme 'il faut que' ou 'je doute que'." },
  { q: "Vrai ou faux : l'impératif ne se conjugue qu'à trois personnes (tu, nous, vous), sans pronom sujet exprimé.", type: "vf", correct: true, exp: "L'impératif s'utilise sans pronom sujet et uniquement aux 2e personnes du singulier et du pluriel, ainsi qu'à la 1re personne du pluriel." },
  { q: "L'expression 'avoir le cœur sur la main' signifie :", type: "qcm", choices: ["Être malade", "Être généreux", "Être en colère", "Être fatigué"], correct: 1, exp: "Cette expression imagée désigne une personne très généreuse, prête à donner sans compter." },
  { q: "Vrai ou faux : un homophone est un mot qui se prononce de la même façon qu'un autre mot mais qui a un sens et souvent une orthographe différents.", type: "vf", correct: true, exp: "Les homophones (comme 'vert', 'verre', 'vers' et 'ver') se prononcent identiquement mais diffèrent par le sens et souvent l'orthographe." },
  { q: "Dans un roman, l'incipit désigne :", type: "qcm", choices: ["La dernière phrase du livre", "Les premières lignes ou pages du roman", "Le résumé en quatrième de couverture", "Le titre du livre"], correct: 1, exp: "L'incipit correspond au début du texte, souvent déterminant pour capter l'attention du lecteur et poser le cadre du récit." },
  { q: "Vrai ou faux : la tragédie classique respecte traditionnellement la règle des trois unités (lieu, temps, action).", type: "vf", correct: true, exp: "Le théâtre classique (Racine, Corneille) impose une unité de lieu, de temps (24h) et d'action pour assurer la cohérence dramatique." },
  { q: "Le mot 'symbole' dans une œuvre littéraire désigne :", type: "qcm", choices: ["Un signe de ponctuation particulier", "Un élément concret représentant une idée abstraite", "Une rime obligatoire", "Un type de narrateur"], correct: 1, exp: "Le symbole donne un sens abstrait à un élément concret du récit (par exemple, la lumière peut symboliser l'espoir ou la connaissance)." },
  { q: "Vrai ou faux : dans un dialogue théâtral, une 'tirade' désigne une longue réplique prononcée par un seul personnage.", type: "vf", correct: true, exp: "La tirade est un long discours ininterrompu d'un personnage, souvent utilisée pour exprimer une émotion forte ou un argumentaire." },
  { q: "L'anaphore est une figure de style qui consiste à :", type: "qcm", choices: ["Répéter un mot ou groupe de mots en début de phrase ou de vers", "Comparer deux réalités avec 'comme'", "Atténuer une idée", "Employer un mot pour un autre par analogie"], correct: 0, exp: "L'anaphore répète une même expression en tête de plusieurs phrases ou vers pour créer un effet d'insistance, comme chez Victor Hugo." },
  { q: "Vrai ou faux : une périphrase consiste à remplacer un mot simple par une expression plus longue de même sens.", type: "vf", correct: true, exp: "La périphrase désigne une réalité par une expression détournée plutôt que par le mot précis (ex : 'la Ville lumière' pour Paris)." },
  { q: "Dans le récit, l'ellipse narrative consiste à :", type: "qcm", choices: ["Décrire un moment dans le détail", "Passer rapidement sur une période sans la raconter", "Répéter un même évènement plusieurs fois", "Changer de narrateur"], correct: 1, exp: "L'ellipse accélère le récit en passant sous silence une durée, par exemple 'dix ans passèrent'." },
  { q: "Vrai ou faux : le présent de narration permet de rendre plus vivant un récit normalement écrit au passé.", type: "vf", correct: true, exp: "L'emploi du présent dans un récit passé crée un effet de proximité et de vivacité pour le lecteur." },
  { q: "L'adjectif qualificatif épithète se place :", type: "qcm", choices: ["Toujours après le nom uniquement", "Directement auprès du nom qu'il qualifie, sans verbe d'état", "Uniquement en début de phrase", "Jamais à côté d'un nom"], correct: 1, exp: "L'épithète qualifie directement le nom auquel il est accolé, sans l'intermédiaire d'un verbe d'état (contrairement à l'attribut)." },
  { q: "Vrai ou faux : un adjectif attribut est relié au sujet par un verbe d'état comme 'être', 'sembler' ou 'paraître'.", type: "vf", correct: true, exp: "L'attribut du sujet qualifie le sujet à travers un verbe d'état ('elle semble fatiguée')." },
  { q: "Le mouvement littéraire du réalisme, porté notamment par Balzac et Flaubert, cherche à :", type: "qcm", choices: ["Idéaliser totalement la réalité", "Représenter fidèlement la société et ses travers", "Décrire uniquement des mondes imaginaires", "Éviter toute description"], correct: 1, exp: "Le réalisme du XIXe siècle vise à dépeindre la société telle qu'elle est, avec ses détails parfois crus et ses travers sociaux." },
  { q: "Vrai ou faux : 'Germinal' d'Émile Zola appartient au mouvement naturaliste.", type: "vf", correct: true, exp: "Zola, chef de file du naturalisme, dépeint dans 'Germinal' la dure condition des mineurs avec une approche presque scientifique de la réalité sociale." }
];


// ===== app.js =====
// ============================================================
// NOCTURNE — Moteur de révisions Brevet
// ============================================================

const SUBJECTS = [
  {
    id: "histoire",
    name: "Histoire",
    desc: "Guerres mondiales, totalitarismes, décolonisation et construction européenne.",
    icon: "⚔",
    accent: "var(--histoire)",
    accentDim: "var(--histoire-dim)",
    data: () => QUESTIONS_HISTOIRE
  },
  {
    id: "geographie",
    name: "Géographie",
    desc: "Aires urbaines, espaces ruraux, territoires ultramarins et aménagement.",
    icon: "🧭",
    accent: "var(--geo)",
    accentDim: "var(--geo-dim)",
    data: () => QUESTIONS_GEOGRAPHIE
  },
  {
    id: "svt",
    name: "SVT",
    desc: "Génétique, immunité, évolution, écosystèmes et corps humain.",
    icon: "🧬",
    accent: "var(--svt)",
    accentDim: "var(--svt-dim)",
    data: () => QUESTIONS_SVT
  },
  {
    id: "physique",
    name: "Physique-Chimie",
    desc: "Forces, circuits électriques, énergie, réactions et atomes.",
    icon: "⚛",
    accent: "var(--physique)",
    accentDim: "var(--physique-dim)",
    data: () => QUESTIONS_PHYSIQUE
  },
  {
    id: "maths",
    name: "Mathématiques",
    desc: "Théorèmes, fonctions, équations, probabilités et géométrie.",
    icon: "∑",
    accent: "var(--maths)",
    accentDim: "var(--maths-dim)",
    data: () => QUESTIONS_MATHS
  },
  {
    id: "francais",
    name: "Français",
    desc: "Grammaire, figures de style, conjugaison et littérature.",
    icon: "✒",
    accent: "var(--francais)",
    accentDim: "var(--francais-dim)",
    data: () => QUESTIONS_FRANCAIS
  }
];

const STORAGE_KEY = "nocturne_progress_v1";

function loadProgress(){
  try{
    const raw = localStorage.getItem(STORAGE_KEY);
    if(!raw) return { bestScores:{}, globalStreak:0 };
    return JSON.parse(raw);
  }catch(e){ return { bestScores:{}, globalStreak:0 }; }
}
function saveProgress(p){
  try{ localStorage.setItem(STORAGE_KEY, JSON.stringify(p)); }catch(e){}
}

let progress = loadProgress();

// ---------- Shuffle helper ----------
function shuffle(arr){
  const a = arr.slice();
  for(let i = a.length - 1; i > 0; i--){
    const j = Math.floor(Math.random() * (i+1));
    [a[i], a[j]] = [a[j], a[i]];
  }
  return a;
}

// ============================================================
// HOME VIEW RENDERING
// ============================================================
const subjectGrid = document.getElementById("subjectGrid");
const totalQCountEl = document.getElementById("totalQCount");
const globalStreakEl = document.getElementById("globalStreak");

function renderHome(){
  subjectGrid.innerHTML = "";
  let total = 0;
  SUBJECTS.forEach(s => {
    const qs = s.data();
    total += qs.length;
    const best = progress.bestScores[s.id];
    const card = document.createElement("button");
    card.className = "subject-card";
    card.style.setProperty("--accent", s.accent);
    card.style.setProperty("--accent-dim", s.accentDim);
    card.innerHTML = `
      <div class="subject-top">
        <div class="subject-icon">${s.icon}</div>
        <div class="subject-qcount">${qs.length} questions</div>
      </div>
      <h3 class="subject-name">${s.name}</h3>
      <p class="subject-desc">${s.desc}</p>
      <div class="subject-foot">
        <div class="subject-cta">
          Lancer le QCM
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.8" stroke-linecap="round"><path d="M9 6l6 6-6 6"/></svg>
        </div>
        <div class="subject-best">${best ? `Meilleur : ${best.percent}%` : ""}</div>
      </div>
    `;
    card.addEventListener("click", () => startQuiz(s.id));
    subjectGrid.appendChild(card);
  });
  totalQCountEl.textContent = `${total} questions au total`;
  globalStreakEl.textContent = progress.globalStreak || 0;
}

document.getElementById("resetProgressBtn").addEventListener("click", () => {
  if(confirm("Réinitialiser toute ta progression et tes meilleurs scores ?")){
    progress = { bestScores:{}, globalStreak:0 };
    saveProgress(progress);
    renderHome();
  }
});

// ============================================================
// QUIZ ENGINE
// ============================================================
const homeView = document.getElementById("homeView");
const quizView = document.getElementById("quizView");
const resultsView = document.getElementById("resultsView");

const quizSubjectTag = document.getElementById("quizSubjectTag");
const quizSubjectName = document.getElementById("quizSubjectName");
const progressFill = document.getElementById("progressFill");
const qCounterText = document.getElementById("qCounterText");
const qTypePill = document.getElementById("qTypePill");
const qText = document.getElementById("qText");
const choicesContainer = document.getElementById("choicesContainer");
const vfContainer = document.getElementById("vfContainer");
const feedbackPanel = document.getElementById("feedbackPanel");
const feedbackTitle = document.getElementById("feedbackTitle");
const feedbackText = document.getElementById("feedbackText");
const nextBtn = document.getElementById("nextBtn");
const nextBtnLabel = document.getElementById("nextBtnLabel");
const qCard = document.getElementById("qCard");

let session = null; // { subject, questions, index, correctCount, streak, bestStreak, missed[] }

function startQuiz(subjectId){
  const subject = SUBJECTS.find(s => s.id === subjectId);
  const allQs = shuffle(subject.data());
  session = {
    subject,
    questions: allQs,
    index: 0,
    correctCount: 0,
    streak: 0,
    bestStreak: 0,
    missed: [],
    answered: false
  };

  document.documentElement.style.setProperty("--accent", subject.accent);
  quizSubjectTag.style.setProperty("--accent", subject.accent);
  quizSubjectTag.style.setProperty("--accent-dim", subject.accentDim);
  quizSubjectName.textContent = subject.name;

  homeView.classList.add("hidden");
  quizView.classList.add("active");
  resultsView.classList.remove("active");

  renderQuestion();
}

function renderQuestion(){
  const { subject, questions, index } = session;
  const q = questions[index];
  session.answered = false;

  // progress + counter
  const pct = (index / questions.length) * 100;
  progressFill.style.width = pct + "%";
  progressFill.style.setProperty("--accent", subject.accent);
  qCounterText.textContent = `Question ${index + 1} / ${questions.length}`;
  qTypePill.textContent = q.type === "vf" ? "Vrai / Faux" : "QCM";

  qText.textContent = q.q;

  feedbackPanel.className = "feedback";
  nextBtn.classList.remove("show");
  nextBtnLabel.textContent = (index === questions.length - 1) ? "Voir mon bilan" : "Question suivante";

  if(q.type === "vf"){
    choicesContainer.style.display = "none";
    vfContainer.style.display = "grid";
    vfContainer.innerHTML = "";
    [true, false].forEach(val => {
      const btn = document.createElement("button");
      btn.className = "vf-btn";
      btn.innerHTML = `<span class="vf-icon">${val ? "✓" : "✕"}</span><span class="vf-label">${val ? "Vrai" : "Faux"}</span>`;
      btn.addEventListener("click", () => handleAnswer(val === q.correct, btn, q));
      vfContainer.appendChild(btn);
    });
  } else {
    vfContainer.style.display = "none";
    choicesContainer.style.display = "flex";
    choicesContainer.innerHTML = "";
    const letters = ["A","B","C","D","E","F"];
    q.choices.forEach((choice, i) => {
      const btn = document.createElement("button");
      btn.className = "choice";
      btn.innerHTML = `
        <span class="letter">${letters[i]}</span>
        <span>${choice}</span>
        <svg class="check-icon" width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6L9 17l-5-5"/></svg>
      `;
      btn.addEventListener("click", () => handleAnswer(i === q.correct, btn, q));
      choicesContainer.appendChild(btn);
    });
  }
}

function handleAnswer(isCorrect, clickedEl, q){
  if(session.answered) return;
  session.answered = true;

  const isVF = q.type === "vf";
  const allButtons = isVF ? [...vfContainer.children] : [...choicesContainer.children];

  allButtons.forEach(btn => btn.classList.add("disabled"));

  if(isVF){
    allButtons.forEach((btn, i) => {
      const val = i === 0; // first = true
      if(val === q.correct) btn.classList.add("correct");
      else if(btn === clickedEl) btn.classList.add("wrong");
      else btn.classList.add("faded");
    });
  } else {
    allButtons.forEach((btn, i) => {
      if(i === q.correct) btn.classList.add("correct");
      else if(btn === clickedEl && !isCorrect) btn.classList.add("wrong");
      else btn.classList.add("faded");
    });
  }

  if(isCorrect){
    session.correctCount++;
    session.streak++;
    session.bestStreak = Math.max(session.bestStreak, session.streak);
    progress.globalStreak = (progress.globalStreak || 0) + 1;
  } else {
    session.streak = 0;
    session.missed.push(q);
  }
  saveProgress(progress);

  feedbackPanel.classList.add("show");
  feedbackPanel.classList.add(isCorrect ? "is-correct" : "is-wrong");
  feedbackTitle.innerHTML = isCorrect
    ? `<svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round"><path d="M20 6L9 17l-5-5"/></svg> Bonne réponse`
    : `<svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round"><path d="M18 6L6 18M6 6l12 12"/></svg> Pas tout à fait`;
  feedbackText.innerHTML = q.exp;

  nextBtn.classList.add("show");
}

nextBtn.addEventListener("click", () => {
  session.index++;
  if(session.index >= session.questions.length){
    showResults();
  } else {
    renderQuestion();
  }
});

document.getElementById("backBtn").addEventListener("click", () => {
  if(confirm("Quitter ce QCM ? Ta progression sur cette tentative sera perdue.")){
    goHome();
  }
});

function goHome(){
  quizView.classList.remove("active");
  resultsView.classList.remove("active");
  homeView.classList.remove("hidden");
  renderHome();
}

// ============================================================
// RESULTS
// ============================================================
const resultPercent = document.getElementById("resultPercent");
const resultFraction = document.getElementById("resultFraction");
const resultsTitle = document.getElementById("resultsTitle");
const resultsSub = document.getElementById("resultsSub");
const statCorrect = document.getElementById("statCorrect");
const statWrong = document.getElementById("statWrong");
const statBestStreak = document.getElementById("statBestStreak");
const ringFg = document.getElementById("ringFg");
const missedReview = document.getElementById("missedReview");
const missedList = document.getElementById("missedList");

function showResults(){
  const { subject, questions, correctCount, bestStreak, missed } = session;
  const total = questions.length;
  const percent = Math.round((correctCount / total) * 100);

  quizView.classList.remove("active");
  resultsView.classList.add("active");
  document.documentElement.style.setProperty("--accent", subject.accent);

  resultPercent.textContent = percent + "%";
  resultFraction.textContent = `${correctCount} / ${total}`;
  statCorrect.textContent = correctCount;
  statWrong.textContent = total - correctCount;
  statBestStreak.textContent = bestStreak;

  const circumference = 439.8;
  const offset = circumference - (percent/100) * circumference;
  // resolve the subject's CSS variable (e.g. "var(--histoire)") to an actual color value
  const varName = subject.accent.replace("var(", "").replace(")", "").trim();
  const resolvedColor = getComputedStyle(document.documentElement).getPropertyValue(varName).trim();
  ringFg.style.stroke = resolvedColor || "#FBBF24";
  requestAnimationFrame(() => {
    ringFg.style.strokeDashoffset = offset;
  });

  let title, sub;
  if(percent >= 90){ title = "Niveau brevet acquis."; sub = "Une maîtrise quasi parfaite du chapitre. Garde ce rythme jusqu'à l'épreuve."; }
  else if(percent >= 70){ title = "Très solide."; sub = "Tu tiens la matière. Reprends les quelques points manqués ci-dessous et ce sera complet."; }
  else if(percent >= 50){ title = "Bonne base, à consolider."; sub = "La moitié est là. Relis les explications ci-dessous, elles ciblent exactement tes lacunes."; }
  else { title = "On reprend depuis le début."; sub = "C'est normal de buter sur un chapitre dense. Relis le cours, puis retente : la mémorisation vient par répétition."; }
  resultsTitle.textContent = title;
  resultsSub.textContent = sub;

  // best score persistence
  const prevBest = progress.bestScores[subject.id];
  if(!prevBest || percent > prevBest.percent){
    progress.bestScores[subject.id] = { percent, date: new Date().toISOString() };
    saveProgress(progress);
  }

  if(missed.length > 0){
    missedReview.style.display = "block";
    missedList.innerHTML = "";
    missed.slice(0, 8).forEach(q => {
      const div = document.createElement("div");
      div.className = "missed-item";
      const correctAnswer = q.type === "vf" ? (q.correct ? "Vrai" : "Faux") : q.choices[q.correct];
      div.innerHTML = `<p class="missed-q">${q.q}</p><p class="missed-a">Réponse : <strong>${correctAnswer}</strong></p>`;
      missedList.appendChild(div);
    });
    if(missed.length > 8){
      const more = document.createElement("p");
      more.className = "missed-a";
      more.style.marginTop = "10px";
      more.textContent = `+ ${missed.length - 8} autres questions à revoir.`;
      missedList.appendChild(more);
    }
  } else {
    missedReview.style.display = "none";
  }
}

document.getElementById("retryBtn").addEventListener("click", () => {
  startQuiz(session.subject.id);
});
document.getElementById("homeBtn").addEventListener("click", goHome);

// ============================================================
// INIT
// ============================================================
renderHome();


</script>
</body>
</html>
