
<html lang="fi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>1714 – Portti</title>

<style>
body {
    margin: 0;
    font-family: Georgia, serif;
    background: url('https://i.postimg.cc/wjw3pmPk/file-00000000ef8871f48c3d26e8733a3413.png') center/cover no-repeat fixed;
    color: #e8d8b0;
}

/* tumma overlay */
.overlay {
    background: rgba(0,0,0,0.55);
    min-height: 100vh;
    position: relative;
    text-align: center;
    padding-top: 80px;
}

/* otsikko */
h1 {
    font-size: 42px;
    letter-spacing: 2px;
    margin-bottom: 10px;
}

p {
    font-size: 18px;
    opacity: 0.9;
}

/* 🔑 näkymätön klikattava alue avaimen kohdalle */
.key-hitbox {
    position: absolute;
    bottom: 120px; /* säädä tarvittaessa */
    left: 50%;
    transform: translateX(-50%);
    width: 180px;
    height: 180px;
    cursor: pointer;
}

/* hover-efekti */
.key-hitbox:hover {
    box-shadow: 0 0 40px rgba(255,200,100,0.5);
    border-radius: 50%;
}

/* 📜 paperi */
#paper {
    display: none;
    margin: 40px auto;
    padding: 30px;
    width: 85%;
    max-width: 600px;
    background: url('https://i.postimg.cc/8zQ1wW3G/paper.png') center/cover no-repeat, #f4e3b2;
    color: black;
    border-radius: 12px;
    animation: fadeIn 1.2s ease;
}

/* symbolit */
.symbols {
    font-size: 26px;
    line-height: 1.8;
    margin-top: 15px;
}

/* animaatio */
@keyframes fadeIn {
    from {opacity:0; transform: translateY(30px);}
    to {opacity:1; transform: translateY(0);}
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

<!-- 🔑 klikattava alue -->
<div class="key-hitbox" onclick="openLock()"></div>

<!-- 📜 PAPERI -->
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
        Numerot yksin eivät johda mihinkään.<br>
        Vain oikea järjestys näyttää tien.
    </p>
</div>

</div>

<!-- 🔊 ÄÄNET -->
<audio id="clickSound" src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_115b9b3a68.mp3?filename=unlock-2-22669.mp3"></audio>
<audio id="oceanSound" loop src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_6c0b5c7c2b.mp3?filename=ocean-waves-112906.mp3"></audio>

<script>
function openLock() {

    document.getElementById("paper").style.display = "block";

    // 🔊 klikkausääni
    document.getElementById("clickSound").play();

    // 🌊 meri päälle
    let ocean = document.getElementById("oceanSound");
    ocean.volume = 0.3;
    ocean.play();
}
</script>

</body>
</html>
