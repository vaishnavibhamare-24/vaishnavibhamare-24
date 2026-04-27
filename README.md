<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Vaishnavi Bhamare — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=Outfit:wght@300;400;500;600;700;800&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #060a12;
    --bg2: #0d1421;
    --bg3: #111928;
    --cyan: #00C9FF;
    --purple: #7B61FF;
    --pink: #FF6B9D;
    --gold: #FFD60A;
    --text: #e0e8ff;
    --muted: #6b7fa3;
    --border: rgba(0,201,255,0.12);
    --glow-cyan: 0 0 20px rgba(0,201,255,0.25);
    --glow-purple: 0 0 20px rgba(123,97,255,0.25);
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', sans-serif;
    font-size: 15px;
    line-height: 1.7;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── Background grid ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,201,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,201,255,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  /* ── Corner glows ── */
  body::after {
    content: '';
    position: fixed;
    top: -200px; left: -200px;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(0,201,255,0.06) 0%, transparent 70%);
    pointer-events: none; z-index: 0;
  }

  .glow-corner-br {
    position: fixed;
    bottom: -200px; right: -200px;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(123,97,255,0.06) 0%, transparent 70%);
    pointer-events: none; z-index: 0;
  }

  .container {
    position: relative; z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 0 24px 80px;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 72px 0 48px;
    position: relative;
  }

  .hero-eyebrow {
    display: inline-flex; align-items: center; gap: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px; letter-spacing: 2px;
    color: var(--cyan);
    border: 1px solid rgba(0,201,255,0.3);
    border-radius: 100px;
    padding: 6px 16px;
    margin-bottom: 28px;
    background: rgba(0,201,255,0.05);
  }
  .hero-eyebrow::before {
    content: '';
    width: 6px; height: 6px; border-radius: 50%;
    background: var(--cyan);
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.4; transform: scale(0.8); }
  }

  .hero h1 {
    font-size: clamp(36px, 6vw, 58px);
    font-weight: 800;
    letter-spacing: -1.5px;
    background: linear-gradient(135deg, #ffffff 0%, var(--cyan) 50%, var(--purple) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 16px;
    line-height: 1.1;
  }

  .hero-sub {
    font-size: 17px;
    color: var(--muted);
    font-weight: 400;
    letter-spacing: 0.5px;
    margin-bottom: 40px;
  }
  .hero-sub strong { color: var(--cyan); font-weight: 600; }

  .badges {
    display: flex; flex-wrap: wrap; gap: 10px;
    justify-content: center;
    margin-bottom: 36px;
  }

  .badge {
    display: inline-flex; align-items: center; gap: 7px;
    padding: 9px 18px;
    border-radius: 100px;
    font-size: 13px; font-weight: 500;
    border: 1px solid;
    text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .badge:hover { transform: translateY(-2px); }
  .badge.cyan { color: var(--cyan); border-color: rgba(0,201,255,0.4); background: rgba(0,201,255,0.07); }
  .badge.cyan:hover { box-shadow: var(--glow-cyan); }
  .badge.purple { color: var(--purple); border-color: rgba(123,97,255,0.4); background: rgba(123,97,255,0.07); }
  .badge.purple:hover { box-shadow: var(--glow-purple); }
  .badge.pink { color: var(--pink); border-color: rgba(255,107,157,0.4); background: rgba(255,107,157,0.07); }
  .badge svg { width: 15px; height: 15px; }

  /* ── ABOUT CARD ── */
  .about-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 32px;
    margin-bottom: 32px;
    position: relative;
    overflow: hidden;
  }
  .about-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, var(--cyan), var(--purple), transparent);
  }
  .about-card pre {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 2;
    color: var(--text);
    white-space: pre-wrap;
  }
  .about-card .key { color: var(--purple); }
  .about-card .val { color: var(--cyan); }
  .about-card .str { color: #7ec8a0; }

  /* ── SECTION HEADERS ── */
  .section { margin-bottom: 48px; }
  .section-title {
    display: flex; align-items: center; gap: 12px;
    font-size: 20px; font-weight: 700;
    letter-spacing: -0.5px;
    margin-bottom: 24px;
    padding-bottom: 14px;
    border-bottom: 1px solid var(--border);
  }
  .section-title .icon {
    font-size: 20px;
    width: 38px; height: 38px;
    display: flex; align-items: center; justify-content: center;
    background: rgba(0,201,255,0.08);
    border: 1px solid rgba(0,201,255,0.2);
    border-radius: 10px;
  }

  /* ── EXPERIENCE ── */
  .timeline { display: flex; flex-direction: column; gap: 16px; }
  .timeline-item {
    display: grid; grid-template-columns: 48px 1fr;
    gap: 0 16px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px;
    transition: border-color 0.2s;
    position: relative;
    overflow: hidden;
  }
  .timeline-item:hover { border-color: rgba(0,201,255,0.35); }
  .timeline-icon {
    font-size: 22px; line-height: 1;
    display: flex; align-items: flex-start; justify-content: center;
    padding-top: 2px;
  }
  .timeline-body {}
  .timeline-header {
    display: flex; align-items: flex-start;
    justify-content: space-between; gap: 12px;
    margin-bottom: 8px;
    flex-wrap: wrap;
  }
  .timeline-title { font-size: 15px; font-weight: 700; color: #fff; }
  .timeline-org { font-size: 13px; color: var(--muted); margin-top: 2px; }
  .timeline-date {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; font-weight: 500;
    color: var(--cyan);
    background: rgba(0,201,255,0.1);
    border: 1px solid rgba(0,201,255,0.2);
    border-radius: 100px;
    padding: 4px 12px;
    white-space: nowrap;
    flex-shrink: 0;
  }
  .timeline-desc {
    font-size: 13px; color: var(--muted); line-height: 1.7;
  }
  .timeline-metrics {
    display: flex; flex-wrap: wrap; gap: 8px; margin-top: 12px;
  }
  .metric {
    font-size: 12px; font-weight: 600;
    padding: 4px 12px; border-radius: 100px;
    background: rgba(0,201,255,0.08);
    color: var(--cyan);
    border: 1px solid rgba(0,201,255,0.2);
  }
  .metric.purple { background: rgba(123,97,255,0.08); color: var(--purple); border-color: rgba(123,97,255,0.2); }
  .metric.green { background: rgba(0,255,136,0.08); color: #00FF88; border-color: rgba(0,255,136,0.2); }

  /* ── SKILLS ── */
  .skills-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 14px;
  }
  .skill-category {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .skill-category:hover { border-color: rgba(0,201,255,0.3); transform: translateY(-2px); }
  .skill-cat-title {
    font-size: 11px; font-weight: 700; letter-spacing: 1.5px;
    color: var(--muted); text-transform: uppercase; margin-bottom: 12px;
  }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .skill-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; font-weight: 500;
    padding: 4px 10px; border-radius: 6px;
  }
  .skill-tag.cyan { background: rgba(0,201,255,0.1); color: var(--cyan); }
  .skill-tag.purple { background: rgba(123,97,255,0.1); color: #a08bff; }
  .skill-tag.green { background: rgba(0,255,136,0.08); color: #00FF88; }
  .skill-tag.amber { background: rgba(255,214,10,0.08); color: var(--gold); }
  .skill-tag.pink { background: rgba(255,107,157,0.1); color: var(--pink); }

  /* ── STATS GRID ── */
  .stats-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 14px; margin-bottom: 32px;
  }
  .stat-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 22px 18px;
    text-align: center;
    transition: border-color 0.2s, transform 0.2s;
  }
  .stat-card:hover { border-color: rgba(0,201,255,0.4); transform: translateY(-3px); }
  .stat-number {
    font-size: 32px; font-weight: 800;
    letter-spacing: -1px; line-height: 1;
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 6px;
  }
  .stat-label { font-size: 12px; color: var(--muted); font-weight: 500; letter-spacing: 0.5px; }

  /* ── ACHIEVEMENT ── */
  .achievement {
    background: linear-gradient(135deg, rgba(255,214,10,0.06), rgba(255,107,157,0.06));
    border: 1px solid rgba(255,214,10,0.2);
    border-radius: 14px;
    padding: 20px 24px;
    display: flex; align-items: center; gap: 16px;
  }
  .achievement-icon { font-size: 32px; flex-shrink: 0; }
  .achievement-text {}
  .achievement-title { font-size: 15px; font-weight: 700; color: var(--gold); }
  .achievement-desc { font-size: 13px; color: var(--muted); margin-top: 4px; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 48px;
    border-top: 1px solid var(--border);
  }
  .footer-quote {
    font-size: 18px; font-weight: 600; font-style: italic;
    color: var(--text); margin-bottom: 24px; line-height: 1.5;
    letter-spacing: -0.3px;
  }
  .footer-quote span { color: var(--cyan); }
  .footer-note {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px; color: var(--muted);
  }

  /* ── DIVIDER ── */
  hr {
    border: none;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 48px 0;
  }

  /* Animate on load */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .hero { animation: fadeUp 0.7s ease both; }
  .section { animation: fadeUp 0.7s ease both; }
  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }
</style>
</head>
<body>

<div class="glow-corner-br"></div>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-eyebrow">OPEN TO FULL-TIME OPPORTUNITIES</div>
    <h1>Vaishnavi Bhamare</h1>
    <p class="hero-sub">
      <strong>Data Analyst</strong> &nbsp;·&nbsp; AI/ML Engineer &nbsp;·&nbsp; BI Developer &nbsp;·&nbsp; Data Engineer
    </p>
    <div class="badges">
      <a href="https://www.linkedin.com/in/vaishnavibhamare/" class="badge cyan" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="https://vaishnavibhamare-24.github.io/vaishnavibhamare.github.io/" class="badge purple" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
        Portfolio
      </a>
      <a href="mailto:vaishnavibhamare24@gmail.com" class="badge pink" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Email
      </a>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="about-card">
      <pre><span class="key">profile</span> = {
  <span class="key">name</span>       : <span class="str">"Vaishnavi Govind Bhamare"</span>,
  <span class="key">education</span>  : <span class="str">"MS Advanced Data Analytics @ UNT"</span>,
  <span class="key">gpa</span>        : <span class="val">4.0</span>,  <span class="key">honor</span>: <span class="str">"Phi Kappa Phi · Top 10% Graduate"</span>,
  <span class="key">experience</span> : <span class="str">"3+ years · Analyst · Engineer · Researcher"</span>,
  <span class="key">location</span>   : <span class="str">"Texas, USA  ·  Open to Relocation"</span>,
  <span class="key">passions</span>   : [<span class="str">"Analytics"</span>, <span class="str">"Gen AI"</span>, <span class="str">"Scalable Systems"</span>],
  <span class="key">status</span>     : <span class="val">✅ Open to Full-Time Roles</span>
}</pre>
    </div>
  </div>

  <!-- IMPACT STATS -->
  <div class="section">
    <div class="section-title">
      <span class="icon">📈</span> Impact by Numbers
    </div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-number">120K+</div>
        <div class="stat-label">Records Analyzed</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">60%</div>
        <div class="stat-label">Faster Processing</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">35%</div>
        <div class="stat-label">Reporting Reduced</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">4.0</div>
        <div class="stat-label">Graduate GPA</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">3+</div>
        <div class="stat-label">Years Experience</div>
      </div>
    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="section">
    <div class="section-title">
      <span class="icon">💼</span> Experience
    </div>
    <div class="timeline">

      <div class="timeline-item">
        <div class="timeline-icon">🔬</div>
        <div class="timeline-body">
          <div class="timeline-header">
            <div>
              <div class="timeline-title">Research Assistant</div>
              <div class="timeline-org">University of North Texas, Texas, USA</div>
            </div>
            <div class="timeline-date">Jan 2025 – Present</div>
          </div>
          <div class="timeline-desc">Analyzed large-scale simulation datasets to evaluate system performance. Built optimized SQL + Python ETL/validation workflows and defined KPIs from business requirements.</div>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-icon">📚</div>
        <div class="timeline-body">
          <div class="timeline-header">
            <div>
              <div class="timeline-title">Teaching Assistant</div>
              <div class="timeline-org">University of North Texas, Texas, USA</div>
            </div>
            <div class="timeline-date">Aug 2024 – Present</div>
          </div>
          <div class="timeline-desc">Mentored graduate students in data analytics tools and concepts. Supported coursework grading and guided real-world problem-solving sessions.</div>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-icon">📊</div>
        <div class="timeline-body">
          <div class="timeline-header">
            <div>
              <div class="timeline-title">Data Analyst</div>
              <div class="timeline-org">Capgemini, India</div>
            </div>
            <div class="timeline-date">Aug 2023 – Jul 2024</div>
          </div>
          <div class="timeline-desc">Delivered measurable outcomes across analytics, BI, and query optimization.</div>
          <div class="timeline-metrics">
            <span class="metric">📈 25% faster decisions</span>
            <span class="metric purple">⚡ 35% less reporting dependency</span>
            <span class="metric green">🔧 30% SQL performance gain</span>
          </div>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-icon">⚡</div>
        <div class="timeline-body">
          <div class="timeline-header">
            <div>
              <div class="timeline-title">Data Analytics Intern</div>
              <div class="timeline-org">Tata Power, India</div>
            </div>
            <div class="timeline-date">Feb 2023 – Jul 2023</div>
          </div>
          <div class="timeline-desc">Built automated Python+SQL pipelines and applied anomaly detection for energy system monitoring.</div>
          <div class="timeline-metrics">
            <span class="metric green">🔄 60% faster processing</span>
          </div>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-icon">🔩</div>
        <div class="timeline-body">
          <div class="timeline-header">
            <div>
              <div class="timeline-title">Data Analytics Engineering Intern</div>
              <div class="timeline-org">CoE Lab, VJTI, India</div>
            </div>
            <div class="timeline-date">May 2022 – Jan 2023</div>
          </div>
          <div class="timeline-desc">Processed 100K+ simulation records for trend analysis. Supported forecasting, model evaluation and improved preprocessing efficiency.</div>
          <div class="timeline-metrics">
            <span class="metric purple">📉 40% preprocessing efficiency</span>
          </div>
        </div>
      </div>

    </div>
  </div>

  <!-- TECH SKILLS -->
  <div class="section">
    <div class="section-title">
      <span class="icon">🛠️</span> Technical Arsenal
    </div>
    <div class="skills-grid">
      <div class="skill-category">
        <div class="skill-cat-title">💻 Languages & Tools</div>
        <div class="skill-tags">
          <span class="skill-tag cyan">Python</span>
          <span class="skill-tag cyan">SQL</span>
          <span class="skill-tag cyan">Pandas</span>
          <span class="skill-tag cyan">NumPy</span>
          <span class="skill-tag cyan">Git</span>
          <span class="skill-tag cyan">Jupyter</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-title">📊 Analytics & BI</div>
        <div class="skill-tags">
          <span class="skill-tag purple">Power BI</span>
          <span class="skill-tag purple">Tableau</span>
          <span class="skill-tag purple">KPI Design</span>
          <span class="skill-tag purple">EDA</span>
          <span class="skill-tag purple">Dashboards</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-title">🤖 AI / ML / Gen AI</div>
        <div class="skill-tags">
          <span class="skill-tag pink">LLMs</span>
          <span class="skill-tag pink">RAG</span>
          <span class="skill-tag pink">Agentic AI</span>
          <span class="skill-tag pink">Vector DBs</span>
          <span class="skill-tag pink">Regression</span>
          <span class="skill-tag pink">Clustering</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-title">⚙️ Data Engineering</div>
        <div class="skill-tags">
          <span class="skill-tag green">ETL Pipelines</span>
          <span class="skill-tag green">Spark</span>
          <span class="skill-tag green">Hadoop</span>
          <span class="skill-tag green">Data Modeling</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-title">☁️ Cloud</div>
        <div class="skill-tags">
          <span class="skill-tag amber">AWS</span>
          <span class="skill-tag amber">GCP</span>
          <span class="skill-tag amber">BigQuery</span>
          <span class="skill-tag amber">S3 / EC2</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-title">📐 Methods</div>
        <div class="skill-tags">
          <span class="skill-tag cyan">Hypothesis Testing</span>
          <span class="skill-tag cyan">A/B Testing</span>
          <span class="skill-tag cyan">Anomaly Detection</span>
          <span class="skill-tag cyan">Feature Engineering</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ACHIEVEMENT -->
  <div class="section">
    <div class="section-title">
      <span class="icon">🏆</span> Achievements
    </div>
    <div class="achievement">
      <div class="achievement-icon">🏅</div>
      <div class="achievement-text">
        <div class="achievement-title">Phi Kappa Phi — Academic Excellence Award</div>
        <div class="achievement-desc">Recognized among the Top 10% of Graduate Students at the University of North Texas for academic achievement and scholarly dedication.</div>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-quote">
      "Turning raw data into real-world impact —<br/><span>one insight at a time.</span>"
    </div>
    <div class="footer-note">vaishnavibhamare24@gmail.com · Texas, USA · Open to relocation</div>
  </div>

</div>
</body>
</html>
