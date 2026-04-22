<!DOCTYPE html>
<html lang="fi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>1714 – Portti</title>

  <style>
    body {
      margin: 0;
      font-family: Georgia, serif;
      background: url('tausta.jpg') center/cover no-repeat fixed;
      color: #e8d8b0;
      text-align: center;
    }

    .overlay {
      background: rgba(0, 0, 0, 0.65);
      min-height: 100vh;
      padding: 40px 20px;
    }

    h1 {
      font-size: 40px;
      letter-spacing: 2px;
      margin-top: 0;
    }

    p {
      font-size: 18px;
      opacity: 0.95;
      line-height: 1.6;
    }

    .key {
      margin-top: 40px;
      cursor: pointer;
      transition: transform 0.2s ease;
    }

    .key:hover {
      transform: scale(1.1);
    }

    #paper {
      display: none;
      margin: 40px auto;
      padding: 30px;
      width: 80%;
      max-width: 600px;
      background: url('paper.png') center/cover no-repeat, #f4e3b2;
      color: black;
      border-radius: 10px;
      box-shadow: 0 0 30px rgba(255, 220, 120, 0.4),
                  0 0 60px rgba(255, 200, 80, 0.2);
      animation: paperOpen 0.8s ease, glow 2s ease;
      transform-origin: top center;
    }

    .symbols {
      font-size: 28px;
      margin-top: 20px;
      line-height: 1.8;
      letter-spacing: 4px;
    }

    @keyframes paperOpen {
      0% {
        opacity: 0;
        transform: scaleY(0.2) rotateX(-20deg);
      }
      60% {
        opacity: 1;
        transform: scaleY(1.05) rotateX(0deg);
      }
      100% {
        opacity: 1;
        transform: scaleY(1);
      }
    }

    @keyframes glow {
      0% {
        box-shadow: 0 0 0 rgba(255,200,80,0);
      }
      50% {
        box-shadow: 0 0 40px rgba(255,200,80,0.5);
      }
      100% {
        box-shadow: 0 0 20px rgba(255,200,80,0.2);
      }
    }
  </style>
</head>

<body>
  <div class="overlay">
    <h1>Olet löytänyt piilotetun sivun</h1>

    <p>Jos pääsit tänne asti… olet lähempänä kuin uskot.</p>

    <p>
      Mustaparta ei luottanut karttoihin.<br>
      Hän piilotti totuuden merkkeihin.
    </p>

    <p><i>Klikkaa avainta avataksesi portin</i></p>

    <img
      src="https://github.com/user-attachments/assets/2c078721-2851-4c9d-83b7-cef8f87070d0"
      width="120"
      class="key"
      onclick="openLock()"
      alt="Avain"
    >

    <div id="paper">
      <h2>MERKIT OVAT NUMEROITA</h2>

      <div class="symbols">
        🧭 = 3<br>
        🗝️ = 2<br>
        ⚙️ = 8<br>
        🌊 = 5<br>
        🌙 = 9<br>
        💧 = 1<br>
        🗼 = 6<br>
        ⚡ = 0<br>
        🔥 = 7<br>
        ⭐ = 4
      </div>

      <p style="margin-top: 20px;">
        Mutta muista…<br>
        Numerot yksin eivät johda mihinkään.<br>
        Vain oikea järjestys näyttää tien.
      </p>
    </div>
  </div>

  <audio id="clickSound">
    <source src="click.mp3" type="audio/mpeg">
  </audio>

  <audio id="oceanSound" loop>
    <source src="meri.mp3" type="audio/mpeg">
  </audio>

  <script>
    function openLock() {
      document.getElementById("paper").style.display = "block";

      const clickSound = document.getElementById("clickSound");
      const oceanSound = document.getElementById("oceanSound");

      if (clickSound) {
        clickSound.play().catch(() => {});
      }

      if (oceanSound) {
        oceanSound.volume = 0.3;
        oceanSound.play().catch(() => {});
      }
    }
  </script>
</body>
</html>
