# Nicky-Valentines 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Be My Valentine?</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: "Comic Sans MS", "Segoe UI", sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 40px;
      border-radius: 24px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
      max-width: 320px;
    }

    h1 {
      margin-top: 0;
      font-size: 28px;
      color: #ff4d6d;
    }

    .buttons {
      margin-top: 30px;
      position: relative;
      height: 120px;
    }

    button {
      padding: 12px 24px;
      font-size: 18px;
      border: none;
      border-radius: 999px;
      cursor: pointer;
      position: absolute;
      transition: transform 0.2s ease;
    }

    #yes {
      background: #ff4d6d;
      color: white;
      left: 50%;
      transform: translateX(-50%);
    }

    #yes:hover {
      transform: translateX(-50%) scale(1.1);
    }

    #no {
      background: #ddd;
      color: #555;
      left: 50%;
      top: 60px;
      transform: translateX(-50%);
    }

    .heart {
      position: absolute;
      font-size: 24px;
      animation: floatUp 1.5s ease-out forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      0% {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
      100% {
        opacity: 0;
        transform: translateY(-120px) scale(1.5);
      }
    }

    .love-message {
      font-size: 24px;
      color: #ff4d6d;
      margin-top: 20px;
      animation: pop 0.6s ease;
    }

    @keyframes pop {
      0% { transform: scale(0); }
      80% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
  </style>
</head>
<body>

  <div class="card" id="card">
    <h1>Nicky 💕<br>Will you be my Valentine?</h1>

    <div class="buttons">
      <button id="yes">YES 💖</button>
      <button id="no">NO 🙃</button>
    </div>
  </div>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const card = document.getElementById("card");

    function moveNoButton() {
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 80 - 40;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    }

    noBtn.addEventListener("mouseenter", moveNoButton);
    noBtn.addEventListener("touchstart", moveNoButton);

    yesBtn.addEventListener("click", () => {
      card.innerHTML = `
        <h1 class="love-message">I LOVE YOU 💖💖💖</h1>
      `;
      for (let i = 0; i < 25; i++) {
        createHeart();
      }
    });

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerText = "💖";
      heart.style.left = Math.random() * window.innerWidth + "px";
      heart.style.top = window.innerHeight / 2 + "px";
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 1500);
    }
  </script>

</body>
</html>