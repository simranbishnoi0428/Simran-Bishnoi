<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Daksh 🎂</title>
<style>
  body {
    font-family: 'Comic Sans MS', cursive;
    background: linear-gradient(to right, #ffe6f0, #e6f7ff);
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
    bottom: -100px;
    width: 50px;
    height: 70px;
    border-radius: 50%;
    animation: float 10s infinite;
  }
  @keyframes float {
    0% { bottom: -100px; }
    100% { bottom: 100vh; }
  }
  .confetti {
    position: fixed;
    width: 10px;
    height: 10px;
    animation: fall 5s infinite;
  }
  @keyframes fall {
    0% { top: -10px; }
    100% { top: 100vh; }
  }
  .game {
    border: 2px solid #ccc;
    margin: 10px;
    padding: 10px;
    background: #fff;
    border-radius: 10px;
    width: 200px;
  }
  .note {
    background: #fff0f5;
    padding: 20px;
    border-radius: 10px;
    margin: 20px;
  }
  #games { display: flex; flex-wrap: wrap; justify-content: center; }
  #birthdayWish {
    font-size: 3em;
    color: #ff66cc;
    text-shadow: 0 0 20px #ff99cc, 0 0 40px #ff66cc, 0 0 60px #ff3399;
  }
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
    <source src="song1.mp3" type="https://youtube.com/playlist?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd&si=gWzmSWsubdrKMVL1">
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
  <div class="game">Game 1: Tic-Tac-Toe <button onclick="alert('Tic-Tac-Toe coming soon!')">Play</button></div>
  <div class="game">Game 2: Rock Paper Scissors <button onclick="alert('Rock Paper Scissors!')">Play</button></div>
  <div class="game">Game 3: Number Guessing <button onclick="alert('Guess a number between 1-10!')">Play</button></div>
  <div class="game">Game 4: Birthday Trivia <button onclick="alert('Trivia: Daksh loves surprises!')">Play</button></div>
  <div class="game">Game 5: Science Quiz <button onclick="alert('Science Quiz: Earth is the 3rd planet!')">Play</button></div>
  <div class="game">Game 6: Memory Match <button onclick="alert('Memory Match!')">Play</button></div>
  <div class="game">Game 7: Hangman <button onclick="alert('Hangman!')">Play</button></div>
  <div class="game">Game 8: Typing Test <button onclick="alert('Typing Test!')">Play</button></div>
  <div class="game">Game 9: Planet Match <button onclick="alert('Match planets!')">Play</button></div>
  <div class="game">Game 10: Solar System Quiz <button onclick="alert('Solar Quiz!')">Play</button></div>
  <div class="game">Game 11: Snake <button onclick="alert('Snake Game!')">Play</button></div>
  <div class="game">Game 12: Maze Runner <button onclick="alert('Maze Runner!')">Play</button></div>
  <div class="game">Game 13: Balloon Pop <button onclick="alert('Pop balloons!')">Play</button></div>
  <div class="game">Game 14: Catch the Star <button onclick="alert('Catch the star!')">Play</button></div>
  <div class="game">Game 15: Word Scramble <button onclick="alert('Scramble words!')">Play</button></div>
  <div class="game">Game 16: Simon Says <button onclick="alert('Simon Says!')">Play</button></div>
  <div class="game">Game 17: Puzzle Slider <button onclick="alert('Puzzle Slider!')">Play</button></div>
  <div class="game">Game 18: Lucky Wheel <button onclick="alert('Spin the wheel!')">Play</button></div>
  <div class="game">Game 19: Treasure Hunt <button onclick="alert('Treasure Hunt!')">Play</button></div>
  <div class="game">Game 20: Space Shooter <button onclick="alert('Space Shooter!')">Play</button></div>
</div>

<!-- Leaderboard & Achievements -->
<h2>🏆 Leaderboard</h2>
<p>Coming soon...</p>
<h2>🎖️ Achievement Badges</h2>
<p>Collect badges by playing games!</p>

<!-- Ending Fireworks & Birthday Wish -->
<canvas id="finalFireworks"></canvas>
<h1 id="birthdayWish">🎆🎂 Happy Birthday Daksh 🎂🎆</h1>

<script>
  // Password screen
  document.getElementById("passwordScreen").style.display = "block";
  function checkPassword() {
    let input = document.getElementById("passInput").value;
    if(input === "MINE") {
      document.getElementById("passwordScreen").style.display = "none";
      document.getElementById("dashboard").style.display = "block";
    } else {
      alert("Wrong password!");
    }
  }
  function unlockNote() {
    let pwd = prompt("Enter secret note password:");
    if(pwd === "28/10/10") {
      document.getElementById("secretNote").style.display = "block";
    } else {
      alert("Incorrect password!");
    }
  }

  // Balloons
  for(let i=0; i<10; i++) {
    let balloon = document.createElement("div");
    balloon.className = "balloon";
    balloon.style.left = Math.random()*100 + "vw";
    balloon.style.background = "hsl(" + Math.random()*360 + ",70%,80%)";
    document.getElementById("balloons").appendChild(balloon);
  }

  // Confetti
  for(let i=0; i<50; i++) {
    let confetti = document.createElement("div");
    confetti.className = "confetti";
    confetti.style.left = Math.random()*100 + "vw";
    confetti.style.background = "hsl(" + Math.random()*360 + ",70%,50%)";
    document.getElementById("confettiContainer").appendChild(confetti);
  }

  // Ending Fireworks
  const canvas = document.get
