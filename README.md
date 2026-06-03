<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Daksh 🎂</title>

<link rel="stylesheet" href="style.css">
</head>

<body>

<!-- PASSWORD SCREEN -->
<div id="passwordScreen">
    <div class="password-box">
        <h1>🎁 A Special Surprise Awaits 🎁</h1>
        <input type="password" id="password" placeholder="Enter Password">
        <button onclick="checkPassword()">Unlock</button>
    </div>
</div>

<!-- MAIN WEBSITE -->
<div id="mainContent">

<header>
    <h1>🎂 HAPPY BIRTHDAY DAKSH 🎂</h1>
    <h2>This One Is Special... Hope You Know Why 💖</h2>
</header>

<!-- SHOOTING STARS -->
<div id="stars"></div>

<!-- CAKE SECTION -->
<section class="card">
    <h2>🕯 Blow The Candle</h2>
    <div id="candle">🕯</div>
    <button onclick="blowCandle()">Blow Candle</button>
</section>

<section class="card">
    <h2>🍰 Cut The Cake</h2>
    <div id="cake">🎂</div>
    <button onclick="cutCake()">Cut Cake</button>
</section>

<section class="card">
    <div id="celebration"></div>
</section>

<!-- BOUQUET -->
<section class="card">
    <h2>💐 Bouquet For Daksh</h2>
    <div class="flowers">
        🌹🌸🌷💐🌻🌺🌹
    </div>
</section>

<!-- SCORE -->
<section class="card">
    <h2>💖 Heart Points</h2>
    <h1 id="points">0</h1>
</section>

<!-- TIC TAC TOE -->
<section class="card">
    <h2>Tic Tac Toe</h2>

    <div id="ticTacToe">
        <button class="cell" onclick="move(this)"> </button>
        <button class="cell" onclick="move(this)"> </button>
        <button class="cell" onclick="move(this)"> </button>

        <button class="cell" onclick="move(this)"> </button>
        <button class="cell" onclick="move(this)"> </button>
        <button class="cell" onclick="move(this)"> </button>

        <button class="cell" onclick="move(this)"> </button>
        <button class="cell" onclick="move(this)"> </button>
        <button class="cell" onclick="move(this)"> </button>
    </div>
</section>

<!-- ROCK PAPER SCISSORS -->
<section class="card">
<h2>Rock Paper Scissors</h2>

<button onclick="playRPS('rock')">🪨</button>
<button onclick="playRPS('paper')">📄</button>
<button onclick="playRPS('scissors')">✂️</button>

<p id="rpsResult"></p>
</section>

<!-- NUMBER GUESSING -->
<section class="card">
<h2>Number Guessing</h2>

<input type="number" id="guess">

<button onclick="guessNumber()">
Guess
</button>

<p id="guessResult"></p>
</section>

<!-- WORD SCRAMBLE -->
<section class="card">
<h2>Word Scramble</h2>

<p>Scrambled Word:</p>
<h3 id="scrambleWord">HPAYP</h3>

<input id="wordAnswer">

<button onclick="checkWord()">
Submit
</button>

<p id="wordResult"></p>
</section>

<!-- TRIVIA -->
<section class="card">
<h2>Birthday Trivia For Daksh</h2>

<div id="quiz">

<p>1. What month is Daksh's birthday?</p>

<button onclick="correctAnswer()">October</button>

<button onclick="wrongAnswer()">January</button>

<button onclick="wrongAnswer()">March</button>

</div>

</section>

<!-- SECRET NOTE -->
<section class="card">

<h2>🔒 Secret Note</h2>

<button onclick="openNote()">
Open Note
</button>

<p id="secretNote"></p>

</section>

<!-- MUSIC -->
<section class="card">

<h2>🎵 Playlist</h2>

<a href="https://youtube.com/playlist?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd&si=yudocVB2b16Vi7YX"
target="_blank">

Open Playlist

</a>

</section>

<!-- PHOTO -->
<section class="card">

<h2>📸 Special Memory</h2>

<img src="daksh.jpg" class="photo">

<h3>
With Best Wishes From Ms. Bishnoi 💖
</h3>

</section>

</div>

<script src="script.js"></script>

</body>
</html>
/* ==========================
   GLOBAL STYLES
========================== */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:'Trebuchet MS',sans-serif;
    background:linear-gradient(
        135deg,
        #ffd6e8,
        #f8e8ff,
        #dff7ff,
        #fff4d8
    );
    min-height:100vh;
    overflow-x:hidden;
    color:#444;
}

/* ==========================
   PASSWORD SCREEN
========================== */

#passwordScreen{
    position:fixed;
    inset:0;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(
        135deg,
        #ffd6e8,
        #f5dfff,
        #d9f5ff
    );
    z-index:1000;
}

.password-box{
    background:white;
    padding:40px;
    border-radius:30px;
    width:90%;
    max-width:450px;
    text-align:center;
    box-shadow:0 15px 40px rgba(0,0,0,.1);
}

.password-box h1{
    color:#ff69b4;
    margin-bottom:20px;
}

.password-box input{
    width:100%;
    padding:15px;
    border-radius:15px;
    border:none;
    background:#f4f4f4;
    margin-bottom:15px;
    font-size:16px;
}

.password-box button{
    width:100%;
}

/* ==========================
   MAIN CONTENT
========================== */

#mainContent{
    display:none;
    position:relative;
    z-index:2;
}

header{
    text-align:center;
    padding:50px 20px;
}

header h1{
    font-size:3rem;
    color:#ff4fa2;
    margin-bottom:10px;
}

header h2{
    color:#7a5cff;
    font-weight:normal;
}

/* ==========================
   CARDS
========================== */

.card{
    width:90%;
    max-width:900px;
    margin:25px auto;
    background:white;
    border-radius:25px;
    padding:30px;
    text-align:center;
    box-shadow:0 10px 25px rgba(0,0,0,.08);
}

.card h2{
    color:#ff69b4;
    margin-bottom:15px;
}

/* ==========================
   BUTTONS
========================== */

button{
    border:none;
    padding:12px 22px;
    border-radius:18px;
    cursor:pointer;
    font-size:16px;
    margin:5px;
    transition:.3s;
    background:#ff8fb8;
    color:white;
}

button:hover{
    transform:translateY(-3px);
    background:#ff69a8;
}

/* ==========================
   FLOWERS
========================== */

.flowers{
    font-size:60px;
}

/* ==========================
   CANDLE & CAKE
========================== */

#candle,
#cake{
    font-size:90px;
    margin:20px 0;
}

/* ==========================
   HEART POINTS
========================== */

#points{
    color:#ff4d88;
    font-size:60px;
}

/* ==========================
   TIC TAC TOE
========================== */

#ticTacToe{
    display:grid;
    grid-template-columns:repeat(3,90px);
    gap:8px;
    justify-content:center;
}

.cell{
    width:90px;
    height:90px;
    font-size:30px;
    font-weight:bold;
    background:#ffe9f3;
    color:#ff4d88;
}

/* ==========================
   INPUTS
========================== */

input{
    padding:12px;
    border:none;
    border-radius:15px;
    background:#f2f2f2;
    margin:10px;
}

/* ==========================
   PHOTO
========================== */

.photo{
    width:280px;
    max-width:100%;
    border-radius:20px;
    box-shadow:0 8px 25px rgba(0,0,0,.15);
}

/* ==========================
   SHOOTING STARS
========================== */

.star{
    position:fixed;
    width:4px;
    height:4px;
    background:white;
    border-radius:50%;
    box-shadow:
        0 0 10px white,
        0 0 20px white;
    z-index:1;
    animation:shoot 6s linear infinite;
}

@keyframes shoot{

    0%{
        transform:
        translateX(0)
        translateY(0);

        opacity:1;
    }

    100%{
        transform:
        translateX(-1200px)
        translateY(600px);

        opacity:0;
    }
}

/* ==========================
   CONFETTI
========================== */

.confetti{
    position:fixed;
    top:-20px;
    font-size:25px;
    z-index:999;
    animation:fall 5s linear forwards;
}

@keyframes fall{

    from{
        transform:translateY(0);
    }

    to{
        transform:translateY(120vh);
    }
}

/* ==========================
   FIREWORKS
========================== */

.fireworks{

    font-size:55px;

    animation:
    explode 1s infinite alternate;

    color:#ff4fa2;
}

@keyframes explode{

    0%{
        transform:scale(1);
    }

    100%{
        transform:scale(1.25);
    }
}

/* ==========================
   HAPPY BIRTHDAY MESSAGE
========================== */

#celebration{

    font-size:40px;
    color:#ff4d88;
    font-weight:bold;
}

/* ==========================
   QUIZ
========================== */

#quiz p{
    margin-bottom:15px;
    font-size:20px;
}

/* ==========================
   LINKS
========================== */

a{
    color:#7a5cff;
    text-decoration:none;
    font-size:18px;
}

a:hover{
    text-decoration:underline;
}

/* ==========================
   FLOATING HEARTS
========================== */

.heart{

    position:fixed;

    bottom:-50px;

    font-size:25px;

    animation:
    floatHeart 6s linear forwards;
}

@keyframes floatHeart{

    from{
        transform:
        translateY(0);
        opacity:1;
    }

    to{
        transform:
        translateY(-120vh);
        opacity:0;
    }
}

/* ==========================
   MOBILE
========================== */

@media(max-width:700px){

    header h1{
        font-size:2rem;
    }

    header h2{
        font-size:1rem;
    }

    .card{
        padding:20px;
    }

    #ticTacToe{
        grid-template-columns:
        repeat(3,70px);
    }

    .cell{
        width:70px;
        height:70px;
        font-size:24px;
    }

    #candle,
    #cake{
        font-size:70px;
    }

    #points{
        font-size:45px;
    }

}
/* ==========================
   GLOBAL VARIABLES
========================== */

let points = 0;
let candleBlown = false;
let cakeCut = false;

/* ==========================
   PASSWORD SCREEN
========================== */

function checkPassword(){

    const pass =
    document.getElementById("password").value;

    if(pass === "MINE"){

        document.getElementById(
        "passwordScreen"
        ).style.display = "none";

        document.getElementById(
        "mainContent"
        ).style.display = "block";

    }else{

        alert("Wrong Password ❌");

    }
}

/* ==========================
   HEART POINTS
========================== */

function addPoints(amount){

    points += amount;

    document.getElementById(
    "points"
    ).innerText = points;

    createFloatingHeart();
}

/* ==========================
   FLOATING HEART
========================== */

function createFloatingHeart(){

    let heart =
    document.createElement("div");

    heart.className = "heart";

    heart.innerHTML = "💖";

    heart.style.left =
    Math.random()*100 + "vw";

    document.body.appendChild(heart);

    setTimeout(()=>{
        heart.remove();
    },6000);
}

/* ==========================
   CANDLE
========================== */

function blowCandle(){

    document.getElementById(
    "candle"
    ).innerHTML = "💨";

    candleBlown = true;

    checkCelebration();
}

/* ==========================
   CAKE
========================== */

function cutCake(){

    document.getElementById(
    "cake"
    ).innerHTML = "🍰";

    cakeCut = true;

    checkCelebration();
}

/* ==========================
   CELEBRATION
========================== */

function checkCelebration(){

    if(candleBlown && cakeCut){

        document.getElementById(
        "celebration"
        ).innerHTML =

        `
        <div class="fireworks">
        🎆 🎇 🎆 🎇 🎆
        <br>
        HAPPY BIRTHDAY DAKSH
        <br>
        🎇 🎆 🎇 🎆 🎇
        </div>
        `;

        launchConfetti();
    }
}

/* ==========================
   CONFETTI
========================== */

function launchConfetti(){

    for(let i=0;i<150;i++){

        let confetti =
        document.createElement("div");

        confetti.className =
        "confetti";

        const emojis =
        ["🎉","✨","🎊","💖"];

        confetti.innerHTML =
        emojis[
        Math.floor(
        Math.random()*emojis.length
        )];

        confetti.style.left =
        Math.random()*100+"vw";

        confetti.style.animationDuration =
        (3 + Math.random()*3)+"s";

        document.body.appendChild(
        confetti
        );

        setTimeout(()=>{
            confetti.remove();
        },6000);
    }
}

/* ==========================
   SHOOTING STARS
========================== */

function createStars(){

    for(let i=0;i<35;i++){

        let star =
        document.createElement("div");

        star.className = "star";

        star.style.left =
        Math.random()*100+"vw";

        star.style.top =
        Math.random()*100+"vh";

        star.style.animationDelay =
        Math.random()*5+"s";

        document.body.appendChild(star);
    }
}

createStars();

/* ==========================
   TIC TAC TOE
========================== */

let currentPlayer = "X";

function move(cell){

    if(cell.innerHTML !== "")
        return;

    cell.innerHTML =
    currentPlayer;

    currentPlayer =
    currentPlayer==="X" ? "O":"X";

    checkWinner();
}

function checkWinner(){

    const cells =
    document.querySelectorAll(".cell");

    const wins = [

        [0,1,2],
        [3,4,5],
        [6,7,8],

        [0,3,6],
        [1,4,7],
        [2,5,8],

        [0,4,8],
        [2,4,6]
    ];

    wins.forEach(combo=>{

        let a =
        cells[combo[0]].innerHTML;

        let b =
        cells[combo[1]].innerHTML;

        let c =
        cells[combo[2]].innerHTML;

        if(a!=="" &&
           a===b &&
           b===c){

            alert(
            a+" Wins! 🎉"
            );

            addPoints(2);

            resetBoard();
        }

    });
}

function resetBoard(){

    document
    .querySelectorAll(".cell")
    .forEach(cell=>{

        cell.innerHTML="";

    });
}

/* ==========================
   ROCK PAPER SCISSORS
========================== */

function playRPS(player){

    const choices =
    ["rock","paper","scissors"];

    const computer =
    choices[
    Math.floor(
    Math.random()*3
    )];

    let result="";

    if(player===computer){

        result="Draw 🤝";
    }
    else if(

        (player==="rock" &&
        computer==="scissors")

        ||

        (player==="paper" &&
        computer==="rock")

        ||

        (player==="scissors" &&
        computer==="paper")

    ){

        result="You Win 🎉";

        addPoints(2);

    }else{

        result="Computer Wins";
    }

    document.getElementById(
    "rpsResult"
    ).innerText =
    result +
    " | Computer: " +
    computer;
}

/* ==========================
   NUMBER GUESSING
========================== */

const secretNumber =
Math.floor(Math.random()*10)+1;

function guessNumber(){

    let guess =
    Number(
    document.getElementById(
    "guess"
    ).value
    );

    if(guess===secretNumber){

        document.getElementById(
        "guessResult"
        ).innerText =
        "Correct 🎉";

        addPoints(2);

    }else{

        document.getElementById(
        "guessResult"
        ).innerText =
        "Try Again";
    }
}

/* ==========================
   WORD SCRAMBLE
========================== */

function checkWord(){

    let answer =
    document.getElementById(
    "wordAnswer"
    ).value
    .toUpperCase();

    if(answer==="HAPPY"){

        document.getElementById(
        "wordResult"
        ).innerText =
        "Correct 🎉";

        addPoints(2);

    }else{

        document.getElementById(
        "wordResult"
        ).innerText =
        "Wrong";
    }
}

/* ==========================
   TRIVIA
========================== */

function correctAnswer(){

    alert(
    "Correct! 🎉 +2 Hearts"
    );

    addPoints(2);
}

function wrongAnswer(){

    alert(
    "Oops! Wrong Answer"
    );
}

/* ==========================
   SECRET NOTE
========================== */

function openNote(){

    let pass =
    prompt(
    "Enter Note Password"
    );

    if(pass==="28/10/10"){

        document.getElementById(
        "secretNote"
        ).innerHTML =

        `
        💖 Happiest Birthday to the person
        who is the reason for my happiness.
        <br><br>

        And this month I would not throw
        tantrums.
        <br><br>

        Will not annoy you as this is your
        Birthday Month.
        <br><br>

        From:
        <b>Ms. Bishnoi</b>
        `;

    }else{

        alert(
        "Wrong Password ❌"
        );
    }
}
