<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Daksh 🎂</title>
<style>
  body {
    font-family: 'Comic Sans MS', cursive;
    background: linear-gradient (right, #ffe6f0, #e6f7ff);
    text-align: center;
    margin: 0;
    overflow-x: hidden;
  }
  #passwordScreen, #dashboard, #secretNote {
    display: none;
  }
  h1, h2 { color: #ff6699; }
  .balloon {
    position: absolute;
    bottom: -100 px;
    width: 50 px;
    height: 70 px;
    border-radius: 50 %;
    animation: float 10s infinite;
  }
  @ keyframes float {
    0% { bottom: -100 px; }
    100% { bottom: 100vh; }
  }
  .confetti {
    position: fixed;
    width: 10 px;
    height: 10 px;
    animation: fall 5 s infinite;
  }
  @ keyframes fall {
    0% { top: -10 px; }
    100% { top: 100vh; }
  }
  .game {
    border: 2 px solid #ccc;
    margin: 10 px;
    padding: 10 px;
    background: #fff;
    border-radius: 10 px;
  }
  .note {
    background: #fff0f5;
    padding: 20 px;
    border-radius: 10 px;
    margin: 20 px;
  }
  #games { display: flex; flex-wrap: wrap; justify-content: center; }
  .game canvas { background: #f9f9f9; }
</style>
</head>
<body>

<!-- Password Screen -->
<div id="passwordScreen">
  <h1>🎁 Surprise!</h1>
  <p>Enter Password:</p>
  <input type="password" id="passInput">
  <button onclick="checkPassword()">Open</button>
</div>

<!-- Birthday Dashboard -->
<div id="dashboard">
  <h1>🎉 Happy Birthday Daksh 🎉</h1>
  <p>This one is special, hope you know why...</p>

  <!-- Fireworks & Confetti -->
  <canvas id="fireworks"></canvas>
  <div id="confettiContainer"></div>

  <!-- Balloons & Kisses -->
  <div id="balloons"></div>
  <p>💋💋💋</p>

  <!-- Playlist -->
  <h2>🎵 Birthday Playlist</h2>
  <audio controls>
    <source src="song1.mp3" type="audio/mpeg">
  </audio>
  <audio controls>
    <source src="song2.mp3" type="audio/mpeg">
  </audio>

  <!-- Secret Note -->
  <button onclick="unlockNote()">Open Secret Note</button>
</div>

<!-- Secret Note -->
<div id="secretNote">
  <div class="note">
    <h2>💌 Secret Note</h2>
    <p>Happiest Birthday to the person who is the reason for my happiness.<br>
    And this month I would not throw tantrums.<br>
    Will not annoy you as this is ur Birthday Month.<br>
    From: Ms. Bishnoi 💖</p>
  </div>
</div>

<!-- Game Menu -->
<h2>🎮 Game Menu</h2>
<div id="games">
  <div class="game" id="game1">Game 1: Tic-Tac-Toe <canvas id="ticTacToe" width="200" height="200"></canvas></div>
  <div class="game" id="game2">Game 2: Rock Paper Scissors <button onclick="playRPS()">Play</button></div>
  <div class="game" id="game3">Game 3: Number Guessing <button onclick="guessNumber()">Play</button></div>
  <div class="game" id="game4">Game 4: Birthday Trivia <button onclick="birthdayTrivia()">Play</button></div>
  <div class="game" id="game5">Game 5: Science Quiz <button onclick="scienceQuiz()">Play</button></div>
  <div class="game" id="game6">Game 6: Memory Match <button onclick="memoryMatch()">Play</button></div>
  <div class="game" id="game7">Game 7: Hangman <button onclick="hangman()">Play</button></div>
  <div class="game" id="game8">Game 8: Typing Test <button onclick="typingTest()">Play</button></div>
  <div class="game" id="game9">Game 9: Planet Match <button onclick="planetMatch()">Play</button></div>
  <div class="game" id="game10">Game 10: Solar System Quiz <button onclick="solarQuiz()">Play</button></div>
  <div class="game" id="game11">Game 11: Snake <canvas id="snake" width="200" height="200"></canvas></div>
  <div class="game" id="game12">Game 12: Maze Runner <button onclick="mazeRunner()">Play</button></div>
  <div class="game" id="game13">Game 13: Balloon Pop <button onclick="balloonPop()">Play</button></div>
  <div class="game" id="game14">Game 14: Catch the Star <button onclick="catchStar()">Play</button></div>
  <div class="game" id="game15">Game 15: Word Scramble <button onclick="wordScramble()">Play</button></div>
  <div class="game" id="game16">Game 16: Simon Says <button onclick="simonSays()">Play</button></div>
  <div class="game" id="game17">Game 17: Puzzle Slider <button onclick="puzzleSlider()">Play</button></div>
  <div class="game" id="game18">Game 18: Lucky Wheel <button onclick="luckyWheel()">Spin</button></div>
  <div class="game" id="game19">Game 19: Treasure Hunt <button onclick="treasureHunt()">Play</button></div>
  <div class="game" id="game20">Game 20: Space Shooter <canvas id="spaceShooter" width="200" height="200"></canvas></div>
</div>

<!-- Leaderboard & Achievements -->
<h2>🏆 Leaderboard</h2>
<p>Coming soon...</p>
<h2>🎖️ Achievement Badges</h2>
<p>Collect badges by playing games!</p>

<script>
  // Password screen
  document.getElementById("passwordScreen").style.display = "block";
  functioncheckPassword() {
    letinput = document.getElementById("passInput").value;
       (input === "MINE") {
      document.getElementById("passwordScreen").style.display = "none";
      document.getElementById("dashboard").style.display = "block";
    }  {
      alert("Wrong password!");
    }
  }
  functionunlockNote() {
    letpwd = prompt("Enter secret note password:");
       (pwd === "28/10/10") {
      document.getElementById("secretNote").style.display = "block";
    }  {
      alert("Incorrect password!");
    }
  }

  // Balloons
  (leti=0; i<10; i++) {
    letballoon = document.createElement("div");
    balloon.className = "balloon";
    balloon.style.left = Math.random()*100 + "vw";
    balloon.style.background = "hsl(" + Math.random()*360 + ",70%,80%)";
    document.getElementById("balloons").appendChild(balloon);
  }

  // Confetti
  (leti=0; i<50; i++) {
    letconfetti = document.createElement("div");
    confetti.className = "confetti";
    confetti.style.left = Math.random()*100 + "vw";
    confetti.style.background = "hsl(" + Math.random()*360 + ",70%,50%)";
    document.getElementById("confettiContainer").appendChild(confetti);
  }

  // Example Game Functions
  functionplayRPS(){ alert("Rock Paper Scissors game coming soon!"); }
  functionguessNumber(){ alert("Guess a number between 1-10!"); }
  functionbirthdayTrivia(){ alert("Trivia: Daksh loves surprises!"); }
  functionscienceQuiz(){ alert("Science Quiz: Earth is the 3rd planet!"); }
  functionmemoryMatch(){ alert
  <!-- Ending Fireworks & Birthday Wish -->
<canvas id="finalFireworks"></canvas>
<h1 id="birthdayWish">🎆🎂 Happy Birthday Daksh 🎂🎆</h1>

<script>
  // Fireworks animation
  constcanvas = document.getElementById("finalFireworks");
  constctx = canvas.getContext("2d");
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  functionrandom(min, max) { returnMath.random() * (max - min) + min; }

  classFirework {
    constructor() {
      this.x = random(0, canvas.width);
      this.y = canvas.height;
      this.targetY = random(canvas.height/4, canvas.height/2);
      this.color = `hsl(${random(0,360)},100%,50%)`;
      this.particles = [];
    }
    update() {
      if(this.y > this.targetY) {
        this.y -= 5;
      } else {
        for(let i=0;i<50;i++) {
          this.particles.push(new Particle(this.x,this.y,this.color));
        }
        fireworks.splice(fireworks.indexOf(this),1);
      }
    }
    draw() {
      ctx.fillStyle = this.color;
      ctx.fillRect(this.x,this.y,2,2);
    }
  }

  class Particle {
    constructor(x,y,color) {
      this.x=x; this.y=y; this.color=color;
      this.velX=random(-3,3); this.velY=random(-3,3);
      this.alpha=1;
    }
    update() {
      this.x+=this.velX; this.y+=this.velY;
      this.alpha-=0.02;
      if(this.alpha<=0) particles.splice(particles.indexOf(this),1);
    }
    draw() {
      ctx.fillStyle=this.color;
      ctx.globalAlpha=this.alpha;
      ctx.fillRect(this.x,this.y,2,2);
      ctx.globalAlpha=1;
    }
  }

  let fireworks=[]; let particles=[];
  function animate() {
    ctx.fillStyle="rgba(0,0,0,0.2)";
    ctx.fillRect(0,0,canvas.width,canvas.height);
    if(Math.random()<0.05) fireworks.push(new Firework());
    fireworks.forEach(f=>{f.update();f.draw();});
    particles.forEach(p=>{p.update();p.draw();});
    requestAnimationFrame(animate);
  }
  animate();

  // Glowing Birthday Wish
  const wish=document.getElementById("birthdayWish");
  wish.style.fontSize="3em";
  wish.style.color="#ff66cc";
  wish.style.textShadow="0 0 20px #ff99cc, 0 0 40px #ff66cc, 0 0 60px #ff3399";
</script>
