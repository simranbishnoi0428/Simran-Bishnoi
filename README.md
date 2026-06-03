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
font-family:Segoe UI,sans-serif;
}

body{
background:linear-gradient(135deg,#0f172a,#1e293b);
color:white;
overflow-x:hidden;
}

.page{
min-height:100vh;
display:flex;
justify-content:center;
align-items:center;
flex-direction:column;
text-align:center;
padding:20px;
}

input{
padding:12px;
width:250px;
border:none;
border-radius:10px;
margin:10px;
}

button{
padding:12px 25px;
background:#ff4da6;
border:none;
color:white;
border-radius:10px;
cursor:pointer;
}

button:hover{
transform:scale(1.05);
}

#main{
display:none;
}

.hero{
height:100vh;
display:flex;
justify-content:center;
align-items:center;
flex-direction:column;
background:
linear-gradient(
rgba(0,0,0,.4),
rgba(0,0,0,.4)
);
}

.hero h1{
font-size:5rem;
color:#ffd700;
}

.hero h2{
margin-top:20px;
}

.section{
padding:60px 20px;
text-align:center;
}

.card{
max-width:900px;
margin:auto;
padding:25px;
border-radius:20px;
background:rgba(255,255,255,.08);
backdrop-filter:blur(10px);
margin-bottom:20px;
}

.games{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
gap:15px;
}

.game{
background:rgba(255,255,255,.1);
padding:20px;
border-radius:15px;
}

.balloon{
position:fixed;
bottom:-100px;
font-size:50px;
animation:float linear infinite;
}

@keyframes float{
from{
transform:translateY(0);
}
to{
transform:translateY(-120vh);
}
}

.kiss{
position:fixed;
font-size:35px;
animation:kissMove 10s linear infinite;
}

@keyframes kissMove{
from{
transform:translateY(100vh);
}
to{
transform:translateY(-100vh);
}
}

.chatBox{
width:80%;
max-width:600px;
height:250px;
overflow:auto;
background:#111;
padding:15px;
border-radius:15px;
margin:auto;
}

.chatInput{
width:70%;
}

</style>
</head>

<body>

<div id="login" class="page">

<h1>🎁 Surprise Waiting...</h1>

<p>Enter Password</p>

<input id="pass" type="password">

<button onclick="unlock()">
Unlock
</button>

</div>

<div id="main">

<div class="hero">

<h1>🎂 HAPPY BIRTHDAY DAKSH 🎂</h1>

<h2>
This one is special...
Hope you know why ❤️
</h2>

</div>

<section class="section">

<div class="card">

<h2>💖 Birthday Message</h2>

<p>

Happy Birthday Daksh ❤️

May your year be filled with happiness,
success, science discoveries,
and unforgettable memories.

</p>

</div>

</section>

<section class="section">

<div class="card">

<h2>🔬 Science Dashboard</h2>

<p>⚛ Theory of Relativity</p>
<p>🌍 Gravity</p>
<p>🧬 DNA Structure</p>
<p>⚡ Electricity</p>
<p>☢ Radioactivity</p>
<p>🌌 Big Bang Theory</p>
<p>🔭 Quantum Mechanics</p>

</div>

</section>

<section class="section">

<div class="card">

<h2>🪐 Solar System Quiz</h2>

<p>

Which planet is known as the Red Planet?

</p>

<button onclick="alert('Correct! Mars')">
Mars
</button>

</div>

</section>

<section class="section">

<div class="card">

<h2>🗺 Treasure Hunt</h2>

<p>

Clue 1:
I shine in the sky and give light.
What am I?

</p>

<input id="clue1">

<button onclick="checkClue()">
Submit
</button>

</div>

</section>

<section class="section">

<div class="card">

<h2>💬 Birthday Chat</h2>

<div id="chat" class="chatBox"></div>

<input
class="chatInput"
id="msg">

<button onclick="sendMsg()">
Send
</button>

</div>

</section>

<section class="section">

<div class="card">

<h2>🎵 MP3 Playlist</h2>

<audio controls>
<source src="music/perfect.mp3">
</audio>

<audio controls>
<source src="music/tu-chahiye.mp3">
</audio>

<audio controls>
<source src="music/haareya.mp3">
</audio>

<audio controls>
<source src="music/ye-tune-kya-kiya.mp3">
</audio>

<audio controls>
<source src="music/teri-deewani.mp3">
</audio>

</div>

</section>

<section class="section">

<div class="card">

<h2>🔒 Secret Note</h2>

<input
id="notePass"
type="password"
placeholder="Password">

<button onclick="openNote()">

Open Note

</button>

<div id="note" style="display:none">

<h3>To Daksh ❤️</h3>

<p>

Happiest Birthday to the person
who is the reason for my happiness.

And this month I would not
throw tantrums.

Will not annoy you as this is
your Birthday Month.

❤️

From:
Ms. Bishnoi

</p>

</div>

</div>

</section>

<section class="section">

<h2>🎮 20 Games Zone</h2>

<div class="games">

<div class="game">1. Tic Tac Toe</div>
<div class="game">2. Snake</div>
<div class="game">3. Memory Game</div>
<div class="game">4. Hangman</div>
<div class="game">5. Word Search</div>
<div class="game">6. Space Shooter</div>
<div class="game">7. Balloon Pop</div>
<div class="game">8. Quiz Challenge</div>
<div class="game">9. Planet Match</div>
<div class="game">10. Puzzle</div>
<div class="game">11. Maze</div>
<div class="game">12. Typing Test</div>
<div class="game">13. Guess Number</div>
<div class="game">14. Rock Paper Scissors</div>
<div class="game">15. Simon Says</div>
<div class="game">16. Memory Cards</div>
<div class="game">17. Speed Click</div>
<div class="game">18. Catch Star</div>
<div class="game">19. Trivia</div>
<div class="game">20. Lucky Wheel</div>

</div>

</section>

</div>

<script>

function unlock(){

let p =
document.getElementById("pass").value;

if(p==="MINE"){

document.getElementById("login").style.display="none";
document.getElementById("main").style.display="block";

fireworks();
balloons();
kisses();

}else{

alert("Wrong Password");

}

}

function openNote(){

let p =
document.getElementById("notePass").value;

if(p==="28/10/10"){

document.getElementById("note").style.display="block";

}

}

function sendMsg(){

let msg =
document.getElementById("msg").value;

document.getElementById("chat").innerHTML +=
"<p>"+msg+"</p>";

}

function checkClue(){

let ans =
document.getElementById("clue1").value
.toLowerCase();

if(ans==="sun"){

alert("Correct! Next clue unlocked!");

}

}

function balloons(){

for(let i=0;i<40;i++){

let b =
document.createElement("div");

b.className="balloon";
b.innerHTML="🎈";

b.style.left=
Math.random()*100+"vw";

b.style.animationDuration=
5+Math.random()*8+"s";

document.body.appendChild(b);

}

}

function kisses(){

for(let i=0;i<20;i++){

let k =
document.createElement("div");

k.className="kiss";
k.innerHTML="💋";

k.style.left=
Math.random()*100+"vw";

document.body.appendChild(k);

}

}

function fireworks(){

for(let i=0;i<300;i++){

let c =
document.createElement("div");

c.innerHTML="🎉";

c.style.position="fixed";
c.style.left=Math.random()*100+"vw";
c.style.top="-50px";

document.body.appendChild(c);

setTimeout(()=>{
c.style.transition="5s";
c.style.top="100vh";
},100);

}

}

</script>

</body>
</html>
