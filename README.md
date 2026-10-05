<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="FlowSync - Modern workflow management platform for developers and productive teams.">
  <title>FlowSync | Effortless Workflow</title>

  <style>
    /* =====================================================
       GLOBAL & VARIABLES
    ===================================================== */
    :root {
      --primary: #2563eb;
      --primary-dark: #1d4ed8;
      --primary-light: #eff6ff;
      --dark: #0f172a;
      --text: #334155;
      --muted: #64748b;
      --white: #ffffff;
      --light: #f8fafc;
      --border: #e2e8f0;
      --success: #16a34a;

      --shadow-sm: 0 4px 12px rgba(15, 23, 42, 0.06);
      --shadow-md: 0 15px 40px rgba(15, 23, 42, 0.10);
      --shadow-lg: 0 25px 60px rgba(37, 99, 235, 0.18);

      --radius: 14px;
      --max-width: 1150px;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      color: var(--text);
      background: #fff;
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    button {
      font-family: inherit;
    }

    .container {
      width: min(92%, var(--max-width));
      margin: auto;
    }

    /* =====================================================
       HEADER
    ===================================================== */
    .header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(255, 255, 255, 0.94);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border);
    }

    .nav {
      height: 75px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 9px;
      color: var(--primary);
      font-size: 1.45rem;
      font-weight: 800;
    }

    .logo-icon {
      width: 35px;
      height: 35px;
      display: grid;
      place-items: center;
      color: white;
      font-size: 16px;
      border-radius: 10px;
      background: linear-gradient(135deg, #3b82f6, #1d4ed8);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 30px;
      list-style: none;
    }

    .nav-links a {
      color: #475569;
      font-size: 0.94rem;
      font-weight: 600;
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: var(--primary);
    }

    .header-btn {
      padding: 10px 18px;
      color: white;
      background: var(--primary);
      border-radius: 8px;
      font-size: 0.9rem;
      font-weight: 700;
      transition: background 0.2s, transform 0.2s;
    }

    .header-btn:hover {
      background: var(--primary-dark);
      transform: translateY(-2px);
    }

    .menu-btn {
      display: none;
      width: 40px;
      height: 40px;
      border: 1px solid var(--border);
      border-radius: 8px;
      background: white;
      font-size: 20px;
      cursor: pointer;
    }

    /* =====================================================
       HERO
    ===================================================== */
    .hero {
      position: relative;
      padding: 90px 0 110px;
      background:
        radial-gradient(circle at 90% 20%, rgba(37, 99, 235, 0.10), transparent 35%),
        linear-gradient(180deg, #ffffff, #f8fbff);
      overflow: hidden;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      align-items: center;
      gap: 65px;
    }

    .hero-content h1 {
      color: var(--dark);
      font-size: clamp(2.6rem, 5vw, 4.2rem);
      line-height: 1.08;
      letter-spacing: -2px;
      margin-bottom: 22px;
    }

    .hero-content h1 span {
      color: var(--primary);
    }

    .hero-content p {
      max-width: 560px;
      color: var(--muted);
      font-size: 1.1rem;
      margin-bottom: 28px;
    }

    .hero-buttons {
      display: flex;
      gap: 13px;
      margin-bottom: 28px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      padding: 13px 21px;
      border-radius: 8px;
      font-size: 0.94rem;
      font-weight: 700;
      transition: all 0.25s;
    }

    .btn-primary {
      color: white;
      background: var(--primary);
      box-shadow: 0 8px 20px rgba(37, 99, 235, 0.22);
    }

    .btn-primary:hover {
      background: var(--primary-dark);
      transform: translateY(-3px);
      box-shadow: 0 12px 25px rgba(37, 99, 235, 0.30);
    }

    .btn-outline {
      color: var(--primary);
      background: white;
      border: 1px solid #bfdbfe;
    }

    .btn-outline:hover {
      background: var(--primary-light);
      transform: translateY(-3px);
    }

    .hero-features {
      display: flex;
      flex-wrap: wrap;
      gap: 18px;
      color: var(--muted);
      font-size: 0.82rem;
      font-weight: 600;
    }

    .hero-features span {
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .check {
      color: var(--success);
      font-weight: 900;
    }

    /* =====================================================
       DASHBOARD MOCKUP
    ===================================================== */
    .dashboard-container {
      position: relative;
    }

    .dashboard {
      display: grid;
      grid-template-columns: 145px 1fr;
      min-height: 430px;
      background: white;
      border: 1px solid var(--border);
      border-radius: 17px;
      overflow: hidden;
      box-shadow: var(--shadow-lg);
      transform: perspective(1200px) rotateY(-3deg) rotateX(2deg);
      transition: transform 0.4s ease;
    }

    .dashboard:hover {
      transform: perspective(1200px) rotateY(0) rotateX(0) translateY(-6px);
    }

    .dashboard-sidebar {
      padding: 18px 11px;
      color: #94a3b8;
      background: linear-gradient(180deg, #172554, #0f172a);
    }

    .dashboard-logo {
      display: flex;
      align-items: center;
      gap: 7px;
      color: white;
      font-weight: 800;
      font-size: 0.8rem;
      margin-bottom: 28px;
      padding-left: 7px;
    }

    .dashboard-logo-icon {
      width: 25px;
      height: 25px;
      display: grid;
      place-items: center;
      background: var(--primary);
      border-radius: 6px;
      font-size: 11px;
    }

    .side-menu {
      display: flex;
      flex-direction: column;
      gap: 5px;
    }

    .side-item {
      padding: 9px 7px;
      border-radius: 6px;
      font-size: 0.68rem;
      transition: background 0.2s, color 0.2s;
    }

    .side-item:hover,
    .side-item.active {
      color: white;
      background: rgba(59, 130, 246, 0.25);
    }

    .dashboard-user {
      display: flex;
      align-items: center;
      gap: 7px;
      margin-top: 65px;
      padding: 8px;
      color: white;
      background: rgba(255, 255, 255, 0.08);
      border-radius: 8px;
      font-size: 0.6rem;
    }

    .avatar {
      width: 26px;
      height: 26px;
      display: grid;
      place-items: center;
      border-radius: 50%;
      background: #3b82f6;
      color: white;
      font-size: 0.65rem;
      font-weight: 700;
    }

    .dashboard-main {
      padding: 18px;
      background: #f8fafc;
    }

    .dashboard-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 15px;
    }

    .dashboard-top h3 {
      color: var(--dark);
      font-size: 1rem;
    }

    .search {
      padding: 7px 10px;
      width: 135px;
      color: #94a3b8;
      background: white;
      border: 1px solid var(--border);
      border-radius: 6px;
      font-size: 0.55rem;
    }

    .stats {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 9px;
      margin-bottom: 10px;
    }

    .stat {
      padding: 11px;
      background: white;
      border: 1px solid var(--border);
      border-radius: 8px;
    }

    .stat small {
      display: block;
      color: var(--muted);
      font-size: 0.5rem;
    }

    .stat strong {
      display: block;
      color: var(--dark);
      font-size: 1rem;
      margin: 3px 0;
    }

    .increase {
      color: var(--success);
      font-size: 0.48rem;
    }

    .dashboard-content {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 9px;
    }

    .dashboard-card {
      padding: 13px;
      min-height: 145px;
      background: white;
      border: 1px solid var(--border);
      border-radius: 8px;
    }

    .card-heading {
      display: flex;
      justify-content: space-between;
      color: var(--dark);
      font-size: 0.68rem;
      font-weight: 700;
      margin-bottom: 12px;
    }

    .bar-chart {
      height: 95px;
      display: flex;
      align-items: flex-end;
      gap: 8px;
      padding-top: 10px;
    }

    .bar {
      flex: 1;
      min-height: 15px;
      border-radius: 5px 5px 2px 2px;
      background: linear-gradient(180deg, #60a5fa, #2563eb);
    }

    .bar:nth-child(1) { height: 40%; }
    .bar:nth-child(2) { height: 60%; }
    .bar:nth-child(3) { height: 50%; }
    .bar:nth-child(4) { height: 75%; }
    .bar:nth-child(5) { height: 65%; }
    .bar:nth-child(6) { height: 90%; }

    .progress {
      height: 9px;
      background: #e2e8f0;
      border-radius: 20px;
      overflow: hidden;
      margin: 15px 0;
    }

    .progress span {
      display: block;
      width: 78%;
      height: 100%;
      background: linear-gradient(90deg, #2563eb, #60a5fa);
      border-radius: inherit;
    }

    .task {
      display: flex;
      align-items: center;
      gap: 7px;
      color: var(--muted);
      font-size: 0.57rem;
      margin-bottom: 8px;
    }

    .task-dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: var(--primary);
    }

    /* =====================================================
       FEATURES
    ===================================================== */
    .section {
      padding: 95px 0;
    }

    .section-heading {
      text-align: center;
      margin-bottom: 50px;
    }

    .section-label {
      display: inline-block;
      color: var(--primary);
      font-size: 0.78rem;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      margin-bottom: 10px;
    }

    .section-title {
      color: var(--dark);
      font-size: clamp(2rem, 4vw, 2.7rem);
      line-height: 1.15;
      margin-bottom: 13px;
    }

    .section-description {
      max-width: 600px;
      margin: auto;
      color: var(--muted);
      font-size: 1rem;
    }

    .features {
      background: white;
    }

    .features-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
    }

    .feature-card {
      padding: 30px;
      background: white;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      box-shadow: var(--shadow-sm);
      transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
    }

    .feature-card:hover {
      transform: translateY(-8px);
      box-shadow: var(--shadow-md);
      border-color: #bfdbfe;
    }

    .feature-icon {
      width: 52px;
      height: 52px;
      display: grid;
      place-items: center;
      border-radius: 12px;
      background: var(--primary-light);
      font-size: 1.45rem;
      margin-bottom: 20px;
    }

    .feature-card h3 {
      color: var(--dark);
      font-size: 1.15rem;
      margin-bottom: 8px;
    }

    .feature-card p {
      color: var(--muted);
      font-size: 0.9rem;
    }

    /* =====================================================
       ANIMATIONS
    ===================================================== */
    .reveal {
      opacity: 0;
      transform: translateY(25px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }

    .reveal.show {
      opacity: 1;
      transform: translateY(0);
    }

    /* =====================================================
       RESPONSIVE BREAKPOINTS
    ===================================================== */
    @media (max-width: 950px) {
      .hero-grid {
        grid-template-columns: 1fr;
        text-align: center;
      }

      .hero-content p {
        margin-left: auto;
        margin-right: auto;
      }

      .hero-buttons,
      .hero-features {
        justify-content: center;
      }

      .dashboard {
        max-width: 750px;
        margin: auto;
      }

      .features-grid {
        grid-template-columns: 1fr;
        max-width: 600px;
        margin-left: auto;
        margin-right: auto;
      }
    }

    @media (max-width: 700px) {
      .nav-links {
        position: absolute;
        display: none;
        top: 68px;
        left: 4%;
        right: 4%;
        flex-direction: column;
        align-items: stretch;
        gap: 2px;
        padding: 12px;
        background: white;
        border: 1px solid var(--border);
        border-radius: 12px;
        box-shadow: var(--shadow-md);
      }

      .nav-links.active {
        display: flex;
      }

      .header-btn { display: none; }
      .menu-btn { display: block; }

      .dashboard {
        grid-template-columns: 82px 1fr;
        min-height: 350px;
        transform: none;
      }

      .stats {
        grid-template-columns: repeat(2, 1fr);
      }

      .dashboard-content {
        grid-template-columns: 1fr;
      }

      .search { display: none; }
    }
  </style>
</head>

<body>

  <!-- HEADER -->
  <header class="header">
    <div class="container nav">
      <a href="#" class="logo">
        <span class="logo-icon">◆</span>
        FlowSync
      </a>

      <ul class="nav-links" id="navLinks">
        <li><a href="#features">Features</a></li>
        <li><a href="#pricing">Pricing</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>

      <div>
        <a href="#contact" class="header-btn">Get Started</a>
        <button class="menu-btn" id="menuBtn" aria-label="Open navigation" aria-expanded="false">☰</button>
      </div>
    </div>
  </header>

  <!-- HERO -->
  <section class="hero">
    <div class="container hero-grid">
      <div class="hero-content reveal">
        <span class="section-label">Modern Workflow Platform</span>
        <h1>Streamline Your <span>Daily Workflow</span> Effortlessly</h1>
        <p>FlowSync centralizes team communication, projects, sprints, and file delivery into one powerful dashboard built for velocity.</p>

        <div class="hero-buttons">
          <a href="#features" class="btn btn-primary">Explore Features →</a>
          <a href="#about" class="btn btn-outline">▶ Watch Demo</a>
        </div>

        <div class="hero-features">
          <span><b class="check">✓</b> Lightning Fast</span>
          <span><b class="check">✓</b> Secure</span>
          <span><b class="check">✓</b> Responsive</span>
          <span><b class="check">✓</b> Cloud Ready</span>
        </div>
      </div>

      <!-- DASHBOARD MOCKUP -->
      <div class="dashboard-container reveal">
        <div class="dashboard">
          <aside class="dashboard-sidebar">
            <div class="dashboard-logo">
              <span class="dashboard-logo-icon">◆</span>
              FlowSync
            </div>
            <div class="side-menu">
              <div class="side-item active">◉ Dashboard</div>
              <div class="side-item">▣ Projects</div>
              <div class="side-item">✓ Tasks</div>
              <div class="side-item">◷ Calendar</div>
              <div class="side-item">◌ Messages</div>
              <div class="side-item">□ Files</div>
            </div>
            <div class="dashboard-user">
              <span class="avatar">B</span>
              <span>Balaji<br><small>Admin</small></span>
            </div>
          </aside>

          <main class="dashboard-main">
            <div class="dashboard-top">
              <h3>Dashboard</h3>
              <div class="search">🔍 Search...</div>
            </div>

            <div class="stats">
              <div class="stat"><small>Projects</small><strong>24</strong><span class="increase">↑ 12%</span></div>
              <div class="stat"><small>Tasks</small><strong>156</strong><span class="increase">↑ 18%</span></div>
              <div class="stat"><small>Members</small><strong>32</strong><span class="increase">↑ 8%</span></div>
              <div class="stat"><small>On Time</small><strong>98%</strong><span class="increase">↑ 5%</span></div>
            </div>

            <div class="dashboard-content">
              <div class="dashboard-card">
                <div class="card-heading"><span>Progress</span><span>This Month ▾</span></div>
                <div class="bar-chart">
                  <span class="bar"></span>
                  <span class="bar"></span>
                  <span class="bar"></span>
                  <span class="bar"></span>
                  <span class="bar"></span>
                  <span class="bar"></span>
                </div>
              </div>

              <div class="dashboard-card">
                <div class="card-heading">Tasks Overview</div>
                <div class="progress"><span></span></div>
                <div class="task"><span class="task-dot"></span> Completed — 156</div>
                <div class="task"><span class="task-dot"></span> In Progress — 74</div>
              </div>
            </div>
          </main>
        </div>
      </div>
    </div>
  </section>

  <!-- FEATURES -->
  <section class="section features" id="features">
    <div class="container">
      <div class="section-heading reveal">
        <span class="section-label">Features</span>
        <h2 class="section-title">Engineered for High Performance</h2>
        <p class="section-description">Everything you need to ship projects on time without unnecessary overhead.</p>
      </div>

      <div class="features-grid">
        <div class="feature-card reveal">
          <div class="feature-icon">⚡</div>
          <h3>Lightning Fast</h3>
          <p>Built from the ground up for minimal latency and real-time state synchronization.</p>
        </div>

        <div class="feature-card reveal">
          <div class="feature-icon">🔒</div>
          <h3>Secure by Default</h3>
          <p>End-to-end encryption for all sensitive enterprise project metadata and communication.</p>
        </div>

        <div class="feature-card reveal">
          <div class="feature-icon">📊</div>
          <h3>Deep Analytics</h3>
          <p>Gain actionable insight into team velocity, bottlenecks, and delivery milestones.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- JAVASCRIPT FOR INTERACTIVITY -->
  <script>
    // Mobile Navigation Toggle
    const menuBtn = document.getElementById('menuBtn');
    const navLinks = document.getElementById('navLinks');

    menuBtn.addEventListener('click', () => {
      const expanded = menuBtn.getAttribute('aria-expanded') === 'true';
      menuBtn.setAttribute('aria-expanded', !expanded);
      navLinks.classList.toggle('active');
    });

    // Scroll Reveal Animation via IntersectionObserver
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('show');
        }
      });
    }, { threshold: 0.1 });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  </script>

</body>
</html>
