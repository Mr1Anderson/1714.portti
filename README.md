
<html lang="fi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>1714 – Portti</title>

<!-- Käsinkirjoitusfontti -->
<link href="https://fonts.googleapis.com/css2?family=Special+Elite&display=swap" rel="stylesheet">

<style>
body {
    margin: 0;
    font-family: Georgia, serif;
    background: url('tausta.jpg') center/cover no-repeat fixed;
    color: #e8d8b0;
    text-align: center;
}

/* tumma sumu */
.overlay {
    background: rgba(0,0,0,0.7);
    min-height: 100vh;
    padding: 40px 20px;
    backdrop-filter: blur(2px);
}

h1 {
    font-size: 42px;
    letter-spacing: 2px;
}

/* AVAIN */
.key {
    margin-top: 60px;
    width: 160px;
    cursor: pointer;
    transition: all 0.3s ease;
    filter: drop-shadow(0 0 10px rgba(255,200,100,0.3));
}

.key:hover {
    transform: scale(1.15) rotate(-5deg);
    filter: drop-shadow(0 0 25px rgba(255,220,120,0.8));
}

/* PAPERI */
#paper {
    display: none;
    margin: 50px auto;
    padding: 35px;
    width: 85%;
    max-width: 650px;
    background: url('https://i.postimg.cc/wjw3pmPk/file-00000000ef8871f48c3d26e8733a3413.png') center/cover no-repeat, #f4e3b2;
    color: #2b1a10;
    border-radius: 12px;

    font-family: 'Special Elite', cursive;

    box-shadow: 0 0 40px rgba(255, 200, 100, 0.4);

    animation: openPaper 1s ease;
    transform-origin: top;
}

.symbols {
    font-size: 30px;
    margin-top: 20px;
    line-height: 1.9;
}

/* ANIMAATIO */
@keyframes openPaper {
    0% {
        opacity: 0;
        transform: scaleY(0.1) rotateX(-30deg);
    }
    60% {
        transform: scaleY(1.05);
    }
    100% {
        opacity: 1;
        transform: scaleY(1);
    }
}

</style>
</head>

<body>

<div class="overlay">

<h1>Olet löytänyt portin</h1>

<p><i>Mutta kaikki portit eivät johda oikeaan paikkaan...</i></p>

<p>Klikkaa avainta avataksesi salaisuuden</p>

<img src="https://github.com/user-attachments/assets/2c078721-2851-4c9d-83b7-cef8f87070d0"
     class="key"
     onclick="openLock()">

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

<p style="margin-top:20px;">
Mutta muista…<br>
Vain oikea järjestys näyttää tien.
</p>

</div>

</div>

<audio id="clickSound">
<source src="click.mp3" type="audio/mpeg">
</audio>

<audio id="oceanSound" loop>
<source src="https://audiomack.com/serkoanderson/song/69e938cf8653d" type="audio/mpeg">
</audio>

<script>
function openLock() {
    document.getElementById("paper").style.display = "block";

    let click = document.getElementById("clickSound");
    let ocean = document.getElementById("oceanSound");

    click.play().catch(()=>{});
    ocean.volume = 0.3;
    ocean.play().catch(()=>{});
}
</script>

</body>
</html>
