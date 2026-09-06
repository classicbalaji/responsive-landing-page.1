<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="FlowSync - Modern workflow management platform for developers and productive teams.">
  <title>FlowSync | Effortless Workflow</title>

  <style>
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
      font-family: Arial, Helvetica, sans-serif;
      color: var(--text);
      background: #fff;
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .container {
      width: min(92%, var(--max-width));
      margin: auto;
    }

    /* HEADER */
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
      transition: 0.2s;
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
      transition: 0.2s;
    }

    .header-btn:hover {
      background: var(--primary-dark);
      transform: translateY(-2px);
    }

    /* HERO */
    .hero {
      padding: 90px 0 110px;
      background: linear-gradient(180deg, #ffffff, #f8fbff);
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: center;
      gap: 50px;
    }

    .hero-content h1 {
      color: var(--dark);
      font-size: clamp(2.4rem, 4vw, 3.5rem);
      line-height: 1.15;
      margin-bottom: 20px;
    }

    .hero-content h1 span {
      color: var(--primary);
    }

    .hero-content p {
      color: var(--muted);
      font-size: 1.05rem;
      margin-bottom: 25px;
    }

    .btn {
      display: inline-block;
      padding: 12px 24px;
      border-radius: 8px;
      font-weight: 700;
      cursor: pointer;
      text-align: center;
    }

    .btn-primary {
      color: white;
      background: var(--primary);
      box-shadow: 0 8px 20px rgba(37, 99, 235, 0.22);
    }

    .btn-primary:hover {
      background: var(--primary-dark);
    }

    .dashboard-preview {
      background: linear-gradient(135deg, #1e293b, #0f172a);
      border-radius: var(--radius);
      padding: 2.5rem;
      color: white;
      text-align: center;
      box-shadow: var(--shadow-lg);
    }

    /* FEATURES */
    .section {
      padding: 80px 0;
    }

    .section-heading {
      text-align: center;
      margin-bottom: 50px;
    }

    .section-heading h2 {
      font-size: 2.2rem;
      color: var(--dark);
      margin-bottom: 10px;
    }

    .features-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 25px;
    }

    .feature-card {
      padding: 30px;
      background: white;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      box-shadow: var(--shadow-sm);
    }

    /* PRICING (FIXED POSITIONING) */
    .pricing {
      background: var(--light);
    }

    .pricing-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 25px;
    }

    .price-card {
      position: relative;
      padding: 35px 25px;
      background: white;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      box-shadow: var(--shadow-sm);
    }

    .price-card.popular-card {
      border: 2px solid var(--primary);
      box-shadow: var(--shadow-md);
    }

    .popular-badge {
      position: absolute;
      top: -12px;
      left: 50%;
      transform: translateX(-50%);
      padding: 4px 14px;
      color: white;
      background: var(--primary);
      border-radius: 20px;
      font-size: 0.75rem;
      font-weight: 700;
    }

    .price {
      font-size: 2.2rem;
      font-weight: 800;
      color: var(--dark);
      margin: 15px 0;
    }

    .price-list {
      list-style: none;
      margin-bottom: 25px;
    }

    .price-list li {
      padding: 6px 0;
      font-size: 0.9rem;
    }

    /* FOOTER */
    .footer {
      background: var(--dark);
      color: var(--muted);
      padding: 40px 0 20px;
      text-align: center;
    }

    @media (max-width: 768px) {
      .hero-grid {
        grid-template-columns: 1fr;
        text-align: center;
      }
      .nav-links {
        display: none;
      }
    }
  </style>
</head>
<body>

  <!-- Header -->
  <header class="header">
    <div class="container nav">
      <div class="logo">
        <div class="logo-icon">✦</div>
        FlowSync
      </div>
      <ul class="nav-links">
        <li><a href="#features">Features</a></li>
        <li><a href="#pricing">Pricing</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <a href="#pricing" class="header-btn">Get Started</a>
    </div>
  </header>

  <!-- Hero -->
  <section class="hero">
    <div class="container hero-grid">
      <div class="hero-content">
        <h1>Streamline Your Daily <span>Workflow</span> Effortlessly</h1>
        <p>FlowSync centralizes team communication, sprints, and task management into one clean, responsive dashboard.</p>
        <a href="#pricing" class="btn btn-primary">Start Free Trial</a>
      </div>
      <div class="dashboard-preview">
        <h3>Live Workspace Overview</h3>
        <p style="color: #94a3b8; margin-top: 10px;">Automated task lists, metrics, and progress tracking.</p>
      </div>
    </div>
  </section>

  <!-- Features -->
  <section class="section" id="features">
    <div class="container">
      <div class="section-heading">
        <h2>Features Built for Focus</h2>
        <p style="color: var(--muted);">Everything you need to deliver projects without friction.</p>
      </div>
      <div class="features-grid">
        <div class="feature-card">
          <h3>Real-time Sync</h3>
          <p>Instantly update work progress across your team with zero delays.</p>
        </div>
        <div class="feature-card">
          <h3>Minimal Design</h3>
          <p>Distraction-free interface engineered for maximum execution speed.</p>
        </div>
        <div class="feature-card">
          <h3>Security First</h3>
          <p>Enterprise-grade encryption keeps all your assets safe and private.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing -->
  <section class="section pricing" id="pricing">
    <div class="container">
      <div class="section-heading">
        <h2>Transparent Pricing</h2>
        <p style="color: var(--muted);">Choose a plan that fits your growth.</p>
      </div>
      <div class="pricing-grid">
        <div class="price-card">
          <h3>Starter</h3>
          <p style="color: var(--muted); font-size: 0.85rem;">For individuals</p>
          <div class="price">Free</div>
          <ul class="price-list">
            <li>✓ Unlimited personal tasks</li>
            <li>✓ 5 GB cloud storage</li>
            <li>✓ Standard support</li>
          </ul>
          <a href="#" class="btn btn-primary" style="width: 100%;">Get Started</a>
        </div>

        <div class="price-card popular-card">
          <div class="popular-badge">Popular</div>
          <h3>Pro</h3>
          <p style="color: var(--muted); font-size: 0.85rem;">For growing teams</p>
          <div class="price">₹499 <span style="font-size: 0.8rem; font-weight: normal;">/mo</span></div>
          <ul class="price-list">
            <li>✓ Everything in Starter</li>
            <li>✓ 50 GB cloud storage</li>
            <li>✓ Priority email support</li>
          </ul>
          <a href="#" class="btn btn-primary" style="width: 100%;">Get Started</a>
        </div>

        <div class="price-card">
          <h3>Enterprise</h3>
          <p style="color: var(--muted); font-size: 0.85rem;">For large organizations</p>
          <div class="price">₹1,499 <span style="font-size: 0.8rem; font-weight: normal;">/mo</span></div>
          <ul class="price-list">
            <li>✓ Dedicated account manager</li>
            <li>✓ Unlimited team storage</li>
            <li>✓ 24/7 Phone support</li>
          </ul>
          <a href="#" class="btn btn-primary" style="width: 100%;">Contact Sales</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="footer">
    <div class="container">
      <p>&copy; 2026 FlowSync. Built for CodeOrbit Tech Internship Task 2.</p>
    </div>
  </footer>

</body>
</html>
