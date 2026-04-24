<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Gayathri Sathish</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Syne:wght@400;500;600;700;800&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0d0d0d;
    --bg2: #141414;
    --bg3: #1a1a1a;
    --border: rgba(255,255,255,0.07);
    --border2: rgba(255,255,255,0.12);
    --text: #f0f0ee;
    --muted: #888884;
    --faint: #3a3a38;
    --accent: #00B4D8;
    --accent2: #7B5EA7;
    --green: #22c55e;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    line-height: 1.6;
  }

  /* ── LAYOUT ── */
  .page {
    max-width: 820px;
    margin: 0 auto;
    padding: 4rem 2rem 6rem;
  }

  /* ── HERO ── */
  .hero {
    margin-bottom: 5rem;
    position: relative;
  }

  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .hero-eyebrow::before {
    content: '';
    display: inline-block;
    width: 24px;
    height: 1px;
    background: var(--muted);
  }

  .hero-name {
    font-size: clamp(52px, 10vw, 88px);
    font-weight: 800;
    line-height: 0.95;
    letter-spacing: -0.03em;
    margin-bottom: 1.5rem;
  }

  .hero-name .dim {
    color: var(--faint);
  }

  .hero-tagline {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    color: var(--muted);
    max-width: 420px;
    line-height: 1.8;
    margin-bottom: 2.5rem;
    border-left: 1px solid var(--faint);
    padding-left: 1rem;
  }

  .hero-links {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .pill-link {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.08em;
    padding: 7px 16px;
    border-radius: 100px;
    border: 1px solid var(--border2);
    color: var(--muted);
    text-decoration: none;
    transition: all 0.2s ease;
    background: var(--bg2);
  }

  .pill-link:hover {
    color: var(--text);
    border-color: rgba(255,255,255,0.25);
    background: var(--bg3);
  }

  /* ── ABOUT CODE BLOCK ── */
  .code-block {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.5rem 2rem;
    margin-bottom: 5rem;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    line-height: 2;
    color: var(--muted);
    overflow-x: auto;
  }

  .code-block .k { color: var(--accent2); }
  .code-block .s { color: #98c379; }
  .code-block .v { color: var(--accent); }
  .code-block .p { color: var(--faint); }
  .code-block .n { color: var(--text); }

  /* ── SECTION ── */
  .section { margin-bottom: 4.5rem; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 1.75rem;
  }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── STACK GRID ── */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  .stack-cell {
    background: var(--bg2);
    padding: 1.5rem;
  }

  .stack-cell:first-child { border-radius: 11px 0 0 0; }
  .stack-cell:nth-child(2) { border-radius: 0 11px 0 0; }
  .stack-cell:nth-child(3) { border-radius: 0 0 0 11px; }
  .stack-cell:last-child { border-radius: 0 0 11px 0; }

  .stack-title {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 1rem;
  }

  .tag-wrap { display: flex; flex-wrap: wrap; gap: 6px; }

  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    padding: 3px 10px;
    border-radius: 4px;
    background: var(--bg3);
    color: var(--muted);
    border: 1px solid var(--border);
    letter-spacing: 0.02em;
  }

  /* ── PROJECTS ── */
  .project-list { display: flex; flex-direction: column; gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; }

  .project {
    background: var(--bg2);
    padding: 1.75rem 2rem;
    transition: background 0.2s ease;
  }

  .project:hover { background: var(--bg3); }

  .project-top {
    display: flex;
    align-items: baseline;
    gap: 12px;
    margin-bottom: 0.6rem;
    flex-wrap: wrap;
  }

  .project-name {
    font-size: 15px;
    font-weight: 700;
    letter-spacing: -0.01em;
  }

  .project-cat {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
  }

  .project-desc {
    font-size: 12.5px;
    color: var(--muted);
    line-height: 1.8;
    margin-bottom: 1rem;
    max-width: 600px;
  }

  .chip-row { display: flex; flex-wrap: wrap; gap: 5px; }

  .chip {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 3px;
    background: var(--bg);
    color: var(--faint);
    border: 1px solid var(--border);
    letter-spacing: 0.03em;
  }

  /* ── IDEAS ── */
  .ideas-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  .idea {
    background: var(--bg2);
    padding: 1.75rem;
  }

  .idea:first-child { border-radius: 11px 0 0 11px; }
  .idea:last-child { border-radius: 0 11px 11px 0; }

  .idea-icon {
    font-size: 20px;
    margin-bottom: 0.75rem;
    display: block;
  }

  .idea-title {
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 0.6rem;
    letter-spacing: -0.01em;
  }

  .idea-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.8;
  }

  /* ── FOOTER ── */
  .footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 2.5rem;
    border-top: 1px solid var(--border);
    flex-wrap: wrap;
    gap: 1rem;
  }

  .footer-left {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.06em;
  }

  .footer-right {
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--green);
    animation: blink 2.2s ease-in-out infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.25; }
  }

  .open-badge {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.06em;
  }

  /* ── FADE IN ── */
  .fade-up {
    opacity: 0;
    transform: translateY(18px);
    animation: fadeUp 0.6s ease forwards;
  }

  .fade-up:nth-child(1) { animation-delay: 0.05s; }
  .fade-up:nth-child(2) { animation-delay: 0.15s; }
  .fade-up:nth-child(3) { animation-delay: 0.25s; }
  .fade-up:nth-child(4) { animation-delay: 0.35s; }
  .fade-up:nth-child(5) { animation-delay: 0.45s; }

  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }

  @media (max-width: 600px) {
    .hero-name { font-size: 48px; }
    .stack-grid, .ideas-grid { grid-template-columns: 1fr; }
    .stack-cell:first-child { border-radius: 11px 11px 0 0; }
    .stack-cell:nth-child(2) { border-radius: 0; }
    .stack-cell:nth-child(3) { border-radius: 0; }
    .stack-cell:last-child { border-radius: 0 0 11px 11px; }
    .idea:first-child { border-radius: 11px 11px 0 0; }
    .idea:last-child { border-radius: 0 0 11px 11px; }
    .page { padding: 2.5rem 1.25rem 4rem; }
  }
</style>
</head>
<body>
<main class="page">

  <!-- HERO -->
  <section class="hero">
    <div class="hero-eyebrow">CS undergrad · SRM IST '28</div>
    <h1 class="hero-name">
      Gayathri<br>
      <span class="dim">Sathish</span>
    </h1>
    <p class="hero-tagline">
      Building systems that deal with<br>
      risk, data, and uncertainty.
    </p>
    <div class="hero-links">
      <a class="pill-link" href="https://linkedin.com/in/gayathrisathish" target="_blank">↗ LinkedIn</a>
      <a class="pill-link" href="mailto:gayathrisathish06@gmail.com">✉ Email</a>
    </div>
  </section>

  <!-- ABOUT CODE BLOCK -->
  <section class="section fade-up">
    <div class="section-header">
      <span class="section-label">About</span>
      <div class="section-line"></div>
    </div>
    <div class="code-block">
<span class="n">gayathri</span> <span class="p">=</span> <span class="p">{</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"role"</span><span class="p">:</span> <span class="s">"CS undergrad @ SRM IST ('28)"</span><span class="p">,</span><br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"builds"</span><span class="p">:</span> <span class="p">[</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"systems that deal with risk, data, and uncertainty"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="p">],</span><br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"current_state"</span><span class="p">:</span> <span class="p">{</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"building"</span><span class="p">:</span> <span class="p">[</span><span class="s">"RiskLens"</span><span class="p">,</span> <span class="s">"multimodal verifier"</span><span class="p">],</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"exploring"</span><span class="p">:</span> <span class="p">[</span><span class="s">"volatility forecasting"</span><span class="p">,</span> <span class="s">"multimodal robustness"</span><span class="p">]</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="p">},</span><br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"stack"</span><span class="p">:</span> <span class="p">[</span><span class="s">"Python"</span><span class="p">,</span> <span class="s">"C++"</span><span class="p">,</span> <span class="s">"SQL"</span><span class="p">,</span> <span class="s">"PyTorch"</span><span class="p">,</span> <span class="s">"FastAPI"</span><span class="p">]</span><br>
<span class="p">}</span>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="section fade-up">
    <div class="section-header">
      <span class="section-label">Tech Stack</span>
      <div class="section-line"></div>
    </div>
    <div class="stack-grid">
      <div class="stack-cell">
        <div class="stack-title">Backend & Data</div>
        <div class="tag-wrap">
          <span class="tag">FastAPI</span>
          <span class="tag">PostgreSQL</span>
          <span class="tag">SQLite</span>
          <span class="tag">Redis</span>
          <span class="tag">pandas</span>
          <span class="tag">NumPy</span>
          <span class="tag">GeoPandas</span>
          <span class="tag">Docker</span>
          <span class="tag">Git</span>
          <span class="tag">pytest</span>
        </div>
      </div>
      <div class="stack-cell">
        <div class="stack-title">ML / AI</div>
        <div class="tag-wrap">
          <span class="tag">PyTorch</span>
          <span class="tag">Hugging Face</span>
          <span class="tag">scikit-learn</span>
          <span class="tag">GARCH</span>
          <span class="tag">FinBERT</span>
          <span class="tag">Isolation Forest</span>
          <span class="tag">Monte Carlo</span>
          <span class="tag">Time Series</span>
          <span class="tag">Geospatial Analysis</span>
        </div>
      </div>
      <div class="stack-cell">
        <div class="stack-title">Frontend</div>
        <div class="tag-wrap">
          <span class="tag">React</span>
          <span class="tag">Streamlit</span>
          <span class="tag">Leaflet</span>
          <span class="tag">HTML/CSS</span>
        </div>
      </div>
      <div class="stack-cell">
        <div class="stack-title">Quant Finance</div>
        <div class="tag-wrap">
          <span class="tag">VaR</span>
          <span class="tag">Sharpe Ratio</span>
          <span class="tag">Beta</span>
          <span class="tag">MPT</span>
          <span class="tag">Maximum Drawdown</span>
          <span class="tag">Jensen's Alpha</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="section fade-up">
    <div class="section-header">
      <span class="section-label">Things I'm Building (and Breaking)</span>
      <div class="section-line"></div>
    </div>
    <div class="project-list">

      <div class="project">
        <div class="project-top">
          <span class="project-name">🌍 GeoSentinel</span>
          <span class="project-cat">Geospatial Threat Intelligence Dashboard</span>
        </div>
        <p class="project-desc">
          Real ACLED conflict data · Isolation Forest anomaly detection · GAN-synthesized threat data · Groq Llama 3 70B SITREP generation · interactive 3D globe.
        </p>
        <div class="chip-row">
          <span class="chip">FastAPI</span>
          <span class="chip">SQLite</span>
          <span class="chip">GeoPandas</span>
          <span class="chip">Groq</span>
          <span class="chip">Three.js</span>
        </div>
      </div>

      <div class="project">
        <div class="project-top">
          <span class="project-name">📊 RiskLens</span>
          <span class="project-cat">Financial Portfolio Risk Dashboard</span>
        </div>
        <p class="project-desc">
          End-to-end risk analytics for Indian retail investors. Computes VaR, Beta, Sharpe Ratio, Max Drawdown, and Jensen's Alpha — benchmarked against Nifty 50. Dual-signal early-warning alerts via GARCH(1,1) volatility forecasting + FinBERT sentiment analysis. Proprietary RiskLens Score with Monte Carlo VaR and MPT efficient frontier optimization.
        </p>
        <div class="chip-row">
          <span class="chip">FastAPI</span>
          <span class="chip">Streamlit</span>
          <span class="chip">PyTorch</span>
          <span class="chip">FinBERT</span>
          <span class="chip">PostgreSQL</span>
          <span class="chip">Docker</span>
        </div>
      </div>

      <div class="project">
        <div class="project-top">
          <span class="project-name">🔍 Multimodal Synthetic Media Verifier</span>
          <span class="project-cat">AI-Generated Content Detection</span>
        </div>
        <p class="project-desc">
          Forensic dashboard aggregating four detection signals — spatial deepfake detection (EfficientNet-B4 + Grad-CAM), DCT frequency-domain analysis, rPPG physiological liveness, and C2PA content provenance — into a single explainable verdict. Built for cross-generator robustness across Stable Diffusion, Midjourney, and DALL-E.
        </p>
        <div class="chip-row">
          <span class="chip">PyTorch</span>
          <span class="chip">OpenCV</span>
          <span class="chip">MediaPipe</span>
          <span class="chip">FastAPI</span>
          <span class="chip">React</span>
          <span class="chip">Docker</span>
        </div>
      </div>

      <div class="project">
        <div class="project-top">
          <span class="project-name">🗺️ DensityX</span>
          <span class="project-cat">Real-Time Crowd Density Monitor</span>
        </div>
        <p class="project-desc">
          DBSCAN-based clustering on live location streams → centroid + density computation → color-coded alert zones on an interactive geospatial map.
        </p>
        <div class="chip-row">
          <span class="chip">FastAPI</span>
          <span class="chip">React</span>
          <span class="chip">Leaflet</span>
          <span class="chip">DBSCAN</span>
        </div>
      </div>

    </div>
  </section>

  <!-- IDEAS -->
  <section class="section fade-up">
    <div class="section-header">
      <span class="section-label">Ideas I'm Exploring</span>
      <div class="section-line"></div>
    </div>
    <div class="ideas-grid">
      <div class="idea">
        <span class="idea-icon">📈</span>
        <div class="idea-title">GARCH-Informed Neural Networks</div>
        <p class="idea-desc">
          Building a hybrid GARCH-LSTM pipeline for financial time-series volatility — testing whether injecting econometric structure into a neural architecture improves forecast robustness across different market regimes. Rolling-window backtesting, comparative evaluation across ML and econometric baselines. Working toward a paper.
        </p>
      </div>
      <div class="idea">
        <span class="idea-icon">🧠</span>
        <div class="idea-title">Multimodal Synthetic Verifier — Cross-Generator Robustness</div>
        <p class="idea-desc">
          Building a detection system trained on one image generator (Stable Diffusion) and testing whether DCT frequency features help it generalise to unseen generators (Midjourney, DALL-E 3). Framing it as an open empirical question: does frequency-domain supervision make deepfake detectors less brittle?
        </p>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer fade-up">
    <div class="footer-left">Chennai, India &nbsp;·&nbsp; SRM IST '28</div>
    <div class="footer-right">
      <div class="dot"></div>
      <span class="open-badge">open to collaborate</span>
    </div>
  </footer>

</main>
</body>
</html>
