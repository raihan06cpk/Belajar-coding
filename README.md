# Belajar-coding
Halo
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Untuk Kamu</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      text-align: center;
      background: url('https://i.ibb.co/fYGQgjB/love-bg.jpg') no-repeat center center fixed;
      background-size: cover;
      padding-top: 100px;
      overflow: hidden;
    }

    #welcome {
      font-size: 28px;
      color: #fff0f5;
      opacity: 0;
      animation: fadeIn 2s ease-in-out forwards;
      text-shadow: 1px 1px 3px #ff69b4;
    }

    h1 {
      color: #fff;
      font-size: 32px;
      white-space: nowrap;
      overflow: hidden;
      border-right: 2px solid #fff;
      width: 0;
      margin-top: 30px;
      animation: typing 3s steps(40, end) forwards;
      animation-delay: 2.5s;
      text-shadow: 1px 1px 3px #ff69b4;
    }

    @keyframes typing {
      from { width: 0 }
      to { width: 100% }
    }

    @keyframes blink {
      50% { border-color: transparent }
    }

    @keyframes fadeIn {
      to { opacity: 1; }
    }

    #buttons {
      margin-top: 50px;
      opacity: 0;
      animation: fadeIn 2s ease-in-out 6s forwards;
    }

    button {
      padding: 15px 30px;
      font-size: 18px;
      margin: 20px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s;
      box-shadow: 2px 2px 6px rgba(0, 0, 0, 0.3);
    }

    #yesBtn {
      background-color: #28a745;
      color: white;
    }

    #noBtn {
      background-color: #dc3545;
      color: white;
      position: absolute;
    }

    #result {
      margin-top: 50px;
      font-size: 24px;
      color: #fff;
      text-shadow: 1px 1px 3px #6f42c1;
    }

    .heart {
      position: fixed;
      font-size: 24px;
      color: red;
      animation: floatUp 2s linear forwards;
    }

    @keyframes floatUp {
      to {
        transform: translateY(-100vh);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <!-- Musik cinta -->
  <audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
    Browsermu tidak mendukung audio.
  </audio>

  <div id="welcome">Halo sayang, selamat datang</div>
  <h1 id="typing-text">Maukah kamu jadi pacarku?</h1>

  <div id="buttons">
    <button id="yesBtn">Ya</button>
    <button id="noBtn">Tidak</button>
  </div>
  <div id="result"></div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const result = document.getElementById("result");

    noBtn.addEventListener("mouseover", () => {
      const i = Math.floor(Math.random() * (window.innerWidth - 100));
      const j = Math.floor(Math.random() * (window.innerHeight - 100));
      noBtn.style.left = i + "px";
      noBtn.style.top = j + "px";
    });

    yesBtn.addEventListener("click", () => {
      result.innerHTML = "Yeay! Aku sayang kamu banget!";

      for (let i = 0; i < 20; i++) {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.top = "80vh";
        heart.innerHTML = "❤️";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 2000);
      }
    });
  </script>

</body>
</html>