<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tejaswini J R — AI & Data Science</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --black: #080810;
  --white: #f0ede8;
  --cream: #f7f4ef;
  --gold: #c9a84c;
  --gold-light: #e8c96e;
  --blue: #3b82f6;
  --purple: #7c3aed;
  --green: #10b981;
  --card: rgba(255,255,255,0.04);
  --border: rgba(255,255,255,0.08);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }

body {
  font-family: 'Outfit', sans-serif;
  background: var(--black);
  color: var(--white);
  overflow-x: hidden;
}

/* ─── NOISE TEXTURE OVERLAY ─── */
body::before {
  content: '';
  position: fixed; inset: 0; z-index: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
  pointer-events: none; opacity: 0.4;
}

/* ─── NAV ─── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 999;
  display: flex; justify-content: space-between; align-items: center;
  padding: 1.4rem 5rem;
  background: rgba(8,8,16,0.7);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border);
}
.logo {
  font-family: 'Playfair Display', serif;
  font-size: 1.15rem; font-weight: 700;
  letter-spacing: 0.02em;
  background: linear-gradient(135deg, var(--gold), var(--gold-light));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
}
.nav-links { display: flex; gap: 2.5rem; }
.nav-links a {
  font-size: 0.78rem; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase;
  color: rgba(240,237,232,0.5); text-decoration: none;
  transition: color 0.25s;
}
.nav-links a:hover { color: var(--gold); }

/* ─── HERO ─── */
.hero {
  position: relative; min-height: 100vh;
  display: flex; flex-direction: column; justify-content: center;
  padding: 0 5rem;
  overflow: hidden;
}
.hero-grid-bg {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(201,168,76,0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(201,168,76,0.05) 1px, transparent 1px);
  background-size: 60px 60px;
  mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 30%, transparent 100%);
}
.hero-glow {
  position: absolute; width: 800px; height: 800px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(201,168,76,0.08) 0%, transparent 65%);
  top: -200px; right: -200px;
  pointer-events: none;
}
.hero-glow2 {
  position: absolute; width: 500px; height: 500px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(124,58,237,0.06) 0%, transparent 65%);
  bottom: 0; left: 100px;
  pointer-events: none;
}

.hero-content { position: relative; z-index: 1; max-width: 900px; }
.hero-kicker {
  display: flex; align-items: center; gap: 0.75rem;
  margin-bottom: 2rem;
}
.kicker-line { width: 40px; height: 1px; background: var(--gold); }
.kicker-text {
  font-size: 0.72rem; font-weight: 600; letter-spacing: 0.2em; text-transform: uppercase;
  color: var(--gold);
}
.hero-name {
  font-family: 'Playfair Display', serif;
  font-size: clamp(4.5rem, 9vw, 8rem);
  font-weight: 900; line-height: 0.92;
  letter-spacing: -0.02em;
  color: var(--white);
  margin-bottom: 1rem;
}
.hero-name em {
  font-style: italic;
  background: linear-gradient(135deg, var(--gold), var(--gold-light));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
}
.hero-sub {
  font-size: 1.05rem; font-weight: 300; color: rgba(240,237,232,0.55);
  line-height: 1.7; max-width: 560px;
  margin-bottom: 3rem;
}
.hero-stats {
  display: flex; gap: 3rem; margin-bottom: 3rem; flex-wrap: wrap;
}
.hero-stat-num {
  font-family: 'Playfair Display', serif;
  font-size: 2.2rem; font-weight: 700;
  color: var(--gold); line-height: 1;
  margin-bottom: 0.2rem;
}
.hero-stat-lbl {
  font-size: 0.72rem; font-weight: 400; color: rgba(240,237,232,0.4);
  letter-spacing: 0.05em; text-transform: uppercase;
}
.hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; }

.btn {
  display: inline-flex; align-items: center; gap: 0.5rem;
  padding: 0.85rem 2rem; border-radius: 4px;
  font-family: 'Outfit', sans-serif; font-size: 0.82rem; font-weight: 600;
  letter-spacing: 0.08em; text-transform: uppercase;
  text-decoration: none; border: none; cursor: pointer;
  transition: all 0.25s;
}
.btn-gold {
  background: linear-gradient(135deg, var(--gold), var(--gold-light));
  color: var(--black);
}
.btn-gold:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(201,168,76,0.35); }
.btn-ghost {
  background: transparent; color: var(--white);
  border: 1px solid rgba(240,237,232,0.2);
}
.btn-ghost:hover { border-color: var(--gold); color: var(--gold); }

.hero-contacts {
  position: absolute; right: 5rem; bottom: 4rem; z-index: 1;
  display: flex; flex-direction: column; gap: 0.5rem; align-items: flex-end;
}
.hc-item {
  display: flex; align-items: center; gap: 0.5rem;
  font-size: 0.78rem; color: rgba(240,237,232,0.4);
  text-decoration: none; transition: color 0.2s;
}
.hc-item:hover { color: var(--gold); }
.hc-dot { width: 5px; height: 5px; border-radius: 50%; background: var(--gold); flex-shrink: 0; }

/* ─── SECTION BASE ─── */
section { position: relative; z-index: 1; padding: 7rem 5rem; }
.sec-label {
  display: flex; align-items: center; gap: 0.75rem;
  margin-bottom: 1rem;
}
.sec-label-line { width: 30px; height: 1px; background: var(--gold); }
.sec-label-txt {
  font-size: 0.68rem; font-weight: 600; letter-spacing: 0.2em; text-transform: uppercase;
  color: var(--gold);
}
.sec-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.2rem, 4vw, 3.2rem);
  font-weight: 900; line-height: 1.1; letter-spacing: -0.02em;
  color: var(--white); margin-bottom: 3.5rem;
}
.sec-title em { font-style: italic; color: var(--gold); }

/* ─── ABOUT STRIP ─── */
.about-strip {
  background: linear-gradient(135deg, rgba(201,168,76,0.08), rgba(124,58,237,0.05));
  border-top: 1px solid rgba(201,168,76,0.15);
  border-bottom: 1px solid rgba(201,168,76,0.15);
  padding: 4rem 5rem;
}
.about-inner {
  display: grid; grid-template-columns: 1fr 2fr; gap: 5rem; align-items: center;
}
.about-portrait-wrap {
  position: relative;
}
.about-portrait-box {
  width: 100%; aspect-ratio: 3/4;
  border-radius: 4px; overflow: hidden;
  background: linear-gradient(135deg, #1a1a2e, #16213e);
  border: 1px solid rgba(201,168,76,0.2);
  display: flex; align-items: center; justify-content: center;
  position: relative;
}
.portrait-initial {
  font-family: 'Playfair Display', serif;
  font-size: 6rem; font-weight: 900; font-style: italic;
  background: linear-gradient(135deg, var(--gold), var(--gold-light));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
}
.portrait-corner {
  position: absolute; width: 40px; height: 40px;
  border-color: var(--gold); border-style: solid; border-width: 0;
}
.portrait-corner.tl { top: 12px; left: 12px; border-top-width: 2px; border-left-width: 2px; }
.portrait-corner.br { bottom: 12px; right: 12px; border-bottom-width: 2px; border-right-width: 2px; }

.about-text {}
.about-bio {
  font-size: 1rem; font-weight: 300; line-height: 1.9;
  color: rgba(240,237,232,0.7);
  margin-bottom: 2rem;
}
.about-chips { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 2.5rem; }
.chip {
  padding: 0.4rem 1rem; border-radius: 2px;
  font-size: 0.75rem; font-weight: 500; letter-spacing: 0.05em;
  border: 1px solid rgba(201,168,76,0.25);
  color: rgba(240,237,232,0.6);
  background: rgba(201,168,76,0.05);
}
.edu-row {
  display: flex; flex-direction: column; gap: 0.85rem;
}
.edu-item {
  display: flex; justify-content: space-between; align-items: baseline;
  padding-bottom: 0.85rem;
  border-bottom: 1px solid rgba(255,255,255,0.06);
}
.edu-item:last-child { border-bottom: none; padding-bottom: 0; }
.edu-deg { font-size: 0.88rem; font-weight: 500; }
.edu-sch { font-size: 0.75rem; color: rgba(240,237,232,0.45); margin-top: 0.15rem; }
.edu-score {
  font-family: 'Playfair Display', serif;
  font-size: 1.1rem; color: var(--gold); font-weight: 700; white-space: nowrap;
}

/* ─── SKILLS ─── */
.skills-section { background: rgba(0,0,0,0.3); }
.skills-masonry {
  display: grid; grid-template-columns: repeat(3, 1fr); gap: 1px;
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 4px; overflow: hidden;
}
.skill-block {
  background: var(--card);
  border: none; padding: 2rem 2rem;
  transition: background 0.3s;
  cursor: default;
}
.skill-block:hover { background: rgba(201,168,76,0.05); }
.skill-block-title {
  font-size: 0.68rem; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase;
  color: var(--gold); margin-bottom: 1rem;
  display: flex; align-items: center; gap: 0.5rem;
}
.skill-pills { display: flex; flex-wrap: wrap; gap: 0.4rem; }
.pill {
  padding: 0.25rem 0.7rem; border-radius: 2px;
  font-size: 0.73rem; font-weight: 400;
  background: rgba(255,255,255,0.05);
  color: rgba(240,237,232,0.65);
  border: 1px solid rgba(255,255,255,0.07);
  transition: all 0.2s;
}
.skill-block:hover .pill { border-color: rgba(201,168,76,0.2); color: rgba(240,237,232,0.85); }

/* ─── EXPERIENCE ─── */
.exp-section {}
.exp-timeline { display: flex; flex-direction: column; gap: 0; position: relative; }
.exp-timeline::before {
  content: '';
  position: absolute; left: 20px; top: 0; bottom: 0; width: 1px;
  background: linear-gradient(to bottom, var(--gold), rgba(201,168,76,0.1));
}
.exp-item {
  display: grid; grid-template-columns: 60px 1fr; gap: 2rem;
  padding-bottom: 3rem; position: relative;
}
.exp-item:last-child { padding-bottom: 0; }
.exp-dot-wrap { display: flex; justify-content: center; padding-top: 0.2rem; }
.exp-dot {
  width: 12px; height: 12px; border-radius: 50%;
  border: 2px solid var(--gold);
  background: var(--black); flex-shrink: 0;
  position: relative; z-index: 1;
}
.exp-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 4px; padding: 1.75rem 2rem;
  transition: border-color 0.3s, background 0.3s;
}
.exp-card:hover {
  border-color: rgba(201,168,76,0.25);
  background: rgba(201,168,76,0.03);
}
.exp-head { display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 0.4rem; }
.exp-role {
  font-family: 'Playfair Display', serif;
  font-size: 1.05rem; font-weight: 700; font-style: italic;
  color: var(--white);
}
.exp-badge {
  font-size: 0.68rem; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase;
  padding: 0.2rem 0.65rem; border-radius: 2px;
  background: rgba(201,168,76,0.12); color: var(--gold);
  border: 1px solid rgba(201,168,76,0.2);
}
.exp-org { font-size: 0.8rem; color: rgba(240,237,232,0.4); margin-bottom: 1rem; }
.exp-points { display: flex; flex-direction: column; gap: 0.45rem; }
.exp-point {
  font-size: 0.82rem; color: rgba(240,237,232,0.6); line-height: 1.65;
  padding-left: 1.1rem; position: relative;
}
.exp-point::before {
  content: '—';
  position: absolute; left: 0; color: var(--gold); font-size: 0.65rem;
  top: 0.3rem;
}

/* ─── PROJECTS ─── */
.projects-section { background: rgba(0,0,0,0.2); }
.projects-duo {
  display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem;
}
.proj-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 4px; padding: 2.5rem;
  transition: all 0.3s; position: relative; overflow: hidden;
}
.proj-card::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 2px;
  background: linear-gradient(90deg, var(--gold), var(--gold-light));
  transform: scaleX(0); transform-origin: left;
  transition: transform 0.4s;
}
.proj-card:hover::before { transform: scaleX(1); }
.proj-card:hover {
  border-color: rgba(201,168,76,0.2);
  transform: translateY(-4px);
  box-shadow: 0 20px 60px rgba(0,0,0,0.3);
}
.proj-num {
  font-family: 'Playfair Display', serif;
  font-size: 3.5rem; font-weight: 900; font-style: italic;
  color: rgba(201,168,76,0.12); line-height: 1;
  margin-bottom: 1rem;
}
.proj-name {
  font-family: 'Playfair Display', serif;
  font-size: 1.3rem; font-weight: 700;
  color: var(--white); margin-bottom: 0.4rem;
}
.proj-context {
  font-size: 0.72rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase;
  color: var(--gold); margin-bottom: 1rem;
}
.proj-desc { font-size: 0.83rem; color: rgba(240,237,232,0.55); line-height: 1.75; margin-bottom: 1.5rem; }
.proj-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
.proj-tag {
  padding: 0.2rem 0.6rem; font-size: 0.68rem; border-radius: 2px;
  background: rgba(255,255,255,0.05); color: rgba(240,237,232,0.5);
  border: 1px solid rgba(255,255,255,0.07);
}

/* ─── CERTIFICATIONS ─── */
.certs-section {}
.cert-filter-row {
  display: flex; gap: 0.5rem; flex-wrap: wrap; margin-bottom: 2.5rem;
}
.cf-btn {
  padding: 0.45rem 1.1rem; border-radius: 2px;
  font-family: 'Outfit', sans-serif;
  font-size: 0.72rem; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase;
  cursor: pointer; border: 1px solid rgba(255,255,255,0.12);
  background: transparent; color: rgba(240,237,232,0.5);
  transition: all 0.2s;
}
.cf-btn.active, .cf-btn:hover {
  background: var(--gold); color: var(--black); border-color: var(--gold);
}

.certs-wall {
  display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 0.75rem;
}
.c-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 3px; padding: 1.1rem 1.25rem;
  display: flex; gap: 1rem; align-items: flex-start;
  transition: all 0.2s;
}
.c-card:hover {
  border-color: rgba(201,168,76,0.3);
  background: rgba(201,168,76,0.04);
  transform: translateX(3px);
}
.c-icon {
  font-size: 1.2rem; flex-shrink: 0;
  width: 36px; height: 36px; border-radius: 3px;
  display: flex; align-items: center; justify-content: center;
}
.c-name {
  font-size: 0.8rem; font-weight: 500; color: rgba(240,237,232,0.85);
  line-height: 1.4; margin-bottom: 0.3rem;
}
.c-issuer { font-size: 0.7rem; color: var(--gold); font-weight: 400; margin-bottom: 0.2rem; }
.c-date { font-size: 0.65rem; color: rgba(240,237,232,0.3); }
.c-badge {
  display: inline-block; font-size: 0.6rem; font-weight: 700;
  letter-spacing: 0.08em; text-transform: uppercase;
  padding: 0.1rem 0.45rem; border-radius: 2px; margin-top: 0.3rem;
}
.cb-course { background: rgba(16,185,129,0.15); color: #34d399; }
.cb-intern { background: rgba(201,168,76,0.15); color: var(--gold); }
.cb-workshop { background: rgba(124,58,237,0.15); color: #a78bfa; }
.c-card[data-hidden] { display: none; }

/* ─── EXTRAS ─── */
.extras-section { background: rgba(0,0,0,0.2); }
.extras-row {
  display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem;
}
.extra-block {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 4px; padding: 2rem;
}
.extra-title {
  font-size: 0.68rem; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase;
  color: var(--gold); margin-bottom: 1.2rem;
  display: flex; align-items: center; gap: 0.5rem;
}
.extra-item {
  display: flex; align-items: flex-start; gap: 0.75rem;
  padding: 0.65rem 0;
  border-bottom: 1px solid rgba(255,255,255,0.05);
  font-size: 0.82rem; color: rgba(240,237,232,0.6); line-height: 1.5;
}
.extra-item:last-child { border-bottom: none; }
.extra-bullet { color: var(--gold); flex-shrink: 0; font-size: 0.6rem; margin-top: 0.35rem; }

/* ─── FOOTER ─── */
footer {
  position: relative; z-index: 1;
  padding: 4rem 5rem;
  border-top: 1px solid rgba(255,255,255,0.06);
  display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 2rem;
}
.footer-brand .logo { font-size: 1.4rem; }
.footer-brand p { font-size: 0.78rem; color: rgba(240,237,232,0.3); margin-top: 0.4rem; }
.footer-links { display: flex; flex-direction: column; gap: 0.4rem; align-items: flex-end; }
.footer-links a {
  font-size: 0.78rem; color: rgba(240,237,232,0.4);
  text-decoration: none; transition: color 0.2s;
}
.footer-links a:hover { color: var(--gold); }
.footer-copy {
  width: 100%; text-align: center;
  font-size: 0.68rem; color: rgba(240,237,232,0.2);
  padding-top: 2rem; border-top: 1px solid rgba(255,255,255,0.04);
}

/* ─── ANIMATIONS ─── */
.reveal {
  opacity: 0; transform: translateY(40px);
  transition: opacity 0.8s cubic-bezier(.16,1,.3,1), transform 0.8s cubic-bezier(.16,1,.3,1);
}
.reveal.in { opacity: 1; transform: translateY(0); }
.reveal-d1 { transition-delay: 0.1s; }
.reveal-d2 { transition-delay: 0.2s; }
.reveal-d3 { transition-delay: 0.3s; }
.reveal-d4 { transition-delay: 0.4s; }

/* ─── RESPONSIVE ─── */
@media (max-width: 900px) {
  nav { padding: 1.2rem 1.5rem; }
  .nav-links { display: none; }
  section { padding: 5rem 1.5rem; }
  .hero { padding: 0 1.5rem; }
  .hero-stats { gap: 1.5rem; }
  .hero-contacts { position: static; align-items: flex-start; margin-top: 2rem; }
  .about-strip { padding: 4rem 1.5rem; }
  .about-inner { grid-template-columns: 1fr; gap: 2.5rem; }
  .about-portrait-box { max-width: 200px; }
  .skills-masonry { grid-template-columns: 1fr; }
  .projects-duo { grid-template-columns: 1fr; }
  .extras-row { grid-template-columns: 1fr; }
  footer { padding: 3rem 1.5rem; }
  .footer-links { align-items: flex-start; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">TJR</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#experience">Experience</a>
    <a href="#projects">Projects</a>
    <a href="#certifications">Certifications</a>
  </div>
</nav>

<!-- ═══ HERO ═══ -->
<div class="hero" id="top">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>

  <div class="hero-content">
    <div class="hero-kicker reveal">
      <div class="kicker-line"></div>
      <div class="kicker-text">AI & Data Science · B.Tech 2024–2028</div>
    </div>
    <h1 class="hero-name reveal reveal-d1">
      Tejaswini<br><em>J R</em>
    </h1>
    <p class="hero-sub reveal reveal-d2">
      Motivated undergraduate at Sree Sastha Institute of Engineering & Technology, Chennai — exploring the intersection of machine learning, data analysis, and real-world impact.
    </p>
    <div class="hero-stats reveal reveal-d3">
      <div>
        <div class="hero-stat-num">8.06</div>
        <div class="hero-stat-lbl">CGPA</div>
      </div>
      <div>
        <div class="hero-stat-num">4</div>
        <div class="hero-stat-lbl">Internships</div>
      </div>
      <div>
        <div class="hero-stat-num">21+</div>
        <div class="hero-stat-lbl">Credentials</div>
      </div>
      <div>
        <div class="hero-stat-num">2028</div>
        <div class="hero-stat-lbl">Graduating</div>
      </div>
    </div>
    <div class="hero-actions reveal reveal-d4">
      <a href="#certifications" class="btn btn-gold">View Certifications</a>
      <a href="#experience" class="btn btn-ghost">My Experience</a>
    </div>
  </div>

  <div class="hero-contacts">
    <a class="hc-item" href="mailto:jrtm0504@gmail.com">
      <div class="hc-dot"></div> jrtm0504@gmail.com
    </a>
    <a class="hc-item" href="tel:+917010912493">
      <div class="hc-dot"></div> +91 70109 12493
    </a>
    <a class="hc-item" href="https://linkedin.com/in/tejaswini-martin" target="_blank">
      <div class="hc-dot"></div> linkedin.com/in/tejaswini-martin
    </a>
    <a class="hc-item">
      <div class="hc-dot"></div> Chennai, India
    </a>
  </div>
</div>

<!-- ═══ ABOUT ═══ -->
<div class="about-strip" id="about">
  <div class="about-inner">
    <div class="about-portrait-wrap reveal">
      <div class="about-portrait-box">
        <div class="portrait-corner tl"></div>
        <div class="portrait-corner br"></div>
        <div class="portrait-initial">TJR</div>
      </div>
    </div>
    <div class="about-text">
      <div class="sec-label reveal">
        <div class="sec-label-line"></div>
        <div class="sec-label-txt">About Me</div>
      </div>
      <p class="about-bio reveal reveal-d1">
        I'm a second-year B.Tech student specialising in Artificial Intelligence & Data Science. I've completed four internships — in AI, sustainability, content writing, and green skills — alongside 21+ certifications and workshops spanning machine learning, IoT, prompt engineering, and web development.
        <br><br>
        I'm passionate about building real-world solutions with AI, curious about entrepreneurship, and committed to continuous learning through every project I take on.
      </p>
      <div class="about-chips reveal reveal-d2">
        <span class="chip">Machine Learning</span>
        <span class="chip">Data Analysis</span>
        <span class="chip">Python</span>
        <span class="chip">Prompt Engineering</span>
        <span class="chip">Tableau</span>
        <span class="chip">IoT</span>
        <span class="chip">Solar Entrepreneurship</span>
        <span class="chip">Technical Writing</span>
      </div>
      <div class="edu-row reveal reveal-d3">
        <div class="edu-item">
          <div>
            <div class="edu-deg">B.Tech — Artificial Intelligence & Data Science</div>
            <div class="edu-sch">Sree Sastha Institute of Engineering & Technology · 2024–2028</div>
          </div>
          <div class="edu-score">8.06</div>
        </div>
        <div class="edu-item">
          <div>
            <div class="edu-deg">Higher Secondary (Class XII)</div>
            <div class="edu-sch">Holy Cross Matric Hr. Sec. School, Vellore · 2024</div>
          </div>
          <div class="edu-score">76%</div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ═══ SKILLS ═══ -->
<section class="skills-section" id="skills">
  <div class="sec-label reveal"><div class="sec-label-line"></div><div class="sec-label-txt">Technical Skills</div></div>
  <h2 class="sec-title reveal reveal-d1">What I Work <em>With</em></h2>
  <div class="skills-masonry reveal reveal-d2">
    <div class="skill-block">
      <div class="skill-block-title">🐍 Programming</div>
      <div class="skill-pills">
        <span class="pill">Python</span><span class="pill">NumPy</span><span class="pill">Pandas</span>
        <span class="pill">Matplotlib</span><span class="pill">SQL</span><span class="pill">Oracle DB</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-title">🤖 ML & AI</div>
      <div class="skill-pills">
        <span class="pill">Supervised Learning</span><span class="pill">Data Preprocessing</span>
        <span class="pill">Model Evaluation</span><span class="pill">TensorFlow (basics)</span>
        <span class="pill">Prompt Engineering</span><span class="pill">Generative AI</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-title">📊 Data & Viz</div>
      <div class="skill-pills">
        <span class="pill">EDA</span><span class="pill">Tableau</span>
        <span class="pill">Statistical Analysis</span><span class="pill">Data Cleaning</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-title">🛠 Tools</div>
      <div class="skill-pills">
        <span class="pill">Jupyter Notebook</span><span class="pill">Google Colab</span>
        <span class="pill">GitHub</span><span class="pill">VS Code</span>
        <span class="pill">Google Workspace</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-title">🌐 Development</div>
      <div class="skill-pills">
        <span class="pill">Web Development</span><span class="pill">Node.js (basics)</span>
        <span class="pill">IoT Device Programming</span><span class="pill">Salesforce CRM</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-title">💬 Soft Skills</div>
      <div class="skill-pills">
        <span class="pill">Technical Writing</span><span class="pill">Research</span>
        <span class="pill">Problem Solving</span><span class="pill">Communication</span>
        <span class="pill">Collaboration</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══ EXPERIENCE ═══ -->
<section id="experience">
  <div class="sec-label reveal"><div class="sec-label-line"></div><div class="sec-label-txt">Work Experience</div></div>
  <h2 class="sec-title reveal reveal-d1">Internships &amp; <em>Roles</em></h2>
  <div class="exp-timeline">
    <div class="exp-item reveal">
      <div class="exp-dot-wrap"><div class="exp-dot"></div></div>
      <div class="exp-card">
        <div class="exp-head">
          <div class="exp-role">Content Writing Intern</div>
          <span class="exp-badge">Mar 2026 · 15 Days</span>
        </div>
        <div class="exp-org">Inamigos Foundation</div>
        <div class="exp-points">
          <div class="exp-point">Produced structured, audience-focused content aligned with the foundation's social impact communication strategy.</div>
          <div class="exp-point">Applied research and technical writing skills to deliver clear messaging for digital and outreach initiatives.</div>
        </div>
      </div>
    </div>
    <div class="exp-item reveal reveal-d1">
      <div class="exp-dot-wrap"><div class="exp-dot"></div></div>
      <div class="exp-card">
        <div class="exp-head">
          <div class="exp-role">Artificial Intelligence Intern</div>
          <span class="exp-badge">Feb 2026 · 1 Week</span>
        </div>
        <div class="exp-org">Top Engineers — India</div>
        <div class="exp-points">
          <div class="exp-point">Explored core AI concepts, tools, and real-world applications through an intensive one-week structured program.</div>
          <div class="exp-point">Participated in live technical sessions on AI frameworks, enhancing problem-solving and analytical capabilities.</div>
          <div class="exp-point">Applied conceptual AI knowledge to practical scenarios, strengthening understanding of industry-standard workflows.</div>
        </div>
      </div>
    </div>
    <div class="exp-item reveal reveal-d2">
      <div class="exp-dot-wrap"><div class="exp-dot"></div></div>
      <div class="exp-card">
        <div class="exp-head">
          <div class="exp-role">Green Skills Intern</div>
          <span class="exp-badge">Dec 2025 – Jan 2026</span>
        </div>
        <div class="exp-org">1M1B Green Skills Academy · AICTE & Salesforce</div>
        <div class="exp-points">
          <div class="exp-point">Completed a 60-hour certified program covering sustainability practices, advanced Tableau, and data visualization.</div>
          <div class="exp-point">Delivered a 20-hour live project applying green skills in a professional context with measurable outcomes.</div>
          <div class="exp-point">Leveraged Salesforce and AICTE-supported tools to execute and document project deliverables effectively.</div>
        </div>
      </div>
    </div>
    <div class="exp-item reveal reveal-d3">
      <div class="exp-dot-wrap"><div class="exp-dot"></div></div>
      <div class="exp-card">
        <div class="exp-head">
          <div class="exp-role">AI Virtual Internship</div>
          <span class="exp-badge">Dec 2025 · 1 Month</span>
        </div>
        <div class="exp-org">CodeAlpha</div>
        <div class="exp-points">
          <div class="exp-point">Executed AI-based programming assignments in Python, reinforcing skills in machine learning workflows.</div>
          <div class="exp-point">Applied theoretical ML knowledge to practical tasks, strengthening understanding of model development.</div>
          <div class="exp-point">Demonstrated self-directed learning and technical initiative in a fully remote, asynchronous environment.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ PROJECTS ═══ -->
<section class="projects-section" id="projects">
  <div class="sec-label reveal"><div class="sec-label-line"></div><div class="sec-label-txt">Projects</div></div>
  <h2 class="sec-title reveal reveal-d1">Featured <em>Work</em></h2>
  <div class="projects-duo">
    <div class="proj-card reveal reveal-d1">
      <div class="proj-num">01</div>
      <div class="proj-name">Rural Health Assistance</div>
      <div class="proj-context">Mind2Market 2k25 Hackathon · 2025</div>
      <p class="proj-desc">
        Engineered a technology-driven solution to improve healthcare accessibility in underserved rural communities. Collaborated with GO TECH and BISLERI; pitched solution to industry judges demonstrating technical depth and communication skills.
      </p>
      <div class="proj-tags">
        <span class="proj-tag">Hackathon</span>
        <span class="proj-tag">Healthcare AI</span>
        <span class="proj-tag">Team Collaboration</span>
        <span class="proj-tag">Pitching</span>
      </div>
    </div>
    <div class="proj-card reveal reveal-d2">
      <div class="proj-num">02</div>
      <div class="proj-name">Zero Waste Eco-Brick System</div>
      <div class="proj-context">1M1B Green Internship · Jan 2026</div>
      <p class="proj-desc">
        Designed an end-to-end plastic waste management pipeline: collection, segregation, and compression into eco-bricks. Documented the full process and promoted zero-waste practices, producing a structured, replicable sustainability model.
      </p>
      <div class="proj-tags">
        <span class="proj-tag">Sustainability</span>
        <span class="proj-tag">Data Documentation</span>
        <span class="proj-tag">Live Project</span>
        <span class="proj-tag">Tableau</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══ CERTIFICATIONS ═══ -->
<section id="certifications">
  <div class="sec-label reveal"><div class="sec-label-line"></div><div class="sec-label-txt">Credentials</div></div>
  <h2 class="sec-title reveal reveal-d1">Certifications &amp; <em>Workshops</em></h2>

  <div class="cert-filter-row reveal reveal-d2">
    <button class="cf-btn active" onclick="fc('all',this)">All (21)</button>
    <button class="cf-btn" onclick="fc('course',this)">Courses</button>
    <button class="cf-btn" onclick="fc('intern',this)">Internships</button>
    <button class="cf-btn" onclick="fc('workshop',this)">Workshops</button>
  </div>

  <div class="certs-wall reveal reveal-d3">
    <!-- COURSES -->
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(59,130,246,0.1)">📘</div>
      <div>
        <div class="c-name">Agile Scrum in Practice</div>
        <div class="c-issuer">Infosys Springboard</div>
        <div class="c-date">Apr 27, 2026</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(59,130,246,0.1)">💡</div>
      <div>
        <div class="c-name">Prompt Engineering</div>
        <div class="c-issuer">Infosys Springboard</div>
        <div class="c-date">Apr 27, 2026</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(59,130,246,0.1)">⚙️</div>
      <div>
        <div class="c-name">Software Engineering & Agile Development</div>
        <div class="c-issuer">Infosys Springboard</div>
        <div class="c-date">Apr 27, 2026</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(59,130,246,0.1)">📊</div>
      <div>
        <div class="c-name">Data Science</div>
        <div class="c-issuer">Infosys Springboard</div>
        <div class="c-date">Apr 24, 2026</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(59,130,246,0.1)">🔒</div>
      <div>
        <div class="c-name">Network Security Fundamentals</div>
        <div class="c-issuer">Infosys Springboard</div>
        <div class="c-date">Nov 21, 2025</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(16,185,129,0.1)">🖥️</div>
      <div>
        <div class="c-name">Data Science & Analytics</div>
        <div class="c-issuer">HP LIFE Foundation</div>
        <div class="c-date">Feb 1, 2026</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(201,168,76,0.1)">🧠</div>
      <div>
        <div class="c-name">Crafting Precision Prompts with Generative AI</div>
        <div class="c-issuer">IBM SkillsBuild</div>
        <div class="c-date">Nov 21, 2025 · 1 hr</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(201,168,76,0.1)">❓</div>
      <div>
        <div class="c-name">What is Prompt Tuning?</div>
        <div class="c-issuer">IBM SkillsBuild</div>
        <div class="c-date">May 9, 2026 · 15 mins</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(201,168,76,0.1)">🎯</div>
      <div>
        <div class="c-name">1M1B | Master the Art of Prompting</div>
        <div class="c-issuer">IBM SkillsBuild</div>
        <div class="c-date">May 9, 2026</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(201,168,76,0.1)">📄</div>
      <div>
        <div class="c-name">Make Your Resume Stand Out | IBM Careers</div>
        <div class="c-issuer">IBM SkillsBuild</div>
        <div class="c-date">May 9, 2026 · 2 mins</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(124,58,237,0.1)">🤖</div>
      <div>
        <div class="c-name">Freedom with AI Masterclass</div>
        <div class="c-issuer">Freedom with AI (ISO 9001:2015)</div>
        <div class="c-date">Nov 22, 2025</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>
    <div class="c-card" data-type="course">
      <div class="c-icon" style="background:rgba(16,185,129,0.1)">☀️</div>
      <div>
        <div class="c-name">ESDP on Solar Entrepreneurship (PM SG: MBY)</div>
        <div class="c-issuer">NIESBUD / Skill India</div>
        <div class="c-date">Mar 23–31, 2026 · Karaikkal</div>
        <span class="c-badge cb-course">Course</span>
      </div>
    </div>

    <!-- INTERNSHIPS -->
    <div class="c-card" data-type="intern">
      <div class="c-icon" style="background:rgba(201,168,76,0.1)">🤖</div>
      <div>
        <div class="c-name">AI Internship (One Week, Online)</div>
        <div class="c-issuer">Top Engineers – India</div>
        <div class="c-date">Feb 2–8, 2026</div>
        <span class="c-badge cb-intern">Internship</span>
      </div>
    </div>
    <div class="c-card" data-type="intern">
      <div class="c-icon" style="background:rgba(201,168,76,0.1)">🌱</div>
      <div>
        <div class="c-name">1M1B Green Internship (60 hrs)</div>
        <div class="c-issuer">1M1B Academy · AICTE & Salesforce</div>
        <div class="c-date">Dec 2025 – Jan 2026</div>
        <span class="c-badge cb-intern">Internship</span>
      </div>
    </div>
    <div class="c-card" data-type="intern">
      <div class="c-icon" style="background:rgba(201,168,76,0.1)">💻</div>
      <div>
        <div class="c-name">AI Virtual Internship (CodeAlpha)</div>
        <div class="c-issuer">CodeAlpha</div>
        <div class="c-date">Dec 1–30, 2025</div>
        <span class="c-badge cb-intern">Internship</span>
      </div>
    </div>

    <!-- WORKSHOPS -->
    <div class="c-card" data-type="workshop">
      <div class="c-icon" style="background:rgba(124,58,237,0.1)">🔌</div>
      <div>
        <div class="c-name">IoT Device Programming Bootcamp (5-Day)</div>
        <div class="c-issuer">CDAC Bangalore / MIT Anna University</div>
        <div class="c-date">Jul 28 – Aug 1, 2025</div>
        <span class="c-badge cb-workshop">Workshop</span>
      </div>
    </div>
    <div class="c-card" data-type="workshop">
      <div class="c-icon" style="background:rgba(124,58,237,0.1)">🤖</div>
      <div>
        <div class="c-name">Exploring Generative AI: A Foundational Approach</div>
        <div class="c-issuer">Kongu Engineering College (IIPC-IT)</div>
        <div class="c-date">Sep 20, 2025</div>
        <span class="c-badge cb-workshop">Workshop</span>
      </div>
    </div>
    <div class="c-card" data-type="workshop">
      <div class="c-icon" style="background:rgba(124,58,237,0.1)">🧩</div>
      <div>
        <div class="c-name">MCP + AI Workshop (T.A.L.O.S.)</div>
        <div class="c-issuer">Chennai Institute of Technology (Dept. AI & DS)</div>
        <div class="c-date">Feb 4, 2026</div>
        <span class="c-badge cb-workshop">Workshop</span>
      </div>
    </div>
    <div class="c-card" data-type="workshop">
      <div class="c-icon" style="background:rgba(124,58,237,0.1)">🌐</div>
      <div>
        <div class="c-name">Web Development Bootcamp (5-Day)</div>
        <div class="c-issuer">KM UniTech / NextStep Learning / Wyntrix</div>
        <div class="c-date">Feb 9–13, 2026</div>
        <span class="c-badge cb-workshop">Workshop</span>
      </div>
    </div>
    <div class="c-card" data-type="workshop">
      <div class="c-icon" style="background:rgba(124,58,237,0.1)">🟢</div>
      <div>
        <div class="c-name">Learn Node.js From Scratch (UniLink Live 3)</div>
        <div class="c-issuer">KM UniTech / Wyntrix</div>
        <div class="c-date">Jan 18, 2026</div>
        <span class="c-badge cb-workshop">Workshop</span>
      </div>
    </div>
    <div class="c-card" data-type="workshop">
      <div class="c-icon" style="background:rgba(124,58,237,0.1)">🌍</div>
      <div>
        <div class="c-name">Youth Climate Diplomacy & AI Inclusion (CSocD64)</div>
        <div class="c-issuer">1M1B Foundation (Virtual)</div>
        <div class="c-date">Feb 6, 2026</div>
        <span class="c-badge cb-workshop">Workshop</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══ EXTRAS ═══ -->
<section class="extras-section">
  <div class="sec-label reveal"><div class="sec-label-line"></div><div class="sec-label-txt">More About Me</div></div>
  <h2 class="sec-title reveal reveal-d1">Beyond the <em>Classroom</em></h2>
  <div class="extras-row">
    <div class="extra-block reveal reveal-d1">
      <div class="extra-title">🏸 Extracurriculars & Interests</div>
      <div class="extra-item"><span class="extra-bullet">◆</span>Actively exploring AI/ML tools, developer frameworks, and emerging technologies in the AI ecosystem.</div>
      <div class="extra-item"><span class="extra-bullet">◆</span>Badminton player — competing regularly and enjoying the sport's strategy and stamina aspects.</div>
      <div class="extra-item"><span class="extra-bullet">◆</span>Avid reader focused on technology, innovation, AI research topics, and entrepreneurship.</div>
      <div class="extra-item"><span class="extra-bullet">◆</span>Participated in the 64th Session of the Commission for Social Development (CSocD64) as a 1M1B side event delegate.</div>
    </div>
    <div class="extra-block reveal reveal-d2">
      <div class="extra-title">🌐 Languages & Reach</div>
      <div class="extra-item"><span class="extra-bullet">◆</span>Institution: Sree Sastha Institute of Engineering & Technology, Chennai (Affiliated with Anna University)</div>
      <div class="extra-item"><span class="extra-bullet">◆</span>Department: Artificial Intelligence & Data Science (B.Tech, 2nd Year)</div>
      <div class="extra-item"><span class="extra-bullet">◆</span>National Career Service ID: E20G65-2155080186444</div>
      <div class="extra-item"><span class="extra-bullet">◆</span>Open to remote internships, collaborative projects, and full-time roles from 2028 onwards.</div>
    </div>
  </div>
</section>

<!-- ═══ FOOTER ═══ -->
<footer>
  <div class="footer-brand">
    <div class="logo">Tejaswini J R</div>
    <p>AI & Data Science · Sree Sastha Institute, Chennai</p>
  </div>
  <div class="footer-links">
    <a href="mailto:jrtm0504@gmail.com">jrtm0504@gmail.com</a>
    <a href="tel:+917010912493">+91 70109 12493</a>
    <a href="https://linkedin.com/in/tejaswini-martin" target="_blank">LinkedIn ↗</a>
  </div>
  <div class="footer-copy">© 2026 Tejaswini J R · Built with purpose.</div>
</footer>

<script>
// Scroll reveal
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) { e.target.classList.add('in'); observer.unobserve(e.target); }
  });
}, { threshold: 0.08 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

// Cert filter
function fc(type, btn) {
  document.querySelectorAll('.cf-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  document.querySelectorAll('.c-card').forEach(c => {
    type === 'all' || c.dataset.type === type
      ? c.removeAttribute('data-hidden')
      : c.dataset.hidden = '1';
  });
}
</script>
</body>
</html>
