<div align="center">
  <h1>Hello World! 👋</h1>
  <h3>I'm Dr. Haseeb Javed — PhD in Computer Science</h3>
</div>

<br>

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=haseebjaved123&label=Profile%20views&color=0e75b6&style=flat" alt="haseebjaved123" />
</div>

<br>

<table width="100%">
  <tr>
    <td valign="top" width="60%">
      <h2>🎯 <b>About Me</b></h2>
      <ul>
        <li>🎓 <b>PhD Student</b> in Computer Science & Engineering at <a href="https://www.skku.edu.com/">Sungkyunkwan University</a> (QS Rank #145)</li>
        <li>🔬 <b>Research Focus</b>: AI/ML, Medical Data Analysis, Blockchain Security</li>
        <li>🌟 <b>Passionate</b> about leveraging AI to improve data security in real-world applications</li>
        <li>💬 <b>Ask me about</b>: Machine Learning, Artificial Intelligence, or anything tech-related!</li>
      </ul>
    </td>
    <td valign="top" align="right" width="40%">
      <div align="center">
        <h3>🐱 <b>Play with the Cat!</b></h3>
        <div style="border: 2px solid #ff6b35; border-radius: 10px; padding: 10px; background: linear-gradient(135deg, #ff6b35, #f7931e);">
          <canvas id="catGame" width="300" height="200" style="border-radius: 8px; background: #fff;"></canvas>
        </div>
        <p><small>Click to play with the orange cat! 🎮</small></p>
      </div>
      
      <script>
        const canvas = document.getElementById('catGame');
        const ctx = canvas.getContext('2d');
        
        let cat = {
          x: 150,
          y: 100,
          vx: 2,
          vy: 1,
          size: 20,
          color: '#ff6b35'
        };
        
        let mouse = {
          x: 0,
          y: 0,
          size: 8,
          color: '#ff6b35'
        };
        
        let score = 0;
        let gameRunning = true;
        
        function drawCat(x, y) {
          ctx.fillStyle = cat.color;
          ctx.beginPath();
          ctx.arc(x, y, cat.size, 0, Math.PI * 2);
          ctx.fill();
          
          // Eyes
          ctx.fillStyle = '#fff';
          ctx.beginPath();
          ctx.arc(x - 6, y - 6, 4, 0, Math.PI * 2);
          ctx.arc(x + 6, y - 6, 4, 0, Math.PI * 2);
          ctx.fill();
          
          // Pupils
          ctx.fillStyle = '#000';
          ctx.beginPath();
          ctx.arc(x - 6, y - 6, 2, 0, Math.PI * 2);
          ctx.arc(x + 6, y - 6, 2, 0, Math.PI * 2);
          ctx.fill();
          
          // Ears
          ctx.fillStyle = cat.color;
          ctx.beginPath();
          ctx.moveTo(x - 15, y - 15);
          ctx.lineTo(x - 25, y - 25);
          ctx.lineTo(x - 10, y - 20);
          ctx.closePath();
          ctx.fill();
          
          ctx.beginPath();
          ctx.moveTo(x + 15, y - 15);
          ctx.lineTo(x + 25, y - 25);
          ctx.lineTo(x + 10, y - 20);
          ctx.closePath();
          ctx.fill();
        }
        
        function drawMouse(x, y) {
          ctx.fillStyle = mouse.color;
          ctx.beginPath();
          ctx.arc(x, y, mouse.size, 0, Math.PI * 2);
          ctx.fill();
          
          // Mouse ears
          ctx.fillStyle = mouse.color;
          ctx.beginPath();
          ctx.arc(x - 3, y - 3, 3, 0, Math.PI * 2);
          ctx.arc(x + 3, y - 3, 3, 0, Math.PI * 2);
          ctx.fill();
        }
        
        function update() {
          if (!gameRunning) return;
          
          // Move cat
          cat.x += cat.vx;
          cat.y += cat.vy;
          
          // Bounce off walls
          if (cat.x <= cat.size || cat.x >= canvas.width - cat.size) {
            cat.vx = -cat.vx;
          }
          if (cat.y <= cat.size || cat.y >= canvas.height - cat.size) {
            cat.vy = -cat.vy;
          }
          
          // Move mouse towards cat
          const dx = cat.x - mouse.x;
          const dy = cat.y - mouse.y;
          const distance = Math.sqrt(dx * dx + dy * dy);
          
          if (distance > 0) {
            mouse.x += (dx / distance) * 1.5;
            mouse.y += (dy / distance) * 1.5;
          }
          
          // Check collision
          const dist = Math.sqrt((cat.x - mouse.x) ** 2 + (cat.y - mouse.y) ** 2);
          if (dist < cat.size + mouse.size) {
            score++;
            // Reset mouse position
            mouse.x = Math.random() * (canvas.width - 20) + 10;
            mouse.y = Math.random() * (canvas.height - 20) + 10;
            // Speed up cat
            cat.vx *= 1.1;
            cat.vy *= 1.1;
          }
        }
        
        function draw() {
          ctx.clearRect(0, 0, canvas.width, canvas.height);
          
          // Draw background pattern
          ctx.fillStyle = '#f0f0f0';
          for (let i = 0; i < canvas.width; i += 20) {
            for (let j = 0; j < canvas.height; j += 20) {
              if ((i + j) % 40 === 0) {
                ctx.fillRect(i, j, 10, 10);
              }
            }
          }
          
          drawCat(cat.x, cat.y);
          drawMouse(mouse.x, mouse.y);
          
          // Draw score
          ctx.fillStyle = '#333';
          ctx.font = '16px Arial';
          ctx.fillText(`Score: ${score}`, 10, 25);
        }
        
        function gameLoop() {
          update();
          draw();
          requestAnimationFrame(gameLoop);
        }
        
        canvas.addEventListener('click', (e) => {
          const rect = canvas.getBoundingClientRect();
          mouse.x = e.clientX - rect.left;
          mouse.y = e.clientY - rect.top;
        });
        
        // Start the game
        gameLoop();
      </script>
    </td>
  </tr>
</table>

## 📊 **GitHub Analytics**

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=haseebjaved123&show_icons=true&theme=default&hide_border=true&count_private=true" alt="GitHub Stats"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=haseebjaved123&layout=compact&theme=default&hide_border=true" alt="Top Languages"/>
</div>


## 🎯 **Current Focus**

- 🔬 **Research**: Enhancing ML models for medical data analysis
- 🛡️ **Security**: Building robust AI systems with advanced security
- 🌐 **Web3**: Exploring decentralized AI applications
- 📚 **Learning**: Staying updated with latest AI/ML breakthroughs

## 🌐 **Connect With Me**

<div align="center">
  <a href="https://www.linkedin.com/in/haseeb-javed-mlengineer" target="_blank">
    <img src="https://img.icons8.com/color/48/000000/linkedin.png" alt="LinkedIn"/>
  </a>
  <a href="https://haseebjaved123.github.io" target="_blank">
    <img src="https://img.icons8.com/color/48/000000/github.png" alt="GitHub"/>
  </a>
  <a href="https://www.instagram.com/haseeebay" target="_blank">
    <img src="https://img.icons8.com/color/48/000000/instagram-new.png" alt="Instagram"/>
  </a>
  <a href="https://scholar.google.com/citations?user=Px3nMw0AAAAJ&hl=en" target="_blank">
    <img src="https://img.icons8.com/color/48/000000/google-scholar.png" alt="Google Scholar"/>
  </a>
  <a href="mailto:haseebjaved1996@yahoo.com">
    <img src="https://img.icons8.com/color/48/000000/gmail.png" alt="Email"/>
  </a>
</div>

---

<div align="center">
  <h3>🌟 Thank you for visiting my profile! 🌟</h3>
  <p>Let's build something amazing together! 🚀</p>
  <p><img src="https://komarev.com/ghpvc/?username=haseebjaved123&label=Visitors&color=0e75b6&style=flat" alt="Visitor Counter"/></p>
</div>