# Valentines-proposal-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Will You Be My Valentine?</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', sans-serif;
      color: white;
      text-align: center;
      overflow: hidden;
    }

    .card {
      background: rgba(255, 255, 255, 0.15);
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
      backdrop-filter: blur(10px);
      max-width: 400px;
    }

    h1 {
      font-size: 2.2rem;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.1rem;
      margin-bottom: 30px;
    }

    button {
      border: none;
      padding: 12px 25px;
      margin: 10px;
      border-radius: 30px;
      font-size: 1rem;
      cursor: pointer;
      transition: transform 0.2s;
    }

    .yes {
      background: #ff4d6d;
      color: white;
    }

    .no {
      background: white;
      color: #ff4d6d;
      position: relative;
    }

    button:hover {
      transform: scale(1.1);
    }

    .hearts {
      position: absolute;
      top: -10px;
      font-size: 20px;
      animation: fall 5s linear infinite;
    }

    @keyframes fall {
      0% { transform: translateY(0); opacity: 1; }
      100% { transform: translateY(110vh); opacity: 0; }
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Hey My Love ❤️</h1>
    <p>
      From the moment you came into my life, everything changed.  
      So today I have just one question for you…
    </p>
    <h2>Will you be my Valentine? 💘</h2>

    <button class="yes" onclick="yesClicked()">YES 💕</button>
    <button class="no" onmouseover="moveNo()">NO 😅</button>
  </div>

  <script>
    function yesClicked() {
      document.body.innerHTML = `
        <div style="text-align:center; color:white;">
          <h1>YAYYYY 😍❤️</h1>
          <p>You just made me the happiest person alive.</p>
          <h2>Happy Valentine’s Day 💖</h2>
        </div>
      `;
    }

    function moveNo() {
      const btn = document.querySelector('.no');
      const x = Math.random() * (window.innerWidth - btn.clientWidth);
      const y = Math.random() * (window.innerHeight - btn.clientHeight);
      btn.style.position = "absolute";
      btn.style.left = x + "px";
      btn.style.top = y + "px";
    }

    // Falling hearts
    setInterval(() => {
      const heart = document.createElement('div');
      heart.className = 'hearts';
      heart.innerText = '❤️';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (3 + Math.random() * 3) + 's';
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 5000);
    }, 300);
  </script>

</body>
</html>
