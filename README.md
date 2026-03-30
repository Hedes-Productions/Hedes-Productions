<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>A.G. Tharindu Gimras — Robotics Researcher</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #04091a;
    --bg2: #060d22;
    --surface: #0a1530;
    --surface2: #0d1c3b;
    --border: #1a2d55;
    --accent: #3b82f6;
    --accent2: #60a5fa;
    --accent3: #93c5fd;
    --gold: #f59e0b;
    --gold2: #fbbf24;
    --green: #10b981;
    --text: #e2f0ff;
    --text2: #a0bfe0;
    --text3: #6b8db5;
    --mono: 'Space Mono', monospace;
    --head: 'Syne', sans-serif;
    --body: 'DM Sans', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--body);
    font-size: 15px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── GRID NOISE BACKGROUND ── */
  body::before {
    content: '';
    position: fixed; inset: 0; z-index: 0;
    background-image:
      radial-gradient(ellipse 80% 60% at 20% 10%, rgba(59,130,246,0.07) 0%, transparent 60%),
      radial-gradient(ellipse 60% 50% at 80% 80%, rgba(16,185,129,0.04) 0%, transparent 60%),
      repeating-linear-gradient(0deg, transparent, transparent 39px, rgba(26,45,85,0.25) 39px, rgba(26,45,85,0.25) 40px),
      repeating-linear-gradient(90deg, transparent, transparent 39px, rgba(26,45,85,0.25) 39px, rgba(26,45,85,0.25) 40px);
    pointer-events: none;
  }

  .wrap { position: relative; z-index: 1; max-width: 900px; margin: 0 auto; padding: 0 24px 80px; }

  /* ════════════════════════ HEADER ════════════════════════ */
  header {
    position: relative;
    padding: 80px 0 60px;
    overflow: hidden;
  }

  header::before {
    content: '';
    position: absolute; top: -60px; left: -100px; right: -100px;
    height: 3px;
    background: linear-gradient(90deg, transparent, var(--accent), var(--accent2), var(--green), transparent);
    animation: scanline 3s ease-in-out infinite;
  }

  @keyframes scanline {
    0%,100% { opacity: 0.3; transform: translateX(-10%); }
    50% { opacity: 1; transform: translateX(10%); }
  }

  .hero-label {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.25em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 16px;
    opacity: 0;
    animation: fadeUp 0.6s 0.2s forwards;
  }

  .hero-name {
    font-family: var(--head);
    font-size: clamp(38px, 7vw, 68px);
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #e2f0ff 0%, var(--accent2) 40%, var(--accent) 70%, #60c4ff 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    opacity: 0;
    animation: fadeUp 0.7s 0.35s forwards;
    position: relative;
  }

  /* Animated underline accent on name */
  .hero-name::after {
    content: '';
    position: absolute;
    bottom: -6px; left: 0;
    height: 3px; width: 0;
    background: linear-gradient(90deg, var(--accent), var(--green));
    border-radius: 2px;
    animation: lineGrow 0.8s 1.1s forwards;
  }
  @keyframes lineGrow { to { width: 55%; } }

  .hero-role {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--text2);
    margin-top: 18px;
    letter-spacing: 0.05em;
    opacity: 0;
    animation: fadeUp 0.6s 0.55s forwards;
  }

  .hero-role .highlight { color: var(--accent2); }

  /* Typewriter rotating line */
  .typewriter {
    font-family: var(--mono);
    font-size: 12.5px;
    color: var(--accent);
    margin-top: 10px;
    height: 20px;
    overflow: hidden;
    opacity: 0;
    animation: fadeUp 0.6s 0.75s forwards;
  }

  .tw-inner {
    display: flex;
    flex-direction: column;
    animation: scroll-lines 12s steps(1) infinite;
  }

  .tw-inner span { height: 20px; display: flex; align-items: center; gap: 8px; }

  @keyframes scroll-lines {
    0%   { transform: translateY(0); }
    20%  { transform: translateY(-20px); }
    40%  { transform: translateY(-40px); }
    60%  { transform: translateY(-60px); }
    80%  { transform: translateY(-80px); }
    100% { transform: translateY(0); }
  }

  .hero-badges {
    display: flex; flex-wrap: wrap; gap: 10px;
    margin-top: 32px;
    opacity: 0;
    animation: fadeUp 0.6s 0.9s forwards;
  }

  .badge {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 14px;
    border-radius: 4px;
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.05em;
    text-decoration: none;
    border: 1px solid;
    transition: all 0.2s;
    white-space: nowrap;
  }

  .badge-primary {
    background: rgba(59,130,246,0.12);
    border-color: rgba(59,130,246,0.4);
    color: var(--accent2);
  }
  .badge-primary:hover { background: rgba(59,130,246,0.22); border-color: var(--accent2); transform: translateY(-1px); }

  .badge-gold {
    background: rgba(245,158,11,0.1);
    border-color: rgba(245,158,11,0.35);
    color: var(--gold2);
  }

  .badge-green {
    background: rgba(16,185,129,0.1);
    border-color: rgba(16,185,129,0.35);
    color: #34d399;
    text-decoration: none;
  }
  .badge-green:hover { background: rgba(16,185,129,0.2); transform: translateY(-1px); }

  .badge-ghost {
    background: transparent;
    border-color: var(--border);
    color: var(--text3);
    text-decoration: none;
  }
  .badge-ghost:hover { border-color: var(--accent); color: var(--accent2); transform: translateY(-1px); }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ════════════════════════ SOCIAL STRIP ════════════════════ */
  .social-strip {
    display: flex; flex-wrap: wrap; gap: 8px;
    margin: 24px 0 0;
    padding-top: 24px;
    border-top: 1px solid var(--border);
    opacity: 0;
    animation: fadeUp 0.6s 1.05s forwards;
  }

  .soc-btn {
    display: inline-flex; align-items: center; gap: 5px;
    padding: 5px 12px;
    border-radius: 3px;
    font-family: var(--mono);
    font-size: 10.5px;
    text-decoration: none;
    border: 1px solid var(--border);
    color: var(--text3);
    transition: all 0.15s;
    letter-spacing: 0.04em;
  }
  .soc-btn:hover { color: var(--accent2); border-color: var(--accent); background: rgba(59,130,246,0.08); }

  /* ════════════════════════ SECTION ════════════════════════ */
  section { margin-top: 64px; }

  .section-tag {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 6px;
  }

  h2 {
    font-family: var(--head);
    font-size: 26px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 28px;
    display: flex; align-items: center; gap: 12px;
  }

  h2::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ════════════════════════ PHD CTA ════════════════════════ */
  .phd-cta {
    background: linear-gradient(135deg, rgba(59,130,246,0.08) 0%, rgba(16,185,129,0.05) 100%);
    border: 1px solid rgba(59,130,246,0.3);
    border-left: 3px solid var(--accent);
    border-radius: 6px;
    padding: 24px 28px;
    position: relative;
    overflow: hidden;
  }

  .phd-cta::before {
    content: '';
    position: absolute; top: 0; right: 0;
    width: 160px; height: 160px;
    background: radial-gradient(circle, rgba(59,130,246,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .phd-cta h3 {
    font-family: var(--head);
    font-size: 18px;
    font-weight: 700;
    color: var(--accent2);
    margin-bottom: 8px;
  }

  .phd-cta p {
    color: var(--text2);
    font-size: 14px;
    line-height: 1.6;
    margin-bottom: 16px;
  }

  .phd-cta p strong { color: var(--text); }

  .phd-interests {
    display: flex; flex-wrap: wrap; gap: 6px;
    margin-top: 12px;
  }

  .interest-tag {
    font-family: var(--mono);
    font-size: 10px;
    padding: 3px 10px;
    border-radius: 3px;
    background: rgba(59,130,246,0.1);
    border: 1px solid rgba(59,130,246,0.25);
    color: var(--accent3);
    letter-spacing: 0.04em;
  }

  /* ════════════════════════ ABOUT CARDS ════════════════════ */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  @media (max-width: 600px) { .about-grid { grid-template-columns: 1fr; } }

  .about-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 16px 20px;
    display: flex; align-items: flex-start; gap: 12px;
    transition: border-color 0.2s;
  }
  .about-card:hover { border-color: rgba(59,130,246,0.4); }

  .about-icon { font-size: 18px; flex-shrink: 0; margin-top: 2px; }

  .about-card strong {
    display: block;
    font-family: var(--head);
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 2px;
  }
  .about-card span { font-size: 12.5px; color: var(--text2); line-height: 1.5; }

  /* ════════════════════════ RESEARCH ════════════════════════ */
  .research-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 16px;
  }

  .research-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 24px 28px;
    position: relative;
    transition: all 0.25s;
    overflow: hidden;
  }

  .research-card.primary {
    border-left: 3px solid var(--accent);
    background: linear-gradient(135deg, rgba(59,130,246,0.06) 0%, var(--surface) 60%);
  }

  .research-card.secondary { border-left: 3px solid rgba(59,130,246,0.35); }

  .research-card:hover { border-color: rgba(59,130,246,0.5); transform: translateX(3px); }

  .research-card .rc-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 8px;
    display: flex; align-items: center; gap: 8px;
  }

  .rc-label .status-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--green);
    box-shadow: 0 0 6px var(--green);
    animation: pulse-dot 2s infinite;
  }

  @keyframes pulse-dot {
    0%,100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  .research-card h3 {
    font-family: var(--head);
    font-size: 17px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 10px;
  }

  .research-card p {
    font-size: 13.5px;
    color: var(--text2);
    line-height: 1.65;
    margin-bottom: 14px;
  }

  .tag-row { display: flex; flex-wrap: wrap; gap: 6px; }

  .tag {
    font-family: var(--mono);
    font-size: 10px;
    padding: 3px 8px;
    border-radius: 3px;
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    color: var(--text3);
    letter-spacing: 0.03em;
  }

  /* ════════════════════════ PUBLICATIONS ════════════════════ */
  .pub-list { display: flex; flex-direction: column; gap: 14px; }

  .pub-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 20px 24px;
    display: grid;
    grid-template-columns: 72px 1fr auto;
    gap: 0 20px;
    align-items: start;
    transition: border-color 0.2s;
  }

  .pub-card:hover { border-color: rgba(59,130,246,0.4); }

  .pub-card.award {
    border-left: 3px solid var(--gold);
    background: linear-gradient(135deg, rgba(245,158,11,0.05) 0%, var(--surface) 50%);
  }

  .pub-year {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text3);
    padding-top: 2px;
  }

  .pub-venue {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.1em;
    color: var(--accent);
    margin-bottom: 5px;
    text-transform: uppercase;
  }

  .pub-title {
    font-size: 14px;
    font-weight: 500;
    color: var(--text);
    line-height: 1.5;
    margin-bottom: 6px;
  }

  .pub-award-badge {
    display: inline-flex; align-items: center; gap: 5px;
    font-family: var(--mono);
    font-size: 10px;
    color: var(--gold2);
    background: rgba(245,158,11,0.1);
    border: 1px solid rgba(245,158,11,0.3);
    border-radius: 3px;
    padding: 2px 8px;
  }

  .pub-links { display: flex; gap: 6px; flex-wrap: wrap; padding-top: 2px; }

  .pub-link {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent2);
    text-decoration: none;
    border: 1px solid rgba(59,130,246,0.3);
    padding: 2px 8px;
    border-radius: 3px;
    transition: all 0.15s;
  }
  .pub-link:hover { background: rgba(59,130,246,0.12); }

  .pub-incoming {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--text3);
    font-style: italic;
  }

  @media (max-width: 580px) {
    .pub-card { grid-template-columns: 1fr; }
    .pub-year { display: none; }
  }

  /* ════════════════════════ NEWS TABLE ════════════════════= */
  .news-list { display: flex; flex-direction: column; gap: 10px; }

  .news-item {
    display: flex; align-items: baseline; gap: 16px;
    padding: 12px 16px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 5px;
    font-size: 13.5px;
    transition: border-color 0.2s;
  }
  .news-item:hover { border-color: rgba(59,130,246,0.35); }

  .news-date {
    font-family: var(--mono);
    font-size: 10.5px;
    color: var(--accent);
    white-space: nowrap;
    flex-shrink: 0;
  }

  .news-text { color: var(--text2); line-height: 1.5; }
  .news-text strong { color: var(--text); }
  .news-text a { color: var(--accent2); text-decoration: none; }
  .news-text a:hover { text-decoration: underline; }

  /* ════════════════════════ TECH STACK ════════════════════= */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .stack-group {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 16px;
  }

  .stack-group-title {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 10px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }

  .stack-items { display: flex; flex-wrap: wrap; gap: 5px; }

  .stack-item {
    font-family: var(--mono);
    font-size: 11px;
    padding: 3px 8px;
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 3px;
    color: var(--text2);
    transition: all 0.15s;
  }
  .stack-item:hover { border-color: var(--accent); color: var(--accent2); }

  /* ════════════════════════ AWARDS ══════════════════════════ */
  .awards-list { display: flex; flex-direction: column; gap: 10px; }

  .award-item {
    display: flex; align-items: center; gap: 16px;
    padding: 14px 20px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 5px;
    transition: border-color 0.2s;
  }
  .award-item:hover { border-color: rgba(245,158,11,0.35); }

  .award-year {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--gold);
    flex-shrink: 0;
    width: 40px;
  }

  .award-icon { font-size: 16px; flex-shrink: 0; }

  .award-text { font-size: 13.5px; color: var(--text2); }
  .award-text strong { color: var(--text); }
  .award-text a { color: var(--accent2); text-decoration: none; font-size: 11px; margin-left: 8px; font-family: var(--mono); }

  /* ════════════════════════ SERVICE ════════════════════════ */
  .service-list { display: flex; flex-direction: column; gap: 8px; }

  .service-item {
    display: flex; align-items: center; gap: 14px;
    padding: 10px 16px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 5px;
    font-size: 13px;
    transition: border-color 0.2s;
  }
  .service-item:hover { border-color: rgba(59,130,246,0.3); }

  .service-role {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.06em;
    color: var(--accent);
    flex-shrink: 0;
    width: 120px;
  }

  .service-text { color: var(--text2); flex: 1; }
  .service-text a { color: var(--accent2); text-decoration: none; }

  .service-year {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--text3);
    flex-shrink: 0;
  }

  /* ════════════════════════ FEATURED PROJECT ════════════════ */
  .project-card {
    background: linear-gradient(135deg, rgba(59,130,246,0.08) 0%, rgba(16,185,129,0.04) 100%);
    border: 1px solid rgba(59,130,246,0.3);
    border-radius: 8px;
    padding: 28px;
    position: relative;
    overflow: hidden;
  }

  .project-card::after {
    content: 'ARoBotX';
    position: absolute;
    right: -20px; top: 50%;
    transform: translateY(-50%) rotate(90deg);
    font-family: var(--head);
    font-size: 80px;
    font-weight: 800;
    color: rgba(59,130,246,0.04);
    letter-spacing: -0.05em;
    pointer-events: none;
    white-space: nowrap;
  }

  .project-card h3 {
    font-family: var(--head);
    font-size: 20px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 6px;
  }

  .project-subtitle {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    margin-bottom: 14px;
    letter-spacing: 0.05em;
  }

  .project-card p {
    font-size: 14px;
    color: var(--text2);
    line-height: 1.65;
    margin-bottom: 16px;
    max-width: 600px;
  }

  /* ════════════════════════ FOOTER ════════════════════════= */
  footer {
    position: relative;
    margin-top: 80px;
    padding: 32px 0 24px;
    border-top: 1px solid var(--border);
    text-align: center;
  }

  footer::before {
    content: '';
    position: absolute; top: -1px; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), var(--green), transparent);
    opacity: 0.6;
  }

  .footer-name {
    font-family: var(--head);
    font-size: 14px;
    font-weight: 700;
    color: var(--accent2);
    margin-bottom: 4px;
  }

  .footer-sub {
    font-family: var(--mono);
    font-size: 10.5px;
    color: var(--text3);
    letter-spacing: 0.1em;
  }

  /* ════════════════════════ DIVIDER ════════════════════════ */
  hr {
    border: none;
    border-top: 1px solid var(--border);
    margin: 40px 0;
  }

  /* ════════════════════════ SCROLL REVEAL ════════════════= */
  .reveal {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.55s ease, transform 0.55s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }
</style>
</head>
<body>
<div class="wrap">

  <!-- ══════ HEADER ══════ -->
  <header>
    <div class="hero-label">// Robotics Researcher · University of Moratuwa · Sri Lanka</div>
    <h1 class="hero-name">A.G. Tharindu Gimras</h1>

    <div class="hero-role">
      Graduate Research Assistant · <span class="highlight">Intelligent Service Robotics Group</span>
    </div>

    <div class="typewriter">
      <div class="tw-inner">
        <span>🦽 RL &amp; Sim-to-Real Control for Wheelchair Robots</span>
        <span>🤖 Shape-Aware Path Planning for Reconfigurable Robots</span>
        <span>👁️ AR &amp; Computer Vision for Robot Navigation</span>
        <span>🏆 Best Poster Award — ICIPRoB 2026</span>
        <span>📬 Actively Seeking PhD Opportunities in Robotics</span>
        <span>🦽 RL &amp; Sim-to-Real Control for Wheelchair Robots</span>
      </div>
    </div>

    <div class="hero-badges">
      <a class="badge badge-gold">🏆 Best Poster — ICIPRoB 2026</a>
      <a href="https://www.tharindugimras.com" class="badge badge-primary" target="_blank">🌐 tharindugimras.com</a>
      <a href="https://drive.google.com/file/d/1c4J0YuP5st_uKGyRfIt3Jvk9joCyiEA_/view" class="badge badge-green" target="_blank">📄 Download CV</a>
      <a href="mailto:tharindugimras@gmail.com" class="badge badge-ghost">✉ tharindugimras@gmail.com</a>
    </div>

    <div class="social-strip">
      <a class="soc-btn" href="https://www.linkedin.com/in/tharindu-gimras/" target="_blank">LinkedIn</a>
      <a class="soc-btn" href="https://scholar.google.com/citations?user=vfX9WjcAAAAJ&hl=en" target="_blank">Google Scholar</a>
      <a class="soc-btn" href="https://orcid.org/0009-0003-5943-0849" target="_blank">ORCID</a>
      <a class="soc-btn" href="https://www.researchgate.net/profile/Tharindu-Gimras-2" target="_blank">ResearchGate</a>
      <a class="soc-btn" href="https://www.semanticscholar.org/author/A.G.-Tharindu-Gimras/2323625598" target="_blank">Semantic Scholar</a>
      <a class="soc-btn" href="https://www.youtube.com/@tharindugimras" target="_blank">YouTube</a>
    </div>
  </header>

  <!-- ══════ PHD PITCH ══════ -->
  <section class="reveal">
    <div class="section-tag">// opportunity</div>
    <h2>📬 Seeking PhD Position</h2>
    <div class="phd-cta">
      <h3>Open to PhD Opportunities in Robotics &amp; Related Fields</h3>
      <p>
        I'm a robotics researcher with <strong>3 peer-reviewed publications</strong> (IEEE + ICIPRoB 2026 Best Poster) and hands-on experience spanning <strong>reinforcement learning, sim-to-real transfer, dynamics modelling, and computer vision</strong>. Currently completing an M.Sc. (Research) at the University of Moratuwa on electric wheelchair control via RL with residual networks.
      </p>
      <p>
        If you work on mobile robotics, control systems, RL, HRI, or related areas — <strong>I'd love to connect.</strong>
      </p>
      <div class="phd-interests">
        <span class="interest-tag">Mobile Robotics</span>
        <span class="interest-tag">Reinforcement Learning</span>
        <span class="interest-tag">Sim-to-Real Transfer</span>
        <span class="interest-tag">Motion Control</span>
        <span class="interest-tag">Dynamic Modelling</span>
        <span class="interest-tag">Computer Vision</span>
        <span class="interest-tag">Reconfigurable Robots</span>
        <span class="interest-tag">Visual SLAM</span>
        <span class="interest-tag">Human-Robot Interaction</span>
        <span class="interest-tag">Augmented Reality</span>
      </div>
    </div>
  </section>

  <!-- ══════ ABOUT ══════ -->
  <section class="reveal">
    <div class="section-tag">// background</div>
    <h2>👨‍🔬 About Me</h2>
    <div class="about-grid">
      <div class="about-card">
        <div class="about-icon">🎓</div>
        <div>
          <strong>M.Sc. (Research) · 2024–present</strong>
          <span>University of Moratuwa, Sri Lanka · Focus: RL-based electric wheelchair control with sim-to-real transfer</span>
        </div>
      </div>
      <div class="about-card">
        <div class="about-icon">⚡</div>
        <div>
          <strong>B.Sc. (Hons.) Electrical Engineering</strong>
          <span>GPA 3.56 · Dean's List · 2nd Sem SGPA 3.97 · University of Moratuwa</span>
        </div>
      </div>
      <div class="about-card">
        <div class="about-icon">📄</div>
        <div>
          <strong>3 Peer-Reviewed Publications</strong>
          <span>1 IEEE (MERCon 2024) · 2 ICIPRoB 2026 (1 poster — Best Award · 1 oral)</span>
        </div>
      </div>
      <div class="about-card">
        <div class="about-icon">🌏</div>
        <div>
          <strong>Experience &amp; Collaboration</strong>
          <span>Co-founded Crytec Labs · Interned at GoTradie, Sydney 🇦🇺 · Languages: Sinhala · English · Finnish (A2)</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ══════ LATEST NEWS ══════ -->
  <section class="reveal">
    <div class="section-tag">// updates</div>
    <h2>📰 Latest News</h2>
    <div class="news-list">
      <div class="news-item">
        <span class="news-date">2026.03</span>
        <span class="news-text">🌐 Launched personal research website — <a href="https://www.tharindugimras.com" target="_blank">tharindugimras.com</a></span>
      </div>
      <div class="news-item">
        <span class="news-date">2026.03</span>
        <span class="news-text">🏆 <strong>Best Poster Award</strong> at <a href="https://www.iciprob.com/2026/" target="_blank">ICIPRoB 2026</a> — Mount Lavinia, Sri Lanka</span>
      </div>
      <div class="news-item">
        <span class="news-date">2026.03</span>
        <span class="news-text">📄 Presented 2 papers at ICIPRoB 2026 (1 poster · 1 oral)</span>
      </div>
      <div class="news-item">
        <span class="news-date">2026.03</span>
        <span class="news-text">🔬 Started as <strong>Graduate Research Assistant</strong> at University of Moratuwa</span>
      </div>
      <div class="news-item">
        <span class="news-date">2025.08</span>
        <span class="news-text">✏️ Editorial Team Member — <a href="https://mercon.uom.lk/" target="_blank">MERCon 2025</a></span>
      </div>
    </div>
  </section>

  <!-- ══════ RESEARCH ══════ -->
  <section class="reveal">
    <div class="section-tag">// work</div>
    <h2>🔬 Research Focus</h2>
    <div class="research-grid">

      <div class="research-card primary">
        <div class="rc-label">
          <span class="status-dot"></span>
          Active · M.Sc. Thesis
        </div>
        <h3>🦽 RL-Based Control for Electric Wheelchair Robots</h3>
        <p>Prototype design, caster wheel dynamics characterisation, and <strong>residual RL networks for sim-to-real trajectory correction</strong> in electric wheelchairs with non-configurable caster wheels. Targeting ICRA 2027.</p>
        <div class="tag-row">
          <span class="tag">Dynamics Modelling</span>
          <span class="tag">Reinforcement Learning</span>
          <span class="tag">Sim-to-Real</span>
          <span class="tag">Residual Networks</span>
          <span class="tag">Prototype Design</span>
        </div>
      </div>

      <div class="research-card secondary">
        <div class="rc-label">ICIPRoB 2026 · Oral</div>
        <h3>🤖 Shape-Aware Path Planning for Reconfigurable Robots</h3>
        <p>Configuration-aware navigation algorithms for the <strong>Smorphi</strong> modular reconfigurable robot, enabling reliable traversal in constrained environments via shape-aware planning.</p>
        <div class="tag-row">
          <span class="tag">Path Planning</span>
          <span class="tag">Reconfigurable Systems</span>
          <span class="tag">Mobile Robotics</span>
          <span class="tag">Computer Vision</span>
        </div>
      </div>

      <div class="research-card secondary">
        <div class="rc-label">IEEE MERCon 2024 · Published</div>
        <h3>👁️ AR &amp; Computer Vision for Robot Navigation</h3>
        <p>Immersive indoor navigation interface using depth estimation (1 cm accuracy, Kinect V2), semantic segmentation (YOLO/OWL-ViT), and AWS IoT for real-time 3D environment mapping.</p>
        <div class="tag-row">
          <span class="tag">Augmented Reality</span>
          <span class="tag">Depth Estimation</span>
          <span class="tag">Semantic Segmentation</span>
          <span class="tag">Cloud Integration</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ══════ PUBLICATIONS ══════ -->
  <section class="reveal">
    <div class="section-tag">// papers</div>
    <h2>📄 Publications</h2>
    <div class="pub-list">

      <div class="pub-card">
        <div class="pub-year">2027</div>
        <div>
          <div class="pub-venue">ICRA 2027</div>
          <div class="pub-title"><em>Advanced wheelchair robotics — RL, Sim-to-Real, Residual Networks</em></div>
          <span class="pub-incoming">🔄 In Progress</span>
        </div>
        <div></div>
      </div>

      <div class="pub-card award">
        <div class="pub-year">2026</div>
        <div>
          <div class="pub-venue">ICIPRoB 2026</div>
          <div class="pub-title">Electric Wheelchair Prototype Design &amp; Caster Wheel Dynamics Characterisation</div>
          <span class="pub-award-badge">🏆 Best Poster Award</span>
        </div>
        <div class="pub-links">
          <a class="pub-link" href="https://drive.google.com/file/d/1MNUnNI0qrooD-5Yxu8IaSPynHlgxne78/view?usp=drive_link" target="_blank">Award</a>
          <a class="pub-link" href="https://drive.google.com/file/d/165LQfVlMsEYrDxOr8EZ45ILE2LB02eoO/view?usp=drive_link" target="_blank">Cert</a>
        </div>
      </div>

      <div class="pub-card">
        <div class="pub-year">2026</div>
        <div>
          <div class="pub-venue">ICIPRoB 2026</div>
          <div class="pub-title">Shape-Aware Path Planning for Smorphi Reconfigurable Modular Robot</div>
          <span class="pub-incoming">✅ Accepted · Oral</span>
        </div>
        <div class="pub-links">
          <a class="pub-link" href="https://drive.google.com/file/d/1SRy9FTK8nTesgXSpPIMCtHenIXKq95Ds/view?usp=drive_link" target="_blank">Cert</a>
        </div>
      </div>

      <div class="pub-card">
        <div class="pub-year">2024</div>
        <div>
          <div class="pub-venue">IEEE · MERCon 2024</div>
          <div class="pub-title">Enabling Immersive Indoor Navigation and Control Through Augmented Reality With Computer Vision</div>
          <span class="pub-incoming">✅ IEEE Published</span>
        </div>
        <div class="pub-links">
          <a class="pub-link" href="https://ieeexplore.ieee.org/document/10688929/" target="_blank">📑 IEEE</a>
        </div>
      </div>

    </div>

    <p style="margin-top:14px; font-size:12px; color:var(--text3); font-family:var(--mono);">
      📚 &nbsp;
      <a href="https://scholar.google.com/citations?user=vfX9WjcAAAAJ&hl=en" target="_blank" style="color:var(--accent2); text-decoration:none;">Google Scholar</a> ·
      <a href="https://orcid.org/0009-0003-5943-0849" target="_blank" style="color:var(--accent2); text-decoration:none;">ORCID</a> ·
      <a href="https://www.researchgate.net/profile/Tharindu-Gimras-2" target="_blank" style="color:var(--accent2); text-decoration:none;">ResearchGate</a> ·
      <a href="https://www.semanticscholar.org/author/A.G.-Tharindu-Gimras/2323625598" target="_blank" style="color:var(--accent2); text-decoration:none;">Semantic Scholar</a>
    </p>
  </section>

  <!-- ══════ FEATURED PROJECT ══════ -->
  <section class="reveal">
    <div class="section-tag">// highlight</div>
    <h2>🚀 Featured Project</h2>
    <div class="project-card">
      <h3>ARoBotX</h3>
      <div class="project-subtitle">AR Indoor Navigation &amp; Robot Control · Final Year Research Project · Jun 2023 – Jun 2024</div>
      <p>Immersive interface for remote robot operators using <strong>Augmented Reality</strong>, computer vision, and <strong>AWS IoT</strong>. Features real-time 3D environment mapping, 3D hand gesture-based control, and global low-latency operation (depth accuracy: 1 cm via Kinect V2).</p>
      <div class="tag-row" style="margin-bottom:16px;">
        <span class="tag">Unity (C#)</span>
        <span class="tag">Vuforia</span>
        <span class="tag">AWS IoT</span>
        <span class="tag">Kinect V2</span>
        <span class="tag">YOLO v8</span>
        <span class="tag">OWL-ViT</span>
        <span class="tag">OpenCV</span>
        <span class="tag">Python</span>
        <span class="tag">C++</span>
        <span class="tag">MQTT</span>
      </div>
      <div style="display:flex; gap:10px; flex-wrap:wrap;">
        <a href="https://github.com/orgs/ARoBotX/repositories" target="_blank" class="badge badge-ghost">⌥ GitHub Repo</a>
        <a href="https://ieeexplore.ieee.org/document/10688929/" target="_blank" class="badge badge-primary">📑 IEEE Paper</a>
      </div>
    </div>
  </section>

  <!-- ══════ TECH STACK ══════ -->
  <section class="reveal">
    <div class="section-tag">// tools</div>
    <h2>🛠️ Tech Stack</h2>
    <div class="stack-grid">
      <div class="stack-group">
        <div class="stack-group-title">Robotics &amp; Simulation</div>
        <div class="stack-items">
          <span class="stack-item">ROS</span>
          <span class="stack-item">Gazebo</span>
          <span class="stack-item">MuJoCo</span>
          <span class="stack-item">Webots</span>
          <span class="stack-item">MATLAB</span>
          <span class="stack-item">Simulink</span>
          <span class="stack-item">SOLIDWORKS</span>
        </div>
      </div>
      <div class="stack-group">
        <div class="stack-group-title">AI &amp; Vision</div>
        <div class="stack-items">
          <span class="stack-item">Python</span>
          <span class="stack-item">PyTorch</span>
          <span class="stack-item">TensorFlow</span>
          <span class="stack-item">OpenCV</span>
          <span class="stack-item">YOLO</span>
          <span class="stack-item">OWL-ViT</span>
          <span class="stack-item">Unity</span>
        </div>
      </div>
      <div class="stack-group">
        <div class="stack-group-title">Software &amp; Cloud</div>
        <div class="stack-items">
          <span class="stack-item">C++</span>
          <span class="stack-item">TypeScript</span>
          <span class="stack-item">Next.js</span>
          <span class="stack-item">AWS IoT</span>
          <span class="stack-item">Docker</span>
          <span class="stack-item">MongoDB</span>
          <span class="stack-item">MQTT</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ══════ AWARDS ══════ -->
  <section class="reveal">
    <div class="section-tag">// recognition</div>
    <h2>🏅 Awards &amp; Honours</h2>
    <div class="awards-list">
      <div class="award-item">
        <span class="award-year">2026</span>
        <span class="award-icon">🏆</span>
        <span class="award-text"><strong>Best Poster Award</strong> — ICIPRoB 2026, Mount Lavinia, Sri Lanka
          <a href="https://drive.google.com/file/d/1MNUnNI0qrooD-5Yxu8IaSPynHlgxne78/view?usp=drive_link" target="_blank">Certificate ↗</a>
        </span>
      </div>
      <div class="award-item">
        <span class="award-year">2024</span>
        <span class="award-icon">🎓</span>
        <span class="award-text"><strong>Dean's List</strong> — University of Moratuwa · 2nd Semester SGPA 3.97</span>
      </div>
      <div class="award-item">
        <span class="award-year">2022</span>
        <span class="award-icon">🥈</span>
        <span class="award-text"><strong>First Runner-Up</strong> — IEEE Y2NPRO Phasor Measurement Units Competition
          <a href="https://drive.google.com/file/d/1GhthYNUy29MgS7D-1zlHVeWlE8rsuuGp/view?usp=drive_link" target="_blank">Certificate ↗</a>
        </span>
      </div>
    </div>
  </section>

  <!-- ══════ ACADEMIC SERVICE ══════ -->
  <section class="reveal">
    <div class="section-tag">// community</div>
    <h2>🎓 Academic Service</h2>
    <div class="service-list">
      <div class="service-item">
        <span class="service-role">Reviewer</span>
        <span class="service-text"><a href="https://icarc.lk/assets/resources/ICARC2025_Program_Book.pdf" target="_blank">ICARC 2025</a></span>
        <span class="service-year">2025</span>
      </div>
      <div class="service-item">
        <span class="service-role">Editorial Team</span>
        <span class="service-text"><a href="https://mercon.uom.lk/" target="_blank">MERCon 2025</a></span>
        <span class="service-year">2025</span>
      </div>
      <div class="service-item">
        <span class="service-role">Teaching Asst.</span>
        <span class="service-text">Introduction to Gazebo · University of Moratuwa</span>
        <span class="service-year">2023</span>
      </div>
      <div class="service-item">
        <span class="service-role">Teaching Asst.</span>
        <span class="service-text">Research Paper Writing with Overleaf · University of Moratuwa</span>
        <span class="service-year">2023</span>
      </div>
      <div class="service-item">
        <span class="service-role">Instructor</span>
        <span class="service-text">React.js &amp; CSS · MIHA Institute</span>
        <span class="service-year">2023</span>
      </div>
    </div>
  </section>

  <!-- ══════ FOOTER ══════ -->
  <footer class="reveal">
    <div class="footer-name">A.G. Tharindu Gimras</div>
    <div class="footer-sub">ROBOTICS RESEARCHER · UNIVERSITY OF MORATUWA · SRI LANKA · 🇱🇰</div>
    <div style="margin-top:16px;">
      <a href="mailto:tharindugimras@gmail.com" class="badge badge-primary" style="margin:0 auto;">✉ tharindugimras@gmail.com</a>
    </div>
  </footer>

</div>

<script>
  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); } });
  }, { threshold: 0.08 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
