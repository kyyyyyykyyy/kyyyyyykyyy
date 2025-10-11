```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>KYYYYYYYKYY - Cyberpunk Profile</title>
  <style>
    body {
      background-color: #0A0F1E;
      color: #B0B0B0;
      font-family: 'Courier New', monospace;
      margin: 0;
      padding: 0;
      overflow-x: hidden;
    }
    
    .container {
      max-width: 1000px;
      margin: 0 auto;
      padding: 20px;
    }
    
    .banner {
      width: 100%;
      height: 300px;
      background: linear-gradient(45deg, #00FFFF, #FF00FF, #00FFFF);
      background-size: 400% 400%;
      animation: gradientBG 8s ease infinite;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 40px;
      border-radius: 10px;
    }
    
    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    
    .title {
      color: #00FFFF;
      font-size: 3.5em;
      font-family: 'Orbitron', monospace;
      text-shadow: 0 0 10px #00FFFF, 0 0 20px #00FFFF;
      text-align: center;
      margin: 20px 0;
      letter-spacing: 5px;
    }
    
    .subtitle {
      color: #00FFFF;
      font-size: 1.8em;
      font-family: 'Russo One', sans-serif;
      text-shadow: 0 0 8px #00FFFF;
      text-align: center;
      margin: 20px 0;
      height: 50px;
    }
    
    .stats-container {
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
      gap: 20px;
      margin: 40px 0;
    }
    
    .stat-card {
      background-color: rgba(10, 15, 30, 0.8);
      border: 1px solid #00FFFF;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 0 15px rgba(0, 255, 255, 0.5);
      flex: 1;
      min-width: 300px;
    }
    
    .stat-title {
      color: #00FFFF;
      font-size: 1.5em;
      text-align: center;
      margin-bottom: 15px;
      text-shadow: 0 0 5px #00FFFF;
    }
    
    .skills-section {
      margin: 40px 0;
    }
    
    .skills-title {
      color: #00FFFF;
      font-size: 2em;
      text-align: center;
      margin-bottom: 20px;
      text-shadow: 0 0 8px #00FFFF;
      font-family: 'Orbitron', monospace;
    }
    
    .badges-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      margin: 20px 0;
    }
    
    .badge {
      background-color: #0A0F1E;
      border: 1px solid #00FFFF;
      border-radius: 5px;
      padding: 8px 15px;
      color: #B0B0B0;
      font-weight: bold;
      display: inline-block;
      transition: all 0.3s ease;
    }
    
    .badge:hover {
      box-shadow: 0 0 10px #00FFFF;
      transform: scale(1.05);
    }
    
    .contributions-section {
      margin: 40px 0;
      text-align: center;
    }
    
    .contributions-title {
      color: #00FFFF;
      font-size: 2em;
      margin-bottom: 20px;
      text-shadow: 0 0 8px #00FFFF;
      font-family: 'Orbitron', monospace;
    }
    
    .snake-container {
      background-color: #000;
      border: 2px solid #00FFFF;
      border-radius: 10px;
      padding: 20px;
      width: 600px;
      height: 400px;
      margin: 0 auto;
      position: relative;
      overflow: hidden;
      box-shadow: 0 0 20px rgba(0, 255, 255, 0.7);
    }
    
    .grid {
      display: grid;
      grid-template-columns: repeat(20, 1fr);
      grid-gap: 2px;
      width: 100%;
      height: 100%;
    }
    
    .cell {
      background-color: #1a1f2e;
      border-radius: 2px;
      transition: background-color 0.2s;
    }
    
    .snake {
      background-color: #00FFFF;
      border-radius: 2px;
      box-shadow: 0 0 5px #00FFFF;
    }
    
    .food {
      background-color: #FF00FF;
      border-radius: 50%;
      box-shadow: 0 0 5px #FF00FF;
    }
    
    .contact-section {
      margin: 40px 0;
      text-align: center;
    }
    
    .contact-title {
      color: #00FFFF;
      font-size: 2em;
      margin-bottom: 20px;
      text-shadow: 0 0 8px #00FFFF;
      font-family: 'Orbitron', monospace;
    }
    
    .contact-links {
      display: flex;
      justify-content: center;
      gap: 15px;
      flex-wrap: wrap;
    }
    
    .contact-link {
      display: inline-block;
      padding: 10px 20px;
      background-color: #0A0F1E;
      border: 1px solid #00FFFF;
      border-radius: 5px;
      color: #B0B0B0;
      text-decoration: none;
      transition: all 0.3s ease;
    }
    
    .contact-link:hover {
      box-shadow: 0 0 10px #00FFFF;
      transform: scale(1.05);
    }
    
    .footer {
      width: 100%;
      height: 10px;
      background: linear-gradient(90deg, transparent, #00FFFF, #FF00FF, #00FFFF, transparent);
      margin: 40px 0;
      border-radius: 5px;
      animation: scanline 3s linear infinite;
    }
    
    @keyframes scanline {
      0% { opacity: 0.3; }
      50% { opacity: 1; }
      100% { opacity: 0.3; }
    }
    
    .glitch-text {
      position: relative;
    }
    
    .glitch-text::before,
    .glitch-text::after {
      content: attr(data-text);
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }
    
    .glitch-text::before {
      left: 2px;
      text-shadow: -2px 0 #FF00FF;
      clip: rect(44px, 450px, 56px, 0);
      animation: glitch-anim 5s infinite linear alternate-reverse;
    }
    
    .glitch-text::after {
      left: -2px;
      text-shadow: -2px 0 #00FFFF;
      clip: rect(44px, 450px, 56px, 0);
      animation: glitch-anim2 5s infinite linear alternate-reverse;
    }
    
    @keyframes glitch-anim {
      0% { clip: rect(42px, 9999px, 44px, 0); }
      5% { clip: rect(12px, 9999px, 59px, 0); }
      10% { clip: rect(48px, 9999px, 29px, 0); }
      15% { clip: rect(42px, 9999px, 73px, 0); }
      20% { clip: rect(63px, 9999px, 27px, 0); }
      25% { clip: rect(34px, 9999px, 55px, 0); }
      30% { clip: rect(86px, 9999px, 73px, 0); }
      35% { clip: rect(20px, 9999px, 20px, 0); }
      40% { clip: rect(26px, 9999px, 60px, 0); }
      45% { clip: rect(25px, 9999px, 66px, 0); }
      50% { clip: rect(57px, 9999px, 98px, 0); }
      55% { clip: rect(5px, 9999px, 46px, 0); }
      60% { clip: rect(82px, 9999px, 31px, 0); }
      65% { clip: rect(54px, 9999px, 27px, 0); }
      70% { clip: rect(28px, 9999px, 99px, 0); }
      75% { clip: rect(45px, 9999px, 69px, 0); }
      80% { clip: rect(23px, 9999px, 85px, 0); }
      85% { clip: rect(1px, 9999px, 83px, 0); }
      90% { clip: rect(72px, 9999px, 11px, 0); }
      95% { clip: rect(60px, 9999px, 73px, 0); }
      100% { clip: rect(2px, 9999px, 65px, 0); }
    }
    
    @keyframes glitch-anim2 {
      0% { clip: rect(65px, 9999px, 100px, 0); }
      5% { clip: rect(52px, 9999px, 74px, 0); }
      10% { clip: rect(79px, 9999px, 85px, 0); }
      15% { clip: rect(75px, 9999px, 5px, 0); }
      20% { clip: rect(67px, 9999px, 61px, 0); }
      25% { clip: rect(14px, 9999px, 79px, 0); }
      30% { clip: rect(1px, 9999px, 66px, 0); }
      35% { clip: rect(86px, 9999px, 30px, 0); }
      40% { clip: rect(23px, 9999px, 98px, 0); }
      45% { clip: rect(85px, 9999px, 72px, 0); }
      50% { clip: rect(71px, 9999px, 75px, 0); }
      55% { clip: rect(2px, 9999px, 48px, 0); }
      60% { clip: rect(30px, 9999px, 16px, 0); }
      65% { clip: rect(59px, 9999px, 50px, 0); }
      70% { clip: rect(41px, 9999px, 62px, 0); }
      75% { clip: rect(2px, 9999px, 82px, 0); }
      80% { clip: rect(47px, 9999px, 73px, 0); }
      85% { clip: rect(3px, 9999px, 27px, 0); }
      90% { clip: rect(26px, 9999px, 55px, 0); }
      95% { clip: rect(42px, 9999px, 97px, 0); }
      100% { clip: rect(38px, 9999px, 49px, 0); }
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Header Animation -->
    <div class="banner">
      <h1 class="glitch-text" data-text="CYBERPUNK CITY">CYBERPUNK CITY</h1>
    </div>
    
    <!-- Title and Introduction -->
    <h1 class="title">[ K Y Y Y Y Y Y K Y Y ]</h1>
    
    <div class="subtitle">
      <span id="typewriter"></span>
    </div>
    
    <!-- GitHub Stats -->
    <div class="stats-container">
      <div class="stat-card">
        <div class="stat-title">GITHUB STATS</div>
        <div>Commits: 1,250</div>
        <div>Stars: 120</div>
        <div>PRs: 85</div>
        <div>Issues: 42</div>
      </div>
      
      <div class="stat-card">
        <div class="stat-title">TOP LANGUAGES</div>
        <div>JavaScript: 45%</div>
        <div>Python: 25%</div>
        <div>CSS: 15%</div>
        <div>HTML: 10%</div>
        <div>Other: 5%</div>
      </div>
    </div>
    
    <!-- Skills Section -->
    <div class="skills-section">
      <h2 class="skills-title">:: 𝗧𝗘𝗖𝗛𝗡𝗢𝗟𝗢𝗚𝗬 // 𝗦𝗞𝗜𝗟𝗟𝗦 ::</h2>
      
      <div class="badges-container">
        <div class="badge">HTML</div>
        <div class="badge">CSS</div>
        <div class="badge">JavaScript</div>
        <div class="badge">Python</div>
        <div class="badge">C++</div>
        <div class="badge">Kotlin</div>
        <div class="badge">React</div>
        <div class="badge">Node.js</div>
        <div class="badge">Bootstrap</div>
        <div class="badge">Figma</div>
        <div class="badge">Git</div>
        <div class="badge">Docker</div>
      </div>
    </div>
    
    <!-- Contributions Section -->
    <div class="contributions-section">
      <h2 class="contributions-title">:: 𝗚𝗜𝗧𝗛𝗨𝗕 // 𝗖𝗢𝗡𝗧𝗥𝗜𝗕𝗨𝗧𝗜𝗢𝗡𝗦 ::</h2>
      
      <div class="snake-container">
        <div class="grid" id="snakeGrid"></div>
      </div>
    </div>
    
    <!-- Contact Section -->
    <div class="contact-section">
      <h2 class="contact-title">:: 𝗖𝗢𝗡𝗡𝗘𝗖𝗧 // 𝗧𝗥𝗔𝗡𝗦𝗠𝗜𝗦𝗦𝗜𝗢𝗡 ::</h2>
      
      <div class="contact-links">
        <a href="mailto:contact@kyy.dev" class="contact-link">EMAIL</a>
        <a href="https://linkedin.com/in/kyy" class="contact-link">LINKEDIN</a>
        <a href="https://twitter.com/kyy" class="contact-link">TWITTER</a>
      </div>
    </div>
    
    <!-- Footer Animation -->
    <div class="footer"></div>
  </div>

  <script>
    // Typewriter effect
    const texts = ["Prompt Engineer", "Web Developer (Full Stack)", "Freelancer", "Digital Architect"];
    let textIndex = 0;
    let charIndex = 0;
    let isDeleting = false;
    const speed = 100;
    const pauseAfterTyping = 1500;

    function typeWriter() {
      const element = document.getElementById("typewriter");
      const currentText = texts[textIndex];

      if (!isDeleting && charIndex < currentText.length) {
        element.innerHTML += currentText.charAt(charIndex);
        charIndex++;
        setTimeout(typeWriter, speed);
      } else if (isDeleting && charIndex > 0) {
        element.innerHTML = currentText.substring(0, charIndex - 1);
        charIndex--;
        setTimeout(typeWriter, speed / 2);
      } else if (charIndex === currentText.length) {
        setTimeout(() => { isDeleting = true; typeWriter(); }, pauseAfterTyping);
      } else {
        isDeleting = false;
        textIndex = (textIndex + 1) % texts.length;
        setTimeout(typeWriter, speed);
      }
    }

    // Create snake game grid
    function createGrid() {
      const grid = document.getElementById('snakeGrid');
      grid.innerHTML = '';
      
      for (let i = 0; i < 400; i++) {
        const cell = document.createElement('div');
        cell.classList.add('cell');
        cell.id = `cell-${i}`;
        grid.appendChild(cell);
      }
      
      // Initial snake position
      const snake = [200, 201, 202];
      const food = Math.floor(Math.random() * 400);
      
      // Render snake
      snake.forEach(segment => {
        const cell = document.getElementById(`cell-${segment}`);
        if (cell) cell.classList.add('snake');
      });
      
      // Render food
      const foodCell = document.getElementById(`cell-${food}`);
      if (foodCell) foodCell.classList.add('food');
    }

    // Initialize when page loads
    window.onload = function() {
      typeWriter();
      createGrid();
      
      // Animate grid cells with contribution pattern
      setInterval(() => {
        const cells = document.querySelectorAll('.cell');
        cells.forEach(cell => {
          if (Math.random() > 0.7) {
            cell.style.backgroundColor = '#00FFFF';
            setTimeout(() => {
              cell.style.backgroundColor = '#1a1f2e';
            }, 200);
          }
        });
      }, 1000);
    };
  </script>
</body>
</html>
```
