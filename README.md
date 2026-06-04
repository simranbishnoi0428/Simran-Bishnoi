<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Surprise Portal</title>
<style>
body{
    margin:0;
    font-family: Arial, sans-serif;
    background: linear-gradient(120deg,#ffd6e0,#d0f4ff,#e8d7ff);
    overflow-x:hidden;
    color:#333;
}
.center{
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    flex-direction:column;
}
input, button{
    padding:10px;
    margin:5px;
    border-radius:10px;
    border:none;
}
button{
    cursor:pointer;
    background:#ff7aa2;
    color:white;
}
.hidden{display:none;}
h1,h2{color:#ff4081;text-align:center;}

.card{
    background:white;
    padding:20px;
    margin:20px;
    border-radius:20px;
    box-shadow:0 0 10px rgba(0,0,0,0.2);
}

.game{margin:10px;padding:10px;background:#fff;border-radius:15px;}

canvas{background:#000;border-radius:10px;}
#confetti{
    position:fixed;
    top:0;left:0;
    width:100%;height:100%;
    pointer-events:none;
}
</style>
</head>

<body>

<canvas id="confetti"></canvas>

<!-- LOGIN -->
<div id="login" class="center">
    <h1>SURPRISE 🎁</h1>
    <p>Enter Password</p>
    <input type="password" id="pass">
    <button onclick="checkPass()">Enter</button>
</div>

<!-- MAIN PAGE -->
<div id="main" class="hidden">

<h1>🎉 Happy Birthday Daksh 🎉</h1>
<h3>This One is special hope you know why...</h3>

<div class="card">
<h2>Cake & Candle</h2>
<p>Click to Blow Candle & Cut Cake</p>
<button onclick="blowCandle()">Blow Candle 🕯️</button>
<button onclick="cutCake()">Cut Cake 🎂</button>
</div>

<div class="card">
<h2>💌 Secret Note (Password: 28/10/10)</h2>
<input id="notePass" placeholder="Enter note password">
<button onclick="openNote()">Open Note</button>
<p id="note" class="hidden">
Happiest Birthday to the person who is the reason for my happiness.<br>
This month I would not throw tantrums.<br>
Will not annoy you as this is your Birthday Month.<br><br>
From: Ms. Bishnoi ❤️<br>
To: Daksh
</p>
</div>

<div class="card">
<h2>🎵 Music</h2>
<iframe width="300" height="200"
src="https://www.youtube.com/embed/videoseries?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd"
allowfullscreen></iframe>
</div>

<div class="card">
<h2>🌸 Flowers & Fireworks</h2>
<button onclick="fireworks()">Launch Fireworks 🎆</button>
<div id="fw"></div>
</div>

<div class="card">
<h2>💋 Kiss Rewards Zone</h2>
<p>Play games to earn kisses 💋</p>
<p id="kissCount">Kisses: 0</p>
</div>

<!-- GAMES -->
<div class="card">
<h2>🎮 Games Hub</h2>

<div class="game">
<h3>Tic Tac Toe</h3>
<div id="ttt"></div>
<button onclick="initTTT()">Start</button>
</div>

<div class="game">
<h3>Rock Paper Scissors</h3>
<button onclick="rps('rock')">Rock</button>
<button onclick="rps('paper')">Paper</button>
<button onclick="rps('scissors')">Scissors</button>
<p id="rpsRes"></p>
</div>

<div class="game">
<h3>Number Guess</h3>
<input id="guess">
<button onclick="guessNum()">Guess</button>
<p id="guessRes"></p>
</div>

<div class="game">
<h3>Typing Test</h3>
<p id="typeText">daksh is special birthday boy</p>
<input id="typeInput">
<button onclick="checkType()">Check</button>
</div>

<div class="game">
<h3>Memory Match (simple)</h3>
<button onclick="memory()">Play</button>
<p id="memRes"></p>
</div>

<div class="game">
<h3>Hangman (word)</h3>
<button onclick="hangman()">Start</button>
<p id="hang"></p>
</div>

</div>

</div>

<script>
let kisses=0;

function checkPass(){
 if(document.getElementById("pass").value==="MINE"){
    document.getElementById("login").classList.add("hidden");
    document.getElementById("main").classList.remove("hidden");
 } else alert("Wrong password!");
}

function addKiss(n){
 kisses+=n;
 document.getElementById("kissCount").innerText="Kisses: "+kisses;
}

// Cake events
function blowCandle(){
 addKiss(2);
 confettiBurst();
 alert("Candle blown! 💨 +2 kisses");
}
function cutCake(){
 addKiss(3);
 confettiBurst();
 alert("Cake cut! 🎂 +3 kisses");
}

// Note
function openNote(){
 if(document.getElementById("notePass").value==="28/10/10"){
    document.getElementById("note").classList.remove("hidden");
    addKiss(2);
 } else alert("Wrong password");
}

// RPS
function rps(user){
 let arr=["rock","paper","scissors"];
 let comp=arr[Math.floor(Math.random()*3)];
 let res="";
 if(user===comp) res="Draw";
 else if(
 (user=="rock"&&comp=="scissors")||
 (user=="paper"&&comp=="rock")||
 (user=="scissors"&&comp=="paper")
 ){
 res="You win +2 kisses",addKiss(2);
 } else res="You lose";
 document.getElementById("rpsRes").innerText=res;
}

// Guess
let num=Math.floor(Math.random()*10);
function guessNum(){
 let g=document.getElementById("guess").value;
 if(g==num){addKiss(2);document.getElementById("guessRes").innerText="Correct +2 kisses";}
 else document.getElementById("guessRes").innerText="Try again";
}

// Typing
function checkType(){
 if(document.getElementById("typeInput").value===document.getElementById("typeText").innerText){
 addKiss(2);
 alert("Perfect typing +2 kisses");
 }
}

// Memory
function memory(){
 let ok=Math.random()>0.5;
 if(ok){addKiss(2);document.getElementById("memRes").innerText="Matched +2 kisses";}
 else document.getElementById("memRes").innerText="Try again";
}

// Hangman simple
function hangman(){
 let word="daksh";
 let guess=prompt("Guess word:");
 if(guess==word){addKiss(3);document.getElementById("hang").innerText="Correct +3 kisses";}
 else document.getElementById("hang").innerText="Wrong";
}

// Confetti
function confettiBurst(){
 let c=document.getElementById("confetti");
 let ctx=c.getContext("2d");
 c.width=window.innerWidth;
 c.height=window.innerHeight;
 for(let i=0;i<100;i++){
  ctx.fillStyle=`hsl(${Math.random()*360},100%,50%)`;
  ctx.fillRect(Math.random()*c.width,Math.random()*c.height,5,5);
 }
 setTimeout(()=>ctx.clearRect(0,0,c.width,c.height),1000);
}

// Fireworks
function fireworks(){
 confettiBurst();
 document.getElementById("fw").innerText="🎆 Boom! 🎆";
}
</script>

</body>
</html>
