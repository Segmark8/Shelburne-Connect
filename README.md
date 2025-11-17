# Shelburne-Connect
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Rx: Community Social Prescribing – Shelburne Pilot | Capstone</title>
  <style>
    :root {
      --bg: #f5f7fb;
      --card: #ffffff;
      --primary: #2563eb;
      --primary-soft: #dbeafe;
      --accent: #059669;
      --text-main: #111827;
      --text-muted: #6b7280;
      --border: #e5e7eb;
      --shadow-soft: 0 14px 40px rgba(15, 23, 42, 0.12);
      --radius-lg: 1.25rem;
      --radius-md: 0.9rem;
      --container: 1120px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
        sans-serif;
    }

    body {
      background: radial-gradient(circle at top left, #e0f2fe 0, #f5f7fb 40%, #f9fafb 100%);
      color: var(--text-main);
      line-height: 1.6;
      scroll-behavior: smooth;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    /* Header & Nav */

    header {
      position: sticky;
      top: 0;
      z-index: 40;
      background: rgba(255, 255, 255, 0.96);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }

    .nav-inner {
      max-width: var(--container);
      margin: 0 auto;
      padding: 0.7rem 1.2rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }

    .brand-logo-wrapper {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .brand-logo {
      width: 40px;
      height: 40px;
      border-radius: 999px;
      overflow: hidden;
      background: #e5e7eb;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .brand-logo img {
      max-width: 100%;
      max-height: 100%;
      display: block;
      object-fit: contain;
    }

    .brand-mark {
      width: 32px;
      height: 32px;
      border-radius: 999px;
      background: linear-gradient(135deg, #2563eb, #059669);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      font-size: 0.85rem;
      font-weight: 700;
      box-shadow: 0 10px 25px rgba(37, 99, 235, 0.4);
    }

    .brand-text-title {
      font-size: 0.9rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    .brand-text-sub {
      font-size: 0.75rem;
      color: var(--text-muted);
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 1.4rem;
      font-size: 0.9rem;
    }

    nav a {
      position: relative;
      padding-bottom: 0.1rem;
      color: #111827;
    }

    nav a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 0;
      height: 2px;
      background: var(--primary);
      transition: width 0.18s ease-out;
    }

    nav a:hover::after {
      width: 100%;
    }

    .nav-cta {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      font-size: 0.8rem;
      color: var(--text-muted);
      text-align: right;
    }

    .nav-cta span.badge {
      padding: 0.15rem 0.6rem;
      border-radius: 999px;
      background: #dcfce7;
      color: #166534;
      font-weight: 600;
      font-size: 0.75rem;
    }

    .menu-btn {
      display: none;
      border: none;
      background: none;
      font-size: 1.4rem;
      cursor: pointer;
    }

    /* Layout helpers */

    .container {
      max-width: var(--container);
      margin: 0 auto;
      padding: 0 1.2rem;
    }

    section {
      padding: 3.5rem 0 0;
    }

    .section-header {
      display: flex;
      justify-content: space-between;
      gap: 1.5rem;
      align-items: flex-start;
      margin-bottom: 1.5rem;
    }

    .section-label {
      font-size: 0.78rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--primary);
      font-weight: 700;
      margin-bottom: 0.25rem;
    }

    .section-title {
      font-size: 1.4rem;
      font-weight: 700;
    }

    .section-subtitle {
      font-size: 0.9rem;
      color: var(--text-muted);
      max-width: 28rem;
    }

    .pill {
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      padding: 0.25rem 0.7rem;
      background: #eef2ff;
      color: #4f46e5;
      border-radius: 999px;
      font-size: 0.75rem;
      margin-right: 0.3rem;
      margin-top: 0.3rem;
    }

    /* Hero */

    .hero {
      padding: 3.2rem 0 2rem;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: minmax(0, 3fr) minmax(0, 2.4fr);
      gap: 2.5rem;
      align-items: center;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.25rem 0.7rem;
      border-radius: 999px;
      background: var(--primary-soft);
      color: #1d4ed8;
      font-size: 0.78rem;
      margin-bottom: 1rem;
    }

    .hero-badge span.dot {
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: #22c55e;
      box-shadow: 0 0 0 4px rgba(34, 197, 94, 0.2);
    }

    .hero-title {
      font-size: clamp(2.1rem, 3.3vw + 1rem, 3.1rem);
      line-height: 1.1;
      font-weight: 800;
      margin-bottom: 0.9rem;
    }

    .hero-highlight {
      background: linear-gradient(120deg, #2563eb, #059669);
      -webkit-background-clip: text;
      color: transparent;
    }

    .hero-text {
      font-size: 0.98rem;
      color: var(--text-muted);
      max-width: 34rem;
      margin-bottom: 1.1rem;
    }

    .hero-meta {
      font-size: 0.85rem;
      color: var(--text-muted);
      margin-top: 0.9rem;
    }

    .hero-meta strong {
      color: #111827;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      align-items: center;
    }

    .btn-primary {
      border: none;
      border-radius: 999px;
      padding: 0.75rem 1.5rem;
      background: var(--primary);
      color: #fff;
      font-size: 0.9rem;
      font-weight: 600;
      cursor: pointer;
      box-shadow: 0 16px 40px rgba(37, 99, 235, 0.35);
      transition: transform 0.12s ease-out, box-shadow 0.12s ease-out,
        background 0.12s ease-out;
    }

    .btn-primary:hover {
      transform: translateY(-1px);
      background: #1d4ed8;
      box-shadow: 0 20px 50px rgba(37, 99, 235, 0.42);
    }

    .btn-ghost {
      border-radius: 999px;
      padding: 0.7rem 1.3rem;
      border: 1px solid var(--border);
      background: rgba(255, 255, 255, 0.8);
      cursor: pointer;
      font-size: 0.88rem;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
    }

    .btn-ghost span.icon {
      font-size: 1rem;
    }

    .hero-card {
      background: rgba(255, 255, 255, 0.96);
      border-radius: var(--radius-lg);
      padding: 1.5rem 1.4rem;
      box-shadow: var(--shadow-soft);
      border: 1px solid #e0e7ff;
    }

    .hero-card-tag {
      font-size: 0.78rem;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      color: var(--text-muted);
      margin-bottom: 0.35rem;
    }

    .hero-card-title {
      font-size: 1.1rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
    }

    .hero-card-text {
      font-size: 0.88rem;
      color: var(--text-muted);
      margin-bottom: 0.9rem;
    }

    .hero-stats {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 0.9rem;
      margin-top: 0.9rem;
      font-size: 0.78rem;
    }

    .stat {
      padding: 0.7rem 0.8rem;
      border-radius: 0.9rem;
      background: #f9fafb;
      border: 1px dashed #e5e7eb;
    }

    .stat strong {
      display: block;
      font-size: 1.05rem;
    }

    /* Cards & Grids */

    .card {
      background: var(--card);
      border-radius: var(--radius-md);
      padding: 1.15rem 1.2rem;
      border: 1px solid var(--border);
      box-shadow: 0 10px 26px rgba(15, 23, 42, 0.06);
      font-size: 0.9rem;
    }

    .card-title {
      font-size: 1rem;
      font-weight: 600;
      margin-bottom: 0.4rem;
    }

    .card-meta {
      font-size: 0.8rem;
      color: var(--text-muted);
      margin-bottom: 0.6rem;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: minmax(0, 1.4fr) minmax(0, 1fr);
      gap: 1.7rem;
    }

    .grid-3 {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1.3rem;
    }

    .list-check {
      list-style: none;
      display: grid;
      gap: 0.4rem;
      font-size: 0.88rem;
    }

    .list-check li::before {
      content: "✔";
      color: #16a34a;
      margin-right: 0.35rem;
    }

    .tag-row {
      font-size: 0.78rem;
      color: var(--text-muted);
      margin-top: 0.7rem;
    }

    /* Budget strip */

    .budget-strip {
      margin-top: 1.2rem;
      padding: 0.9rem 1rem;
      border-radius: 0.9rem;
      background: linear-gradient(120deg, #ecfdf5, #eff6ff);
      border: 1px solid #bbf7d0;
      font-size: 0.85rem;
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem 1.2rem;
      align-items: center;
    }

    .budget-chip {
      padding: 0.2rem 0.7rem;
      border-radius: 999px;
      background: #ffffffaa;
      border: 1px solid #d1fae5;
      font-size: 0.78rem;
    }

    /* Stakeholders */

    .stakeholder-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1rem;
      font-size: 0.86rem;
    }

    .stakeholder-grid h4 {
      font-size: 0.9rem;
      margin-bottom: 0.25rem;
    }

    .stakeholder-grid p {
      color: var(--text-muted);
    }

    /* Outcomes & Evaluation */

    .kpi-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1rem;
    }

    .kpi {
      padding: 0.9rem 1rem;
      border-radius: 0.9rem;
      border: 1px solid #e0f2fe;
      background: #eff6ff;
      font-size: 0.86rem;
    }

    .kpi span.label {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: #1d4ed8;
      display: block;
      margin-bottom: 0.3rem;
    }

    .kpi strong {
      display: block;
      font-size: 1.05rem;
      margin-bottom: 0.2rem;
    }

    /* Call to action / contact */

    .cta-band {
      margin: 3rem 0 2.5rem;
      padding: 1.4rem 1.3rem;
      border-radius: var(--radius-lg);
      background: linear-gradient(135deg, #2563eb, #059669);
      color: #ecfeff;
      display: grid;
      grid-template-columns: minmax(0, 2.2fr) minmax(0, 1.4fr);
      gap: 1.5rem;
      align-items: center;
    }

    .cta-band h3 {
      font-size: 1.3rem;
      margin-bottom: 0.35rem;
    }

    .cta-band p {
      font-size: 0.9rem;
      opacity: 0.95;
    }

    .cta-side {
      font-size: 0.86rem;
    }

    .cta-side a {
      color: #eef2ff;
      text-decoration: underline;
      text-decoration-thickness: 1px;
    }

    /* Contact block */

    .contact-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.4fr) minmax(0, 1fr);
      gap: 1.6rem;
    }

    .info-line {
      font-size: 0.86rem;
      color: var(--text-muted);
      margin-bottom: 0.35rem;
    }

    form {
      display: grid;
      gap: 0.7rem;
      font-size: 0.86rem;
    }

    label {
      display: block;
      margin-bottom: 0.2rem;
      font-weight: 500;
      font-size: 0.84rem;
      color: #374151;
    }

    input,
    textarea {
      width: 100%;
      border-radius: 0.7rem;
      border: 1px solid #d1d5db;
      padding: 0.55rem 0.65rem;
      font-size: 0.86rem;
      resize: vertical;
      background: #ffffffdd;
    }

    input:focus,
    textarea:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 1px rgba(37, 99, 235, 0.18);
      background: #ffffff;
    }

    /* Footer */

    footer {
      padding: 1.4rem 1.2rem 2rem;
      border-top: 1px solid var(--border);
      margin-top: 3rem;
      font-size: 0.78rem;
      color: var(--text-muted);
      text-align: center;
    }

    footer a {
      text-decoration: underline;
      text-decoration-thickness: 1px;
    }

    /* Responsive */

    @media (max-width: 900px) {
      .hero-grid,
      .grid-2,
      .cta-band,
      .contact-grid {
        grid-template-columns: minmax(0, 1fr);
      }

      .hero {
        padding-top: 2.3rem;
      }

      .hero-card {
        order: -1;
      }

      .kpi-grid,
      .stakeholder-grid,
      .grid-3,
      .hero-stats {
        grid-template-columns: minmax(0, 1fr);
      }

      .section-header {
        flex-direction: column;
      }

      .nav-inner {
        align-items: center;
      }

      nav ul {
        position: absolute;
        right: 1.2rem;
        top: 3.1rem;
        padding: 0.7rem 0.9rem;
        background: #ffffff;
        border-radius: 0.9rem;
        border: 1px solid var(--border);
        box-shadow: 0 14px 40px rgba(15, 23, 42, 0.22);
        flex-direction: column;
        gap: 0.8rem;
        display: none;
      }

      nav ul.open {
        display: flex;
      }

      .menu-btn {
        display: block;
      }

      .nav-cta {
        display: none;
      }
    }
  </style>
</head>
<body>
  <!-- HEADER -->
  <header>
    <div class="nav-inner">
      <div class="brand">
        <div class="brand-logo-wrapper">
          <div class="brand-logo">
            <!-- Replace shelburne-logo.png with your actual logo filename/path -->
            <img src="shelburne-logo.png" alt="Town of Shelburne logo" />
          </div>
          <div class="brand-mark">Rx</div>
        </div>
        <div>
          <div class="brand-text-title">Shelburne Pilot</div>
          <div class="brand-text-sub">Community Social Prescribing</div>
        </div>
      </div>

      <button class="menu-btn" id="menuBtn" aria-label="Toggle navigation">
        ☰
      </button>

      <nav>
        <ul id="navList">
          <li><a href="#overview">Overview</a></li>
          <li><a href="#needs">Needs</a></li>
          <li><a href="#solution">Solution</a></li>
          <li><a href="#stakeholders">Partners</a></li>
          <li><a href="#budget">Budget</a></li>
          <li><a href="#outcomes">Outcomes</a></li>
          <li><a href="#contact">Get Involved</a></li>
        </ul>
      </nav>

      <div class="nav-cta">
        <span class="badge">Capstone Project</span>
        <span>Conestoga College · 2026</span>
      </div>
    </div>
  </header>

  <!-- HERO -->
  <section class="hero" id="overview">
    <div class="container hero-grid">
      <div>
        <div class="hero-badge">
          <span class="dot"></span>
          <span>Reducing social isolation among seniors</span>
        </div>
        <h1 class="hero-title">
          Rx: <span class="hero-highlight">Community Social Prescribing</span><br />
          Pilot in Shelburne, Ontario
        </h1>
        <p class="hero-text">
          A 12-month, community-driven initiative connecting older adults (65+) in
          Shelburne with non-clinical supports such as volunteer home visits,
          recreation programs, and social activities — so no senior has to age in
          isolation.
        </p>
        <p class="hero-text" style="font-size:0.9rem;">
          This website presents the capstone project by
          <strong>Segun Michael Olanipekun</strong> and team in the
          <strong>Health Care Administration &amp; Service Management</strong>
          program at Conestoga College.
        </p>
        <div class="hero-actions">
          <button class="btn-primary" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">
            Partner / Volunteer
          </button>
          <button class="btn-ghost" onclick="document.getElementById('solution').scrollIntoView({behavior:'smooth'})">
            <span class="icon">⬇</span>
            Learn how the pilot works
          </button>
        </div>
        <p class="hero-meta">
          <strong>Target group:</strong> ~260 socially isolated seniors in Shelburne ·
          <strong>Timeline:</strong> Jan–Dec 2026 ·
          <strong>Goal:</strong> 30% reduction in loneliness scores
        </p>
      </div>

      <aside class="hero-card">
        <div class="hero-card-tag">Executive Snapshot</div>
        <div class="hero-card-title">Why this project matters</div>
        <p class="hero-card-text">
          Social isolation among older adults is as harmful to health as many
          well-known risk factors and is linked to depression, cognitive decline,
          avoidable ER visits, and increased healthcare costs. The Shelburne pilot
          uses social prescribing to link seniors to community-based supports instead
          of leaving them “alone with a brochure.”
        </p>

        <ul class="list-check">
          <li>Evidence-informed, based on Ontario social prescribing pilots</li>
          <li>Built on partnerships across health, municipal, and community sectors</li>
          <li>Uses volunteers (“connection crew”) for door-to-door outreach</li>
          <li>Evaluated with validated tools (UCLA Loneliness Scale, WHO-5)</li>
        </ul>

        <div class="hero-stats">
          <div class="stat">
            <strong>260+</strong>
            Seniors estimated to be living in social isolation in Shelburne
          </div>
          <div class="stat">
            <strong>$45k</strong>
            Total project budget with grants &amp; in-kind support
          </div>
          <div class="stat">
            <strong>12 mo</strong>
            Pilot period with baseline, mid-term, and final evaluation
          </div>
        </div>
      </aside>
    </div>
  </section>

  <!-- NEEDS ASSESSMENT -->
  <section id="needs">
    <div class="container">
      <div class="section-header">
        <div>
          <div class="section-label">Needs Assessment</div>
          <h2 class="section-title">Understanding social isolation in Shelburne</h2>
        </div>
        <p class="section-subtitle">
          Canada’s population is aging, and smaller communities like Shelburne feel
          the impact more intensely. Limited transportation, digital inequality, and
          shrinking social networks leave many seniors disconnected from daily life.
        </p>
      </div>

      <div class="grid-2">
        <div class="card">
          <h3 class="card-title">The national &amp; local picture</h3>
          <p>
            Across Canada, nearly one in five older adults reports feeling lonely, and
            about 30% are at risk of social isolation. In rural and semi-urban areas,
            barriers such as distance, fewer programs, and limited public transit make
            it harder for seniors to stay socially connected.
          </p>
          <p style="margin-top:0.6rem;">
            In Shelburne, approximately <strong>1,300 residents</strong> are aged 65+,
            representing about <strong>14.5%</strong> of the town’s population. Based
            on national evidence, an estimated <strong>~260 seniors</strong> are
            currently experiencing or at high risk of social isolation.
          </p>
          <div class="tag-row">
            <span class="pill">Rural &amp; semi-urban context</span>
            <span class="pill">Transportation barriers</span>
            <span class="pill">Living alone</span>
          </div>
        </div>

        <div class="card">
          <h3 class="card-title">Why isolation is a health issue</h3>
          <p>
            Social isolation is more than “feeling lonely.” It is associated with
            higher rates of depression, anxiety, cognitive decline, dementia, chronic
            conditions, and premature mortality. It also drives avoidable use of
            healthcare — including ER visits and hospital admissions.
          </p>
          <p style="margin-top:0.6rem;">
            With older adults already accounting for a large share of health
            expenditures, reducing isolation is both a <strong>compassionate</strong>
            and a <strong>system-level</strong> priority.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECT & SOLUTION -->
  <section id="solution">
    <div class="container">
      <div class="section-header">
        <div>
          <div class="section-label">Project Model</div>
          <h2 class="section-title">How the Rx: Community pilot works</h2>
        </div>
        <p class="section-subtitle">
          The pilot adapts proven social prescribing approaches from Ontario and
          tailors them to Shelburne’s rural context, using volunteers and local
          partners to bridge healthcare and community life.
        </p>
      </div>

      <div class="grid-2">
        <div class="card">
          <h3 class="card-title">Core idea: Social prescribing</h3>
          <p class="card-meta">From medical prescriptions to “community prescriptions”</p>
          <p>
            Instead of responding to loneliness only with medication or clinic visits,
            healthcare providers can write a <strong>social prescription</strong>.
            This links seniors to:
          </p>
          <ul class="list-check" style="margin-top:0.5rem;">
            <li>Volunteer home visits and friendly check-ins</li>
            <li>Recreation, arts, and fitness programs at local facilities</li>
            <li>Faith-based and cultural activities</li>
            <li>Neighbourhood groups, walking clubs, and peer support</li>
          </ul>
          <p style="margin-top:0.6rem;">
            A dedicated <strong>Link Worker / Connection Crew</strong> helps each
            senior navigate options, enroll in programs, and overcome practical
            barriers like forms, transport, and confidence.
          </p>
        </div>

        <div class="card">
          <h3 class="card-title">Pilot goals &amp; objectives</h3>
          <ul class="list-check">
            <li>Reduce social isolation and loneliness among ~260 seniors in Shelburne</li>
            <li>Improve mental well-being and quality of life</li>
            <li>Strengthen trust and coordination between health and community sectors</li>
            <li>Reduce preventable healthcare use related to isolation</li>
            <li>Develop a scalable model for other rural Ontario communities</li>
          </ul>
          <div class="budget-strip">
            <div>⏱ <strong>Duration:</strong> 12-month pilot (Jan–Dec 2026)</div>
            <div class="budget-chip">Target: 30% reduction in loneliness scores</div>
            <div class="budget-chip">Mixed-methods evaluation (quant + qual)</div>
          </div>
        </div>
      </div>

      <div style="margin-top:2rem;" class="grid-2">
        <div class="card">
          <h3 class="card-title">Key activities (high level timeline)</h3>
          <ul class="list-check">
            <li><strong>Jan–Mar:</strong> Planning, stakeholder engagement, recruitment</li>
            <li><strong>Feb–Apr:</strong> Volunteer training &amp; community mapping</li>
            <li><strong>Apr–Jun:</strong> Door-to-door outreach in pilot areas</li>
            <li><strong>Jun–Sep:</strong> Expanded outreach &amp; referrals to programs</li>
            <li><strong>May–Jul:</strong> Community events &amp; workshops</li>
            <li><strong>Jul–Oct:</strong> Follow-up visits and participant support</li>
            <li><strong>Aug–Oct:</strong> Data collection and evaluation</li>
            <li><strong>Oct–Dec:</strong> Final reporting &amp; sustainability planning</li>
          </ul>
        </div>

        <div class="card">
          <h3 class="card-title">Human resources model</h3>
          <p>
            The pilot uses a blended HR model grounded in the
            <strong>Harvard Human Resource Management framework</strong> —
            emphasizing engagement, equity, and long-term organizational outcomes.
          </p>
          <ul class="list-check" style="margin-top:0.5rem;">
            <li>Part-time Project Manager (0.25 FTE, 10 hrs/week)</li>
            <li>Volunteer connection crew and drivers</li>
            <li>Healthcare partners (family physicians, NPs, social workers)</li>
            <li>Training on geriatric care, mental health, PHIPA &amp; privacy</li>
          </ul>
          <p style="margin-top:0.5rem;">
            Employee and volunteer satisfaction are monitored through regular
            feedback and performance reviews to sustain quality and engagement.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- STAKEHOLDERS & PARTNERS -->
  <section id="stakeholders">
    <div class="container">
      <div class="section-header">
        <div>
          <div class="section-label">Partners &amp; Governance</div>
          <h2 class="section-title">Who is involved in the Shelburne pilot?</h2>
        </div>
        <p class="section-subtitle">
          The project is intentionally collaborative, bringing together health, social
          services, municipal leaders, community organizations, and volunteers to
          build a more connected community for seniors.
        </p>
      </div>

      <div class="stakeholder-grid">
        <div>
          <h4>Project &amp; implementation leads</h4>
          <p>
            <strong>Luma Care Community</strong> – Volunteer coordination, navigation,
            and service linkages.<br />
            <strong>Project Manager</strong> – Day-to-day operations, reporting, and
            stakeholder communication.
          </p>
        </div>
        <div>
          <h4>Health system partners</h4>
          <p>
            <strong>Headwaters Health Care Centre</strong> &amp; Hills of Headwaters
            Ontario Health Team – Identify at-risk seniors, issue social prescriptions,
            share evaluation data, and support clinical-community integration.
          </p>
        </div>
        <div>
          <h4>Municipal &amp; community services</h4>
          <p>
            <strong>Town of Shelburne</strong> – Venues, outreach channels,
            transportation support.<br />
            <strong>Dufferin County Community Support Services</strong> – Transport,
            meals, day programs and friendly visiting.
          </p>
        </div>
        <div>
          <h4>Long-term care &amp; housing</h4>
          <p>
            <strong>Dufferin Oaks LTC</strong>, Shelburne Residence, Shelburne Long-Term
            Care &amp; Retirement Community – Identify isolated residents, support
            outreach and referrals.
          </p>
        </div>
        <div>
          <h4>Recreation &amp; social spaces</h4>
          <p>
            <strong>Centre Dufferin Recreation Complex</strong> – Space for fitness,
            arts, and social programs.<br />
            <strong>Shelburne Public Library</strong> – Reading circles, creative
            activities, and program promotion.
          </p>
        </div>
        <div>
          <h4>Families, faith groups &amp; civic partners</h4>
          <p>
            Seniors &amp; caregivers, Dufferin Oaks Family Council, Rotary Club of
            Shelburne, Grace Church of the Nazarene and other faith communities –
            support outreach, host events, and build community trust.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- BUDGET -->
  <section id="budget">
    <div class="container">
      <div class="section-header">
        <div>
          <div class="section-label">Budget</div>
          <h2 class="section-title">Funding the pilot responsibly</h2>
        </div>
        <p class="section-subtitle">
          The total budget for the 12-month pilot is <strong>CAD $45,000</strong>,
          combining municipal grants, healthcare funding, private sponsorship, and
          significant in-kind contributions.
        </p>
      </div>

      <div class="grid-2">
        <div class="card">
          <h3 class="card-title">Revenue sources (cash)</h3>
          <ul class="list-check">
            <li><strong>$20,000</strong> – Town of Shelburne corporate grant</li>
            <li><strong>$15,000</strong> – Fiddleville (Shelburne) Non-Profit Housing Corp.</li>
            <li><strong>$10,000</strong> – Hills of Headwaters Collaborative Ontario Health Team</li>
          </ul>
          <p style="margin-top:0.7rem;">
            In addition, multiple partners (long-term care homes, community support
            services, library, churches, recreation complex, etc.) contribute
            <strong>in-kind</strong> support such as staff time, space, transport,
            program materials, and logistics.
          </p>
        </div>

        <div class="card">
          <h3 class="card-title">Major expense categories</h3>
          <ul class="list-check">
            <li>Human resources (Project Manager salary, benefits &amp; payroll taxes)</li>
            <li>Volunteer recruitment, onboarding &amp; training workshops</li>
            <li>Tablets/phones for field data collection and secure referrals</li>
            <li>Transportation &amp; logistics for outreach and participation</li>
            <li>Program materials, wellness kits, and community events</li>
            <li>Communications, promotion, and administrative supplies</li>
            <li>Evaluation &amp; reporting tools</li>
            <li>5% contingency for unexpected needs and cost pressures</li>
          </ul>
          <p style="margin-top:0.6rem;">
            The budget is designed to be transparent, equitable, and replicable for
            other rural communities.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- OUTCOMES & EVALUATION -->
  <section id="outcomes">
    <div class="container">
      <div class="section-header">
        <div>
          <div class="section-label">Outcomes &amp; Quality</div>
          <h2 class="section-title">How success will be measured</h2>
        </div>
        <p class="section-subtitle">
          The pilot uses a quality and risk framework aligned with WHO’s dimensions
          of care and Enterprise Risk Management (ERM) to ensure that services are
          safe, effective, equitable, and sustainable.
        </p>
      </div>

      <div class="kpi-grid">
        <div class="kpi">
          <span class="label">Loneliness &amp; well-being</span>
          <strong>30% reduction</strong>
          <p>
            Target reduction in loneliness scores after 12 months, measured using
            validated tools such as the UCLA Loneliness Scale and WHO-5 Well-Being
            Index.
          </p>
        </div>
        <div class="kpi">
          <span class="label">Healthcare utilization</span>
          <strong>Fewer avoidable visits</strong>
          <p>
            Decreased ED visits and hospital admissions linked to social isolation
            (with an average hospital stay estimated at ~$7,500).
          </p>
        </div>
        <div class="kpi">
          <span class="label">Engagement &amp; trust</span>
          <strong>Stronger community ties</strong>
          <p>
            Increased participation in community programs, improved trust in local
            care systems, and stronger collaboration across agencies.
          </p>
        </div>
      </div>

      <div class="card" style="margin-top:1.7rem;">
        <h3 class="card-title">Evaluation approach</h3>
        <p>
          A mixed-methods evaluation will be conducted at three time-points:
          baseline (Month 0), mid-term (Month 6), and end-of-pilot (Month 12).
        </p>
        <ul class="list-check" style="margin-top:0.6rem;">
          <li>Standardized scales for loneliness and mental well-being</li>
          <li>Tracking referrals, home visits, participation, and follow-up</li>
          <li>Interviews and focus groups with seniors, caregivers, and partners</li>
          <li>Quality indicators aligned with WHO’s six domains of care</li>
          <li>Risk identification and mitigation across ERM domains</li>
        </ul>
      </div>

      <div class="cta-band">
        <div>
          <h3>Scaling beyond Shelburne</h3>
          <p>
            The Shelburne pilot is designed as a <strong>blueprint</strong> for rural
            and small-town communities across Ontario. By documenting what works —
            and why — the project will support other municipalities to adapt social
            prescribing to their own local context.
          </p>
        </div>
        <div class="cta-side">
          <p>
            Interested in adapting this model in your community or organization?
            Use the contact form below to connect with the project team or request a
            copy of the full capstone report and implementation tools.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT / GET INVOLVED -->
  <section id="contact">
    <div class="container">
      <div class="section-header">
        <div>
          <div class="section-label">Get Involved</div>
          <h2 class="section-title">Partner, volunteer, or learn more</h2>
        </div>
        <p class="section-subtitle">
          This website is an informational overview of the Rx: Community Social
          Prescribing Pilot in Shelburne, ON. Use this section to share real contact
          details, referral pathways, or volunteer sign-up information.
        </p>
      </div>

      <div class="contact-grid">
        <div>
          <div class="card">
            <h3 class="card-title">Ways you can support</h3>
            <ul class="list-check">
              <li>Refer socially isolated seniors who might benefit from the pilot</li>
              <li>Volunteer as a driver, connection crew member, or event helper</li>
              <li>Offer in-kind space, materials, or program expertise</li>
              <li>Collaborate on evaluation, research, or future scaling</li>
            </ul>
          </div>

          <div style="margin-top:1rem;" class="card">
            <h3 class="card-title">Capstone project team</h3>
            <p class="card-meta">
              Health Care Administration &amp; Service Management (HCASM) · Conestoga College
            </p>
            <p>
              Project lead: <strong>Segun Michael Olanipekun</strong><br />
              Team members:
              <strong>Saiduraya</strong>,
              <strong>Chioma</strong>,
              <strong>Pamela</strong>,
              <strong>Elizbeth</strong>,
              <strong>Jennifer</strong>,
              <strong>Yvvone</strong>,
              <strong>Diana</strong>,
              <strong>Neel</strong>.
            </p>
            <p style="margin-top:0.8rem;">
              Supervised by:
              <strong>Professor Erin Gilbert</strong>
            </p>
            <p style="margin-top:0.6rem; font-size:0.86rem;">
              You may include student numbers, campus, or course code here if needed for submission.
            </p>
          </div>

          <div style="margin-top:1rem;">
            <p class="info-line">
              📍 <strong>Location:</strong> Shelburne, Dufferin County, Ontario
            </p>
            <p class="info-line">
              ℹ️ Replace the placeholders here with real project contact information
              (email, phone, website, social media) when you’re ready to publish.
            </p>
          </div>
        </div>

        <div class="card">
          <h3 class="card-title">Contact form (demo)</h3>
          <p class="card-meta">
            This form is front-end only. Connect it to a service like Formspree,
            Netlify Forms, or your own backend to receive submissions.
          </p>
          <form onsubmit="event.preventDefault(); alert('Demo only – connect to a backend to receive messages.');">
            <div>
              <label for="name">Name</label>
              <input id="name" type="text" placeholder="Your full name" />
            </div>
            <div>
              <label for="email">Email</label>
              <input id="email" type="email" placeholder="you@example.com" />
            </div>
            <div>
              <label for="role">I am a...</label>
              <input id="role" type="text" placeholder="e.g., Senior, caregiver, partner, volunteer" />
            </div>
            <div>
              <label for="message">Message</label>
              <textarea id="message" rows="4" placeholder="How would you like to be involved?"></textarea>
            </div>
            <button type="submit" class="btn-primary" style="margin-top:0.3rem;">
              Send Message
            </button>
          </form>
        </div>
      </div>

      <div style="margin-top:2.5rem;" class="card">
        <h3 class="card-title">References &amp; full report</h3>
        <p class="card-meta">
          This website summarizes key elements of the full capstone report:
          <em>“Reducing Social Isolation Among Seniors Through Rx: Community Social Prescribing Pilot in Shelburne, ON.”</em>
        </p>
        <p>
          You can use this section to link to:
        </p>
        <ul class="list-check" style="margin-top:0.5rem;">
          <li>A downloadable PDF of the full report</li>
          <li>Selected tools (Gantt chart, budget table, logic model, HR plan)</li>
          <li>External resources such as Statistics Canada, Government of Canada, WHO, and Alliance for Healthier Communities</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    © <span id="year"></span> Rx: Community Social Prescribing Pilot – Shelburne, ON.
    Capstone project by Segun Michael Olanipekun &amp; team · Conestoga College.
  </footer>

  <script>
    // Mobile nav toggle
    const menuBtn = document.getElementById("menuBtn");
    const navList = document.getElementById("navList");
    menuBtn.addEventListener("click", () => {
      navList.classList.toggle("open");
    });

    // Dynamic year
    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
