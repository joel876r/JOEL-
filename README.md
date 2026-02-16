<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>stellar portfolio · MR__JOEL R</title>
  <!-- Google Fonts & Font Awesome for clean icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,500;14..32,700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #f5f7fb;
      color: #1e1e2f;
      line-height: 1.6;
      scroll-behavior: smooth;
    }

    /* modern gradient navbar */
    .navbar {
      background: rgba(10, 10, 20, 0.85);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
      position: sticky;
      top: 0;
      z-index: 100;
      padding: 0.8rem 2rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      border-bottom: 1px solid rgba(255,255,255,0.08);
    }

    .logo {
      font-size: 1.8rem;
      font-weight: 700;
      background: linear-gradient(135deg, #a18cd1, #fbc2eb);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.5px;
    }

    .nav-links {
      display: flex;
      gap: 2rem;
    }

    .nav-links a {
      color: #f0f0f0;
      text-decoration: none;
      font-weight: 500;
      font-size: 1rem;
      transition: 0.2s ease;
      padding: 0.5rem 0;
      border-bottom: 2px solid transparent;
    }

    .nav-links a:hover {
      border-bottom-color: #c084fc;
      color: white;
    }

    /* hero section — advanced glassmorphism */
    .hero {
      min-height: 70vh;
      background: linear-gradient(145deg, #0b0c1e 0%, #1f1d3a 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      color: white;
      position: relative;
      overflow: hidden;
      isolation: isolate;
    }

    .hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at 20% 50%, rgba(168, 139, 250, 0.3), transparent 50%);
      z-index: 0;
    }

    .hero-content {
      max-width: 800px;
      padding: 2rem;
      position: relative;
      z-index: 2;
    }

    .hero h1 {
      font-size: 4rem;
      font-weight: 700;
      background: linear-gradient(to right, #e0c3fc, #b1b1ff, #a3c8ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      line-height: 1.2;
    }

    .hero .highlight {
      background: linear-gradient(145deg, #f5b5ff, #b794f4);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      font-weight: 800;
    }

    .hero p {
      font-size: 1.4rem;
      margin: 1.5rem 0 2rem;
      color: rgba(255,255,255,0.7);
      font-weight: 300;
      letter-spacing: 0.5px;
    }

    .btn-glow {
      background: rgba(255,255,255,0.05);
      backdrop-filter: blur(6px);
      border: 1px solid rgba(255,255,255,0.2);
      padding: 1rem 2.5rem;
      border-radius: 50px;
      font-size: 1.2rem;
      font-weight: 600;
      color: white;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 10px 20px -8px rgba(0,0,0,0.4);
      border: none;
      background: linear-gradient(125deg, #8e77e3, #b085f0);
    }

    .btn-glow:hover {
      transform: scale(1.05);
      box-shadow: 0 0 25px #c4a1ff;
    }

    /* section style */
    .section {
      max-width: 1200px;
      margin: 5rem auto;
      padding: 0 2rem;
    }

    .section-title {
      font-size: 2.5rem;
      font-weight: 700;
      background: linear-gradient(145deg, #23233b, #41416e);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin-bottom: 2rem;
      display: inline-block;
      border-left: 8px solid #9f7aea;
      padding-left: 1rem;
    }

    /* about card */
    .about-card {
      background: white;
      border-radius: 2rem;
      padding: 2.5rem;
      box-shadow: 0 30px 40px -20px rgba(0,0,0,0.2);
      display: flex;
      align-items: center;
      gap: 3rem;
      flex-wrap: wrap;
      backdrop-filter: blur(4px);
      border: 1px solid rgba(255,255,255,0.6);
    }

    .about-card img {
      width: 200px;
      height: 200px;
      border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
      object-fit: cover;
      box-shadow: 20px 20px 30px rgba(0,0,0,0.1);
      border: 4px solid white;
      transition: 0.4s ease;
    }

    .about-card img:hover {
      border-radius: 50% 50% 30% 70% / 40% 50% 50% 60%;
    }

    .about-card p {
      font-size: 1.3rem;
      color: #2d2d44;
      font-weight: 400;
      max-width: 600px;
    }

    /* project grid — 3D cards */
    .project-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 2rem;
      margin-top: 2rem;
    }

    .project-card {
      background: rgba(255,255,255,0.7);
      backdrop-filter: blur(8px);
      border-radius: 2rem;
      padding: 2rem 1.5rem;
      box-shadow: 0 20px 30px -10px rgba(0,0,0,0.15), 0 0 0 1px rgba(255,255,255,0.8) inset;
      transition: transform 0.25s ease, box-shadow 0.3s ease;
      text-align: center;
      border: 1px solid rgba(255,255,255,0.7);
    }

    .project-card:hover {
      transform: translateY(-12px) scale(1.02);
      box-shadow: 0 35px 40px -15px #b2a2d9;
    }

    .project-icon {
      font-size: 3rem;
      margin-bottom: 1rem;
      background: linear-gradient(135deg, #46467a, #a181d6);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .project-card h3 {
      font-size: 1.8rem;
      font-weight: 600;
      margin-bottom: 0.8rem;
      color: #20203a;
    }

    .project-card p {
      color: #4a4a66;
      margin-bottom: 1.8rem;
    }

    .project-btn {
      background: #1e1e30;
      border: none;
      color: white;
      padding: 0.8rem 2rem;
      border-radius: 3rem;
      font-weight: 600;
      cursor: pointer;
      transition: 0.2s;
      box-shadow: 0 5px 15px #afa0dd;
      border: 1px solid #9289c0;
    }

    .project-btn:hover {
      background: #302e4a;
      box-shadow: 0 8px 22px #bba8ff;
    }

    /* iframe panel */
    .iframe-panel {
      background: #11121f;
      border-radius: 2rem;
      margin: 3rem 0 1rem;
      padding: 0.5rem;
      box-shadow: 0 25px 40px -10px #1a1a2e;
    }

    iframe {
      width: 100%;
      height: 550px;
      border: none;
      border-radius: 1.5rem;
      background: white;
      display: none;
      box-shadow: inset 0 0 20px #00000010;
    }

    iframe.active-iframe {
      display: block;
    }

    /* contact form — advanced */
    .contact-container {
      background: white;
      border-radius: 2.5rem;
      padding: 3rem;
      box-shadow: 0 40px 50px -20px #aea0d4;
      background: linear-gradient(145deg, #ffffff, #f6f3ff);
    }

    .form-group {
      margin-bottom: 1.8rem;
      position: relative;
    }

    .form-group i {
      position: absolute;
      left: 20px;
      top: 50%;
      transform: translateY(-50%);
      color: #8f85c9;
      font-size: 1.2rem;
    }

    input, textarea {
      width: 100%;
      padding: 1.2rem 1.2rem 1.2rem 3rem;
      border: 2px solid #e4e0f0;
      border-radius: 3rem;
      font-size: 1rem;
      transition: 0.2s;
      background: rgba(255,255,255,0.7);
    }

    textarea {
      padding-left: 3rem;
      border-radius: 2rem;
      resize: vertical;
    }

    input:focus, textarea:focus {
      border-color: #a28bd7;
      outline: none;
      box-shadow: 0 0 0 5px rgba(161, 128, 219, 0.2);
    }

    .send-btn {
      background: linear-gradient(95deg, #40407a, #7d67b5);
      color: white;
      border: none;
      padding: 1.2rem 2.5rem;
      border-radius: 4rem;
      font-size: 1.3rem;
      font-weight: 600;
      cursor: pointer;
      transition: 0.2s;
      box-shadow: 0 10px 20px #b5a5e0;
      display: inline-flex;
      align-items: center;
      gap: 12px;
    }

    .send-btn:hover {
      background: linear-gradient(95deg, #56569b, #957edb);
      box-shadow: 0 18px 30px #bbaef0;
      transform: scale(1.02);
    }

    footer {
      background: #0c0c18;
      color: #aaaaca;
      text-align: center;
      padding: 2rem;
      font-size: 1rem;
      border-top-left-radius: 3rem;
      border-top-right-radius: 3rem;
      margin-top: 5rem;
    }

    /* responsiveness */
    @media (max-width: 700px) {
      .navbar {
        flex-direction: column;
        gap: 0.5rem;
      }
      .hero h1 {
        font-size: 2.8rem;
      }
      .about-card {
        justify-content: center;
        text-align: center;
      }
    }
  </style>
</head>
<body>
  <!-- sticky navbar -->
  <nav class="navbar">
    <span class="logo">⋆⭒˚. MR_JOEL</span>
    <div class="nav-links">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </div>
  </nav>

  <!-- Hero -->
  <section id="home" class="hero">
    <div class="hero-content">
      <h1>Hello, I'm <span class="highlight">MR__JOEL R</span></h1>
      <p>design-minded · code enthusiast · student</p>
      <button class="btn-glow" onclick="document.getElementById('projects').scrollIntoView({behavior:'smooth'})">
        <i class="fas fa-arrow-down" style="margin-right: 8px;"></i>View my work
      </button>
    </div>
  </section>

  <!-- About Section (clean) -->
  <section id="about" class="section">
    <h2 class="section-title">about me</h2>
    <div class="about-card">
      <!-- photo placeholder (keep same name) -->
      <img src="IMG-20250912-WA0034.jpg" alt="profile" onerror="this.src='https://via.placeholder.com/300x300/1e1e2f/ffffff?text=📸'">
      <div>
        <p style="font-size: 1.6rem; font-weight: 500;">👨🏻‍💻 JOEL</p>
        <p style="font-size: 1.2rem;">I'm deeply enthusiastic about interaction design and modern web tools. I craft pixel‑perfect experiences and love breathing life into code. currently exploring creative dev & 3D web.</p>
        <div style="margin-top: 1.5rem; display: flex; gap: 1.5rem;">
          <i class="fab fa-react fa-2x" style="color:#6c5f9e;"></i>
          <i class="fab fa-js fa-2x" style="color:#dbbc74;"></i>
          <i class="fab fa-figma fa-2x" style="color:#a68bc7;"></i>
        </div>
      </div>
    </div>
  </section>

  <!-- Projects section -->
  <section id="projects" class="section">
    <h2 class="section-title">creative projects</h2>
    <div class="project-grid">
      <div class="project-card">
        <div class="project-icon"><i class="fas fa-laptop-code"></i></div>
        <h3>responsive website</h3>
        <p>fluid grid, smart sidebar, fully adaptive.</p>
        <button class="project-btn" onclick="showProject('responsive')"><i class="fas fa-eye"></i> preview</button>
      </div>
      <div class="project-card">
        <div class="project-icon"><i class="fas fa-question-circle"></i></div>
        <h3>quiz app</h3>
        <p>interactive js quiz with instant scoring.</p>
        <button class="project-btn" onclick="showProject('quiz')"><i class="fas fa-eye"></i> preview</button>
      </div>
      <div class="project-card">
        <div class="project-icon"><i class="fas fa-pencil-alt"></i></div>
        <h3>personal blog</h3>
        <p>CMS‑ready, dynamic post container.</p>
        <button class="project-btn" onclick="showProject('blog')"><i class="fas fa-eye"></i> preview</button>
      </div>
    </div>

    <!-- iframe preview panel (project iframes enhanced) -->
    <div class="iframe-panel">
      <!-- responsive iframe -->
      <iframe id="responsive" class="active-iframe" srcdoc='
      <html>
      <head><style>body{margin:0;font-family:"Inter",sans-serif;background:#f2f0fa;}header{background:#21213b;color:white;padding:1.5rem;text-align:center;}nav{display:flex;gap:2rem;justify-content:center;background:#2f2f4a;padding:0.8rem;}nav a{color:white;text-decoration:none;}nav a:hover{color:#cfb3ff;}.container{display:grid;grid-template-columns:3fr 1fr;gap:2rem;padding:2rem;}.content{background:white;padding:2rem;border-radius:2rem;}.sidebar{background:#e7deff;padding:2rem;border-radius:2rem;}footer{text-align:center;padding:1.5rem;background:#21213b;color:white;}@media(max-width:700px){.container{grid-template-columns:1fr;}}</style></head>
      <body><header><h1>⋆ responsive lab</h1></header><nav><a>Home</a><a>Work</a><a>Contact</a></nav><div class="container"><div class="content"><h2>main content</h2><p>built with flex & grid — smooth.</p></div><div class="sidebar"><h3>extra</h3><p>sidebar adapts</p></div></div><footer>&copy; 2025 JOEL</footer></body></html>'></iframe>

      <!-- quiz iframe (with two sample questions) -->
      <iframe id="quiz" srcdoc='
      <html><head><style>body{background:linear-gradient(145deg,#35355e,#202035);display:flex;justify-content:center;align-items:center;min-height:100vh;margin:0;font-family:"Inter";}.quiz-card{background:rgba(255,255,255,0.95);padding:2.5rem;border-radius:3rem;width:90%;max-width:500px;box-shadow:0 30px 40px #00000040;}.question{font-size:1.5rem;font-weight:600;margin-bottom:1rem;}.options label{display:block;margin:0.8rem 0;background:#eeebf7;padding:0.8rem 1.5rem;border-radius:3rem;cursor:pointer;transition:0.2s;}.options label:hover{background:#d7cdf3;}.btn-submit{background:#30305a;color:white;border:none;padding:0.8rem 2rem;border-radius:4rem;font-size:1.1rem;margin-top:1rem;}.result{font-weight:bold;margin-top:1rem;}</style></head>
      <body><div class="quiz-card" id="root"><div class="question" id="qtext">loading...</div><div class="options" id="options"></div><button class="btn-submit" id="submitBtn">submit</button><div class="result" id="resultDisplay"></div></div>
      <script>
        const q=[{q:"which tag is for line break?",a:"&lt;br&gt;",b:"&lt;lb&gt;",c:"&lt;break&gt;",d:"&lt;hr&gt;",correct:"a"},{q:"largest heading?",a:"&lt;h1&gt;",b:"&lt;h6&gt;",c:"&lt;heading&gt;",d:"&lt;h0&gt;",correct:"a"}];let idx=0,score=0;const qtext=document.getElementById("qtext"),optionsDiv=document.getElementById("options"),resDiv=document.getElementById("resultDisplay");function render(){if(idx>=q.length){optionsDiv.innerHTML="";document.getElementById("submitBtn").style.display="none";resDiv.innerText="✨ you scored "+score+"/"+q.length;return;}let cur=q[idx];qtext.innerText=cur.q;let html="";for(let key of["a","b","c","d"]){html+=\`<label><input type="radio" name="opt" value="\${key}"> \${cur[key]}</label>\`;}optionsDiv.innerHTML=html;}render();document.getElementById("submitBtn").onclick=()=>{let selected=document.querySelector("input[name=opt]:checked");if(!selected)return;if(selected.value===q[idx].correct)score++;idx++;render();};
      </script></body></html>'></iframe>

      <!-- blog iframe -->
      <iframe id="blog" srcdoc='
      <html><head><style>body{background:#f0ebf8;font-family:"Inter";padding:1rem;}.blog-header{background:white;border-radius:2rem;padding:2rem;text-align:center;margin-bottom:2rem;}.post-card{background:white;border-radius:1.8rem;padding:1.8rem;margin-bottom:1rem;box-shadow:0 4px 10px #00000010;}.date{color:#7777a0;font-size:0.9rem;}</style></head>
      <body><div class="blog-header"><h2>📝 joel''s blog</h2><p>latest thoughts</p></div><div id="postContainer"></div>
      <script>const posts=[{title:"first day of spring",date:new Date(),content:"coded a new component 🌱"},{title:"portfolio launch",date:new Date(),content:"my new site is alive!"}];const container=document.getElementById("postContainer");posts.forEach(p=>{container.innerHTML+=\`<div class="post-card"><h3>\${p.title}</h3><div class="date">\${p.date.toLocaleString()}</div><p>\${p.content}</p></div>\`})</script></body></html>'></iframe>
    </div>
  </section>

  <!-- Contact section – modern -->
  <section id="contact" class="section">
    <h2 class="section-title">let's connect</h2>
    <div class="contact-container">
      <form id="portfolioForm" onsubmit="event.preventDefault(); alert('✨ Thanks for your message (demo)');">
        <div class="form-group">
          <i class="fas fa-user"></i>
          <input type="text" placeholder="your name" required>
        </div>
        <div class="form-group">
          <i class="fas fa-envelope"></i>
          <input type="email" placeholder="email address" required>
        </div>
        <div class="form-group">
          <i class="fas fa-pen"></i>
          <textarea rows="4" placeholder="what would you like to say?"></textarea>
        </div>
        <button type="submit" class="send-btn"><i class="fas fa-paper-plane"></i> send message</button>
      </form>
    </div>
  </section>

  <footer>
    <p>© 2025 MR__JOEL R · built with ⚡ and stardust</p>
    <p style="margin-top: 0.8rem;">
      <i class="fab fa-github" style="margin: 0 10px;"></i>
      <i class="fab fa-linkedin" style="margin: 0 10px;"></i>
      <i class="fab fa-codepen" style="margin: 0 10px;"></i>
    </p>
  </footer>

  <script>
    function showProject(id) {
      // hide all iframes
      document.querySelectorAll('iframe').forEach(iframe => {
        iframe.classList.remove('active-iframe');
      });
      // show selected
      const target = document.getElementById(id);
      if (target) {
        target.classList.add('active-iframe');
        target.scrollIntoView({ behavior: 'smooth', block: 'center' });
      }
    }

    // set first iframe active on page load (responsive shown)
    window.onload = function() {
      // ensure only responsive iframe visible initially
      document.querySelectorAll('iframe').forEach(ifr => ifr.classList.remove('active-iframe'));
      const resp = document.getElementById('responsive');
      if (resp) resp.classList.add('active-iframe');
    }
  </script>
</body>
</html>
