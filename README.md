<!DOCTYPE html>
<html lang="fi">
<head>
<meta charset="UTF-8">
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
    background: rgba(0,0,0,0.65);
    min-height: 100vh;
    padding: 40px;
}

h1 {
    font-size: 40px;
    letter-spacing: 2px;
}

p {
    font-size: 18px;
    opacity: 0.9;
}

.key {
    margin-top: 40px;
    cursor: pointer;
    transition: transform 0.2s;
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
    background: url('paper.png') center/cover;
    color: black;
    border-radius: 10px;
    animation: fadeIn 1.5s ease;
}

.symbols {
    font-size: 28px;
    margin-top: 20px;
    letter-spacing: 10px;
}

@keyframes fadeIn {
    from {opacity: 0; transform: translateY(30px);}
    to {opacity: 1; transform: translateY(0);}
}
</style>

</head>

<body>

<div class="overlay">

<h1>Olet löytänyt piilotetun sivun</h1>

<p>Jos pääsit tänne asti… olet lähempänä kuin uskot.</p>

<p>Mustaparta ei luottanut karttoihin.<br>
Hän piilotti totuuden merkkeihin.</p>

<br>

<p><i>Klikkaa avainta avataksesi portin</i></p>

<img src="key.png" width="120" class="key" onclick="openLock()">

<div id="paper">
    <h2>MERKIT OVAT NUMEROITA</h2>

    <div class="symbols">
        🧭 3 &nbsp;&nbsp;
        🗝️ 2 &nbsp;&nbsp;
        ⚙️ 8 &nbsp;&nbsp;
        🌊 5 &nbsp;&nbsp;
        🌙 9 &nbsp;&nbsp;
        💧 1 &nbsp;&nbsp;
        🗼 6 &nbsp;&nbsp;
        ⚡ 0 &nbsp;&nbsp;
        🔥 7 &nbsp;&nbsp;
        ⭐ 4
    </div>

    <p style="margin-top:20px;">
        Mutta muista…<br>
        Numerot yksin eivät johda mihinkään.<br>
        Vain oikea järjestys näyttää tien.
    </p>
</div>

</div>

<script>
function openLock() {
    document.getElementById("paper").style.display = "block";
}
</script>

</body>
</html>
