 
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Love Option with Animation</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(to right, #ffdde1, #ee9ca7);
      text-align: center;
      padding: 50px;
      overflow: hidden; /* biar animasi ga bikin scroll */
    }

    .love {
      background-color: rgba(255, 105, 180, 0.9);
      border-radius: 20px;
      padding: 15px 30px;
      color: #fff;
      font-weight: bold;
      font-size: 22px;
      margin: 15px;
      cursor: pointer;
      display: inline-block;
      transition: transform 0.2s, background 0.3s;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }
.cheeky-emoji {
      font-size: 80px; /* ubah di sini biar lebih besar */
      position: fixed;
      animation: floatUp 3s ease-out forwards;
      pointer-events: none;
      z-index: 200;
    .love:hover {
      transform: scale(1.1) rotate(-3deg);
      background: hotpink;
    }

    /* Popup styling */
    .popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0.7);
      background: white;
      padding: 20px 30px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
      display: none;
      font-size: 20px;
      animation: popupShow 0.5s forwards;
      z-index: 100;
    }

    .popup.show {
      display: block;
    }

    @keyframes popupShow {
      0% { transform: translate(-50%, -50%) scale(0); opacity: 0; }
      70% { transform: translate(-50%, -50%) scale(1.2); opacity: 1; }
      100% { transform: translate(-50%, -50%) scale(1); }
    }

    .close-btn {
      margin-top: 15px;
      background: hotpink;
      border: none;
      padding: 8px 15px;
      border-radius: 10px;
      cursor: pointer;
      color: white;
      font-weight: bold;
      transition: 0.2s;
    }
    .close-btn:hover {
      background: deeppink;
      transform: scale(1.1);
    }

    .floating-emoji {
      font-size: 50px;
      animation: floatUp 3s ease-out forwards;
        position: fixed;
    }

    /* Animasi hati naik (nailong) */
    .floating-heart {
      position: fixed;
      font-size: 30px;
      animation: floatUp 3s ease-out forwards;
      pointer-events: none;
      z-index: 50;
    }

    @keyframes floatUp {
      0%   { transform: translateY(0) scale(1); opacity: 1; }
      50%  { transform: translateY(-150px) scale(1.3); opacity: 0.8; }
      100% { transform: translateY(-300px) scale(0.8); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="love" onclick="showMessage('Haooooo')">R</div>
  <div class="love" onclick="showMessage('there is from your girlfriend, who\'s your girlfriend?')">I</div>
  <div class="love" onclick="showMessage('yeaaaa iniii akuuu iwiyyy, ahahah')">Z</div>
  <div class="love" onclick="showMessage('diperjelas deh, Tiara Wina indriani')">A</div>
  <div class="love" onclick="showMessage('semangat terus ya! bukan cuma buat hari ini, seterusnya!')">L</div>
  <div class="love" onclick="showMessage('if u have a problem, just remember kamu punya aku, selalunya')">D</div>
  <div class="love" onclick="showMessage('Thanks for everything, maa cute boyfriend')">I</div>

  <div id="popup" class="popup">
    <p id="popupMessage"></p>
    <button class="close-btn" onclick="closePopup()">Tutup</button>
  </div>

  <script>
    function showMessage(message) {
      document.getElementById("popupMessage").innerText = message;
      const popup = document.getElementById("popup");
      popup.classList.add("show");

      for (let i = 0; i < 3; i++) {
        createFloatingHeart();
      }
    }

    function closePopup() {
      const popup = document.getElementById("popup");
      popup.classList.remove("show");
      popup.style.display = "none";

      // Bikin 3 emoji genit random
      for (let i = 0; i < 3; i++) {
        createCheekyEmoji();
      }
    }


    function createFloatingHeart() {
      const heart = document.createElement("div");
      heart.className = "floating-heart";
      heart.innerText = "❤️";
      heart.style.left = (window.innerWidth / 2 + (Math.random() * 100 - 50)) + "px";
      heart.style.top = (window.innerHeight / 2) + "px";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 3000);
    }

    function createCheekyEmoji() {
      const emojis = ["😉","🥰","😚","😏"];
      const emoji = document.createElement("div");
      emoji.className = "cheeky-emoji";
      emoji.innerText = emojis[Math.floor(Math.random() * emojis.length)];
      emoji.style.left = (window.innerWidth / 50 + (Math.random() * 120 - 60)) + "px";
      emoji.style.top = (window.innerHeight / 50 + (Math.random() * 50 - 25)) + "px";
      document.body.appendChild(emoji);
      setTimeout(() => emoji.remove(), 2000);
    }

  </script>
</body>
</html>
