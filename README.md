# Mistiii-birthday
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For MISTIII 🦋❤️</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    min-height: 100vh;
    background: #fff;
    color: #222;
    font-family: Georgia, serif;
    overflow: hidden;
}

.screen {
    min-height: 100vh;
    display: none;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 25px;
    position: relative;
}

.screen.active {
    display: flex;
}

.content {
    max-width: 700px;
    position: relative;
    z-index: 5;
    animation: fadeIn 1.5s ease;
}

h1 {
    font-size: clamp(38px, 10vw, 70px);
    margin: 15px 0;
}

h2 {
    font-size: clamp(27px, 7vw, 48px);
}

p {
    font-size: 18px;
    line-height: 1.8;
}

button {
    margin-top: 25px;
    padding: 14px 28px;
    border: none;
    border-radius: 30px;
    background: #222;
    color: white;
    font-size: 16px;
}

.butterfly {
    font-size: 55px;
    animation: butterfly 3s ease-in-out infinite;
}

@keyframes butterfly {
    0%,100% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(-15px);
    }
}

.heart {
    font-size: 90px;
    animation: heartbeat 1.2s infinite;
}

@keyframes heartbeat {
    0%,100% {
        transform: scale(1);
    }
    50% {
        transform: scale(1.2);
    }
}

#countdown {
    font-size: clamp(30px, 8vw, 55px);
    font-weight: bold;
    margin: 25px 0;
}

.date {
    letter-spacing: 5px;
    font-size: 15px;
}

#memoryScreen {
    background: linear-gradient(#eef5f9, #fff);
}

.raindrop {
    position: absolute;
    top: -40px;
    width: 2px;
    height: 30px;
    background: #8aaabd;
    opacity: 0.55;
    animation: rain linear infinite;
}

@keyframes rain {
    from {
        transform: translateY(-40px);
    }
    to {
        transform: translateY(110vh);
    }
}

#finalScreen {
    background: #111;
    color: white;
}

.finalHeart {
    font-size: 120px;
    animation: heartbeat 1s infinite;
}

@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(25px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.small {
    font-size: 14px;
    opacity: 0.65;
}
</style>
</head>

<body>

<!-- COUNTDOWN -->

<section id="countdownScreen" class="screen active">

<div class="content">

<div class="butterfly">🦋</div>

<h1>For MISTIII 🦋❤️</h1>

<p class="date">31 • 08 • 2026</p>

<p>Something special is waiting for you...</p>

<div id="countdown">Loading...</div>

<p class="small">
Come back when the day arrives 🦋
</p>

</div>

</section>


<!-- BIRTHDAY -->

<section id="birthdayScreen" class="screen">

<div class="content">

<div class="heart">❤️</div>

<h1>
Happy Birthday,
<br>
MISTIII 🦋❤️
</h1>

<p>
Today is your day,
<br>
so I wanted to make something
a little different for you.
</p>

<p>
I hope this year gives you
countless reasons to smile. ✨
</p>

<button onclick="nextScreen('memoryScreen')">
Open Your Surprise ✨
</button>

</div>

</section>


<!-- RAIN MEMORY -->

<section id="memoryScreen" class="screen">

<div id="rain"></div>

<div class="content">

<div style="font-size:60px;">🌧️</div>

<h2>Some memories just stay...</h2>

<p>
That day in the rain...
<br><br>
Getting drenched together,
<br>
holding your hand,
<br>
and just being there with you.
</p>

<p>
Maybe it was just a normal moment for you,
<br>
but for me...
<br>
it became one of those memories
<br>
I don't think I'll ever forget.
</p>

<button onclick="nextScreen('wordsScreen')">
There's something else... 🤍
</button>

</div>

</section>


<!-- HER WORDS -->

<section id="wordsScreen" class="screen">

<div class="content">

<div style="font-size:55px;">💭</div>

<h2>And then you said...</h2>

<p style="font-size:22px;font-style:italic;">

“আমার মনে হয় আমরা ভালোর থেকে
<br>
আরেকটু ভালো বন্ধু।”

</p>

<p>
You probably don't know,
<br>
but that little sentence stayed with me.
</p>

<p>
Because sometimes the simplest words
<br>
become the most memorable ones. 🦋
</p>

<button onclick="nextScreen('feelingsScreen')">
One more thing... ❤️
</button>

</div>

</section>


<!-- FEELINGS -->

<section id="feelingsScreen" class="screen">

<div class="content">

<div class="butterfly">🦋❤️</div>

<h2>
There's something I never really said...
</h2>

<p>
I don't know what place I have
in your heart,
<br>
and I don't want to force an answer.
</p>

<p>
I just know that somewhere
along the way,
<br>
<strong>
you became really,
really special to me.
</strong>
</p>

<p>
And whatever happens,
<br>
I'm genuinely glad that I met you.
❤️
</p>

<button onclick="nextScreen('finalScreen')">
One Last Surprise ✨
</button>

</div>

</section>


<!-- FINAL -->

<section id="finalScreen" class="screen">

<div class="content">

<div class="finalHeart">❤️</div>

<div class="butterfly">🦋</div>

<h1>MISTIII 🦋❤️</h1>

<p>
Keep smiling.
<br>
Keep being the person you are.
</p>

<p>
Happy Birthday. 🎂❤️
</p>

<p class="small">
From someone who is really lucky
to have you in his life.
</p>

</div>

</section>


<script>

/* COUNTDOWN */

const birthday =
new Date("August 31, 2026 00:00:00").getTime();

function updateCountdown() {

const now =
new Date().getTime();

const distance =
birthday - now;

if (distance <= 0) {

document
.getElementById("countdownScreen")
.classList.remove("active");

document
.getElementById("birthdayScreen")
.classList.add("active");

return;
}

const days =
Math.floor(
distance /
(1000 * 60 * 60 * 24)
);

const hours =
Math.floor(
(distance %
(1000 * 60 * 60 * 24)) /
(1000 * 60 * 60)
);

const minutes =
Math.floor(
(distance %
(1000 * 60 * 60)) /
(1000 * 60)
);

const seconds =
Math.floor(
(distance %
(1000 * 60)) /
1000
);

document.getElementById("countdown").innerHTML =
`${days}d ${hours}h ${minutes}m ${seconds}s`;

}

updateCountdown();

setInterval(updateCountdown, 1000);


/* SCREEN CHANGE */

function nextScreen(screenId) {

document
.querySelectorAll(".screen")
.forEach(screen => {
screen.classList.remove("active");
});

document
.getElementById(screenId)
.classList.add("active");

}


/* RAIN EFFECT */

const rain =
document.getElementById("rain");

for (let i = 0; i < 80; i++) {

const drop =
document.createElement("div");

drop.classList.add("raindrop");

drop.style.left =
Math.random() * 100 + "%";

drop.style.animationDuration =
(0.5 + Math.random()) + "s";

drop.style.animationDelay =
Math.random() * 2 + "s";

rain.appendChild(drop);

}

</script>

</body>
</html>
