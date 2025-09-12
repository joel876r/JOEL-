<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,initial-scale=1.0">
  <title>Student Portfolio</title>
  <style>
    * {margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif;}
    body {line-height:1.6;background:#f9f9f9;color:#333;}
    header {background:#333;color:#fff;padding:1rem;text-align:center;}
    nav {display:flex;justify-content:center;background:#444;flex-wrap:wrap;}
    nav a {color:white;padding:1rem;text-decoration:none;}
    nav a:hover {background:#666;}
    .hero {padding:3rem;text-align:center;background:#eee;}
    .about, .projects, .contact {padding:2rem;max-width:900px;margin:auto;}
    .about img {width:150px;border-radius:50%;margin-right:20px;}
    .about-content {display:flex;align-items:center;gap:20px;flex-wrap:wrap;}
    .project-grid {display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:1rem;}
    .project-card {background:#fff;padding:1rem;border-radius:8px;box-shadow:0 0 5px rgba(0,0,0,0.1);text-align:center;}
    .project-card button {margin-top:10px;padding:8px 12px;background:#333;color:white;border:none;border-radius:5px;cursor:pointer;}
    .project-card button:hover {background:#555;}
    iframe {width:100%;height:500px;border:1px solid #ccc;margin-top:15px;display:none;}
    form {display:flex;flex-direction:column;gap:10px;}
    input, textarea {padding:10px;border:1px solid #ccc;border-radius:5px;}
    button[type="submit"] {background:#333;color:white;padding:10px;border:none;border-radius:5px;cursor:pointer;}
    footer {text-align:center;background:#333;color:white;padding:1rem;margin-top:1rem;}
  </style>
</head>
<body>

  <!-- Navbar -->
  <header>
    <h1>MyPortfolio</h1>
  </header>
  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>

  <!-- Hero -->
  <section id="home" class="hero">
    <h1>Hello, I'm <span>MR__JOEL R</span></h1>
    <p>I am a student</p>
    <a href="#projects"><button>View My Work</button></a>
  </section>

  <!-- About -->
  <section id="about" class="about">
    <h2>About Me</h2>
    <div class="about-content">
      <img src="IMG-20250912-WA0034.jpg" alt="Profile Photo">
      <p>I am a student enthusiastic about technology and design. I love building interactive,
        user-friendly web applications and exploring new tools in the tech world.</p>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects" class="projects">
    <h2>My Projects</h2>
    <div class="project-grid">
      <div class="project-card">
        <h3>Responsive Website</h3>
        <p>A simple responsive website.</p>
        <button onclick="showProject('responsive')">Open</button>
      </div>
      <div class="project-card">
        <h3>Quiz App</h3>
        <p>JavaScript-based quiz app.</p>
        <button onclick="showProject('quiz')">Open</button>
      </div>
      <div class="project-card">
        <h3>Blog</h3>
        <p>Personal blog with CMS.</p>
        <button onclick="showProject('blog')">Open</button>
      </div>
    </div>

    <!-- Iframes for projects -->
    <iframe id="responsive" srcdoc='
      <html><head><style>
      body{font-family:Arial;margin:0}header{background:#333;color:#fff;padding:1rem;text-align:center}
      nav{display:flex;justify-content:center;background:#444}nav a{color:#fff;padding:1rem;text-decoration:none}
      nav a:hover{background:#666}.container{display:grid;grid-template-columns:3fr 1fr;gap:1rem;padding:1rem}
      .content{background:#f4f4f4;padding:1rem;border-radius:8px}.sidebar{background:#e2e2e2;padding:1rem;border-radius:8px}
      footer{text-align:center;background:#333;color:#fff;padding:1rem;margin-top:1rem}
      @media(max-width:768px){.container{grid-template-columns:1fr}}
      </style></head><body>
      <header><h1>My Responsive Website</h1></header>
      <nav><a href="#">Home</a><a href="#">About</a><a href="#">Services</a><a href="#">Contact</a></nav>
      <div class="container"><div class="content"><h2>Main Content</h2><p>Responsive design example.</p></div>
      <div class="sidebar"><h3>Sidebar</h3><p>Extra info.</p></div></div>
      <footer>&copy; 2025 Responsive Site</footer></body></html>'></iframe>

    <iframe id="quiz" srcdoc='
      <html><head><style>
      body{display:flex;justify-content:center;align-items:center;height:100vh;background:#f4f4f4;font-family:Arial}
      .quiz-container{background:white;padding:20px;border-radius:10px;width:90%;max-width:500px;box-shadow:0 0 10px rgba(0,0,0,0.2)}
      h2{margin-bottom:15px}button{background:#333;color:white;padding:10px 15px;border:none;border-radius:5px;cursor:pointer}
      button:hover{background:#555}.result{font-size:18px;font-weight:bold;text-align:center}
      </style></head><body>
      <div class="quiz-container" id="quiz">
        <h2 id="question">Question text</h2>
        <ul>
          <li><label><input type="radio" name="answer" class="answer" id="a"> <span id="a_text">A</span></label></li>
          <li><label><input type="radio" name="answer" class="answer" id="b"> <span id="b_text">B</span></label></li>
          <li><label><input type="radio" name="answer" class="answer" id="c"> <span id="c_text">C</span></label></li>
          <li><label><input type="radio" name="answer" class="answer" id="d"> <span id="d_text">D</span></label></li>
        </ul>
        <button id="submit">Submit</button>
        <div class="result" id="result"></div>
      </div>
      <script>
        const quizData=[{question:"Which tag inserts a line break?",a:"<br>",b:"<lb>",c:"<break>",d:"<newline>",correct:"a"},
        {question:"Largest heading?",a:"<h1>",b:"<h6>",c:"<h3>",d:"<heading>",correct:"a"}];
        const q=document.getElementById("question"),a_text=document.getElementById("a_text"),b_text=document.getElementById("b_text"),
        c_text=document.getElementById("c_text"),d_text=document.getElementById("d_text"),submit=document.getElementById("submit"),
        result=document.getElementById("result"),answers=document.querySelectorAll(".answer");let current=0,score=0;loadQuiz();
        function loadQuiz(){answers.forEach(a=>a.checked=false);q.innerText=quizData[current].question;a_text.innerText=quizData[current].a;
          b_text.innerText=quizData[current].b;c_text.innerText=quizData[current].c;d_text.innerText=quizData[current].d;}
        function getSelected(){let ans;answers.forEach(a=>{if(a.checked)ans=a.id});return ans;}
        submit.onclick=()=>{const ans=getSelected();if(ans){if(ans===quizData[current].correct)score++;current++;
          if(current<quizData.length)loadQuiz();else result.innerHTML="You scored "+score+"/"+quizData.length;}} 
      </script></body></html>'></iframe>

    <iframe id="blog" srcdoc='
      <html><head><style>
      body{font-family:Arial;margin:0;background:#f9f9f9;color:#333}header{background:#333;color:#fff;padding:1rem;text-align:center}
      .container{max-width:800px;margin:20px auto;padding:10px}.post{background:white;padding:15px;margin-bottom:20px;
      border-radius:8px;box-shadow:0 0 5px rgba(0,0,0,0.1)}.post h2{margin:0 0 10px}.post small{color:gray;font-size:12px}
      </style></head><body>
      <header><h1>My Blog</h1><p>Welcome to my personal blog!</p></header>
      <div class="container" id="postsContainer"></div>
      <script>
        const posts=[{title:"My First Post",date:Date.now(),content:"This is a sample blog post!"}];
        const cont=document.getElementById("postsContainer");
        posts.reverse().forEach(p=>{cont.innerHTML+=`<div class="post"><h2>${p.title}</h2><small>${new Date(p.date).toLocaleString()}</small><p>${p.content}</p></div>`});
      </script></body></html>'></iframe>
  </section>

  <!-- Contact -->
  <section id="contact" class="contact">
    <h2>Contact Me</h2>
    <form>
      <input type="text" placeholder="Your Name" required>
      <input type="email" placeholder="Your Email" required>
      <textarea placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 MR__JOEL R | All rights reserved</p>
  </footer>

  <script>
    function showProject(id){
      document.querySelectorAll("iframe").forEach(f=>f.style.display="none");
      document.getElementById(id).style.display="block";
      document.getElementById(id).scrollIntoView({behavior:"smooth"});
    }
  </script>
</body>
</html>
