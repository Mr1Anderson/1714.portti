<!DOCTYPE html>
<html lang="fi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>1714 – Portti</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=IM+Fell+English:ital@0;1&display=swap" rel="stylesheet">

  <style>
    :root {
      --paper-text: #2c1a10;
      --gold-glow: rgba(255, 193, 76, 0.55);
      --gold-glow-soft: rgba(255, 193, 76, 0.22);
    }

    * {
      box-sizing: border-box;
    }

    html, body {
      margin: 0;
      min-height: 100%;
    }

    body {
      font-family: Georgia, serif;
      background: url('https://i.postimg.cc/wjw3pmPk/file-00000000ef8871f48c3d26e8733a3413.png') center center / cover no-repeat fixed;
      overflow-x: hidden;
    }

    .overlay {
      min-height: 100vh;
      background: rgba(0, 0, 0, 0.18);
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
    }

    /* Klikattava alue avaimen kohdalle */
    .key-hitbox {
      position: absolute;
      left: 50%;
      bottom: 28%;
      transform: translateX(-50%);
      width: 130px;
      height: 130px;
      cursor: pointer;
      border-radius: 50%;
      transition: box-shadow 0.25s ease, transform 0.25s ease;
    }

    .key-hitbox:hover {
      box-shadow:
        0 0 18px var(--gold-glow-soft),
        0 0 40px var(--gold-glow);
      transform: translateX(-50%) scale(1.03);
    }

    .paper-wrap {
      width: min(860px, 92vw);
      display: flex;
      justify-content: center;
      pointer-events: none;
    }

    .paper {
      display: none;
      width: min(760px, 88vw);
      min-height: 360px;
      padding: 78px 90px 72px;
      background:
        url('https://i.postimg.cc/8jYZQCMh/file-00000000ef8871f48c3d26e8733a3413.png') center/100% 100% no-repeat,
        linear-gradient(#f4dfb0, #ebcf97);
      color: var(--paper-text);
      filter: drop-shadow(0 0 18px var(--gold-glow-soft))
              drop-shadow(0 0 34px var(--gold-glow));
      animation: parchmentOpen 0.9s ease forwards, parchmentGlow 2s ease-in-out;
      transform-origin: top center;
      font-family: "IM Fell English", Georgia, serif;
      pointer-events: auto;
    }

    .paper h2 {
      margin: 0 0 22px;
      text-align: center;
      font-size: clamp(1.6rem, 3vw, 2.2rem);
      letter-spacing: 0.5px;
    }

    .symbols {
      text-align: center;
      font-size: clamp(1.1rem, 2vw, 1.5rem);
      line-height: 2;
    }

    .symbols span {
      display: inline-block;
      min-width: 140px;
      margin: 4px 8px;
    }

    .note {
      margin-top: 26px;
      text-align: center;
      font-size: clamp(1rem, 1.8vw, 1.2rem);
      line-height: 1.7;
    }

    .hint4 {
      margin-top: 16px;
      text-align: center;
      font-style: italic;
      opacity: 0.8;
      font-size: 1rem;
    }

    @keyframes parchmentOpen {
      0% {
        opacity: 0;
        transform: translateY(26px) scaleY(0.2);
      }
      60% {
        opacity: 1;
        transform: translateY(0) scaleY(1.03);
      }
      100% {
        opacity: 1;
        transform: translateY(0) scaleY(1);
      }
    }

    @keyframes parchmentGlow {
      0%, 100% {
        filter: drop-shadow(0 0 12px var(--gold-glow-soft))
                drop-shadow(0 0 22px var(--gold-glow-soft));
      }
      50% {
        filter: drop-shadow(0 0 22px var(--gold-glow))
                drop-shadow(0 0 50px var(--gold-glow));
      }
    }

    @media (max-width: 700px) {
      .key-hitbox {
        width: 110px;
        height: 110px;
        bottom: 27%;
      }

      .paper {
        padding: 62px 34px 58px;
      }

      .symbols span {
        display: block;
        min-width: 0;
      }
    }
  </style>
</head>
<body>
  <div class="overlay">
    <div class="key-hitbox" onclick="openLock()" aria-label="Avaa lukko"></div>

    <div class="paper-wrap">
      <div id="paper" class="paper">
        <h2>Merkit ovat numeroita</h2>

        <div class="symbols">
          <span>🧭 = 3</span>
          <span>🗝️ = 2</span>
          <span>⚙️ = 8</span>
          <span>🌊 = 5</span>
          <span>🌙 = 9</span>
          <span>💧 = 1</span>
          <span>🗼 = 6</span>
          <span>⚡ = 0</span>
          <span>🔥 = 7</span>
          <span>⭐ = 4</span>
        </div>

        <div class="hint4">
          Kaikki merkit eivät kerro totuutta.
        </div>

        <div class="note">
          Mutta muista…<br>
          Numerot yksin eivät johda mihinkään.<br>
          Vain oikea järjestys näyttää tien.
        </div>
      </div>
    </div>
  </div>

  <audio id="clickSound" preload="auto">
    <source src="click.mp3" type="audio/mpeg">
  </audio>

  <audio id="oceanSound" preload="auto" loop>
    <source src="meri.mp3" type="audio/mpeg">
  </audio>

  <script>
    let opened = false;

    function openLock() {
      const paper = document.getElementById("paper");
      const clickSound = document.getElementById("clickSound");
      const oceanSound = document.getElementById("oceanSound");

      if (!opened) {
        paper.style.display = "block";
        opened = true;
      }

      if (clickSound) {
        clickSound.currentTime = 0;
        clickSound.play().catch(() => {});
      }

      if (oceanSound && oceanSound.paused) {
        oceanSound.volume = 0.3;
        oceanSound.play().catch(() => {});
      }
    }
  </script>
</body>
</html>
