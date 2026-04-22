
<html lang="fi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>1714 – Portti</title>

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
    padding: 80px 40px; /* enemmän tilaa koska kuva iso */
    width: 90%;
    max-width: 700px;

    background: url('https://i.postimg.cc/8zp9vJCn/vecteezy-old-paper-scroll-isolated-on-transparent-background-with-60363436.png') center/contain no-repeat;

    color: #2b1a10;
    font-family: 'Special Elite', cursive;

    text-shadow: 0 1px 0 rgba(255,255,255,0.2);

    animation: openPaper 1s ease;
    transform-origin: top;
}

/* sisältö keskelle paperia */
.paper-content {
    max-width: 500px;
    margin: auto;
}

/* SYMBOLIT */
.symbols {
    font-size: 26px;
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

<img src="https://i.postimg.cc/9FngDxvV/vecteezy-aesthetic-value-of-vintage-keys-44183313.png"
     class="key"
     onclick="openLock()"
     alt="Avain">

<div id="paper">

<div class="paper-content">

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

    let click = document.getElementById("clickSound");
    let ocean = document.getElementById("oceanSound");

    click.currentTime = 0;
    click.play().catch(()=>{});

    ocean.volume = 0.3;
    ocean.play().catch(()=>{});
}
</script>

</body>
</html>
