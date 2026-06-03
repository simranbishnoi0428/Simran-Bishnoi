<!-- ==========================
PART 1 - BIRTHDAY WEBSITE
Password: MINE
Secret Note Password: 28/10/10
Games Included:
1. Tic Tac Toe
2. Rock Paper Scissors
3. Number Guess
4. Birthday Trivia
5. Science Quiz
========================== -->

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Happy Birthday Daksh ❤️</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Poppins,sans-serif;
}

body{
background:linear-gradient(135deg,#ffb6c1,#87ceeb);
overflow-x:hidden;
text-align:center;
}

#login{
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
}

input{
padding:12px;
border:none;
border-radius:10px;
margin:10px;
}

button{
padding:12px 20px;
border:none;
border-radius:10px;
cursor:pointer;
background:#ff4da6;
color:white;
margin:5px;
}

button:hover{
transform:scale(1.05);
}

#main{
display:none;
}

.hero{
padding:80px 20px;
}

.hero h1{
font-size:4rem;
color:#ff1493;
}

.card{
background:white;
margin:20px auto;
max-width:900px;
padding:20px;
border-radius:20px;
box-shadow:0 0 15px rgba(0,0,0,.2);
}

.menu{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
gap:15px;
padding:20px;
}

.gameCard{
background:#fff;
padding:15px;
border-radius:15px;
cursor:pointer;
}

.gameSection{
display:none;
margin-top:20px;
}

.cell{
width:80px;
height:80px;
font-size:35px;
}

.balloon{
position:fixed;
font-size:40px;
bottom:-100px;
animation:float linear infinite;
}

@keyframes float{
to{
transform:translateY(-120vh);
}
}

.kiss{
position:fixed;
font-size:25px;
animation:kissMove 8s linear infinite;
}

@keyframes kissMove{
from{transform:translateY(100vh);}
to{transform:translateY(-100vh);}
}

</style>
</head>

<body>

<div id="login">

<h1>🎁 Surprise Waiting...</h1>

<input
type="password"
id="pass"
placeholder="Enter Password">

<button onclick="unlock()">
Unlock
</button>

</div>

<div id="main">

<div class="hero">

<h1>🎂 HAPPY BIRTHDAY DAKSH 🎂</h1>

<h2>This one is special... Hope you know why ❤️</h2>

</div>

<div class="card">

<h2>💌 Birthday Message</h2>

<p>

Happy Birthday Daksh ❤️

May every dream come true,
every smile stay forever,
and every day be brighter than today.

— Ms. Bishnoi

</p>

</div>

<div class="card">

<h2>🎵 Playlist Section</h2>

<p>https://youtube.com/playlist?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd&si=YYH1n-ALANV6Ifde</p>

</div>
<div class="card">

<h2>🎮 Games Menu</h2>

<div class="menu">

<div class="gameCard"
onclick="showGame('ttt')">
Tic Tac Toe
</div>

<div class="gameCard"
onclick="showGame('rps')">
Rock Paper Scissors
</div>

<div class="gameCard"
onclick="showGame('guess')">
Number Guess
</div>

<div class="gameCard"
onclick="showGame('trivia')">
Birthday Trivia
</div>

<div class="gameCard"
onclick="showGame('science')">
Science Quiz
</div>

</div>

</div>

<!-- GAME 1 -->

<div id="ttt" class="gameSection card">

<h2>Tic Tac Toe</h2>

<div>

<button class="cell" onclick="move(this,0)"></button>
<button class="cell" onclick="move(this,1)"></button>
<button class="cell" onclick="move(this,2)"></button><br>

<button class="cell" onclick="move(this,3)"></button>
<button class="cell" onclick="move(this,4)"></button>
<button class="cell" onclick="move(this,5)"></button><br>

<button class="cell" onclick="move(this,6)"></button>
<button class="cell" onclick="move(this,7)"></button>
<button class="cell" onclick="move(this,8)"></button>

</div>

<h3 id="tttStatus">Player X Turn</h3>

</div>

<!-- GAME 2 -->

<div id="rps" class="gameSection card">

<h2>Rock Paper Scissors</h2>

<button onclick="rps('Rock')">Rock</button>
<button onclick="rps('Paper')">Paper</button>
<button onclick="rps('Scissors')">Scissors</button>

<h3 id="rpsResult"></h3>

</div>

<!-- GAME 3 -->

<div id="guess" class="gameSection card">

<h2>Guess Number (1-10)</h2>

<input id="guessInput">

<button onclick="guessGame()">
Guess
</button>

<h3 id="guessResult"></h3>

</div>

<!-- GAME 4 -->

<div id="trivia" class="gameSection card">

<h2>Birthday Trivia</h2>

<p>What day is Daksh's birthday?</p>

<input id="triviaInput">

<button onclick="triviaGame()">
Submit
</button>

<h3 id="triviaResult"></h3>

</div>

<!-- GAME 5 -->

<div id="science" class="gameSection card">

<h2>Science Quiz</h2>

<p>Which planet is known as the Red Planet?</p>

<button onclick="scienceQuiz('Mars')">
Mars
</button>

<button onclick="scienceQuiz('Earth')">
Earth
</button>

<button onclick="scienceQuiz('Venus')">
Venus
</button>

<h3 id="scienceResult"></h3>

</div>

<div class="card">

<h2>🔒 Secret Note</h2>

<input
type="password"
id="notePass">

<button onclick="openNote()">
Open
</button>

<div id="note" style="display:none">

<h3>For Daksh ❤️</h3>

<p>

Happiest Birthday to the person who is the reason for my happiness.

And this month I would not throw tantrums.

Will not annoy you as this is ur Birthday Month.

❤️

From:
Ms. Bishnoi

</p>

</div>

</div>

</div>

<script>

function unlock(){

if(
document.getElementById("pass").value==="MINE"
){

document.getElementById("login").style.display="none";
document.getElementById("main").style.display="block";

balloons();
kisses();
confetti();

}else{
alert("Wrong Password");
}

}

function showGame(id){

document
.querySelectorAll(".gameSection")
.forEach(x=>x.style.display="none");

document.getElementById(id)
.style.display="block";

}

function openNote(){

if(
document.getElementById("notePass").value==="28/10/10"
){

document.getElementById("note")
.style.display="block";

}

}

/* BALLOONS */

function balloons(){

for(let i=0;i<30;i++){

let b=document.createElement("div");

b.className="balloon";

b.innerHTML="🎈";

b.style.left=Math.random()*100+"vw";

b.style.animationDuration=
5+Math.random()*10+"s";

document.body.appendChild(b);

}

}

/* KISSES */

function kisses(){

for(let i=0;i<20;i++){

let k=document.createElement("div");

k.className="kiss";

k.innerHTML="💋";

k.style.left=Math.random()*100+"vw";

document.body.appendChild(k);

}

}

/* CONFETTI */

function confetti(){

for(let i=0;i<150;i++){

let c=document.createElement("div");

c.innerHTML="🎉";

c.style.position="fixed";

c.style.left=Math.random()*100+"vw";

c.style.top="-20px";

document.body.appendChild(c);

setTimeout(()=>{
c.style.transition="5s";
c.style.top="100vh";
},100);

}

}

/* TIC TAC TOE */

let board=["","","","","","","","",""];
let player="X";

const wins=[
[0,1,2],
[3,4,5],
[6,7,8],
[0,3,6],
[1,4,7],
[2,5,8],
[0,4,8],
[2,4,6]
];

function move(cell,index){

if(board[index]!="") return;

board[index]=player;
cell.innerHTML=player;

for(let w of wins){

if(
board[w[0]] &&
board[w[0]]===board[w[1]] &&
board[w[1]]===board[w[2]]
){

document.getElementById(
"tttStatus"
).innerHTML=
player+" Wins 🎉";

return;

}

}

player=player==="X"?"O":"X";

document.getElementById(
"tttStatus"
).innerHTML=
"Player "+player+" Turn";

}

/* RPS */

function rps(user){

let arr=[
"Rock",
"Paper",
"Scissors"
];

let comp=
arr[Math.floor(Math.random()*3)];

document.getElementById(
"rpsResult"
).innerHTML=
"You: "+user+
" | Computer: "+comp;

}

/* NUMBER GUESS */

let random=
Math.floor(Math.random()*10)+1;

function guessGame(){

let g=
Number(
document.getElementById(
"guessInput"
).value
);

if(g===random){

document.getElementById(
"guessResult"
).innerHTML=
"Correct 🎉";

}else{

document.getElementById(
"guessResult"
).innerHTML=
"Try Again";

}

}

/* TRIVIA */

function triviaGame(){

let ans=
document.getElementById(
"triviaInput"
).value;

document.getElementById(
"triviaResult"
).innerHTML=
"Nice Answer ❤️";

}

/* SCIENCE */

function scienceQuiz(ans){

if(ans==="Mars"){

document.getElementById(
"scienceResult"
).innerHTML=
"Correct 🎉";

}else{

document.getElementById(
"scienceResult"
).innerHTML=
"Wrong";

}

}

</script>

</body>
</html>
<div class="gameCard" onclick="showGame('memory')">Memory Match</div>
<div class="gameCard" onclick="showGame('hangman')">Hangman</div>
<div class="gameCard" onclick="showGame('typing')">Typing Speed</div>
<div class="gameCard" onclick="showGame('planet')">Planet Match</div>
<div class="gameCard" onclick="showGame('solar')">Solar System Quiz</div>
<div id="memory" class="gameSection card">

<h2>🧠 Memory Match</h2>

<div id="memoryBoard"></div>

<button onclick="startMemory()">
New Game
</button>

</div>
#memoryBoard{
display:grid;
grid-template-columns:repeat(4,80px);
gap:10px;
justify-content:center;
margin:20px;
}

.memoryCard{
width:80px;
height:80px;
font-size:35px;
cursor:pointer;
background:#ffd700;
border-radius:10px;
display:flex;
justify-content:center;
align-items:center;
}
let memoryIcons=[
"🌍","🌍",
"🪐","🪐",
"⭐","⭐",
"☄️","☄️",
"🚀","🚀",
"🌙","🌙",
"⚡","⚡",
"🔭","🔭"
];

let firstCard=null;

function startMemory(){

memoryIcons.sort(()=>Math.random()-0.5);

let board=document.getElementById("memoryBoard");

board.innerHTML="";

memoryIcons.forEach(icon=>{

let div=document.createElement("div");

div.className="memoryCard";

div.innerHTML="?";

div.dataset.icon=icon;

div.onclick=function(){

this.innerHTML=icon;

if(!firstCard){

firstCard=this;

}else{

if(firstCard.dataset.icon!==icon){

setTimeout(()=>{

firstCard.innerHTML="?";

div.innerHTML="?";

},800);

}

firstCard=null;

}

};

board.appendChild(div);

});

}

startMemory();
<div id="hangman" class="gameSection card">

<h2>🎯 Hangman</h2>

<h3 id="hangWord"></h3>

<input id="hangGuess">

<button onclick="guessLetter()">
Guess
</button>

<p id="hangStatus"></p>

</div>
let secretWord="DAKSH";
let displayWord=["_","_","_","_","_"];

document.getElementById(
"hangWord"
).innerHTML=
displayWord.join(" ");

function guessLetter(){

let letter=
document.getElementById(
"hangGuess"
).value.toUpperCase();

for(let i=0;i<secretWord.length;i++){

if(secretWord[i]===letter){

displayWord[i]=letter;

}

}

document.getElementById(
"hangWord"
).innerHTML=
displayWord.join(" ");

if(displayWord.join("")===secretWord){

document.getElementById(
"hangStatus"
).innerHTML=
"🎉 You Win!";

}

}
<div id="typing" class="gameSection card">

<h2>⌨️ Typing Speed Test</h2>

<p id="typingText">
Happy Birthday Daksh
</p>

<input id="typingInput">

<button onclick="checkTyping()">
Check
</button>

<h3 id="typingResult"></h3>

</div>
function checkTyping(){

let text=
document.getElementById(
"typingInput"
).value;

if(text==="Happy Birthday Daksh"){

document.getElementById(
"typingResult"
).innerHTML=
"⚡ Perfect!";

}else{

document.getElementById(
"typingResult"
).innerHTML=
"Try Again";

}

}

<div id="planet" class="gameSection card">

<h2>🪐 Planet Match</h2>

<p>Which planet is called the Red Planet?</p>

<button onclick="planetGame('Mars')">
Mars
</button>

<button onclick="planetGame('Earth')">
Earth
</button>

<button onclick="planetGame('Jupiter')">
Jupiter
</button>

<h3 id="planetResult"></h3>

</div>
function planetGame(ans){

if(ans==="Mars"){

document.getElementById(
"planetResult"
).innerHTML=
"✅ Correct";

}else{

document.getElementById(
"planetResult"
).innerHTML=
"❌ Wrong";

}

}
<div id="solar" class="gameSection card">

<h2>☀️ Solar System Quiz</h2>

<p>
Largest planet in our solar system?
</p>

<button onclick="solarQuiz('Jupiter')">
Jupiter
</button>

<button onclick="solarQuiz('Mars')">
Mars
</button>

<button onclick="solarQuiz('Venus')">
Venus
</button>

<h3 id="solarResult"></h3>

</div>
function solarQuiz(ans){

if(ans==="Jupiter"){

document.getElementById(
"solarResult"
).innerHTML=
"🎉 Correct Answer";

}else{

document.getElementById(
"solarResult"
).innerHTML=
"Wrong Answer";

}

}
<div class="game">
<h2>Memory Flip Cards</h2>
<div id="memoryBoard"></div>
<button onclick="startMemory()">Start Game</button>
</div>

<script>
let cards = ["🍎","🍌","🍇","🍒","🍎","🍌","🍇","🍒"];
let flipped = [];

function startMemory(){
  document.getElementById("memoryBoard").innerHTML = "";
  cards.sort(()=>0.5-Math.random());
  cards.forEach((c,i)=>{
    let btn = document.createElement("button");
    btn.innerHTML = "❓";
    btn.onclick = ()=>{
      btn.innerHTML = c;
      flipped.push(c);
    };
    document.getElementById("memoryBoard").appendChild(btn);
  });
}
</script>
<div class="game">
<h2>Quick Math Challenge</h2>
<p id="mathQ"></p>
<input id="mathA" placeholder="Answer">
<button onclick="checkMath()">Submit</button>
</div>

<script>
let correct;

function newQ(){
  let a = Math.floor(Math.random()*20);
  let b = Math.floor(Math.random()*20);
  correct = a + b;
  document.getElementById("mathQ").innerText = a + " + " + b;
}
function checkMath(){
  let ans = document.getElementById("mathA").value;
  alert(ans == correct ? "Correct!" : "Wrong!");
  newQ();
}
newQ();
</script>
<div class="game">
<h2>Guess the Number</h2>
<input id="guess" placeholder="1-100">
<button onclick="checkGuess()">Guess</button>
</div>

<script>
let num = Math.floor(Math.random()*100)+1;

function checkGuess(){
  let g = document.getElementById("guess").value;
  if(g == num){
    alert("🎉 Correct!");
    num = Math.floor(Math.random()*100)+1;
  } else if(g > num){
    alert("Too high!");
  } else {
    alert("Too low!");
  }
}
</script>
<div class="game">
<h2>Balloon Pop</h2>
<div id="balloons"></div>
</div>

<script>
function spawnBalloons(){
  let box = document.getElementById("balloons");
  for(let i=0;i<10;i++){
    let b = document.createElement("span");
    b.innerHTML = "🎈";
    b.style.fontSize = "30px";
    b.onclick = ()=> b.remove();
    box.appendChild(b);
  }
}
spawnBalloons();
</script>
<div class="game">
<h2>Color Tap Challenge</h2>
<p id="colorText">Click the correct color!</p>
<button id="btn1" onclick="checkColor(this)"></button>
<button id="btn2" onclick="checkColor(this)"></button>
<button id="btn3" onclick="checkColor(this)"></button>
</div>

<script>
let colors = ["red","blue","green"];
let correctColor;

function setup(){
  correctColor = colors[Math.floor(Math.random()*3)];
  let buttons = document.querySelectorAll("button");
  buttons.forEach((b,i)=>{
    b.innerText = colors[i];
  });
}
function checkColor(btn){
  alert(btn.innerText === correctColor ? "Correct!" : "Wrong!");
  setup();
}
setup();
</script>
<div class="game">
<h2>Tic Tac Toe</h2>
<div id="ttt"></div>
<p id="tttStatus"></p>
<button onclick="resetTTT()">Reset</button>
</div>

<script>
let turn = "X";
let board = Array(9).fill("");

function drawTTT(){
  let box = document.getElementById("ttt");
  box.innerHTML = "";
  board.forEach((v,i)=>{
    let b = document.createElement("button");
    b.style.width="50px";
    b.style.height="50px";
    b.innerText = v;
    b.onclick = ()=>move(i);
    box.appendChild(b);
  });
}

function move(i){
  if(board[i] === ""){
    board[i] = turn;
    turn = turn === "X" ? "O" : "X";
    drawTTT();
  }
}

function resetTTT(){
  board = Array(9).fill("");
  turn = "X";
  drawTTT();
}

drawTTT();
</script>
<div class="game">
<h2>Word Scramble</h2>
<p id="scrambled"></p>
<input id="wordGuess" placeholder="Unscramble">
<button onclick="checkWord()">Check</button>
</div>

<script>
let words = ["birthday","galaxy","planet","science","friend"];
let current = words[Math.floor(Math.random()*words.length)];

function shuffle(word){
  return word.split('').sort(()=>0.5-Math.random()).join('');
}

document.getElementById("scrambled").innerText = shuffle(current);

function checkWord(){
  let g = document.getElementById("wordGuess").value;
  alert(g === current ? "Correct!" : "Wrong! Answer: " + current);
}
</script>
<div class="game">
<h2>Reaction Time Test</h2>
<p id="rtText">Wait for green...</p>
<button id="rtBtn" onclick="stopRT()">Click!</button>
</div>

<script>
let start;

function startRT(){
  document.getElementById("rtText").innerText = "Wait...";
  setTimeout(()=>{
    start = Date.now();
    document.getElementById("rtText").innerText = "CLICK NOW!";
  }, Math.random()*3000 + 1000);
}

function stopRT(){
  if(!start){
    startRT();
    return;
  }
  let time = Date.now() - start;
  alert("Your reaction time: " + time + " ms");
  start = null;
  startRT();
}

startRT();
</script>
<div class="game">
<h2>Solar System Quiz</h2>
<p id="q"></p>
<button onclick="answer(true)">Earth is the 3rd planet?</button>
<button onclick="answer(false)">Sun is a planet?</button>
</div>

<script>
function loadQ(){
  document.getElementById("q").innerText = "Answer the question:";
}

function answer(a){
  alert(a ? "Correct!" : "Wrong!");
}
loadQ();
</script>
<div class="game">
<h2>Treasure Hunt</h2>
<p>Pick a box 👇</p>
<div id="treasure"></div>
</div>

<script>
function createBoxes(){
  let box = document.getElementById("treasure");
  for(let i=0;i<6;i++){
    let b = document.createElement("button");
    b.innerText = "📦";
    b.onclick = ()=>{
      if(i === Math.floor(Math.random()*6)){
        alert("🎉 You found the treasure!");
      } else {
        alert("Try again!");
      }
    };
    box.appendChild(b);
  }
}
createBoxes();
</script>
<div class="game">
<h2>💬 Birthday Chat</h2>

<div id="chatBox" style="height:200px; overflow:auto; border:1px solid #ccc; padding:10px;"></div>

<input id="msg" placeholder="Type message">
<button onclick="sendMsg()">Send</button>
</div>

<script>
function sendMsg(){
  let text = document.getElementById("msg").value;
  if(!text) return;

  let box = document.getElementById("chatBox");
  let msg = document.createElement("p");

  msg.innerText = "You 🎂: " + text;
  box.appendChild(msg);

  document.getElementById("msg").value = "";
  box.scrollTop = box.scrollHeight;
}
</script>
<div class="game">
<h2>🏆 Leaderboard</h2>

<input id="player" placeholder="Your name">
<button onclick="addScore()">Add Score</button>

<ul id="board"></ul>
</div>

<script>
let scores = [];

function addScore(){
  let name = document.getElementById("player").value || "Player";
  let score = Math.floor(Math.random()*100);

  scores.push({name, score});
  scores.sort((a,b)=>b.score-a.score);

  renderBoard();
}

function renderBoard(){
  let list = document.getElementById("board");
  list.innerHTML = "";

  scores.forEach((s,i)=>{
    let li = document.createElement("li");
    li.innerText = `${i+1}. ${s.name} - ${s.score}`;
    list.appendChild(li);
  });
}
</script>
<div class="game">
<h2>🎖️ Achievements</h2>

<button onclick="unlock('First Game Played')">Play Game</button>
<button onclick="unlock('Chat Master')">Send Message</button>
<button onclick="unlock('Score Hunter')">Get Score</button>

<div id="badges"></div>
</div>

<script>
let badges = [];

function unlock(name){
  if(!badges.includes(name)){
    badges.push(name);
  }
  renderBadges();
}

function renderBadges(){
  let box = document.getElementById("badges");
  box.innerHTML = "";

  badges.forEach(b=>{
    let d = document.createElement("div");
    d.innerText = "🏅 " + b;
    box.appendChild(d);
  });
}
</script>
<style>
body {
  overflow-x: hidden;
}

.balloon {
  position: fixed;
  bottom: -100px;
  font-size: 30px;
  animation: floatUp 6s linear infinite;
}

@keyframes floatUp {
  from { transform: translateY(0); }
  to { transform: translateY(-110vh); }
}
</style>

<script>
function spawnBalloon(){
  let b = document.createElement("div");
  b.className = "balloon";
  b.innerText = "🎈";
  b.style.left = Math.random()*100 + "vw";
  b.style.animationDuration = (3 + Math.random()*5) + "s";
  document.body.appendChild(b);

  setTimeout(()=>b.remove(),8000);
}

setInterval(spawnBalloon, 800);
</script>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Bouquet Surprise</title>
<style>
    body {
        margin: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(to top, #ffe6f0, #fff);
        font-family: Arial, sans-serif;
    }

    .container {
        text-align: center;
    }

    .bouquet {
        width: 200px;
        cursor: pointer;
        transition: transform 0.3s ease;
    }

    .bouquet:hover {
        transform: scale(1.1);
    }

    .message {
        margin-top: 20px;
        font-size: 30px;
        color: #ff1493;
        display: none;
        font-weight: bold;
    }
</style>
</head>
<body>

<div class="container">
    <!-- Simple bouquet emoji image alternative -->
    <img src="https://cdn-icons-png.flaticon.com/512/3468/3468376.png" 
         class="bouquet" 
         onclick="showMessage()" 
         alt="Bouquet">

    <div id="msg" class="message">🎉 Happy Birthday 🎉</div>
</div>

<script>
    function showMessage() {
        document.getElementById("msg").style.display = "block";
    }
</script>

</body>
</html>
<!-- MESSAGE -->
<div id="msg" class="message">🎉 Happy Birthday 🎉</div>

<canvas id="fireworks"></canvas>

<script>
function showMessage() {
    document.getElementById("msg").style.display = "block";
    startFireworks();
}

/* ---------- FIREWORKS ---------- */
const canvas = document.getElementById("fireworks");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let particles = [];

function random(min, max) {
    return Math.random() * (max - min) + min;
}

function createFirework(x, y) {
    for (let i = 0; i < 60; i++) {
        particles.push({
            x: x,
            y: y,
            radius: 2,
            color: `hsl(${Math.random() * 360}, 100%, 60%)`,
            angle: Math.random() * 2 * Math.PI,
            speed: random(2, 6),
            alpha: 1
        });
    }
}

function updateFireworks() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    particles.forEach((p, i) => {
        p.x += Math.cos(p.angle) * p.speed;
        p.y += Math.sin(p.angle) * p.speed;
        p.alpha -= 0.01;

        ctx.globalAlpha = p.alpha;
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
        ctx.fillStyle = p.color;
        ctx.fill();

        if (p.alpha <= 0) {
            particles.splice(i, 1);
        }
    });

    ctx.globalAlpha = 1;
    requestAnimationFrame(updateFireworks);
}

function startFireworks() {
    createFirework(window.innerWidth / 2, window.innerHeight / 2);
}

updateFireworks();
</script>

</body>
</html>
