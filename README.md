<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>AIML for Geoscientists 🪨🤖</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600;700&family=JetBrains+Mono:wght@400;700&display=swap');

  :root {
    --rock: #1a1a2e;
    --magma: #e94560;
    --mineral: #f5a623;
    --quartz: #a8edea;
    --slate: #16213e;
    --fossil: #0f3460;
    --gold: #ffd700;
    --text: #e0e0e0;
    --muted: #8892a4;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--rock);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    overflow-x: hidden;
  }

  /* ANIMATED STARFIELD */
  .stars {
    position: fixed; top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none; z-index: 0;
    overflow: hidden;
  }
  .star {
    position: absolute;
    width: 2px; height: 2px;
    background: white;
    border-radius: 50%;
    animation: twinkle 3s infinite alternate;
  }
  @keyframes twinkle {
    0% { opacity: 0.2; transform: scale(1); }
    100% { opacity: 1; transform: scale(1.5); }
  }

  /* LAVA LAMP BG BLOBS */
  .blob {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.15;
    animation: drift 12s ease-in-out infinite alternate;
    pointer-events: none;
    z-index: 0;
  }
  .blob1 { width: 400px; height: 400px; background: var(--magma); top: -100px; left: -100px; }
  .blob2 { width: 350px; height: 350px; background: var(--mineral); bottom: 100px; right: -80px; animation-delay: -4s; }
  .blob3 { width: 300px; height: 300px; background: var(--quartz); top: 40%; left: 50%; animation-delay: -8s; }
  @keyframes drift {
    0% { transform: translate(0, 0) scale(1); }
    100% { transform: translate(40px, 60px) scale(1.1); }
  }

  /* LAYOUT */
  .content { position: relative; z-index: 1; max-width: 900px; margin: 0 auto; padding: 0 24px 80px; }

  /* HERO */
  .hero {
    text-align: center;
    padding: 80px 0 60px;
  }

  .badge-row {
    display: flex; flex-wrap: wrap; justify-content: center; gap: 8px;
    margin-bottom: 32px;
    animation: fadeDown 0.6s ease both;
  }
  .badge {
    background: var(--fossil);
    border: 1px solid rgba(168,237,234,0.25);
    border-radius: 999px;
    padding: 4px 14px;
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--quartz);
    letter-spacing: 0.05em;
  }

  .hero-emoji {
    font-size: 80px;
    display: block;
    animation: bounce 2s ease-in-out infinite;
    margin-bottom: 16px;
  }
  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-14px); }
  }

  h1 {
    font-size: clamp(2rem, 6vw, 3.6rem);
    font-weight: 700;
    line-height: 1.1;
    animation: fadeDown 0.7s ease 0.1s both;
  }
  h1 .accent { color: var(--magma); }
  h1 .gold { color: var(--gold); }

  .tagline {
    margin-top: 18px;
    font-size: 1.15rem;
    color: var(--muted);
    max-width: 600px;
    margin-left: auto; margin-right: auto;
    animation: fadeDown 0.7s ease 0.2s both;
  }

  .hero-cta {
    margin-top: 32px;
    display: inline-flex; gap: 12px; flex-wrap: wrap; justify-content: center;
    animation: fadeDown 0.7s ease 0.3s both;
  }
  .btn {
    padding: 12px 28px;
    border-radius: 8px;
    font-weight: 600;
    font-size: 0.95rem;
    cursor: pointer;
    text-decoration: none;
    transition: transform 0.15s, box-shadow 0.15s;
    display: inline-block;
  }
  .btn:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,0,0,0.4); }
  .btn-primary { background: var(--magma); color: white; }
  .btn-secondary { background: transparent; border: 1px solid var(--quartz); color: var(--quartz); }

  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* DIVIDER */
  .divider {
    border: none;
    height: 1px;
    background: linear-gradient(to right, transparent, rgba(168,237,234,0.3), transparent);
    margin: 48px 0;
  }

  /* SECTION HEADINGS */
  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: var(--magma);
    margin-bottom: 8px;
  }
  h2 {
    font-size: 1.6rem;
    font-weight: 700;
    margin-bottom: 20px;
  }
  h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin-bottom: 6px;
    color: var(--quartz);
  }
  p { color: var(--muted); line-height: 1.7; margin-bottom: 12px; }

  /* WHY CARD */
  .why-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 16px;
    margin-top: 24px;
  }
  .why-card {
    background: var(--slate);
    border: 1px solid rgba(168,237,234,0.1);
    border-radius: 12px;
    padding: 20px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .why-card:hover { border-color: var(--quartz); transform: translateY(-3px); }
  .why-card .icon { font-size: 2rem; margin-bottom: 10px; }

  /* STRATA COURSE TIMELINE */
  .strata {
    margin-top: 24px;
    position: relative;
  }
  .strata::before {
    content: '';
    position: absolute;
    left: 20px; top: 0; bottom: 0;
    width: 2px;
    background: linear-gradient(to bottom, var(--magma), var(--mineral), var(--quartz), var(--magma));
  }
  .layer {
    display: flex;
    gap: 20px;
    margin-bottom: 28px;
    padding-left: 54px;
    position: relative;
    opacity: 0;
    transform: translateX(-20px);
    animation: slideIn 0.5s ease forwards;
  }
  .layer:nth-child(1) { animation-delay: 0.1s; }
  .layer:nth-child(2) { animation-delay: 0.2s; }
  .layer:nth-child(3) { animation-delay: 0.3s; }
  .layer:nth-child(4) { animation-delay: 0.4s; }
  .layer:nth-child(5) { animation-delay: 0.5s; }
  @keyframes slideIn {
    to { opacity: 1; transform: translateX(0); }
  }
  .layer-dot {
    position: absolute;
    left: 12px;
    top: 4px;
    width: 18px; height: 18px;
    border-radius: 50%;
    border: 2px solid var(--quartz);
    background: var(--rock);
    display: flex; align-items: center; justify-content: center;
    font-size: 9px;
  }
  .layer-body {
    background: var(--slate);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    padding: 18px 20px;
    flex: 1;
  }
  .layer-title {
    font-weight: 700;
    font-size: 1rem;
    color: var(--text);
    margin-bottom: 8px;
    display: flex; align-items: center; gap: 8px;
  }
  .layer-topics {
    display: flex; flex-wrap: wrap; gap: 6px;
    margin-top: 10px;
  }
  .topic-pill {
    background: rgba(168,237,234,0.08);
    border: 1px solid rgba(168,237,234,0.18);
    border-radius: 6px;
    padding: 3px 10px;
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--quartz);
  }
  .topic-pill.hot {
    background: rgba(233,69,96,0.12);
    border-color: rgba(233,69,96,0.3);
    color: #ff8fa3;
  }
  .topic-pill.warm {
    background: rgba(245,166,35,0.1);
    border-color: rgba(245,166,35,0.25);
    color: var(--mineral);
  }

  /* TOOLS SHELF */
  .tools-shelf {
    display: flex; flex-wrap: wrap; gap: 12px; margin-top: 20px;
  }
  .tool-chip {
    background: var(--fossil);
    border-radius: 8px;
    padding: 8px 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    display: flex; align-items: center; gap: 8px;
    border: 1px solid rgba(255,255,255,0.08);
    transition: background 0.2s;
  }
  .tool-chip:hover { background: rgba(168,237,234,0.1); }

  /* FUN QUOTE */
  .fun-quote {
    background: linear-gradient(135deg, var(--fossil), rgba(15,52,96,0.5));
    border-left: 4px solid var(--magma);
    border-radius: 0 12px 12px 0;
    padding: 20px 24px;
    margin: 32px 0;
    font-style: italic;
    font-size: 1.05rem;
    color: var(--text);
    position: relative;
  }
  .fun-quote .quote-attr {
    display: block;
    margin-top: 10px;
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--muted);
    font-style: normal;
  }

  /* ANIMATED SEISMIC BAR */
  .seismic-bar {
    display: flex; gap: 3px; align-items: flex-end;
    height: 40px; margin: 20px 0;
    justify-content: center;
  }
  .seis-line {
    width: 4px;
    background: linear-gradient(to top, var(--magma), var(--mineral));
    border-radius: 2px;
    animation: pulse 1.2s ease-in-out infinite alternate;
  }
  .seis-line:nth-child(odd) { animation-delay: 0.2s; }
  .seis-line:nth-child(3n) { animation-delay: 0.5s; }
  @keyframes pulse {
    from { height: 4px; opacity: 0.3; }
    to { height: 36px; opacity: 1; }
  }

  /* PREREQS */
  .prereq-list {
    list-style: none;
    display: flex; flex-direction: column; gap: 10px;
    margin-top: 16px;
  }
  .prereq-list li {
    display: flex; align-items: flex-start; gap: 12px;
    color: var(--muted);
    line-height: 1.5;
  }
  .prereq-list li span.check { color: var(--quartz); font-size: 1.1em; flex-shrink: 0; }

  /* FOOTER */
  footer {
    text-align: center;
    padding: 40px 0 20px;
    font-size: 13px;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
  }
  footer span { color: var(--magma); }

</style>
</head>
<body>

<!-- STARS -->
<div class="stars" id="stars"></div>
<!-- BLOBS -->
<div class="blob blob1"></div>
<div class="blob blob2"></div>
<div class="blob blob3"></div>

<div class="content">

  <!-- HERO -->
  <section class="hero">
    <div class="badge-row">
      <span class="badge">🪨 Geoscience</span>
      <span class="badge">🤖 Machine Learning</span>
      <span class="badge">🐍 Python</span>
      <span class="badge">📊 Data Science</span>
      <span class="badge">⛏️ From Scratch</span>
    </div>

    <span class="hero-emoji">🌋</span>

    <h1>
      <span class="gold">AI & ML</span> for<br/>
      <span class="accent">Geoscientists</span>
    </h1>

    <p class="tagline">
      Because your rocks deserve better analysis than eyeballing a well log at 3am ☕<br/>
      A beginner-friendly, zero-fluff course to go from <em>"what even is Python?"</em> to <em>"I just trained a neural net on seismic data!"</em>
    </p>

    <div class="seismic-bar">
      <div class="seis-line"></div><div class="seis-line"></div><div class="seis-line"></div>
      <div class="seis-line"></div><div class="seis-line"></div><div class="seis-line"></div>
      <div class="seis-line"></div><div class="seis-line"></div><div class="seis-line"></div>
      <div class="seis-line"></div><div class="seis-line"></div><div class="seis-line"></div>
      <div class="seis-line"></div><div class="seis-line"></div><div class="seis-line"></div>
    </div>

    <div class="hero-cta">
      <a class="btn btn-primary" href="#course">🚀 Start Drilling</a>
      <a class="btn btn-secondary" href="#why">🤔 Why Though?</a>
    </div>
  </section>

  <hr class="divider"/>

  <!-- FUN QUOTE -->
  <div class="fun-quote">
    "A geoscientist who can code is dangerous. A geoscientist who knows ML is unstoppable. A geoscientist who does both? They probably run the whole field by Thursday."
    <span class="quote-attr">— Anonymous, possibly a geoscientist in denial about Python</span>
  </div>

  <!-- WHY -->
  <section id="why">
    <p class="section-label">// motivation.py</p>
    <h2>Why Should a Geoscientist Learn AI? 🤷</h2>
    <p>Great question. Short answer: because the oil isn't going to find itself. Long answer: below.</p>

    <div class="why-grid">
      <div class="why-card">
        <div class="icon">💸</div>
        <h3>Career Glow-Up</h3>
        <p>Employers love a geo who can script. You go from "the rock person" to "the strategic AI rock person."</p>
      </div>
      <div class="why-card">
        <div class="icon">⚡</div>
        <h3>10x Faster Analysis</h3>
        <p>Processes that took days in Excel? Python does them in milliseconds. Sleep is back on the menu.</p>
      </div>
      <div class="why-card">
        <div class="icon">🔭</div>
        <h3>See Patterns Humans Can't</h3>
        <p>ML finds subtle patterns in seismic and well data that would take you 40 years of squinting to spot.</p>
      </div>
      <div class="why-card">
        <div class="icon">🌍</div>
        <h3>Climate & Energy</h3>
        <p>Carbon capture, geothermal, mineral exploration — the world needs smart geos with AI superpowers.</p>
      </div>
    </div>
  </section>

  <hr class="divider"/>

  <!-- COURSE CONTENT -->
  <section id="course">
    <p class="section-label">// course_content.py</p>
    <h2>What's Inside the Core 🧱</h2>
    <p>Think of this as geological strata — we drill from the surface all the way down to the neural network basement.</p>

    <div class="strata">

      <!-- LAYER 1 -->
      <div class="layer">
        <div class="layer-dot">1</div>
        <div class="layer-body">
          <div class="layer-title">🌍 The Big Picture: Data Science & ML</div>
          <p>Before writing a single line of code, we make sure you actually know what we're talking about. No jargon-dumping allowed.</p>
          <div class="layer-topics">
            <span class="topic-pill">What is Data Science?</span>
            <span class="topic-pill">What is Machine Learning?</span>
            <span class="topic-pill">Brief History</span>
            <span class="topic-pill">Analysis vs Analytics</span>
            <span class="topic-pill">DS vs ML</span>
            <span class="topic-pill warm">DS Life Cycle</span>
            <span class="topic-pill">DS Knowledge Domains</span>
            <span class="topic-pill">DS Skills</span>
          </div>
        </div>
      </div>

      <!-- LAYER 2 -->
      <div class="layer">
        <div class="layer-dot">2</div>
        <div class="layer-body">
          <div class="layer-title">🐍 Learning Python (Yes, You Can Do This)</div>
          <p>Python is not hard. It's basically English with brackets. We go from zero to confident coder, step by step.</p>
          <div class="layer-topics">
            <span class="topic-pill hot">Why Python?</span>
            <span class="topic-pill">Why Learn to Code?</span>
            <span class="topic-pill">Coding Workflow</span>
            <span class="topic-pill">Programming Concepts</span>
            <span class="topic-pill">Which Language First?</span>
          </div>
        </div>
      </div>

      <!-- LAYER 3 -->
      <div class="layer">
        <div class="layer-dot">3</div>
        <div class="layer-body">
          <div class="layer-title">📊 The Pydata Stack (Your New Best Friends)</div>
          <p>The holy trinity of scientific Python. Master these and you can wrangle any dataset on the planet.</p>
          <div class="layer-topics">
            <span class="topic-pill warm">NumPy</span>
            <span class="topic-pill warm">Pandas</span>
            <span class="topic-pill warm">Matplotlib</span>
            <span class="topic-pill warm">Seaborn</span>
            <span class="topic-pill">Array Operations</span>
            <span class="topic-pill">DataFrame Ops</span>
            <span class="topic-pill">Plotting & Viz</span>
          </div>
        </div>
      </div>

      <!-- LAYER 4 -->
      <div class="layer">
        <div class="layer-dot">4</div>
        <div class="layer-body">
          <div class="layer-title">🪨 Geoscience-Specific Libraries (The Good Stuff)</div>
          <p>Finally — libraries made <em>for us</em>, by people who have also cried over bad LAS files.</p>
          <div class="layer-topics">
            <span class="topic-pill hot">Welly</span>
            <span class="topic-pill hot">LASIO</span>
            <span class="topic-pill hot">SEGYIO</span>
            <span class="topic-pill">Well Log I/O</span>
            <span class="topic-pill">Seismic Data Handling</span>
          </div>
        </div>
      </div>

      <!-- LAYER 5 -->
      <div class="layer">
        <div class="layer-dot">5</div>
        <div class="layer-body">
          <div class="layer-title">🤖 Machine Learning — The Main Event</div>
          <p>This is where the magic happens. Regression, clustering, random forests, neural nets — all taught with real geoscience context.</p>
          <div class="layer-topics">
            <span class="topic-pill hot">ML vs Coding</span>
            <span class="topic-pill hot">Algorithm Types</span>
            <span class="topic-pill warm">Linear Regression</span>
            <span class="topic-pill warm">Logistic Regression</span>
            <span class="topic-pill warm">SVM</span>
            <span class="topic-pill warm">K-Means</span>
            <span class="topic-pill warm">PCA</span>
            <span class="topic-pill warm">Random Forest</span>
            <span class="topic-pill hot">Neural Networks</span>
            <span class="topic-pill">Supervised ML</span>
            <span class="topic-pill">Clustering</span>
          </div>
        </div>
      </div>

    </div>
  </section>

  <hr class="divider"/>

  <!-- TOOLS -->
  <section>
    <p class="section-label">// requirements.txt</p>
    <h2>Your Toolkit 🧰</h2>
    <p>Everything you need is free and open-source. We love open source. Open source never ghosted us.</p>
    <div class="tools-shelf">
      <div class="tool-chip">🐍 Python 3.x</div>
      <div class="tool-chip">📓 Jupyter Notebook</div>
      <div class="tool-chip">🔢 NumPy</div>
      <div class="tool-chip">🐼 Pandas</div>
      <div class="tool-chip">📈 Matplotlib</div>
      <div class="tool-chip">🌊 Seaborn</div>
      <div class="tool-chip">🪨 Welly / LASIO</div>
      <div class="tool-chip">📡 SEGYIO</div>
      <div class="tool-chip">🤖 Scikit-learn</div>
      <div class="tool-chip">🧠 TensorFlow / PyTorch</div>
    </div>
  </section>

  <hr class="divider"/>

  <!-- PREREQS -->
  <section>
    <p class="section-label">// prerequisites.txt</p>
    <h2>What You Need to Start 🎒</h2>
    <ul class="prereq-list">
      <li><span class="check">✅</span> Basic geoscience background (you've seen a well log. That counts.)</li>
      <li><span class="check">✅</span> A computer (borrowed laptops are fine. We don't judge.)</li>
      <li><span class="check">✅</span> Curiosity and a willingness to Google error messages at 11pm</li>
      <li><span class="check">✅</span> Zero coding experience needed. Seriously. None.</li>
      <li><span class="check">☕</span> Optional but strongly recommended: coffee. Lots of coffee.</li>
    </ul>
  </section>

  <hr class="divider"/>

  <!-- FINAL QUOTE -->
  <div class="fun-quote">
    "The best time to learn Python was 10 years ago. The second best time is right now, with this repo open in your browser."
    <span class="quote-attr">— Ancient geoscientist proverb (invented just now)</span>
  </div>

  <!-- FOOTER -->
  <footer>
    Made with <span>❤️</span> + <span>🪨</span> + too much <span>☕</span> by geoscientists, for geoscientists<br/><br/>
    <span>// No rocks were harmed in the making of this course.</span>
  </footer>

</div>

<script>
  // Generate random stars
  const starsContainer = document.getElementById('stars');
  for (let i = 0; i < 120; i++) {
    const star = document.createElement('div');
    star.className = 'star';
    star.style.left = Math.random() * 100 + '%';
    star.style.top = Math.random() * 100 + '%';
    star.style.animationDelay = Math.random() * 4 + 's';
    star.style.animationDuration = (2 + Math.random() * 3) + 's';
    star.style.width = star.style.height = (Math.random() > 0.7 ? 3 : 2) + 'px';
    starsContainer.appendChild(star);
  }

  // Intersection observer for layer animations
  const layers = document.querySelectorAll('.layer');
  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.animationPlayState = 'running';
      }
    });
  }, { threshold: 0.15 });
  layers.forEach(l => {
    l.style.animationPlayState = 'paused';
    obs.observe(l);
  });
</script>
</body>
</html>
