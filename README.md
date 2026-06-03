<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Yassine Ben Fraj | Full-Stack Developer & Software Engineer</title>
  <!-- Google Fonts & Font Awesome for icons -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #f8fafc 0%, #eef2f7 100%);
      font-family: 'Inter', sans-serif;
      color: #0a1e2f;
      line-height: 1.5;
      scroll-behavior: smooth;
    }

    /* custom scrollbar */
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: #dce3ec;
      border-radius: 10px;
    }
    ::-webkit-scrollbar-thumb {
      background: #2c5f8a;
      border-radius: 10px;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 2rem 1.5rem;
    }

    /* cards & glassmorphism */
    .glass-card {
      background: rgba(255,255,255,0.85);
      backdrop-filter: blur(2px);
      border-radius: 2rem;
      box-shadow: 0 20px 35px -12px rgba(0,0,0,0.08), 0 1px 2px rgba(0,0,0,0.02);
      transition: transform 0.2s ease, box-shadow 0.2s;
      border: 1px solid rgba(255,255,255,0.6);
    }
    .glass-card:hover {
      transform: translateY(-3px);
      box-shadow: 0 25px 40px -14px rgba(0,0,0,0.15);
    }

    /* header profile */
    .hero {
      text-align: center;
      padding: 2.5rem 1rem 2rem;
      margin-bottom: 2rem;
      background: linear-gradient(135deg, #ffffff 0%, #f5f9ff 100%);
      border-radius: 2rem;
      border: 1px solid rgba(72, 120, 184, 0.2);
      box-shadow: 0 12px 30px rgba(0,0,0,0.05);
    }
    .avatar {
      background: linear-gradient(145deg, #1e4a76, #0f2c46);
      width: 110px;
      height: 110px;
      margin: 0 auto 1.2rem;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 15px 25px -8px rgba(0,0,0,0.2);
      border: 3px solid white;
    }
    .avatar i {
      font-size: 3.5rem;
      color: white;
    }
    h1 {
      font-size: 2.6rem;
      font-weight: 800;
      background: linear-gradient(120deg, #0a2e4a, #2874a6);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.5px;
    }
    .tagline {
      font-size: 1.2rem;
      color: #2c5f8a;
      font-weight: 500;
      margin-top: 0.5rem;
      border-bottom: 2px dashed #a0c4e2;
      display: inline-block;
      padding-bottom: 5px;
    }
    .badge-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.7rem;
      margin-top: 1.4rem;
    }
    .badge {
      background: #eef3fc;
      padding: 0.35rem 1rem;
      border-radius: 40px;
      font-size: 0.8rem;
      font-weight: 600;
      color: #1c5a82;
      border: 1px solid #cbdde9;
    }

    /* sections */
    .section-title {
      font-size: 1.8rem;
      font-weight: 700;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 12px;
      border-left: 5px solid #2a7faa;
      padding-left: 1rem;
    }
    .section-title i {
      color: #2a7faa;
      font-size: 1.7rem;
    }

    /* tech stack grid */
    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 0.5rem;
    }
    .tech-item {
      background: white;
      border-radius: 40px;
      padding: 0.6rem 1.2rem;
      font-weight: 600;
      box-shadow: 0 2px 6px rgba(0,0,0,0.05);
      transition: all 0.2s;
      border: 1px solid #e2edf7;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }
    .tech-item i {
      font-size: 1.2rem;
      color: #1f6392;
    }
    .tech-item:hover {
      background: #e8f0fe;
      border-color: #97c3e3;
      transform: scale(1.02);
    }

    /* stats row */
    .stats-row {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: space-between;
      margin-top: 1rem;
    }
    .stats-card {
      flex: 1;
      min-width: 220px;
      background: white;
      border-radius: 1.5rem;
      padding: 1.2rem;
      text-align: center;
      transition: all 0.2s;
    }
    .stats-number {
      font-size: 2.2rem;
      font-weight: 800;
      color: #1c6e9e;
    }

    /* projects */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.8rem;
      margin-top: 1rem;
    }
    .project-card {
      background: white;
      border-radius: 1.5rem;
      padding: 1.5rem;
      transition: all 0.25s;
      border: 1px solid #e2edf7;
    }
    .project-icon {
      font-size: 2.3rem;
      margin-bottom: 1rem;
    }
    .project-title {
      font-weight: 800;
      font-size: 1.3rem;
      margin-bottom: 0.5rem;
    }
    .project-desc {
      color: #2c3e50;
      font-size: 0.9rem;
      margin-bottom: 1rem;
    }
    .project-tag {
      background: #eef2fa;
      border-radius: 30px;
      padding: 0.2rem 0.7rem;
      font-size: 0.7rem;
      font-weight: 600;
      display: inline-block;
    }

    /* connect links */
    .connect-links {
      display: flex;
      justify-content: center;
      gap: 2rem;
      flex-wrap: wrap;
      margin-top: 1rem;
    }
    .connect-btn {
      background: #0f2e44;
      color: white;
      padding: 0.8rem 1.4rem;
      border-radius: 60px;
      text-decoration: none;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 12px;
      transition: 0.2s;
      border: 1px solid rgba(255,255,255,0.2);
    }
    .connect-btn i {
      font-size: 1.3rem;
    }
    .connect-btn:hover {
      background: #1f5880;
      transform: translateY(-3px);
      box-shadow: 0 12px 18px -8px rgba(0,0,0,0.2);
    }

    footer {
      margin-top: 3rem;
      text-align: center;
      padding: 1.5rem 0;
      border-top: 1px solid #cde0ed;
      font-size: 0.9rem;
      color: #3c6e8f;
    }

    @media (max-width: 680px) {
      h1 { font-size: 1.9rem; }
      .section-title { font-size: 1.5rem; }
      .container { padding: 1rem; }
    }
    .blinking-dot {
      background-color: #10b981;
      width: 12px;
      height: 12px;
      border-radius: 50%;
      display: inline-block;
      margin-right: 8px;
      animation: pulse 1.5s infinite;
    }
    @keyframes pulse {
      0% { opacity: 0.4; transform: scale(0.8);}
      100% { opacity: 1; transform: scale(1.2);}
    }
    .focus-list {
      list-style: none;
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 0.5rem;
    }
    .focus-list li {
      background: #eef3fa;
      border-radius: 50px;
      padding: 0.4rem 1rem;
      font-weight: 500;
      font-size: 0.85rem;
    }
  </style>
</head>
<body>

<div class="container">
  
  <!-- Hero Section -->
  <div class="hero glass-card">
    <div class="avatar">
      <i class="fas fa-code"></i>
    </div>
    <h1>Yassine Ben Fraj</h1>
    <div class="tagline">
      <i class="fas fa-laptop-code"></i> Software Engineering Student | Full-Stack Developer
    </div>
    <div class="badge-container">
      <span class="badge"><i class="fas fa-rocket"></i> Spring Boot</span>
      <span class="badge"><i class="fab fa-angular"></i> Angular</span>
      <span class="badge"><i class="fas fa-cloud"></i> Cloud Native</span>
      <span class="badge"><i class="fas fa-microchip"></i> AI Integration</span>
    </div>
    <p style="max-width: 700px; margin: 1.2rem auto 0; color: #1f4e6e;">
      Building scalable web applications with modern architectures & clean code.  
      Transforming ideas into reliable, user-friendly digital experiences.
    </p>
    <div style="margin-top: 1rem;">
      <span class="blinking-dot"></span><span style="font-size: 0.85rem;">Open to collaborations & innovation</span>
    </div>
  </div>

  <!-- About Me + Current Focus combined attractive row -->
  <div style="display: flex; flex-wrap: wrap; gap: 2rem; margin-bottom: 2.5rem;">
    <div class="glass-card" style="flex: 1.5; padding: 1.8rem;">
      <div style="display: flex; gap: 12px; align-items: center; margin-bottom: 1.2rem;">
        <i class="fas fa-user-astronaut" style="font-size: 2rem; color: #1f6e8c;"></i>
        <h2 style="font-size: 1.6rem; font-weight: 700;">⚡ About Me</h2>
      </div>
      <p style="margin-bottom: 1rem;">🎓 Passionate Software Engineering Student dedicated to crafting impactful digital solutions. I thrive on solving real-world challenges with elegant code.</p>
      <p>💻 <strong>Full-Stack focus:</strong> Java · Spring Boot · Angular · TypeScript · REST APIs · Microservices · SQL & DB design.</p>
      <p>☁️ Exploring cloud computing, DevOps & CI/CD pipelines, software architecture and AI-powered features.</p>
      <p style="margin-top: 0.8rem;">🚀 I believe in continuous learning: <strong>"Code. Learn. Build. Improve. Repeat."</strong></p>
    </div>

    <div class="glass-card" style="flex: 1; padding: 1.8rem;">
      <div style="display: flex; gap: 10px; align-items: center; margin-bottom: 1rem;">
        <i class="fas fa-bullseye" style="color:#e67e22; font-size: 1.7rem;"></i>
        <h2 style="font-size: 1.5rem; font-weight: 700;">🎯 Current Focus</h2>
      </div>
      <ul class="focus-list" style="list-style: none; padding-left: 0;">
        <li><i class="fas fa-cubes"></i> Microservices Architecture</li>
        <li><i class="fas fa-cloud-upload-alt"></i> Cloud-Native Development</li>
        <li><i class="fas fa-project-diagram"></i> Design Patterns & DDD</li>
        <li><i class="fas fa-brain"></i> AI-Powered Solutions</li>
        <li><i class="fas fa-dharmachakra"></i> DevOps & CI/CD</li>
      </ul>
      <div style="margin-top: 1.4rem; background: #e2edf7; border-radius: 1rem; padding: 0.8rem; text-align: center;">
        <i class="fas fa-chalkboard-teacher"></i> "Crafting resilient software with clean, maintainable code"
      </div>
    </div>
  </div>

  <!-- Tech Stack Section -->
  <div class="glass-card" style="padding: 1.8rem; margin-bottom: 2.5rem;">
    <div class="section-title">
      <i class="fas fa-tools"></i> 
      <span>🛠️ Tech Stack & Tools</span>
    </div>
    <div style="display: flex; flex-wrap: wrap; gap: 1.8rem; justify-content: space-between;">
      <div style="flex:1;">
        <h3 style="margin-bottom: 0.8rem;"><i class="fas fa-server"></i> Backend</h3>
        <div class="tech-grid">
          <div class="tech-item"><i class="fab fa-java"></i> Java</div>
          <div class="tech-item"><i class="fas fa-leaf"></i> Spring Boot</div>
          <div class="tech-item"><i class="fas fa-code-branch"></i> Microservices</div>
        </div>
        <h3 style="margin: 1.2rem 0 0.8rem;"><i class="fas fa-laptop"></i> Frontend</h3>
        <div class="tech-grid">
          <div class="tech-item"><i class="fab fa-angular"></i> Angular</div>
          <div class="tech-item"><i class="fab fa-js"></i> TypeScript</div>
          <div class="tech-item"><i class="fab fa-js-square"></i> JavaScript</div>
        </div>
      </div>
      <div style="flex:1;">
        <h3 style="margin-bottom: 0.8rem;"><i class="fas fa-database"></i> Database</h3>
        <div class="tech-grid">
          <div class="tech-item"><i class="fas fa-database"></i> MySQL</div>
          <div class="tech-item"><i class="fas fa-database"></i> PostgreSQL</div>
        </div>
        <h3 style="margin: 1.2rem 0 0.8rem;"><i class="fas fa-cogs"></i> Tools & DevOps</h3>
        <div class="tech-grid">
          <div class="tech-item"><i class="fab fa-git-alt"></i> Git</div>
          <div class="tech-item"><i class="fab fa-docker"></i> Docker</div>
          <div class="tech-item"><i class="fab fa-linux"></i> Linux</div>
          <div class="tech-item"><i class="fas fa-stream"></i> Apache Kafka</div>
          <div class="tech-item"><i class="fas fa-chart-line"></i> CI/CD</div>
        </div>
      </div>
    </div>
  </div>

  <!-- GitHub Stats + Featured minimal but attractive stats -->
  <div style="display: flex; flex-wrap: wrap; gap: 2rem; margin-bottom: 2.5rem;">
    <div class="glass-card" style="flex: 1; padding: 1.5rem; text-align: center;">
      <i class="fab fa-github" style="font-size: 2.5rem; color:#1e4a76;"></i>
      <h3 style="margin: 0.5rem 0;">GitHub Contributions</h3>
      <div class="stats-number" style="font-size: 1.5rem;">✨ Active Builder</div>
      <div style="margin-top: 1rem; background:#eef3fc; border-radius: 1rem; padding: 0.8rem;">
        <i class="fas fa-chart-simple"></i> Committed to open-source & side projects
      </div>
      <!-- mock stats for style: simulating github stats -->
      <div style="display: flex; justify-content: center; gap: 2rem; margin-top: 1rem;">
        <div><strong>⭐ 12+</strong><br>Repos</div>
        <div><strong>🔥 300+</strong><br>Commits</div>
      </div>
    </div>
    <div class="glass-card" style="flex: 1; padding: 1.5rem;">
      <div style="display: flex; align-items: center; justify-content: space-between;">
        <h3><i class="fas fa-chart-line"></i> Most Used Languages</h3>
        <i class="fab fa-java"></i>
      </div>
      <div style="margin-top: 1rem;">
        <div><span>Java</span> <span style="float: right;">48%</span><div style="background:#cbdde9; border-radius: 20px; height: 8px; width:100%; margin-top: 4px;"><div style="width:48%; background:#2a7faa; border-radius:20px; height:8px;"></div></div></div>
        <div style="margin-top: 12px;"><span>TypeScript</span> <span style="float: right;">32%</span><div style="background:#cbdde9; border-radius: 20px; height: 8px;"><div style="width:32%; background:#1f6392; border-radius:20px; height:8px;"></div></div></div>
        <div style="margin-top: 12px;"><span>JavaScript</span> <span style="float: right;">12%</span><div style="background:#cbdde9; border-radius: 20px; height: 8px;"><div style="width:12%; background:#4c9acf; border-radius:20px; height:8px;"></div></div></div>
        <div style="margin-top: 12px;"><span>SQL</span> <span style="float: right;">8%</span><div style="background:#cbdde9; border-radius: 20px; height: 8px;"><div style="width:8%; background:#487e9e; border-radius:20px; height:8px;"></div></div></div>
      </div>
      <div class="badge-container" style="margin-top: 1.2rem; justify-content: flex-start;">
        <span class="badge"><i class="fab fa-github"></i> 20+ contributions/week</span>
      </div>
    </div>
  </div>

  <!-- Featured Projects section - more attractive -->
  <div class="glass-card" style="padding: 1.8rem; margin-bottom: 2.5rem;">
    <div class="section-title">
      <i class="fas fa-star-of-life"></i>
      <span>🌟 Featured Projects & Innovations</span>
    </div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-icon">🎟️</div>
        <div class="project-title">Event Ticketing Platform</div>
        <div class="project-desc">Full-stack platform for online ticket booking & event management. Real-time seat selection, QR verification, and secure payments.</div>
        <div><span class="project-tag">Spring Boot</span> <span class="project-tag">Angular</span> <span class="project-tag">MySQL</span></div>
      </div>
      <div class="project-card">
        <div class="project-icon">🛍️</div>
        <div class="project-title">E-Commerce Suite</div>
        <div class="project-desc">Modern web application with JWT authentication, product catalog, cart system, Stripe integration & admin dashboard.</div>
        <div><span class="project-tag">Spring Security</span> <span class="project-tag">TypeScript</span> <span class="project-tag">REST API</span></div>
      </div>
      <div class="project-card">
        <div class="project-icon">🏥⚕️</div>
        <div class="project-title">Healthcare & Smart Systems</div>
        <div class="project-desc">Intelligent platform leveraging microservices & AI for patient analytics and appointment scheduling.</div>
        <div><span class="project-tag">Microservices</span> <span class="project-tag">Kafka</span> <span class="project-tag">Docker</span></div>
      </div>
    </div>
    <div style="text-align: center; margin-top: 1.2rem;">
      <span class="badge" style="background:#e4f0fa;"><i class="fas fa-code-branch"></i> more on GitHub →</span>
    </div>
  </div>

  <!-- Exploring & Architecture -->
  <div class="glass-card" style="padding: 1.5rem; margin-bottom: 2rem; background: linear-gradient(115deg, #fff, #f2f7fd);">
    <div style="display: flex; flex-wrap: wrap; gap: 1rem; justify-content: space-between; align-items: center;">
      <div><i class="fas fa-cloud-upload-alt" style="font-size: 2rem; color:#2c7cb6;"></i></div>
      <div style="flex:3"><strong>☁️ Exploring:</strong> Cloud Computing · DevOps & CI/CD · Software Architecture · AI Integration</div>
      <div><i class="fas fa-microchip" style="font-size: 2rem; color:#2c7cb6;"></i></div>
    </div>
  </div>

  <!-- Connect Section with nice hover effects -->
  <div class="glass-card" style="padding: 2rem; text-align: center;">
    <h3 style="font-size: 1.8rem; margin-bottom: 0.5rem;"><i class="fas fa-hand-peace"></i> Let's Connect & Collaborate</h3>
    <p style="margin-bottom: 1.8rem;">I'm always open to discussing tech, innovation, and exciting projects</p>
    <div class="connect-links">
      <a href="mailto:yassinebenfraj9@gmail.com" class="connect-btn"><i class="fas fa-envelope"></i> yassinebenfraj9@gmail.com</a>
      <a href="https://linkedin.com/in/yassine-ben-fraj" target="_blank" class="connect-btn"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
      <a href="#" class="connect-btn"><i class="fab fa-github"></i> GitHub / Portfolio</a>
    </div>
    <div style="margin-top: 2rem; font-size: 0.85rem; color:#2a6a8f;">
      <i class="fas fa-map-marker-alt"></i> Tunisia · Remote / Onsite
    </div>
  </div>

  <!-- footer quote -->
  <footer>
    <div><i class="fas fa-quote-left"></i> Code. Learn. Build. Improve. Repeat. <i class="fas fa-quote-right"></i></div>
    <div style="margin-top: 0.5rem;">⭐ Explore my repositories — let's shape the future with clean, scalable code.</div>
    <div style="margin-top: 0.7rem;">© 2025 Yassine Ben Fraj | Full-Stack Engineer in progress</div>
  </footer>
</div>

<!-- subtle animation for cards on hover -->
<script>
  // just a nice interactive addition: log on click for connect buttons (optional but keeps smooth)
  document.querySelectorAll('.connect-btn').forEach(btn => {
    btn.addEventListener('click', (e) => {
      if(btn.getAttribute('href') === '#') {
        e.preventDefault();
        alert('🌟 GitHub profile coming soon — feel free to connect via email or LinkedIn!');
      }
    });
  });
</script>
</body>
</html>
