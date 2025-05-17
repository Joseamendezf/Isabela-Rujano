<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Isabela Rujano | Portfolio</title>
  <!-- Google Fonts: Montserrat and Open Sans (as used on Robert's site) -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #0e0e0e;
      --accent: #f5f5f5;
      --primary: #fff;
      --secondary: #bdbdbd;
      --button-bg: #fff;
      --button-text: #0e0e0e;
      --button-hover-bg: #0e0e0e;
      --button-hover-text: #fff;
      --nav-bg: rgba(14,14,14,0.95);
      --nav-shadow: 0 2px 16px rgba(0,0,0,0.2);
      --border-radius: 32px;
      --transition: 0.3s cubic-bezier(.4,0,.2,1);
    }
    html, body {
      margin: 0;
      padding: 0;
      background: var(--bg);
      color: var(--primary);
      font-family: 'Open Sans', Arial, sans-serif;
      scroll-behavior: smooth;
    }
    body {
      min-height: 100vh;
      overflow-x: hidden;
    }
    /* Navbar */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 1000;
      background: var(--nav-bg);
      box-shadow: var(--nav-shadow);
      height: 64px;
      transition: background var(--transition);
      display: flex;
      align-items: center;
      justify-content: flex-start;
      padding: 0;
    }
    .nav-container {
      width: 100%;
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 64px;
      padding: 0 2vw;
    }
    .nav-profile {
      width: 36px;
      height: 36px;
      border-radius: 50%;
      object-fit: cover;
      border: 2px solid var(--primary);
      background: #222;
      box-shadow: 0 2px 12px rgba(0,0,0,0.18);
      margin-right: 1.2rem;
      flex-shrink: 0;
    }
    nav ul {
      list-style: none;
      display: flex;
      gap: 0.5rem;
      margin: 0;
      padding: 0;
      align-items: center;
    }
    nav a {
      color: var(--primary);
      text-decoration: none;
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 300;
      font-size: 0.92rem;
      letter-spacing: 0.01em;
      padding: 4px 10px;
      border-radius: 12px;
      transition: background var(--transition), color var(--transition);
      background: none;
      opacity: 0.85;
    }
    nav a:hover, nav a.active {
      background: var(--primary);
      color: var(--bg);
      opacity: 1;
    }
    /* Hero Section */
    .hero {
      min-height: 60vh;
      display: flex;
      align-items: flex-start;
      justify-content: flex-start;
      text-align: left;
      padding-top: 110px;
      background: var(--bg);
      position: relative;
      padding-left: 2vw;
    }
    .hero-text {
      max-width: 600px;
      margin-left: 0;
      padding-left: 0;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: flex-start;
    }
    .main-name {
      font-family: 'DM Sans', Arial, sans-serif;
      font-size: 2.1rem;
      font-weight: 300;
      letter-spacing: 0.01em;
      margin: 0 0 0.5rem 0;
      color: var(--primary);
      line-height: 1.08;
      text-align: left;
      transition: color 0.3s;
      cursor: pointer;
      display: block;
      animation: fadeInUp 1s cubic-bezier(.4,0,.2,1);
    }
    .main-name:hover {
      color: var(--accent);
      text-shadow: 0 2px 24px #fff2;
    }
    .hero-sub {
      font-family: 'DM Sans', Arial, sans-serif;
      font-size: 1.05rem;
      font-weight: 300;
      color: var(--primary);
      opacity: 0.62;
      margin-bottom: 1.1rem;
      line-height: 1.2;
      text-align: left;
      transition: opacity 0.2s;
    }
    .hero-details {
      list-style: disc inside;
      color: var(--secondary);
      font-size: 0.98rem;
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 300;
      margin: 0 0 1.1rem 0;
      padding-left: 1.2rem;
      text-align: left;
    }
    .hero-details li {
      margin-bottom: 0.1rem;
    }
    .hero .cta {
      display: inline-block;
      background: var(--button-bg);
      color: var(--button-text);
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 300;
      font-size: 0.92rem;
      padding: 0.4em 1em;
      border-radius: 12px;
      border: none;
      cursor: pointer;
      box-shadow: 0 2px 12px rgba(0,0,0,0.10);
      transition: background var(--transition), color var(--transition), transform var(--transition);
      margin-top: 0.1rem;
      text-decoration: none;
      opacity: 0.92;
    }
    .hero .cta:hover {
      background: var(--button-hover-bg);
      color: var(--button-hover-text);
      transform: translateY(-2px) scale(1.04);
      opacity: 1;
    }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(40px); }
      to { opacity: 1; transform: translateY(0); }
    }
    /* Section Styles */
    section {
      max-width: 900px;
      margin: 0 auto;
      padding: 80px 24px 40px 24px;
    }
    section h2 {
      font-family: 'Montserrat', sans-serif;
      font-size: 2.2rem;
      font-weight: 700;
      margin-bottom: 1.5rem;
      color: var(--primary);
      letter-spacing: 0.06em;
      text-align: center;
    }
    /* About */
    .about p {
      font-size: 1.15rem;
      color: var(--secondary);
      line-height: 1.7;
      text-align: center;
      max-width: 700px;
      margin: 0 auto;
    }
    /* Projects Grid */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 2rem;
      margin-top: 2rem;
    }
    .project-card {
      background: #181818;
      border-radius: 24px;
      box-shadow: 0 2px 16px rgba(0,0,0,0.12);
      overflow: hidden;
      transition: transform 0.25s, box-shadow 0.25s;
      display: flex;
      flex-direction: column;
      cursor: pointer;
    }
    .project-card:hover {
      transform: translateY(-6px) scale(1.03);
      box-shadow: 0 8px 32px rgba(0,0,0,0.18);
    }
    .project-thumb {
      width: 100%;
      height: 180px;
      object-fit: cover;
      background: #222;
    }
    .project-content {
      padding: 1.2rem 1rem 1rem 1rem;
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .project-title {
      font-family: 'Montserrat', sans-serif;
      font-size: 1.1rem;
      font-weight: 700;
      color: var(--primary);
      margin-bottom: 0.5rem;
    }
    .project-desc {
      color: var(--secondary);
      font-size: 1rem;
      margin-bottom: 0.5rem;
    }
    .project-link {
      color: var(--accent);
      font-size: 0.98rem;
      text-decoration: underline;
      margin-top: auto;
      align-self: flex-start;
      transition: color 0.2s;
    }
    .project-link:hover {
      color: #ffd700;
    }
    /* Videos Carousel */
    .carousel {
      display: flex;
      overflow-x: auto;
      gap: 2rem;
      scroll-snap-type: x mandatory;
      padding-bottom: 1rem;
    }
    .carousel::-webkit-scrollbar {
      height: 8px;
      background: #222;
    }
    .carousel::-webkit-scrollbar-thumb {
      background: #444;
      border-radius: 8px;
    }
    .video-card {
      min-width: 320px;
      max-width: 400px;
      background: #181818;
      border-radius: 20px;
      box-shadow: 0 2px 16px rgba(0,0,0,0.12);
      overflow: hidden;
      scroll-snap-align: start;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-bottom: 1rem;
    }
    .video-card iframe {
      width: 100%;
      height: 220px;
      border: none;
      background: #000;
    }
    .video-title {
      color: var(--primary);
      font-size: 1rem;
      font-weight: 600;
      margin: 0.7rem 0 1rem 0;
      text-align: center;
    }
    /* Photos Gallery */
    .photos-gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 1.2rem;
      margin-top: 2rem;
    }
    .photo-thumb {
      width: 100%;
      aspect-ratio: 1/1;
      object-fit: cover;
      border-radius: 18px;
      cursor: pointer;
      transition: transform 0.2s, box-shadow 0.2s;
      box-shadow: 0 2px 12px rgba(0,0,0,0.10);
    }
    .photo-thumb:hover {
      transform: scale(1.04) translateY(-2px);
      box-shadow: 0 8px 32px rgba(0,0,0,0.18);
    }
    .photo-caption {
      color: var(--secondary);
      font-size: 0.98rem;
      text-align: center;
      margin-top: 0.4rem;
    }
    /* Lightbox */
    .lightbox {
      position: fixed;
      top: 0; left: 0; right: 0; bottom: 0;
      background: rgba(0,0,0,0.92);
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 2000;
      transition: opacity 0.3s;
    }
    .lightbox img {
      max-width: 90vw;
      max-height: 80vh;
      border-radius: 24px;
      box-shadow: 0 8px 48px #000a;
    }
    .lightbox .close {
      position: absolute;
      top: 32px;
      right: 48px;
      font-size: 2.5rem;
      color: #fff;
      cursor: pointer;
      background: none;
      border: none;
      z-index: 2100;
      transition: color 0.2s;
    }
    .lightbox .close:hover {
      color: #ffd700;
    }
    /* Voice Clips Carousel */
    .audio-carousel {
      display: flex;
      overflow-x: auto;
      gap: 2rem;
      scroll-snap-type: x mandatory;
      padding-bottom: 1rem;
    }
    .audio-card {
      min-width: 260px;
      max-width: 320px;
      background: #181818;
      border-radius: 20px;
      box-shadow: 0 2px 16px rgba(0,0,0,0.12);
      padding: 1.2rem 1rem 1rem 1rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      scroll-snap-align: start;
    }
    .audio-title {
      color: var(--primary);
      font-size: 1rem;
      font-weight: 600;
      margin-bottom: 0.7rem;
      text-align: center;
    }
    audio {
      width: 100%;
      outline: none;
      margin-bottom: 0.5rem;
      filter: invert(1) grayscale(1) brightness(1.2);
      border-radius: 8px;
      background: #222;
    }
    .audio-desc {
      color: var(--secondary);
      font-size: 0.95rem;
      text-align: center;
    }
    /* Contact Form */
    .contact-form {
      max-width: 480px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 1.2rem;
      background: #181818;
      border-radius: 24px;
      padding: 2rem 1.5rem 1.5rem 1.5rem;
      box-shadow: 0 2px 16px rgba(0,0,0,0.12);
    }
    .contact-form label {
      font-family: 'Montserrat', sans-serif;
      font-size: 1rem;
      color: var(--primary);
      margin-bottom: 0.3rem;
    }
    .contact-form input, .contact-form textarea {
      width: 100%;
      padding: 0.8em 1em;
      border-radius: 16px;
      border: none;
      background: #222;
      color: var(--primary);
      font-size: 1rem;
      font-family: inherit;
      margin-bottom: 0.5rem;
      resize: none;
      outline: none;
      transition: box-shadow 0.2s;
    }
    .contact-form input:focus, .contact-form textarea:focus {
      box-shadow: 0 0 0 2px #ffd70044;
    }
    .contact-form button {
      background: var(--button-bg);
      color: var(--button-text);
      font-family: 'Montserrat', sans-serif;
      font-weight: 700;
      font-size: 1.1rem;
      padding: 0.8em 2em;
      border-radius: var(--border-radius);
      border: none;
      cursor: pointer;
      box-shadow: 0 2px 16px rgba(0,0,0,0.12);
      transition: background var(--transition), color var(--transition), transform var(--transition);
      margin-top: 0.5rem;
    }
    .contact-form button:hover {
      background: var(--button-hover-bg);
      color: var(--button-hover-text);
      transform: translateY(-2px) scale(1.04);
    }
    .socials {
      display: flex;
      justify-content: center;
      gap: 1.2rem;
      margin-top: 1.2rem;
    }
    .socials a {
      color: var(--primary);
      font-size: 1.6rem;
      transition: color 0.2s;
    }
    .socials a:hover {
      color: #ffd700;
    }
    /* Footer */
    footer {
      text-align: center;
      color: var(--secondary);
      font-size: 0.98rem;
      padding: 2rem 0 1rem 0;
      margin-top: 2rem;
    }
    /* Responsive */
    @media (max-width: 700px) {
      .nav-container { padding: 0 1vw; }
      .nav-profile { width: 28px; height: 28px; }
      .main-name { font-size: 1.2rem; }
      .hero { padding-left: 1vw; }
      .hero-text { margin-left: 0; padding-left: 0; }
    }
    @media (max-width: 480px) {
      .main-name { font-size: 1rem; }
      .hero { padding-top: 70px; padding-left: 0.5vw; }
      .hero-text { margin-left: 0; padding-left: 0; }
    }
    .contact-gradient {
      background: linear-gradient(90deg, #ffe259 0%, #ffa751 50%, #ff5858 100%);
      color: #fff !important;
      font-weight: 400 !important;
      border: none;
      opacity: 1 !important;
      box-shadow: 0 2px 8px rgba(255, 88, 88, 0.08);
      transition: background 0.3s, color 0.3s;
    }
    .contact-gradient:hover, .contact-gradient.active {
      background: linear-gradient(90deg, #ff5858 0%, #ffa751 100%);
      color: #fff !important;
    }
    .menu-btn {
      background: none;
      border: none;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      margin-left: 1rem;
      height: 32px;
      width: 32px;
      padding: 0;
    }
    .menu-btn span {
      display: block;
      width: 22px;
      height: 3px;
      background: #fff;
      margin: 3px 0;
      border-radius: 2px;
      transition: all 0.2s;
    }
    .dropdown-menu {
      display: none;
      position: absolute;
      top: 60px;
      right: 2vw;
      background: #181818;
      border-radius: 12px;
      box-shadow: 0 4px 24px #0005;
      min-width: 160px;
      z-index: 2000;
      flex-direction: column;
      padding: 0.7rem 0;
      animation: fadeInUp 0.3s;
    }
    .dropdown-menu.show {
      display: flex;
    }
    .dropdown-menu a {
      color: #fff;
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 300;
      font-size: 1rem;
      padding: 0.6em 1.2em;
      text-decoration: none;
      transition: background 0.2s, color 0.2s;
      border-radius: 8px;
      margin: 0 0.2em;
    }
    .dropdown-menu a:hover {
      background: #222;
      color: #ffe259;
    }
    .contact-info {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 1.2rem;
      font-size: 1.1rem;
      margin: 2rem 0 1rem 0;
      padding-left: 2vw;
    }
    .contact-info i {
      color: #ffe259;
      margin-right: 0.7em;
      font-size: 1.2em;
      vertical-align: middle;
    }
    .contact-info a {
      color: #fff;
      text-decoration: underline;
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 300;
      font-size: 1.1rem;
    }
    .footer-socials {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 1.2rem;
      margin-bottom: 0.7rem;
    }
    .footer-socials a {
      color: #fff;
      font-size: 1.3rem;
      opacity: 0.7;
      transition: color 0.2s, opacity 0.2s;
    }
    .footer-socials a:hover {
      color: #ffe259;
      opacity: 1;
    }
    .footer-copy {
      text-align: center;
      color: var(--secondary);
      font-size: 0.95rem;
      margin-bottom: 1.2rem;
    }
    @media (max-width: 700px) {
      .dropdown-menu { right: 1vw; }
      .contact-info { padding-left: 1vw; }
    }
    @media (max-width: 480px) {
      .dropdown-menu { right: 0.5vw; }
      .contact-info { padding-left: 0.5vw; }
    }
    .nav-btn {
      background: rgba(255,255,255,0.08);
      color: #fff;
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 300;
      font-size: 0.92rem;
      letter-spacing: 0.01em;
      padding: 4px 10px;
      border-radius: 12px;
      border: none;
      opacity: 0.85;
      transition: background 0.2s, color 0.2s, box-shadow 0.2s;
      backdrop-filter: blur(4px);
      box-shadow: 0 1px 6px rgba(0,0,0,0.04);
    }
    .nav-btn:hover, .nav-btn.active {
      background: rgba(255,255,255,0.18);
      color: #ffe259;
      opacity: 1;
    }
    .contact-btn {
      background: #fff;
      color: #181818 !important;
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 400;
      font-size: 0.92rem;
      letter-spacing: 0.01em;
      padding: 4px 14px;
      border-radius: 12px;
      border: none;
      opacity: 1;
      box-shadow: 0 2px 8px rgba(255, 88, 88, 0.08);
      transition: background 0.2s, color 0.2s;
    }
    .contact-btn:hover, .contact-btn.active {
      background: #181818;
      color: #fff !important;
      border: 1px solid #fff;
    }
    /* Animaciones fadeInUp */
    .fadein {
      opacity: 0;
      transform: translateY(40px);
      transition: opacity 0.7s cubic-bezier(.4,0,.2,1), transform 0.7s cubic-bezier(.4,0,.2,1);
    }
    .fadein.visible {
      opacity: 1;
      transform: translateY(0);
    }
    /* Contact pills */
    .contact-pill {
      display: flex;
      align-items: center;
      justify-content: center;
      background: rgba(255,255,255,0.08);
      backdrop-filter: blur(4px);
      border-radius: 24px;
      padding: 0.6em 1.5em;
      margin: 0.3em auto;
      font-size: 1.08rem;
      color: #fff;
      box-shadow: 0 1px 6px rgba(0,0,0,0.04);
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 300;
      min-width: 220px;
      max-width: 340px;
    }
    .contact-pill i {
      color: #ffe259;
      margin-right: 0.7em;
      font-size: 1.2em;
      vertical-align: middle;
    }
    .contact-pill a {
      color: #fff;
      text-decoration: underline;
      font-family: 'DM Sans', Arial, sans-serif;
      font-weight: 300;
      font-size: 1.08rem;
    }
    .footer-contact {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 0.5em;
      margin-bottom: 0.7em;
    }
  </style>
  <!-- FontAwesome for social icons -->
  <script src="https://kit.fontawesome.com/7e2e4e2e2e.js" crossorigin="anonymous"></script>
</head>
<body>
  <!-- Navbar -->
  <nav>
    <div class="nav-container">
      <img src="profile.jpg" alt="Isabela Rujano" class="nav-profile" />
      <ul>
        <li><a href="#home" class="nav-btn">Home</a></li>
        <li><a href="#about" class="nav-btn">About</a></li>
        <li><a href="#projects" class="nav-btn">Projects</a></li>
        <li><a href="#videos" class="nav-btn">Videos</a></li>
        <li><a href="#photos" class="nav-btn">Photos</a></li>
        <li><a href="#voice" class="nav-btn">Voice Clips</a></li>
        <li><a href="#contact" class="contact-btn">Contact</a></li>
      </ul>
      <button class="menu-btn" aria-label="Más opciones" onclick="toggleMenu()">
        <span></span><span></span><span></span>
      </button>
      <div class="dropdown-menu" id="dropdownMenu">
        <a href="#">Curriculum</a>
        <a href="https://www.linkedin.com/" target="_blank">LinkedIn</a>
        <a href="https://www.instagram.com/" target="_blank">Instagram</a>
        <a href="https://wa.me/" target="_blank">WhatsApp</a>
      </div>
    </div>
  </nav>
  <!-- Hero Section -->
  <section class="hero" id="home">
    <div class="hero-text">
      <h1 class="main-name" tabindex="0">Soy Isabela.</h1>
      <div class="hero-sub">
        <span>Comunicadora Social.</span><br>
        <span>Voice Over | Presentadora.</span>
      </div>
      <ul class="hero-details">
        <li>10+ años en comunicación y medios</li>
        <li>Experta en locución y presentación</li>
      </ul>
      <a href="#contact" class="cta">Invite</a>
    </div>
  </section>
  <!-- About Section -->
  <section class="about" id="about">
    <h2>About</h2>
    <p>
      I am Isabela Rujano, a passionate Comunicadora Social, voice over artist, and presenter. My work bridges the worlds of storytelling, media, and performance, bringing ideas to life through voice and presence. I thrive on creative collaboration and believe in the power of authentic communication.
    </p>
  </section>
  <!-- Projects Section -->
  <section id="projects">
    <h2>Projects</h2>
    <div class="projects-grid">
      <div class="project-card">
        <img src="https://images.unsplash.com/photo-1465101046530-73398c7f28ca?auto=format&fit=crop&w=400&q=80" class="project-thumb" alt="Project 1" />
        <div class="project-content">
          <div class="project-title">Podcast Series</div>
          <div class="project-desc">A series of interviews with inspiring voices in media and culture.</div>
          <a href="#" class="project-link" target="_blank">View Project</a>
        </div>
      </div>
      <div class="project-card">
        <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=400&q=80" class="project-thumb" alt="Project 2" />
        <div class="project-content">
          <div class="project-title">Documentary Voiceover</div>
          <div class="project-desc">Narration for a documentary on Latin American culture and history.</div>
          <a href="#" class="project-link" target="_blank">View Project</a>
        </div>
      </div>
      <div class="project-card">
        <img src="https://images.unsplash.com/photo-1515378791036-0648a3ef77b2?auto=format&fit=crop&w=400&q=80" class="project-thumb" alt="Project 3" />
        <div class="project-content">
          <div class="project-title">TV Hosting</div>
          <div class="project-desc">Hosting a weekly TV show focused on arts and entertainment.</div>
          <a href="#" class="project-link" target="_blank">View Project</a>
        </div>
      </div>
    </div>
  </section>
  <!-- Videos Section -->
  <section id="videos">
    <h2>Videos</h2>
    <div class="carousel">
      <div class="video-card">
        <iframe src="https://www.youtube.com/embed/ysz5S6PUM-U" allowfullscreen></iframe>
        <div class="video-title">Showreel 2024</div>
      </div>
      <div class="video-card">
        <iframe src="https://www.youtube.com/embed/jNQXAC9IVRw" allowfullscreen></iframe>
        <div class="video-title">Interview: The Art of Voice</div>
      </div>
      <div class="video-card">
        <iframe src="https://www.youtube.com/embed/tgbNymZ7vqY" allowfullscreen></iframe>
        <div class="video-title">TV Hosting Highlights</div>
      </div>
    </div>
  </section>
  <!-- Photos Section -->
  <section id="photos">
    <h2>Photos</h2>
    <div class="photos-gallery">
      <div>
        <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=400&q=80" class="photo-thumb" alt="Photo 1" onclick="openLightbox(this)" data-caption="On set, 2023" />
        <div class="photo-caption">On set, 2023</div>
      </div>
      <div>
        <img src="https://images.unsplash.com/photo-1529626455594-4ff0802cfb7e?auto=format&fit=crop&w=400&q=80" class="photo-thumb" alt="Photo 2" onclick="openLightbox(this)" data-caption="Studio session" />
        <div class="photo-caption">Studio session</div>
      </div>
      <div>
        <img src="https://images.unsplash.com/photo-1519125323398-675f0ddb6308?auto=format&fit=crop&w=400&q=80" class="photo-thumb" alt="Photo 3" onclick="openLightbox(this)" data-caption="Live event" />
        <div class="photo-caption">Live event</div>
      </div>
      <div>
        <img src="https://images.unsplash.com/photo-1508214751196-bcfd4ca60f91?auto=format&fit=crop&w=400&q=80" class="photo-thumb" alt="Photo 4" onclick="openLightbox(this)" data-caption="Behind the scenes" />
        <div class="photo-caption">Behind the scenes</div>
      </div>
    </div>
    <!-- Lightbox Modal -->
    <div id="lightbox" class="lightbox" style="display:none;">
      <button class="close" onclick="closeLightbox()">&times;</button>
      <img id="lightbox-img" src="" alt="Expanded photo" />
      <div class="photo-caption" id="lightbox-caption"></div>
    </div>
  </section>
  <!-- Voice Clips Section -->
  <section id="voice">
    <h2>Voice Clips</h2>
    <div class="audio-carousel">
      <div class="audio-card">
        <div class="audio-title">Commercial Demo</div>
        <audio controls preload="none">
          <source src="https://www.samplelib.com/mp3/sample-3s.mp3" type="audio/mp3" />
          Your browser does not support the audio element.
        </audio>
        <div class="audio-desc">Energetic, upbeat commercial spot.</div>
      </div>
      <div class="audio-card">
        <div class="audio-title">Narration Sample</div>
        <audio controls preload="none">
          <source src="https://www.samplelib.com/mp3/sample-6s.mp3" type="audio/mp3" />
          Your browser does not support the audio element.
        </audio>
        <div class="audio-desc">Warm, engaging narration for documentary.</div>
      </div>
      <div class="audio-card">
        <div class="audio-title">Promo Voice</div>
        <audio controls preload="none">
          <source src="https://www.samplelib.com/mp3/sample-9s.mp3" type="audio/mp3" />
          Your browser does not support the audio element.
        </audio>
        <div class="audio-desc">Dynamic promo for TV segment.</div>
      </div>
    </div>
  </section>
  <!-- Contact Section -->
  <section id="contact">
    <h2>Contacto</h2>
    <div class="contact-info fadein">
      <div class="contact-pill"><i class="fas fa-envelope"></i> <a href="mailto:isabelarujanop@gmail.com">isabelarujanop@gmail.com</a></div>
      <div class="contact-pill"><i class="fab fa-whatsapp"></i> <a href="https://wa.me/1234567890" target="_blank">+1 234 567 890</a></div>
    </div>
  </section>
  <footer>
    <div class="footer-contact">
      <div class="contact-pill"><i class="fas fa-envelope"></i> <a href="mailto:isabelarujanop@gmail.com">isabelarujanop@gmail.com</a></div>
      <div class="contact-pill"><i class="fab fa-whatsapp"></i> <a href="https://wa.me/1234567890" target="_blank">+1 234 567 890</a></div>
    </div>
    <div class="footer-socials">
      <a href="https://www.instagram.com/" target="_blank" title="Instagram"><i class="fab fa-instagram"></i></a>
      <a href="https://www.linkedin.com/" target="_blank" title="LinkedIn"><i class="fab fa-linkedin"></i></a>
      <a href="https://wa.me/1234567890" target="_blank" title="WhatsApp"><i class="fab fa-whatsapp"></i></a>
      <a href="mailto:isabelarujanop@gmail.com" title="Email"><i class="fas fa-envelope"></i></a>
    </div>
    <div class="footer-copy">&copy; 2024 Isabela Rujano. All rights reserved.</div>
  </footer>
  <script>
    // Navbar active link on scroll
    const navLinks = document.querySelectorAll('nav a');
    const sections = document.querySelectorAll('section');
    window.addEventListener('scroll', () => {
      let current = '';
      sections.forEach(section => {
        const sectionTop = section.offsetTop - 80;
        if (pageYOffset >= sectionTop) {
          current = section.getAttribute('id');
        }
      });
      navLinks.forEach(link => {
        link.classList.remove('active');
        if (link.getAttribute('href') === '#' + current) {
          link.classList.add('active');
        }
      });
    });
    // Lightbox for photos
    function openLightbox(img) {
      document.getElementById('lightbox-img').src = img.src;
      document.getElementById('lightbox-caption').textContent = img.getAttribute('data-caption') || '';
      document.getElementById('lightbox').style.display = 'flex';
    }
    function closeLightbox() {
      document.getElementById('lightbox').style.display = 'none';
      document.getElementById('lightbox-img').src = '';
      document.getElementById('lightbox-caption').textContent = '';
    }
    // Close lightbox on click outside image
    document.getElementById('lightbox').addEventListener('click', function(e) {
      if (e.target === this) closeLightbox();
    });
    function toggleMenu() {
      var menu = document.getElementById('dropdownMenu');
      menu.classList.toggle('show');
    }
    // Cierra el menú si se hace click fuera
    document.addEventListener('click', function(event) {
      var menu = document.getElementById('dropdownMenu');
      var btn = document.querySelector('.menu-btn');
      if (!menu.contains(event.target) && !btn.contains(event.target)) {
        menu.classList.remove('show');
      }
    });
    // Animación fadeInUp al hacer scroll
    function fadeInOnScroll() {
      const fadeEls = document.querySelectorAll('.fadein');
      const trigger = window.innerHeight * 0.92;
      fadeEls.forEach(el => {
        const rect = el.getBoundingClientRect();
        if (rect.top < trigger) {
          el.classList.add('visible');
        }
      });
    }
    window.addEventListener('scroll', fadeInOnScroll);
    window.addEventListener('DOMContentLoaded', fadeInOnScroll);
  </script>
</body>
</html> 
