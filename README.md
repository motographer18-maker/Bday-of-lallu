# Bday-of-lallu
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Erumaaa 🫶🏻</title>

<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4);
    text-align: center;
    overflow-x: hidden;
    color: #333;
}

/* Floating Hearts */
.heart {
    position: fixed;
    bottom: -10px;
    font-size: 20px;
    animation: floatUp 6s linear infinite;
}

@keyframes floatUp {
    0% { transform: translateY(0); opacity: 1; }
    100% { transform: translateY(-100vh); opacity: 0; }
}

/* Title Glow */
h1 {
    margin-top: 60px;
    font-size: 3rem;
    animation: glow 2s infinite alternate;
}

@keyframes glow {
    from { text-shadow: 0 0 10px #ff4e50; }
    to { text-shadow: 0 0 25px #ff004f; }
}

.subtitle {
    opacity: 0.8;
    margin-bottom: 30px;
}

.card {
    background: white;
    padding: 30px;
    border-radius: 15px;
    max-width: 600px;
    margin: 40px auto;
    box-shadow: 0 10px 30px rgba(0,0,0,0.15);
    line-height: 1.6;
}

button {
    padding: 12px 25px;
    border: none;
    border-radius: 25px;
    background: #ff4e50;
    color: white;
    font-size: 16px;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    background: #e63c3f;
}

.hidden {
    display: none;
}

/* Gallery */
.gallery img {
    width: 100%;
    border-radius: 15px;
}

footer {
    margin-top: 60px;
    padding: 20px;
    opacity: 0.6;
}
</style>
</head>

<body>

<h1>Happy Birthday Erumaaa 🫶🏻</h1>
<p class="subtitle">To the cutest distraction I know.</p>

<!-- Countdown -->
<div class="card">
    <h2>Countdown to Your Day ⏳</h2>
    <p id="countdown"></p>
</div>

<!-- Flirty Message -->
<div class="card">
    <p>Okay fine… I’ll say it.</p>
    <p><b>Happy Birthday, Erumaaa 🫶🏻</b></p>

    <p>
        I was going to write something normal…
        but you’re not exactly a normal person in my life.
    </p>

    <p>
        It’s actually unfair how one person can look that cute,
        act that innocent,
        and still cause this much distraction.
    </p>

    <p>
        I hope this year gives you everything you want.
        And maybe… gives me a little more of your time too.
    </p>

    <p>Don’t worry. I kept it classy. Mostly. 😉</p>
</div>

<!-- Photo Gallery -->
<div class="card gallery">
    <h2>Some of My Favorite Photos of You 🖼</h2>
    <img id="galleryImage" src="photo1.jpg">
    <br><br>
    <button onclick="nextImage()">Next Photo ➡</button>
</div>

<!-- Secret Button -->
<div class="card">
    <button onclick="showMessage()">Click this… carefully 😌</button>

    <div id="secret" class="hidden">
        <p>No pressure. No expectations.</p>
        <p>Just wanted to make you smile today.</p>
        <p>
            And if I get to be part of a few more of your birthdays…
            I wouldn’t complain.
        </p>
        <p>
            Now go enjoy your day.
            I’ll pretend I’m not thinking about you. 🙂
        </p>
    </div>
</div>

<footer>Built with intention.</footer>

<!-- Background Music -->
<audio autoplay loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

<script>

/* Countdown (Set Her Birthday Date Below) */
var countDownDate = new Date("Feb 20, 2026 00:00:00").getTime();

var x = setInterval(function() {
    var now = new Date().getTime();
    var distance = countDownDate - now;

    var days = Math.floor(distance / (1000 * 60 * 60 * 24));
    var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));

    document.getElementById("countdown").innerHTML =
        days + "d " + hours + "h " + minutes + "m ";

    if (distance < 0) {
        clearInterval(x);
        document.getElementById("countdown").innerHTML = "It's Your Day 🎉";
    }
}, 1000);

/* Gallery */
var images = ["photo1.jpg", "photo2.jpg", "photo3.jpg"];
var index = 0;

function nextImage() {
    index++;
    if(index >= images.length) index = 0;
    document.getElementById("galleryImage").src = images[index];
}

/* Secret */
function showMessage() {
    document.getElementById("secret").classList.remove("hidden");
}

/* Floating Hearts */
setInterval(function() {
    var heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 10 + "px";
    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 6000);
}, 500);

</script>

</body>
</html>
