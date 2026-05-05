<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>My Portfolio | Fresher Web Developer</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />

  <!-- Google Font -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link
    href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap"
    rel="stylesheet"
  />

  <style>
    :root {
      --bg: #f4f5fb;
      --card-bg: #ffffff;
      --primary: #2563eb;
      --primary-soft: rgba(37, 99, 235, 0.08);
      --text: #0f172a;
      --muted: #6b7280;
      --border: #e5e7eb;
      --shadow-soft: 0 18px 45px rgba(15, 23, 42, 0.08);
      --radius-xl: 1.5rem;
      --transition-fast: 180ms ease-out;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      font-family: "Poppins", sans-serif;
      background: radial-gradient(circle at top, #e0ebff 0, #f4f5fb 45%, #f9fafb 100%);
      color: var(--text);
      line-height: 1.6;
    }

    /* Layout */
    .page {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    .max-w {
      max-width: 1100px;
      margin: 0 auto;
      padding: 1.5rem 1.25rem 3rem;
    }

    /* Navbar */
    header {
      position: sticky;
      top: 0;
      z-index: 20;
      backdrop-filter: blur(14px);
      background: linear-gradient(
        to bottom,
        rgba(244, 245, 251, 0.92),
        rgba(244, 245, 251, 0.75),
        transparent
      );
      border-bottom: 1px solid rgba(229, 231, 235, 0.7);
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1.5rem;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .brand-mark {
      width: 34px;
      height: 34px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 20%, #60a5fa, #2563eb);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #eff6ff;
      font-weight: 700;
      font-size: 1.05rem;
      box-shadow: 0 10px 25px rgba(37, 99, 235, 0.5);
    }

    .brand-text {
      font-weight: 600;
      letter-spacing: 0.03em;
      font-size: 0.95rem;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 1.2rem;
      font-size: 0.9rem;
    }

    .nav-links a {
      text-decoration: none;
      color: var(--muted);
      position: relative;
      padding-bottom: 0.1rem;
      transition: color var(--transition-fast);
    }

    .nav-links a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: -0.25rem;
      width: 0%;
      height: 2px;
      border-radius: 999px;
      background: var(--primary);
      transition: width var(--transition-fast);
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .nav-links a:hover::after {
      width: 100%;
    }

    .nav-cta {
      padding: 0.4rem 0.9rem;
      border-radius: 999px;
      border: 1px solid rgba(37, 99, 235, 0.25);
      font-size: 0.85rem;
      text-decoration: none;
      color: var(--primary);
      background: rgba(255, 255, 255, 0.7);
      backdrop-filter: blur(16px);
      box-shadow: 0 12px 25px rgba(37, 99, 235, 0.15);
      transition: transform var(--transition-fast),
        box-shadow var(--transition-fast),
        background var(--transition-fast);
    }

    .nav-cta:hover {
      transform: translateY(-1px);
      background: #eff6ff;
      box-shadow: 0 18px 35px rgba(37, 99, 235, 0.35);
    }

    /* Hero */
    .hero {
      display: grid;
      grid-template-columns: minmax(0, 1.2fr) minmax(0, 1fr);
      gap: 3rem;
      padding-top: 3rem;
      padding-bottom: 3rem;
      align-items: center;
    }

    .hero-left {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      padding: 0.25rem 0.7rem;
      border-radius: 999px;
      border: 1px solid rgba(37, 99, 235, 0.18);
      background: rgba(255, 255, 255, 0.9);
      font-size: 0.75rem;
      color: var(--muted);
    }

    .badge-dot {
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: #22c55e;
      box-shadow: 0 0 0 5px rgba(34, 197, 94, 0.25);
    }

    .hero-title {
      font-size: clamp(2.1rem, 4vw, 2.8rem);
      line-height: 1.2;
      letter-spacing: -0.03em;
    }

    .hero-title span {
      background: linear-gradient(120deg, #2563eb, #7c3aed);
      -webkit-background-clip: text;
      color: transparent;
    }

    .hero-subtitle {
      font-size: 0.95rem;
      color: var(--muted);
      max-width: 32rem;
    }

    .hero-subtitle b {
      color: var(--text);
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 0.75rem;
      margin-top: 0.75rem;
    }

    .btn-primary,
    .btn-ghost {
      border-radius: 999px;
      padding: 0.65rem 1.4rem;
      font-size: 0.9rem;
      font-weight: 500;
      border: none;
      cursor: pointer;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      transition: transform var(--transition-fast),
        box-shadow var(--transition-fast),
        background var(--transition-fast),
        color var(--transition-fast);
    }

    .btn-primary {
      background: linear-gradient(135deg, #2563eb, #1d4ed8);
      color: #f9fafb;
      box-shadow: 0 22px 45px rgba(37, 99, 235, 0.6);
    }

    .btn-primary:hover {
      transform: translateY(-1px) translateX(1px);
      box-shadow: 0 22px 55px rgba(37, 99, 235, 0.8);
    }

    .btn-ghost {
      background: rgba(255, 255, 255, 0.8);
      color: var(--text);
      border: 1px solid rgba(148, 163, 184, 0.6);
    }

    .btn-ghost:hover {
      background: #e5edff;
      border-color: #2563eb;
    }

    .hero-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      font-size: 0.8rem;
      color: var(--muted);
      margin-top: 0.8rem;
    }

    .hero-meta span b {
      display: block;
      font-size: 0.95rem;
      color: var(--text);
    }

    .hero-right {
      display: flex;
      justify-content: center;
    }

    .hero-card {
      width: 100%;
      max-width: 320px;
      padding: 1.3rem 1.3rem 1.5rem;
      border-radius: 1.7rem;
      background: linear-gradient(160deg, #0f172a, #111827);
      color: #f9fafb;
      box-shadow: var(--shadow-soft);
      position: relative;
      overflow: hidden;
    }

    .hero-card::before {
      content: "";
      position: absolute;
      width: 180px;
      height: 180px;
      border-radius: 999px;
      background: radial-gradient(circle at 20% 0, rgba(96, 165, 250, 0.8), transparent);
      top: -40px;
      left: -60px;
      opacity: 0.6;
    }

    .hero-card::after {
      content: "";
      position: absolute;
      width: 160px;
      height: 160px;
      border-radius: 999px;
      background: radial-gradient(circle at 90% 100%, rgba(129, 140, 248, 0.9), transparent);
      bottom: -60px;
      right: -40px;
      opacity: 0.75;
    }

    .hero-card-inner {
      position: relative;
      z-index: 2;
    }

    .tag-chip {
      display: inline-flex;
      padding: 0.2rem 0.6rem;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.6);
      border: 1px solid rgba(148, 163, 184, 0.5);
      font-size: 0.7rem;
      margin-bottom: 0.7rem;
    }

    .hero-name {
      font-size: 1.15rem;
      font-weight: 600;
      margin-bottom: 0.2rem;
    }

    .hero-role {
      font-size: 0.8rem;
      color: #cbd5f5;
      margin-bottom: 0.7rem;
    }

    .hero-summary {
      font-size: 0.78rem;
      color: #e5e7eb;
    }

    .skill-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
      margin: 1rem 0;
    }

    .pill {
      font-size: 0.7rem;
      padding: 0.2rem 0.6rem;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.7);
      border: 1px solid rgba(148, 163, 184, 0.5);
    }

    .stack-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 0.4rem;
      font-size: 0.7rem;
      margin-top: 0.4rem;
    }

    .stack-item span:first-child {
      color: #9ca3af;
    }

    .stack-item span:last-child {
      color: #e5e7eb;
      font-weight: 500;
    }

    /* Sections */
    section {
      margin-top: 2.5rem;
    }

    .section-header {
      display: flex;
      align-items: baseline;
      justify-content: space-between;
      margin-bottom: 1rem;
      gap: 1rem;
    }

    .section-title {
      font-size: 1.1rem;
      font-weight: 600;
      letter-spacing: -0.02em;
    }

    .section-subtitle {
      font-size: 0.8rem;
      color: var(--muted);
    }

    /* About */
    .about-card {
      background: rgba(255, 255, 255, 0.96);
      border-radius: var(--radius-xl);
      padding: 1.4rem 1.5rem;
      border: 1px solid var(--border);
      box-shadow: var(--shadow-soft);
      display: grid;
      grid-template-columns: minmax(0, 2.2fr) minmax(0, 1.5fr);
      gap: 1.5rem;
    }

    .about-text {
      font-size: 0.9rem;
      color: var(--muted);
    }

    .about-text b {
      color: var(--text);
    }

    .about-meta {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 0.8rem;
      font-size: 0.78rem;
    }

    .about-meta-item {
      padding: 0.7rem 0.8rem;
      border-radius: 1rem;
      background: var(--primary-soft);
      border: 1px dashed rgba(37, 99, 235, 0.38);
    }

    .about-meta-item b {
      display: block;
      font-size: 0.78rem;
      color: var(--primary);
      margin-bottom: 0.1rem;
    }

    /* Skills */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1rem;
      font-size: 0.8rem;
    }

    .skill-card {
      background: rgba(255, 255, 255, 0.96);
      border-radius: 1.2rem;
      padding: 0.9rem 1rem;
      border: 1px solid var(--border);
      box-shadow: 0 14px 30px rgba(148, 163, 184, 0.18);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast),
        border-color var(--transition-fast);
    }

    .skill-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 20px 45px rgba(148, 163, 184, 0.32);
      border-color: rgba(37, 99, 235, 0.5);
    }

    .skill-card h3 {
      font-size: 0.88rem;
      margin-bottom: 0.3rem;
    }

    .skill-list {
      list-style: none;
      margin-top: 0.2rem;
    }

    .skill-list li {
      position: relative;
      padding-left: 0.9rem;
      margin: 0.08rem 0;
    }

    .skill-list li::before {
      content: "•";
      position: absolute;
      left: 0.25rem;
      top: 0;
      color: var(--primary);
    }

    /* Projects */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1.1rem;
    }

    .project-card {
      background: rgba(255, 255, 255, 0.98);
      border-radius: 1.2rem;
      padding: 1rem 1rem 1.1rem;
      border: 1px solid var(--border);
      box-shadow: 0 14px 34px rgba(148, 163, 184, 0.2);
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
      transition: transform var(--transition-fast), box-shadow var(--transition-fast),
        border-color var(--transition-fast);
    }

    .project-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 22px 50px rgba(148, 163, 184, 0.35);
      border-color: rgba(37, 99, 235, 0.55);
    }

    .project-tag {
      font-size: 0.7rem;
      color: var(--muted);
    }

    .project-title {
      font-size: 0.95rem;
      font-weight: 600;
    }

    .project-desc {
      font-size: 0.8rem;
      color: var(--muted);
    }

    .project-tech {
      font-size: 0.75rem;
      margin-top: 0.25rem;
    }

    .project-tech span {
      background: var(--primary-soft);
      color: var(--primary);
      border-radius: 999px;
      padding: 0.12rem 0.55rem;
      margin-right: 0.25rem;
      font-size: 0.72rem;
    }

    .project-links {
      margin-top: 0.55rem;
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
      font-size: 0.8rem;
    }

    .project-links a {
      text-decoration: none;
      color: var(--primary);
      padding-bottom: 0.04rem;
      border-bottom: 1px dashed rgba(37, 99, 235, 0.6);
    }

    /* Education / Experience */
    .two-col-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 1.3rem;
    }

    .timeline-card {
      background: rgba(255, 255, 255, 0.98);
      border-radius: 1.2rem;
      padding: 1rem 1.1rem;
      border: 1px solid var(--border);
      box-shadow: 0 14px 30px rgba(148, 163, 184, 0.2);
      font-size: 0.8rem;
    }

    .timeline-item + .timeline-item {
      margin-top: 0.7rem;
      padding-top: 0.6rem;
      border-top: 1px dashed rgba(148, 163, 184, 0.8);
    }

    .timeline-title {
      font-weight: 600;
      font-size: 0.86rem;
    }

    .timeline-meta {
      font-size: 0.75rem;
      color: var(--muted);
      margin-bottom: 0.25rem;
    }

    /* Contact */
    .contact-card {
      margin-top: 1rem;
      background: rgba(15, 23, 42, 0.98);
      color: #e5e7eb;
      border-radius: 1.6rem;
      padding: 1.5rem 1.6rem;
      display: grid;
      grid-template-columns: minmax(0, 1.6fr) minmax(0, 1.4fr);
      gap: 1.6rem;
      box-shadow: 0 24px 65px rgba(15, 23, 42, 0.9);
      position: relative;
      overflow: hidden;
    }

    .contact-card::after {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at top left, rgba(37, 99, 235, 0.4), transparent),
        radial-gradient(circle at bottom right, rgba(129, 140, 248, 0.4), transparent);
      opacity: 0.8;
      mix-blend-mode: soft-light;
      pointer-events: none;
    }

    .contact-main,
    .contact-form {
      position: relative;
      z-index: 2;
    }

    .contact-main h3 {
      font-size: 1rem;
      margin-bottom: 0.5rem;
    }

    .contact-main p {
      font-size: 0.85rem;
      color: #cbd5f5;
      margin-bottom: 0.9rem;
    }

    .contact-list {
      list-style: none;
      font-size: 0.8rem;
      display: flex;
      flex-direction: column;
      gap: 0.3rem;
    }

    .contact-list span {
      color: #e5e7eb;
    }

    .social-links {
      margin-top: 0.7rem;
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      font-size: 0.8rem;
    }

    .social-links a {
      text-decoration: none;
      color: #e5e7eb;
      border-bottom: 1px dashed rgba(191, 219, 254, 0.7);
    }

    .contact-form {
      background: rgba(15, 23, 42, 0.9);
      border-radius: 1.3rem;
      padding: 1rem 1.1rem 1.1rem;
      border: 1px solid rgba(148, 163, 184, 0.7);
      font-size: 0.8rem;
    }

    .form-row {
      display: flex;
      flex-direction: column;
      gap: 0.3rem;
      margin-bottom: 0.6rem;
    }

    .form-row label {
      font-size: 0.78rem;
      color: #cbd5f5;
    }

    .form-row input,
    .form-row textarea {
      padding: 0.45rem 0.65rem;
      border-radius: 0.65rem;
      border: 1px solid rgba(148, 163, 184, 0.75);
      background: rgba(17, 24, 39, 0.9);
      color: #e5e7eb;
      font-family: inherit;
      font-size: 0.8rem;
      outline: none;
      transition: border-color var(--transition-fast), box-shadow var(--transition-fast),
        background var(--transition-fast);
    }

    .form-row input:focus,
    .form-row textarea:focus {
      border-color: #60a5fa;
      box-shadow: 0 0 0 1px rgba(96, 165, 250, 0.8);
      background: rgba(15, 23, 42, 0.9);
    }

    .form-row textarea {
      min-height: 80px;
      resize: vertical;
    }

    .btn-form {
      width: 100%;
      margin-top: 0.2rem;
      border-radius: 999px;
      border: none;
      padding: 0.55rem;
      font-size: 0.82rem;
      font-weight: 500;
      cursor: pointer;
      background: linear-gradient(135deg, #2563eb, #4f46e5);
      color: #f9fafb;
      box-shadow: 0 14px 40px rgba(37, 99, 235, 0.7);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast);
    }

    .btn-form:hover {
      transform: translateY(-1px);
      box-shadow: 0 20px 55px rgba(37, 99, 235, 0.85);
    }

    /* Footer */
    footer {
      margin-top: 2.5rem;
      padding-top: 1.4rem;
      border-top: 1px solid var(--border);
      font-size: 0.75rem;
      color: var(--muted);
      display: flex;
      justify-content: space-between;
      gap: 1rem;
      flex-wrap: wrap;
    }

    /* Responsive */
    @media (max-width: 900px) {
      .hero {
        grid-template-columns: minmax(0, 1fr);
      }

      .hero-right {
        order: -1;
      }

      .about-card {
        grid-template-columns: minmax(0, 1fr);
      }

      .skills-grid,
      .projects-grid,
      .two-col-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }

      .contact-card {
        grid-template-columns: minmax(0, 1fr);
      }
    }

    @media (max-width: 640px) {
      .nav-links {
        display: none;
      }

      .max-w {
        padding-inline: 1rem;
      }

      .hero {
        padding-top: 2.2rem;
        gap: 2rem;
      }

      .skills-grid,
      .projects-grid,
      .two-col-grid {
        grid-template-columns: minmax(0, 1fr);
      }

      .about-card {
        padding: 1.1rem 1.1rem;
      }

      .contact-card {
        padding: 1.15rem 1.1rem;
      }

      .hero-card {
        max-width: 100%;
      }
    }
  </style>
</head>
<body>
  <div class="page">
    <!-- NAVBAR -->
    <header>
      <div class="max-w nav">
        <div class="brand">
          <div class="brand-mark">A</div>
          <div class="brand-text">Fresher Web Developer</div>
        </div>
        <nav class="nav-links">
          <a href="#about">About</a>
          <a href="#skills">Skills</a>
          <a href="#projects">Projects</a>
          <a href="#contact">Contact</a>
        </nav>
        <a
          href="#contact"
          class="nav-cta"
        >
          Hire Me
        </a>
      </div>
    </header>

    <main class="max-w">
      <!-- HERO -->
      <section class="hero">
        <div class="hero-left">
          <div class="badge">
            <div class="badge-dot"></div>
            Open to work · Fresher
          </div>
          <h1 class="hero-title">
            Hi, I’m <span>A.V.Govardhan Reddy</span><br />
            Full-Stack Web Developer
          </h1>
          <p class="hero-subtitle">
            I’m a fresher web developer who has built <b>multiple modern web designs</b> and
            knows how to connect the <b>front end with the back end</b> using
            <b>Spring Boot</b> and <b>REST APIs</b>. I love turning ideas into clean and
            responsive web applications.
          </p>

          <div class="hero-actions">
            <a href="https://1drv.ms/b/c/b6ef8cd3d8890958/IQBCh06LLfOPSIEvZ9Ao1gDWAWRIXG8cdiHjzwBj4Ossj_A?e=7N9Cfx" class="btn-primary" target="_blank">
              Download Resume
            </a>
            <a href="#projects" class="btn-ghost">
              View My Projects
            </a>
          </div>

          <div class="hero-meta">
            <span><b>Tech Stack</b> HTML, CSS, JS, Spring Boot, REST APIs</span>
            <span><b>Location</b> India · Ready for relocation</span>
          </div>
        </div>

        <div class="hero-right">
          <div class="hero-card">
            <div class="hero-card-inner">
              <div class="tag-chip">Portfolio Snapshot</div>
              <div class="hero-name">A.V. Govardhan Reddy</div>
              <div class="hero-role">Fresher · Full-Stack Web Developer</div>
              <p class="hero-summary">
                Focused on building clean, responsive UIs and connecting them to robust
                backends using Spring Boot & REST APIs.
              </p>

              <div class="skill-pills">
                <div class="pill">Responsive UI</div>
                <div class="pill">REST APIs</div>
                <div class="pill">Spring Boot</div>
                <div class="pill">SQL</div>
              </div>

              <div class="stack-grid">
                <div class="stack-item">
                  <span>Frontend</span><br />
                  <span>HTML · CSS · JS</span>
                </div>
                <div class="stack-item">
                  <span>Backend</span><br />
                  <span>Java · Spring Boot</span>
                </div>
                <div class="stack-item">
                  <span>APIs</span><br />
                  <span>REST · JSON</span>
                </div>
                <div class="stack-item">
                  <span>Database</span><br />
                  <span>MySQL / PostgreSQL</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- ABOUT -->
      <section id="about">
        <div class="section-header">
          <h2 class="section-title">About Me</h2>
          <p class="section-subtitle">Who I am and what I do</p>
        </div>

        <div class="about-card">
          <div class="about-text">
            <p>
              I’m a <b>fresher web developer</b> passionate about building user-friendly,
              responsive and modern websites. I have created multiple web designs from
              scratch and learned how to connect the <b>front end</b> with
              <b>back-end services</b> using <b>Spring Boot</b> and <b>REST APIs</b>.
            </p>
            <br />
            <p>
              I like writing clean and readable code, following proper folder structure and
              thinking about the user experience first. I’m actively looking for an
              opportunity where I can <b>learn from a team</b>, contribute to real projects
              and grow as a full-stack developer.
            </p>
          </div>

          <div class="about-meta">
            <div class="about-meta-item">
              <b>What I bring</b>
              Good understanding of web fundamentals, eagerness to learn and the ability to
              quickly pick up new technologies.
            </div>
            <div class="about-meta-item">
              <b>My goals</b>
              To work on real-time applications, APIs and scalable backends while improving
              my UI/UX and problem-solving skills.
            </div>
            <div class="about-meta-item">
              <b>Work style</b>
              Organized, consistent, and comfortable working with Git, small teams and
              task-based workflows.
            </div>
            <div class="about-meta-item">
              <b>Current focus</b>
              Spring Boot projects, REST API integration, database design and improving
              frontend animations and interactions.
            </div>
          </div>
        </div>
      </section>

      <!-- SKILLS -->
      <section id="skills">
        <div class="section-header">
          <h2 class="section-title">Skills</h2>
          <p class="section-subtitle">Technologies I’ve worked with</p>
        </div>

        <div class="skills-grid">
          <div class="skill-card">
            <h3>Frontend</h3>
            <ul class="skill-list">
              <li>HTML5, semantic structure</li>
              <li>Modern CSS (Flexbox, Grid)</li>
              <li>Responsive layouts for mobile & desktop</li>
              <li>Basic JavaScript interactivity</li>
              <li>Word Press</li>
              <li>Wix</li>
               
            </ul>
          </div>

          <div class="skill-card">
            <h3>Backend & APIs</h3>
            <ul class="skill-list">
              <li>Java · Spring Boot framework</li>
              <li>REST API design & integration</li>
              
              <li>Connecting UI forms to API endpoints</li>
            </ul>
          </div>

          <div class="skill-card">
            <h3>Database</h3>
            <ul class="skill-list">
              <li>MySQL / PostgreSQL basics</li>
              <li>CRUD operations</li>
              <li>Simple joins and filters</li>
              <li>Connecting DB with Spring Boot</li>
            </ul>
          </div>

          <div class="skill-card">
            <h3>Tools & Workflow</h3>
            <ul class="skill-list">
              <li>Git & GitHub (basic)</li>
              <li>Maven / Gradle (as needed)</li>
              <li>Postman for testing APIs</li>
              <li>VS Code / IntelliJ IDE</li>
            </ul>
          </div>

          <div class="skill-card">
            <h3>Soft Skills</h3>
            <ul class="skill-list">
              <li>Quick learner and self-motivated</li>
              <li>Good communication skills</li>
              <li>Comfortable working in teams</li>
              <li>Time management & ownership</li>
            </ul>
          </div>

          <div class="skill-card">
            <h3>Currently Learning</h3>
            <ul class="skill-list">
              <li>Advanced JavaScript & React</li>
              <li>Better project structuring</li>
              <li>Error handling and logging</li>
              <li>Basic deployment & hosting</li>
            </ul>
          </div>
        </div>
      </section>

     
      <section id="projects">
        <div class="section-header">
          <h2 class="section-title">Projects</h2>
          <p class="section-subtitle">Some of the work I’ve done</p>
        </div>

        <div class="projects-grid">
          
          <article class="project-card">
            <div class="project-tag">Full-Stack · Spring Boot · REST API</div>
            <h3 class="project-title">Online Student Management System</h3>
            <p class="project-desc">
              A web application to manage students, courses and admissions. Frontend sends
              data through forms and calls backend APIs built with Spring Boot.
            </p>
            <div class="project-tech">
              <span>HTML</span>
              <span>CSS</span>
              <span>JavaScript</span>
              <span>Spring Boot</span>
              <span>REST</span>
              <span>MySQL</span>
            </div>
            <div class="project-links">
              <a href="https://github.com/avgovardhan1" target="_blank">View Live</a>
              <a href="https://github.com/avgovardhan1" target="_blank">Source Code</a>
            </div>
          </article>

          <article class="project-card">
            <div class="project-tag">Frontend · Responsive Design</div>
            <h3 class="project-title">Modern Landing Page Collection</h3>
            <p class="project-desc">
              A set of modern, responsive landing pages created to practice layouts,
              animations and clean UI for products and services.
            </p>
            <div class="project-tech">
              <span>HTML</span>
              <span>CSS</span>
              <span>Flexbox</span>
              <span>Grid</span>
            </div>
            <div class="project-links">
              <a href="https://github.com/avgovardhan1" target="_blank">View Designs</a>
              <a href="https://github.com/avgovardhan1" target="_blank">GitHub Repo</a>
            </div>
          </article>

          
          <article class="project-card">
            <div class="project-tag">API Integration · JSON</div>
            <h3 class="project-title">REST API Demo Dashboard</h3>
            <p class="project-desc">
              A simple dashboard UI that consumes sample REST APIs and displays data in a
              clean, card-based interface with basic filters.
            </p>
            <div class="project-tech">
              <span>HTML</span>
              <span>CSS</span>
              <span>JavaScript</span>
              <span>REST API</span>
            </div>
            <div class="project-links">
              <a href="#" target="_blank">Live Demo</a>
              <a href="#" target="_blank">Source Code</a>
            </div>
          </article>
        </div>
      </section>

      <!-- EDUCATION & EXTRA -->
      <section>
        <div class="section-header">
          <h2 class="section-title">Education & Highlights</h2>
          <p class="section-subtitle">Background and achievements</p>
        </div>

        <div class="two-col-grid">
          <div class="timeline-card">
            <h3 style="font-size:0.9rem; margin-bottom:0.5rem;">Education</h3>
            <div class="timeline-item">
              <div class="timeline-title">Bachelor’s Degree</div>
              <div class="timeline-meta">NRI INISTITUTE OF TECHNOLOGY · 2025</div>
              <p>
                Completed my degree with focus on programming, databases and basic software
                engineering concepts.
              </p>
            </div>
            <div class="timeline-item">
              <div class="timeline-title">Certifications / Courses</div>
              <div class="timeline-meta">Online platforms / Institutes</div>
              <div class="timeline-meta">4 weeks (Certificated Web development full stack)</div>
              <div class="timeline-meta">Certificated Web development with Cognifyz Intern </div>
              <p>
                Completed online courses on Java, Spring Boot, web development and RESTful
                APIs to strengthen my practical skills.
              </p>
            </div>
          </div>

          <div class="timeline-card">
            <h3 style="font-size:0.9rem; margin-bottom:0.5rem;">Highlights</h3>
            <div class="timeline-item">
              <div class="timeline-title">Multiple Web Designs</div>
              <div class="timeline-meta">Personal practice projects</div>
              <p>
                Built different types of layouts including landing pages, forms and
                dashboards to understand responsive design.
              </p>
            </div>
            <div class="timeline-item">
              <div class="timeline-title">API-Integrated Projects</div>
              <div class="timeline-meta">Spring Boot · REST APIs</div>
              <p>
                Implemented simple CRUD APIs and tested them using Postman, then connected
                them with frontend forms and AJAX calls.
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- CONTACT -->
      <section id="contact">
        <div class="section-header">
          <h2 class="section-title" style="color:#111827;">Contact</h2>
          <p class="section-subtitle">Let’s work together</p>
        </div>

        <div class="contact-card">
          <div class="contact-main">
            <h3>Let’s build something together</h3>
            <p>
              I’m available for <b>internships</b>, <b>fresher roles</b> and
              <b>project-based work</b>. If you think I’m a good fit, feel free to reach
              out.
            </p>
            <ul class="contact-list">
              <li>Email: <span>avgovardhanr@gmail.com</span></li>
              <li>Phone / WhatsApp: <span>+91-8919131844</span></li>
              <li>Location: <span>Hyderabad, India</span></li>
            </ul>

            <div class="social-links">
              <a href="https://github.com/avgovardhan1" target="_blank">GitHub</a>
              <a href="https://www.linkedin.com/in/annapureddy-venkat-govardhan-reddy-597bb4278/" target="_blank">LinkedIn</a>
              <a href="https://1drv.ms/b/c/b6ef8cd3d8890958/IQBCh06LLfOPSIEvZ9Ao1gDWAWRIXG8cdiHjzwBj4Ossj_A?e=7N9Cfx" target="_blank">Download Resume</a>
            </div>
          </div>

          <div class="contact-form">
            <form action="https://formspree.io/f/movoeqzd" method="POST">
  <div class="form-row">
    <label for="name">Name</label>
    <input
      id="name"
      type="text"
      name="name"
      placeholder="Your name"
      required
    />
  </div>

  <div class="form-row">
    <label for="email">Email</label>
    <input
      id="email"
      type="email"
      name="email"
      placeholder="you@example.com"
      required
    />
  </div>

  <div class="form-row">
    <label for="message">Message</label>
    <textarea
      id="message"
      name="message"
      placeholder="Write your message here..."
      required
    ></textarea>
  </div>

  <button type="submit" class="btn-form">Send Message</button>
</form>

          </div>
        </div>
      </section>

      <!-- FOOTER -->
      <footer>
        <span>© 2025 Your Name. All rights reserved.</span>
        <span>Built with HTML, CSS & love for clean design.</span>
      </footer>
    </main>
  </div>
</body>
</html>
