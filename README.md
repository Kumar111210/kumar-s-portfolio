<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Portfolio of Banavath Kumar, an aspiring full-stack developer and data engineer.">
  <meta name="keywords" content="Banavath Kumar, portfolio, full-stack developer, data engineer, web development">
  <meta name="author" content="Banavath Kumar">
  <title>Banavath Kumar - Portfolio</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }
    body {
      background: #1a1a1a;
      color: #fff;
      line-height: 1.6;
    }
    section {
      padding: 80px 10%;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
    }
    .section-content {
      display: grid;
      grid-template-columns: 1fr 3fr;
      gap: 40px;
      max-width: 1200px;
      width: 100%;
      align-items: center;
    }
    .section-content.reverse {
      grid-template-columns: 3fr 1fr;
    }
    .side-image {
      width: 100%;
      max-width: 300px;
      border-radius: 5px;
      object-fit: cover;
      transition: transform 0.3s, box-shadow 0.3s;
      opacity: 0;
      transform: translateX(-50px);
    }
    .side-image.visible {
      opacity: 1;
      transform: translateX(0);
      transition: opacity 0.5s, transform 0.5s;
    }
    .side-image:hover {
      transform: scale(1.05);
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
    }
    .side-image.float {
      animation: float 3s ease-in-out infinite;
    }
    @keyframes float {
      0%, 100% { transform: translateY(-10px); }
      50% { transform: translateY(10px); }
    }
    h1, h2 {
      font-size: 2.5rem;
      margin-bottom: 20px;
      color: #00ff88;
      font-weight: 700;
    }
    p {
      font-size: 1.2rem;
      max-width: 800px;
      text-align: center;
    }
    .home {
      background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://source.unsplash.com/random/1920x1080?tech');
      background-size: cover;
      background-attachment: fixed;
      text-align: center;
    }
    .profile-container {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 20px;
      margin-bottom: 20px;
      position: relative;
    }
    .profile-box {
      position: relative;
      animation: floatSide 4s ease-in-out infinite;
      border: 4px solid;
      border-radius: 50%;
      animation: borderColorCycle 6s infinite;
    }
    @keyframes floatSide {
      0%, 100% { transform: translate(0, -10px); }
      25% { transform: translate(10px, 0); }
      50% { transform: translate(0, 10px); }
      75% { transform: translate(-10px, 0); }
    }
    @keyframes borderColorCycle {
      0% { border-color: #00ff88; }
      25% { border-color: #33ccff; }
      50% { border-color: #ff3366; }
      75% { border-color: #ffcc00; }
      100% { border-color: #00ff88; }
    }
    .profile-pic-container {
      position: relative;
    }
    .profile-pic {
      width: 200px;
      height: 200px;
      border-radius: 50%;
      object-fit: cover;
      border: 6px solid transparent;
      background: linear-gradient(45deg, #00ff88, #00cc70, #33ccff) border-box;
      animation: borderRotate 5s linear infinite;
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .profile-pic:hover {
      transform: scale(1.1);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.5);
    }
    .profile-pic-container::before {
      content: '';
      position: absolute;
      top: -20px;
      left: -20px;
      right: -20px;
      bottom: -20px;
      background: radial-gradient(circle, rgba(0, 255, 136, 0.2), transparent);
      z-index: -1;
      border-radius: 50%;
    }
    @keyframes borderRotate {
      0% { border-image: linear-gradient(45deg, #00ff88, #00cc70, #33ccff) 1; }
      100% { border-image: linear-gradient(405deg, #00ff88, #00cc70, #33ccff) 1; }
    }
    .home-icon {
      color: #fff;
      font-size: 30px;
      cursor: pointer;
      transition: color 0.3s;
    }
    .home-icon:hover {
      color: #00cc70;
    }
    .nav-menu {
      display: none;
      position: absolute;
      top: 100%;
      left: 50%;
      transform: translateX(-50%);
      background: #333;
      padding: 20px;
      border-radius: 5px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
      z-index: 999;
      opacity: 0;
      animation: fadeInMenu 0.3s ease-out forwards;
    }
    .nav-menu.active {
      display: block;
    }
    @keyframes fadeInMenu {
      to { opacity: 1; }
    }
    .nav-menu a {
      display: block;
      color: #fff;
      text-decoration: none;
      font-size: 18px;
      margin: 10px 0;
      transition: color 0.3s;
    }
    .nav-menu a:hover {
      color: #00ff88;
    }
    .subtitle {
      font-size: 1.4rem;
      color: #fff;
      margin-bottom: 20px;
      opacity: 0;
      animation: fadeIn 1s ease-in forwards 0.5s;
    }
    @keyframes fadeIn {
      to { opacity: 1; }
    }
    .home .tagline {
      font-size: 1.5rem;
      color: #fff;
      margin: 20px 0;
      min-height: 30px;
      opacity: 0;
      transform: translateY(20px);
      animation: slideUp 0.5s ease-out forwards;
    }
    @keyframes slideUp {
      to { opacity: 1; transform: translateY(0); }
    }
    .btn {
      display: inline-block;
      padding: 10px 20px;
      background: #00ff88;
      color: #000;
      text-decoration: none;
      border-radius: 5px;
      margin-top: 20px;
      transition: background 0.3s, transform 0.3s;
    }
    .btn:hover {
      background: #00cc70;
      transform: translateY(-3px);
    }
    .timeline {
      position: relative;
      max-width: 800px;
      margin: 20px auto;
    }
    .timeline::before {
      content: '';
      position: absolute;
      width: 6px;
      background: #00ff88;
      top: 0;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
    }
    .timeline-item {
      padding: 10px 40px;
      position: relative;
      width: 50%;
      margin-bottom: 20px;
    }
    .timeline-item:nth-child(odd) {
      left: 0;
    }
    .timeline-item:nth-child(even) {
      left: 50%;
    }
    .timeline-item::before {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: #00ff88;
      border-radius: 50%;
      top: 15px;
      right: -13px;
    }
    .timeline-item:nth-child(even)::before {
      left: -13px;
    }
    .timeline-item.float {
      animation: float 3s ease-in-out infinite;
    }
    .timeline-content {
      padding: 20px;
      background: #333;
      border-radius: 5px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
      border: 3px solid;
      animation: borderColorCycle 6s infinite;
    }
    .timeline-item:nth-child(2) .timeline-content {
      animation-delay: 1s;
    }
    .timeline-item:nth-child(3) .timeline-content {
      animation-delay: 2s;
    }
    .timeline-content:hover {
      transform: translateY(-5px);
    }
    .skills-list, .projects-list {
      list-style: none;
      padding: 0;
      margin: 20px 0;
      text-align: left;
    }
    .skills-list li, .projects-list li {
      padding: 10px;
      background: #333;
      border-radius: 5px;
      margin-bottom: 10px;
      border: 3px solid;
      animation: borderColorCycle 6s infinite;
    }
    .skills-list li:hover, .projects-list li:hover {
      transform: translateY(-5px);
      transition: transform 0.3s;
    }
    .skills-list li:nth-child(2), .projects-list li:nth-child(2) { animation-delay: 1s; }
    .skills-list li:nth-child(3), .projects-list li:nth-child(3) { animation-delay: 2s; }
    .contact-form {
      max-width: 600px;
      margin: 20px auto;
    }
    .contact-form input, .contact-form textarea {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: none;
      border-radius: 5px;
      background: #333;
      color: #fff;
      font-size: 1rem;
    }
    .contact-form button {
      background: #00ff88;
      color: #000;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s, transform 0.3s;
    }
    .contact-form button:hover {
      background: #00cc70;
      transform: translateY(-3px);
    }
    .social-icons a {
      color: #fff;
      font-size: 24px;
      margin: 0 10px;
      transition: color 0.3s, transform 0.3s;
    }
    .social-icons a:hover {
      color: #00ff88;
      transform: scale(1.2);
    }
    .contact-info {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 10px;
    }
    .contact-info span {
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .contact-info i {
      font-size: 20px;
      color: #00ff88;
      transition: color 0.3s, transform 0.3s;
    }
    .contact-info i:hover {
      color: #00cc70;
      transform: scale(1.2);
    }
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.8);
      align-items: center;
      justify-content: center;
      z-index: 1000;
    }
    .modal-content {
      background: #333;
      padding: 20px;
      border-radius: 5px;
      max-width: 600px;
      text-align: center;
    }
    .modal-content img {
      max-width: 100%;
      border-radius: 5px;
    }
    .close {
      position: absolute;
      top: 10px;
      right: 20px;
      font-size: 24px;
      cursor: pointer;
      color: #fff;
    }
    @media (max-width: 768px) {
      section {
        padding: 60px 5%;
      }
      .section-content, .section-content.reverse {
        grid-template-columns: 1fr;
        gap: 20px;
      }
      .side-image {
        max-width: 200px;
        margin: 0 auto;
      }
      .profile-container {
        flex-direction: column;
        gap: 10px;
      }
      .profile-pic {
        width: 150px;
        height: 150px;
      }
      .profile-box {
        animation: float 3s ease-in-out infinite;
      }
      .home-icon {
        font-size: 24px;
      }
      .nav-menu {
        width: 80%;
        max-width: 300px;
        top: 220px;
      }
      h1, h2 {
        font-size: 2rem;
      }
      .subtitle {
        font-size: 1.2rem;
      }
      .timeline::before {
        left: 20px;
      }
      .timeline-item {
        width: 100%;
        padding-left: 60px;
        padding-right: 20px;
      }
      .timeline-item:nth-child(even) {
        left: 0;
      }
      .timeline-item::before {
        left: 7px;
      }
      .timeline-item:nth-child(even)::before {
        left: 7px;
      }
    }
  </style>
</head>
<body>
  <!-- Home Section -->
  <section id="home" class="home">
    <div class="section-content">
      <img src="images/green.jpg" alt="Technology illustration" class="side-image float">
      <div>
        <div class="profile-container">
          <div class="profile-box">
            <div class="profile-pic-container">
             
            </div>
          </div>
          <div class="nav-toggle">
            <i class="fas fa-home home-icon" onclick="toggleProfileNavMenu()" aria-label="Toggle navigation menu" tabindex="0"></i>
            <div class="nav-menu" id="nav-menu">
              <a href="#home" aria-label="Home section">Home</a>
              <a href="#about" aria-label="About section">About</a>
              <a href="#education" aria-label="Education section">Education</a>
              <a href="#skills" aria-label="Skills section">Skills</a>
              <a href="#certifications" aria-label="Certifications section">Certifications</a>
              <a href="#projects" aria-label="Projects section">Projects</a>
              <a href="#experience" aria-label="Experience section">Experience</a>
              <a href="#activities" aria-label="Activities section">Activities</a>
              <a href="#contact" aria-label="Contact section">Contact</a>
            </div>
          </div>
        </div>
        <h1>Banavath Kumar</h1>
        <p class="subtitle">Currently Pursuing B.Tech in Computer Science and Engineering, Nalla Malla Reddy Engineering College</p>
        <div class="tagline" id="typewriter"></div>
        <a href="#about" class="btn" aria-label="Explore portfolio">Explore My Work</a>
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section id="about">
    <div class="section-content">
      <img src="images/black.jpg" alt="Leadership illustration" class="side-image float">
      <div>
        <h2>About Me</h2>
        <p>I'm a B.Tech student pursuing Computer Science and Engineering at Nalla Malla Reddy Engineering College with a GPA of 8.0. As a class representative, I foster teamwork and positivity. My goal is to create impactful tech solutions as a full-stack developer and data engineer.</p>
        <div class="timeline">
          <div class="timeline-item float">
            <div class="timeline-content">
              <h3>2021</h3>
              <p>Started B.Tech in Computer Science and Engineering</p>
            </div>
          </div>
          <div class="timeline-item float">
            <div class="timeline-content">
              <h3>2023</h3>
              <p>Earned Certifications in Data Engineering and Full-Stack Development</p>
            </div>
          </div>
          <div class="timeline-item float">
            <div class="timeline-content">
              <h3>2025</h3>
              <p>Currently pursuing B.Tech, GPA 8.0 (3-1)</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Education Section -->
  <section id="education">
    <div class="section-content">
      <img src="images/edu.jpg" alt="Graduation illustration" class="side-image float">
      <div>
        <h2>Education</h2>
        <p><strong>Nalla Malla Reddy Engineering College (JNTUH)</strong><br>
        Bachelor of Technology in Computer Science and Engineering (Pursuing)<br>
        GPA: 8.0 (3-1)<br>
        Relevant Courses: Computer Architecture, Software Development, Web Development, Frontend & Backend Development</p>
        <a href="#" class="btn" aria-label="Download academic transcript">Download Transcript (Coming Soon)</a>
      </div>
    </div>
  </section>

  <!-- Skills Section -->
  <section id="skills">
    <div class="section-content reverse">
      <div>
        <h2>Technical Skills</h2>
        <ul class="skills-list">
          <li aria-label="Python skill with 90% proficiency">Python - Proficiency: 90%</li>
          <li aria-label="Java skill with 85% proficiency">Java - Proficiency: 85%</li>
          <li aria-label="HTML/CSS skill with 80% proficiency">HTML/CSS - Proficiency: 80%</li>
          <li aria-label="JavaScript skill with 75% proficiency">JavaScript - Proficiency: 75%</li>
          <li aria-label="SQL skill with 70% proficiency">SQL - Proficiency: 70%</li>
          <li aria-label="Communication skill with 95% proficiency">Communication - Proficiency: 95%</li>
        </ul>
      </div>
      <img src="images/Screenshot 2025-05-17 185715.png" alt="Coding setup" class="side-image float">
    </div>
  </section>

  <!-- Certifications Section -->
  <section id="certifications">
    <div class="section-content reverse">
      <div>
        <h2>Certifications</h2>
        <ul class="skills-list">
          <li onclick="openModal('Learned data pipelines and analytics.')" aria-label="Data Engineering certification from AICTE">Data Engineering - AICTE</li>
          <li onclick="openModal('Mastered Spring Boot, Hibernate, and React.')" aria-label="Java Full Stack certification from AICTE">Java Full Stack - AICTE</li>
          <li onclick="openModal('Built projects with Django and Flask.')" aria-label="Python Full Stack certification from AICTE">Python Full Stack - AICTE</li>
          <li onclick="openModal('Learned user-centered design principles.')" aria-label="UI/UX Basics certification">UI/UX Basics - Online</li>
          <li onclick="openModal('Studied cybersecurity and penetration testing.')" aria-label="Ethical Hacking certification">Ethical Hacking - Online</li>
        </ul>
      </div>
      <img src="images/Screenshot 2025-05-17 190211.png" alt="Certificate illustration" class="side-image float">
    </div>
  </section>

  <!-- Projects Section -->
  <section id="projects">
    <div class="section-content">
      <img src="images/Screenshot 2025-04-14 213427.png" alt="Web app mockup" class="side-image float">
      <div>
        <h2>Projects</h2>
        <ul class="projects-list">
          <li onclick="openModal('Promotes mental health awareness and stress reduction for employees and students.\n\nTech Stack: HTML, CSS, JavaScript')" aria-label="Social Outreach Project">Social Outreach Project - Promotes mental health awareness...</li>
          <li onclick="openModal('Web app simulating on-campus and off-campus placements.\n\nTech Stack: HTML, CSS, TypeScript, MongoDB')" aria-label="Campus Recruitment System">Campus Recruitment System - Web app simulating placements...</li>
          <li onclick="openModal('Details coming soon.\n\nTech Stack: TBD')" aria-label="Mini Project">Mini Project - Details coming soon...</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- Experience Section -->
  <section id="experience">
    <div class="section-content reverse">
      <div>
        <h2>Experience</h2>
        <p><strong>Class Representative</strong><br>
        - Fostered teamwork and motivated peers in academics and extracurriculars.<br>
        - Created a positive and supportive environment.<br>
        - Developed leadership, communication, and management skills.</p>
        <a href="#" class="btn" aria-label="Download resume">Download Resume (Coming Soon)</a>
      </div>
      <img src="images/exp.jpg" alt="Teamwork illustration" class="side-image float">
    </div>
  </section>

  <!-- Activities Section -->
  <section id="activities">
    <div class="section-content">
      <img src="images/spo.jpg" alt="Sports illustration" class="side-image float">
      <div>
        <h2>Activities</h2>
        <p>I enjoy reading inspirational books like <em>Autobiography of a Yogi</em>, playing sports (kabaddi, volleyball, cricket), watching movies, traveling, and spending time with friends.</p>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact">
    <div class="section-content">
      <img src="images/main.jpg" alt="Contact illustration" class="side-image float">
      <div>
        <h2>Contact Me</h2>
        <div class="contact-info">
          <span>
            <i class="fas fa-envelope" aria-label="Email icon"></i>
            <span>Email: kumarbanavath60@gmail.com</span>
          </span>
          <span>
            <i class="fas fa-phone" aria-label="Phone icon"></i>
            <span>Phone: 8688229823</span>
          </span>
        </div>
        <div class="social-icons">
          <a href="https://www.linkedin.com/in/banavath-kumar-5a520a2a4" target="_blank" aria-label="LinkedIn profile"><i class="fab fa-linkedin"></i></a>
          <a href="https://github.com" target="_blank" aria-label="GitHub profile"><i class="fab fa-github"></i></a>
        </div>
        <div class="contact-form">
          <input type="text" id="name" placeholder="Your Name" required aria-label="Name">
          <input type="email" id="email" placeholder="Your Email" required aria-label="Email">
          <textarea id="message" placeholder="Your Message" rows="5" required aria-label="Message"></textarea>
          <button onclick="sendEmail()" aria-label="Send message">Send Message</button>
        </div>
      </div>
    </div>
  </section>

  <!-- Modal for Certifications and Projects -->
  <div id="modal" class="modal">
    <div class="modal-content">
      <span class="close" onclick="closeModal()" aria-label="Close modal">×</span>
      <h3 id="modal-title">Details</h3>
      <p id="modal-text"></p>
    </div>
  </div>

  <!-- Back to Top Button -->
  <a href="#home" class="btn" style="position: fixed; bottom: 20px; right: 20px;" aria-label="Back to top">Back to Top</a>

  <!-- Scripts -->
  <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
  <script src="https://cdn.jsdelivr.net/npm/emailjs-com@3.2.0/dist/email.min.js"></script>
  <script>
    // Initialize EmailJS
    emailjs.init("YOUR_PUBLIC_KEY"); // Replace with your EmailJS public key

    // Typewriter Effect with Scrolling
    const typed = new Typed('#typewriter', {
      strings: ['Aspiring Full-Stack Developer', 'Data Engineer', 'Tech Enthusiast'],
      typeSpeed: 50,
      backSpeed: 30,
      backDelay: 1000,
      startDelay: 500,
      loop: true,
      showCursor: false,
      onStringTyped: () => {
        const tagline = document.querySelector('.tagline');
        tagline.style.animation = 'none';
        void tagline.offsetWidth; // Trigger reflow
        tagline.style.animation = 'slideUp 0.5s ease-out';
      }
    });

    // Toggle Profile Navigation Menu
    function toggleProfileNavMenu() {
      const menu = document.getElementById('nav-menu');
      menu.classList.toggle('active');
    }

    // Keyboard Accessibility for Home Icon
    document.querySelector('.home-icon').addEventListener('keydown', (e) => {
      if (e.key === 'Enter' || e.key === ' ') {
        e.preventDefault();
        toggleProfileNavMenu();
      }
    });

    // Scroll-Triggered Animations for Side Images
    const sideImages = document.querySelectorAll('.side-image');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, { threshold: 0.2 });
    sideImages.forEach(image => observer.observe(image));

    // Modal Functions
    function openModal(text) {
      document.getElementById('modal-text').innerText = text;
      document.getElementById('modal').style.display = 'flex';
    }
    function closeModal() {
      document.getElementById('modal').style.display = 'none';
    }

    // EmailJS Contact Form
    function sendEmail() {
      const name = document.getElementById('name').value;
      const email = document.getElementById('email').value;
      const message = document.getElementById('message').value;

      if (name && email && message) {
        emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', {
          from_name: name,
          from_email: email,
          message: message
        }).then(() => {
          alert('Message sent successfully!');
          document.getElementById('name').value = '';
          document.getElementById('email').value = '';
          document.getElementById('message').value = '';
        }).catch(() => {
          alert('Failed to send message. Please try again.');
        });
      } else {
        alert('Please fill in all fields.');
      }
    }

    // Smooth Scrolling
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function(e) {
        e.preventDefault();
        document.getElementById('nav-menu').classList.remove('active');
        document.querySelector(this.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
      });
    });
  </script>
</body>
</html>
