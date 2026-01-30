<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Pour Alessia ❤️</title>

<style>
body {
    margin: 0;
    font-family: 'Arial', sans-serif;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff758c, #ff7eb3);
    overflow: hidden;
}

/* Carte */
.card {
    background: white;
    padding: 35px;
    border-radius: 25px;
    text-align: center;
    width: 320px;
    box-shadow: 0 15px 35px rgba(0,0,0,0.2);
    animation: fadeIn 1s ease;
}

@keyframes fadeIn {
    from { opacity: 0; transform: scale(0.8);}
    to { opacity: 1; transform: scale(1);}
}

/* Boutons */
button {
    margin: 10px;
    padding: 12px 22px;
    border: none;
    border-radius: 20px;
    cursor: pointer;
    font-size: 16px;
    background-color: #ff4d6d;
    color: white;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.1);
    background-color: #ff1f4b;
}

/* Coeurs qui tombent */
.heart {
    position: absolute;
    color: rgba(255,255,255,0.7);
    font-size: 20px;
    animation: fall linear infinite;
}

@keyframes fall {
    0% { transform: translateY(-10vh); }
    100% { transform: translateY(110vh); }
}
</style>
</head>

<body>

<div class="card" id="card">
    <h2>💌 Pour toi Alessia</h2>
    <p>J’ai quelque chose à te demander...</p>
    <button onclick="ouvrirCarte()">Ouvrir</button>
</div>

<script>

/* Animation coeurs */
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "❤️";

    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (Math.random() * 3 + 3) + "s";

    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 6000);
}

setInterval(createHeart, 300);

/* Étapes de la carte */

function ouvrirCarte() {
    document.getElementById("card").innerHTML = `
        <h2>Alessia ❤️</h2>
        <p>Veux-tu être ma Valentine ?</p>
        <button onclick="restaurant()">Oui 💕</button>
        <button onclick="refus()">Non 😢</button>
    `;
}

function restaurant() {
    document.getElementById("card").innerHTML = `
        <h2>Parfait 😍</h2>
        <p>Accepterais-tu d'aller au restaurant avec moi ?</p>
        <button onclick="amour()">Oui 🍝</button>
        <button onclick="refus()">Non 😭</button>
    `;
}

function amour() {
    document.getElementById("card").innerHTML = `
        <h1>Je t'aime Alessia ❤️</h1>
        <p>Merci d’être dans ma vie.</p>
        <p>— Nathan</p>
    `;
}

function refus() {
    document.getElementById("card").innerHTML = `
        <h2>Réfléchis encore 🥺❤️</h2>
        <button onclick="ouvrirCarte()">Revenir</button>
    `;
}

</script>

</body>
</html>
