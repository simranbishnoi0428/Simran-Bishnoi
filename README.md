<!DOCTYPE html>
<html>
<head>
  <title>Happy Birthday Daksh</title>
  <style>
    body {
      background: linear-gradient(to bottom, #f8d9e0, #d9f8f0);
      font-family: Arial, sans-serif;
      text-align: center;
      overflow-x: hidden;
    }
    #passwordGate, #noteGate {
      margin-top: 100px;
    }
    .hidden { display: none; }
    canvas { border: 2px solid #333; margin: 10px; }
    #kissCounter { font-size: 20px; margin-top: 20px; color: #e91e63; }
  </style>
</head>
<body>

<div id="passwordGate">
  <h2>🎁 Surprise! Enter Password:</h2>
  <input type="password" id="pwInput" placeholder="Enter password">
  <button onclick="checkPassword()">Unlock</button>
</div>

<div id="birthdayContent" class="hidden">
  <h1>🎉 Happy Birthday Daksh 🎉</h1>
  <p>This One is special, hope you know why...</p>
  
  <!-- Candle + Cake -->
  <button onclick="blowCandle()">Blow Candle</button>
  <button onclick="cutCake()">Cut Cake</button>
  <div id="confetti"></div>
  
  <!-- Music -->
  <iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd" frameborder="0" allowfullscreen></iframe>
  
  <!-- Kiss Counter -->
  <div id="kissCounter">💋 Kisses: 0</div>
  
  <!-- Game Hub -->
  <h2>🎮 Play Games</h2>
  <button onclick="loadGame('ticTacToe')">Tic Tac Toe</button>
  <button onclick="loadGame('snake')">Snake</button>
  <div id="gameContainer"></div>
  
  <!-- Note Gate -->
  <div id="noteGate">
    <h3>🔒 Enter Note Password:</h3>
    <input type="password" id="noteInput" placeholder="Enter password">
    <button onclick="checkNote()">Unlock Note</button>
    <div id="noteContent" class="hidden">
      <p>Happiest Birthday to the person who is the reason for my happiness. And this month I would not throw tantrums. Will not annoy you as this is ur Birthday Month. <br>From: Ms. Bishnoi 💕</p>
    </div>
  </div>
</div>

<script>
let kisses = 0;

function checkPassword() {
  if(document.getElementById('pwInput').value === "MINE") {
    document.getElementById('passwordGate').classList.add('hidden');
    document.getElementById('birthdayContent').classList.remove('hidden');
  } else { alert("Wrong password!"); }
}

function blowCandle() {
  alert("🎂 Candle blown! Confetti burst!");
  document.body.style.background = "pink";
}

function cutCake() {
  alert("🍰 Cake cut! Fireworks!");
  document.body.style.background = "lightyellow";
}

function checkNote() {
  if(document.getElementById('noteInput').value === "28/10/10") {
    document.getElementById('noteContent').classList.remove('hidden');
  } else { alert("Wrong note password!"); }
}

function addKiss(count) {
  kisses += count;
  document.getElementById('kissCounter').innerText = "💋 Kisses: " + kisses;
}

function loadGame(game) {
  let container = document.getElementById('gameContainer');
  container.innerHTML = "";
  if(game === "ticTacToe") {
    container.innerHTML = `<canvas id="ticTacToeCanvas" width="300" height="300"></canvas>`;
    // Simple Tic Tac Toe placeholder
    addKiss(2); // reward
  }
  if(game === "snake") {
    container.innerHTML = `<canvas id="snakeCanvas" width="300" height="300"></canvas>`;
    // Simple Snake placeholder
    addKiss(2); // reward
  }
}
</script>

</body>
</html>
<!DOCTYPE html>
<html>
<head>
  <title>Happy Birthday Daksh</title>
  <style>
    body {
      background: linear-gradient(to bottom, #f8d9e0, #d9f8f0);
      font-family: Arial, sans-serif;
      text-align: center;
      overflow-x: hidden;
    }
    #passwordGate, #noteGate { margin-top: 100px; }
    .hidden { display: none; }
    canvas { border: 2px solid #333; margin: 10px; }
    #kissCounter { font-size: 20px; margin-top: 20px; color: #e91e63; }
    button { margin: 5px; padding: 10px; }
  </style>
</head>
<body>

<div id="passwordGate">
  <h2>🎁 Surprise! Enter Password:</h2>
  <input type="password" id="pwInput" placeholder="Enter password">
  <button onclick="checkPassword()">Unlock</button>
</div>

<div id="birthdayContent" class="hidden">
  <h1>🎉 Happy Birthday Daksh 🎉</h1>
  <p>This One is special, hope you know why...</p>
  
  <!-- Candle + Cake -->
  <button onclick="blowCandle()">Blow Candle</button>
  <button onclick="cutCake()">Cut Cake</button>
  
  <!-- Music -->
  <iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd" frameborder="0" allowfullscreen></iframe>
  
  <!-- Kiss Counter -->
  <div id="kissCounter">💋 Kisses: 0</div>
  
  <!-- Game Hub -->
  <h2>🎮 Play Games</h2>
  <button onclick="loadGame('ticTacToe')">Tic Tac Toe</button>
  <button onclick="loadGame('snake')">Snake</button>
  <button onclick="loadGame('rps')">Rock Paper Scissors</button>
  <button onclick="loadGame('hangman')">Hangman</button>
  <button onclick="loadGame('memory')">Memory Match</button>
  <button onclick="loadGame('scramble')">Word Scramble</button>
  <div id="gameContainer"></div>
  
  <!-- Note Gate -->
  <div id="noteGate">
    <h3>🔒 Enter Note Password:</h3>
    <input type="password" id="noteInput" placeholder="Enter password">
    <button onclick="checkNote()">Unlock Note</button>
    <div id="noteContent" class="hidden">
      <p>Happiest Birthday to the person who is the reason for my happiness. And this month I would not throw tantrums. Will not annoy you as this is ur Birthday Month. <br>From: Ms. Bishnoi 💕</p>
    </div>
  </div>
</div>

<script>
let kisses = 0;

function checkPassword() {
  if(document.getElementById('pwInput').value === "MINE") {
    document.getElementById('passwordGate').classList.add('hidden');
    document.getElementById('birthdayContent').classList.remove('hidden');
  } else { alert("Wrong password!"); }
}

function blowCandle() {
  alert("🎂 Candle blown! Confetti burst!");
  document.body.style.background = "pink";
}

function cutCake() {
  alert("🍰 Cake cut! Fireworks!");
  document.body.style.background = "lightyellow";
}

function checkNote() {
  if(document.getElementById('noteInput').value === "28/10/10") {
    document.getElementById('noteContent').classList.remove('hidden');
  } else { alert("Wrong note password!"); }
}

function addKiss(count) {
  kisses += count;
  document.getElementById('kissCounter').innerText = "💋 Kisses: " + kisses;
}

function loadGame(game) {
  let container = document.getElementById('gameContainer');
  container.innerHTML = "";
  
  if(game === "ticTacToe") {
    container.innerHTML = `<p>Tic Tac Toe coming soon...</p>`;
    addKiss(2);
  }
  if(game === "snake") {
    container.innerHTML = `<p>Snake Game coming soon...</p>`;
    addKiss(2);
  }
  if(game === "rps") {
    container.innerHTML = `
      <h3>Rock Paper Scissors</h3>
      <button onclick="playRPS('rock')">Rock</button>
      <button onclick="playRPS('paper')">Paper</button>
      <button onclick="playRPS('scissors')">Scissors</button>
      <p id="rpsResult"></p>`;
  }
  if(game === "hangman") {
    container.innerHTML = `
      <h3>Hangman</h3>
      <p id="hangmanWord"></p>
      <input id="hangGuess" maxlength="1">
      <button onclick="guessHangman()">Guess</button>
      <p id="hangmanStatus"></p>`;
    startHangman();
  }
  if(game === "memory") {
    container.innerHTML = `
      <h3>Memory Match</h3>
      <p>Match pairs to win kisses!</p>`;
    addKiss(2);
  }
  if(game === "scramble") {
    container.innerHTML = `
      <h3>Word Scramble</h3>
      <p id="scrambleWord"></p>
      <input id="scrambleGuess">
      <button onclick="checkScramble()">Guess</button>
      <p id="scrambleResult"></p>`;
    startScramble();
  }
}

// Rock Paper Scissors
function playRPS(choice) {
  let options = ["rock","paper","scissors"];
  let comp = options[Math.floor(Math.random()*3)];
  let result = "";
  if(choice===comp) result="Draw!";
  else if((choice==="rock"&&comp==="scissors")||(choice==="paper"&&comp==="rock")||(choice==="scissors"&&comp==="paper")) {
    result="You win!";
    addKiss(2);
  } else result="You lose!";
  document.getElementById('rpsResult').innerText = "Computer chose "+comp+". "+result;
}

// Hangman
let hangWord, hangDisplay, hangTries;
function startHangman() {
  hangWord = "birthday";
  hangDisplay = "_".repeat(hangWord.length).split("");
  hangTries = 6;
  document.getElementById('hangmanWord').innerText = hangDisplay.join(" ");
}
function guessHangman() {
  let guess = document.getElementById('hangGuess').value;
  let found = false;
  for(let i=0;i<hangWord.length;i++){
    if(hangWord[i]===guess){ hangDisplay[i]=guess; found=true; }
  }
  if(!found) hangTries--;
  document.getElementById('hangmanWord').innerText = hangDisplay.join(" ");
  if(hangDisplay.join("")===hangWord){ document.getElementById('hangmanStatus').innerText="You win!"; addKiss(2); }
  else if(hangTries<=0){ document.getElementById('hangmanStatus').innerText="Game over!"; }
}

// Word Scramble
let scrambleWord, scrambled;
function startScramble() {
  scrambleWord = "cake";
  scrambled = scrambleWord.split("").sort(()=>Math.random()-0.5).join("");
  document.getElementById('scrambleWord').innerText = scrambled;
}
function checkScramble() {
  let guess = document.getElementById('scrambleGuess').value;
  if(guess===scrambleWord){ document.getElementById('scrambleResult').innerText="Correct!"; addKiss(2); }
  else document.getElementById('scrambleResult').innerText="Try again!";
}
</script>

</body>
</html>
<!DOCTYPE html>
<html>
<head>
  <title>Happy Birthday Daksh</title>
  <style>
    body {
      background: linear-gradient(to bottom, #f8d9e0, #d9f8f0);
      font-family: Arial, sans-serif;
      text-align: center;
      overflow-x: hidden;
    }
    #passwordGate, #noteGate { margin-top: 100px; }
    .hidden { display: none; }
    canvas { border: 2px solid #333; margin: 10px; }
    #kissCounter { font-size: 20px; margin-top: 20px; color: #e91e63; }
    button { margin: 5px; padding: 10px; }
  </style>
</head>
<body>

<div id="passwordGate">
  <h2>🎁 Surprise! Enter Password:</h2>
  <input type="password" id="pwInput" placeholder="Enter password">
  <button onclick="checkPassword()">Unlock</button>
</div>

<div id="birthdayContent" class="hidden">
  <h1>🎉 Happy Birthday Daksh 🎉</h1>
  <p>This One is special, hope you know why...</p>
  
  <!-- Candle + Cake -->
  <button onclick="blowCandle()">Blow Candle</button>
  <button onclick="cutCake()">Cut Cake</button>
  
  <!-- Music -->
  <iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd" frameborder="0" allowfullscreen></iframe>
  
  <!-- Kiss Counter -->
  <div id="kissCounter">💋 Kisses: 0</div>
  
  <!-- Game Hub -->
  <h2>🎮 Play Games</h2>
  <button onclick="loadGame('ticTacToe')">Tic Tac Toe</button>
  <button onclick="loadGame('snake')">Snake</button>
  <button onclick="loadGame('rps')">Rock Paper Scissors</button>
  <button onclick="loadGame('hangman')">Hangman</button>
  <button onclick="loadGame('memory')">Memory Match</button>
  <button onclick="loadGame('scramble')">Word Scramble</button>
  <button onclick="loadGame('balloon')">Balloon Pop</button>
  <button onclick="loadGame('treasure')">Treasure Hunt</button>
  <button onclick="loadGame('wheel')">Lucky Wheel</button>
  <button onclick="loadGame('simon')">Simon Says</button>
  <button onclick="loadGame('slider')">Puzzle Slider</button>
  <div id="gameContainer"></div>
  
  <!-- Note Gate -->
  <div id="noteGate">
    <h3>🔒 Enter Note Password:</h3>
    <input type="password" id="noteInput" placeholder="Enter password">
    <button onclick="checkNote()">Unlock Note</button>
    <div id="noteContent" class="hidden">
      <p>Happiest Birthday to the person who is the reason for my happiness. And this month I would not throw tantrums. Will not annoy you as this is ur Birthday Month. <br>From: Ms. Bishnoi 💕</p>
    </div>
  </div>
</div>

<script>
let kisses = 0;

function checkPassword() {
  if(document.getElementById('pwInput').value === "MINE") {
    document.getElementById('passwordGate').classList.add('hidden');
    document.getElementById('birthdayContent').classList.remove('hidden');
  } else { alert("Wrong password!"); }
}

function blowCandle() {
  alert("🎂 Candle blown! Confetti burst!");
  document.body.style.background = "pink";
}

function cutCake() {
  alert("🍰 Cake cut! Fireworks!");
  document.body.style.background = "lightyellow";
}

function checkNote() {
  if(document.getElementById('noteInput').value === "28/10/10") {
    document.getElementById('noteContent').classList.remove('hidden');
  } else { alert("Wrong note password!"); }
}

function addKiss(count) {
  kisses += count;
  document.getElementById('kissCounter').innerText = "💋 Kisses: " + kisses;
}

function loadGame(game) {
  let container = document.getElementById('gameContainer');
  container.innerHTML = "";
  
  if(game === "balloon") {
    container.innerHTML = `
      <h3>Balloon Pop 🎈</h3>
      <button onclick="popBalloon()">Pop Balloon</button>
      <p id="balloonResult"></p>`;
  }
  if(game === "treasure") {
    container.innerHTML = `
      <h3>Treasure Hunt 🗺️</h3>
      <button onclick="findTreasure()">Search Treasure</button>
      <p id="treasureResult"></p>`;
  }
  if(game === "wheel") {
    container.innerHTML = `
      <h3>Lucky Wheel 🎡</h3>
      <button onclick="spinWheel()">Spin</button>
      <p id="wheelResult"></p>`;
  }
  if(game === "simon") {
    container.innerHTML = `
      <h3>Simon Says 🎵</h3>
      <button onclick="playSimon()">Play</button>
      <p id="simonResult"></p>`;
  }
  if(game === "slider") {
    container.innerHTML = `
      <h3>Puzzle Slider 🧩</h3>
      <p>Slide puzzle coming soon...</p>`;
    addKiss(2);
  }
}

// Balloon Pop
function popBalloon() {
  document.getElementById('balloonResult').innerText = "🎈 Balloon popped!";
  addKiss(2);
}

// Treasure Hunt
function findTreasure() {
  let found = Math.random() > 0.5;
  if(found){ document.getElementById('treasureResult').innerText="You found treasure!"; addKiss(2); }
  else { document.getElementById('treasureResult').innerText="No treasure here..."; }
}

// Lucky Wheel
function spinWheel() {
  let outcomes = ["Win Kiss","Lose","Try Again"];
  let result = outcomes[Math.floor(Math.random()*outcomes.length)];
  document.getElementById('wheelResult').innerText = result;
  if(result==="Win Kiss") addKiss(2);
}

// Simon Says
function playSimon() {
  let commands = ["Simon says jump","Simon says clap","Clap"];
  let command = commands[Math.floor(Math.random()*commands.length)];
  document.getElementById('simonResult').innerText = command;
  if(command.startsWith("Simon says")) addKiss(2);
}
</script>

</body>
</html>
<!DOCTYPE html>
<html>
<head>
  <title>Happy Birthday Daksh</title>
  <style>
    body {
      background: linear-gradient(to bottom, #f8d9e0, #d9f8f0);
      font-family: Arial, sans-serif;
      text-align: center;
      overflow-x: hidden;
    }
    #passwordGate, #noteGate { margin-top: 100px; }
    .hidden { display: none; }
    canvas { border: 2px solid #333; margin: 10px; }
    #kissCounter { font-size: 20px; margin-top: 20px; color: #e91e63; }
    button { margin: 5px; padding: 10px; }
  </style>
</head>
<body>

<div id="passwordGate">
  <h2>🎁 Surprise! Enter Password:</h2>
  <input type="password" id="pwInput" placeholder="Enter password">
  <button onclick="checkPassword()">Unlock</button>
</div>

<div id="birthdayContent" class="hidden">
  <h1>🎉 Happy Birthday Daksh 🎉</h1>
  <p>This One is special, hope you know why...</p>
  
  <!-- Candle + Cake -->
  <button onclick="blowCandle()">Blow Candle</button>
  <button onclick="cutCake()">Cut Cake</button>
  
  <!-- Music -->
  <iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd" frameborder="0" allowfullscreen></iframe>
  
  <!-- Kiss Counter -->
  <div id="kissCounter">💋 Kisses: 0</div>
  
  <!-- Game Hub -->
  <h2>🎮 Play Games</h2>
  <button onclick="loadGame('ticTacToe')">Tic Tac Toe</button>
  <button onclick="loadGame('snake')">Snake</button>
  <button onclick="loadGame('rps')">Rock Paper Scissors</button>
  <button onclick="loadGame('hangman')">Hangman</button>
  <button onclick="loadGame('memory')">Memory Match</button>
  <button onclick="loadGame('scramble')">Word Scramble</button>
  <button onclick="loadGame('balloon')">Balloon Pop</button>
  <button onclick="loadGame('treasure')">Treasure Hunt</button>
  <button onclick="loadGame('wheel')">Lucky Wheel</button>
  <button onclick="loadGame('simon')">Simon Says</button>
  <button onclick="loadGame('slider')">Puzzle Slider</button>
  <button onclick="loadGame('maze')">Maze Runner</button>
  <button onclick="loadGame('typing')">Typing Speed Test</button>
  <button onclick="loadGame('number')">Number Guessing</button>
  <button onclick="loadGame('planet')">Planet Match</button>
  <button onclick="loadGame('space')">Space Shooter</button>
  <button onclick="loadGame('star')">Catch the Star</button>
  <button onclick="loadGame('trivia')">Birthday Trivia</button>
  <div id="gameContainer"></div>
  
  <!-- Note Gate -->
  <div id="noteGate">
    <h3>🔒 Enter Note Password:</h3>
    <input type="password" id="noteInput" placeholder="Enter password">
    <button onclick="checkNote()">Unlock Note</button>
    <div id="noteContent" class="hidden">
      <p>Happiest Birthday to the person who is the reason for my happiness. And this month I would not throw tantrums. Will not annoy you as this is ur Birthday Month. <br>From: Ms. Bishnoi 💕</p>
    </div>
  </div>
</div>

<script>
let kisses = 0;

function checkPassword() {
  if(document.getElementById('pwInput').value === "MINE") {
    document.getElementById('passwordGate').classList.add('hidden');
    document.getElementById('birthdayContent').classList.remove('hidden');
  } else { alert("Wrong password!"); }
}

function blowCandle() {
  alert("🎂 Candle blown! Confetti burst!");
  document.body.style.background = "pink";
}

function cutCake() {
  alert("🍰 Cake cut! Fireworks!");
  document.body.style.background = "lightyellow";
}

function checkNote() {
  if(document.getElementById('noteInput').value === "28/10/10") {
    document.getElementById('noteContent').classList.remove('hidden');
  } else { alert("Wrong note password!"); }
}

function addKiss(count) {
  kisses += count;
  document.getElementById('kissCounter').innerText = "💋 Kisses: " + kisses;
}

function loadGame(game) {
  let container = document.getElementById('gameContainer');
  container.innerHTML = "";
  
  if(game === "maze") {
    container.innerHTML = `<h3>Maze Runner 🏃</h3><p>Navigate the maze (demo)...</p>`;
    addKiss(2);
  }
  if(game === "typing") {
    container.innerHTML = `
      <h3>Typing Speed Test ⌨️</h3>
      <p>Type: "HappyBirthdayDaksh"</p>
      <input id="typingInput">
      <button onclick="checkTyping()">Submit</button>
      <p id="typingResult"></p>`;
  }
  if(game === "number") {
    container.innerHTML = `
      <h3>Number Guessing 🔢</h3>
      <input id="numGuess" type="number">
      <button onclick="checkNumber()">Guess</button>
      <p id="numResult"></p>`;
    window.secretNum = Math.floor(Math.random()*10)+1;
  }
  if(game === "planet") {
    container.innerHTML = `
      <h3>Planet Match 🌍</h3>
      <p>Earth is the ____ planet from the Sun.</p>
      <input id="planetGuess">
      <button onclick="checkPlanet()">Submit</button>
      <p id="planetResult"></p>`;
  }
  if(game === "space") {
    container.innerHTML = `<h3>Space Shooter 🚀</h3><p>Shoot aliens (demo)...</p>`;
    addKiss(2);
  }
  if(game === "star") {
    container.innerHTML = `
      <h3>Catch the Star ⭐</h3>
      <button onclick="catchStar()">Catch</button>
      <p id="starResult"></p>`;
  }
  if(game === "trivia") {
    container.innerHTML = `
      <h3>Birthday Trivia 🎂</h3>
      <p>What date is Daksh's birthday?</p>
      <input id="triviaGuess">
      <button onclick="checkTrivia()">Submit</button>
      <p id="triviaResult"></p>`;
  }
}

// Typing Speed
function checkTyping() {
  let val = document.getElementById('typingInput').value;
  if(val==="HappyBirthdayDaksh"){ document.getElementById('typingResult').innerText="Correct!"; addKiss(2); }
  else document.getElementById('typingResult').innerText="Try again!";
}

// Number Guessing
function checkNumber() {
  let guess = parseInt(document.getElementById('numGuess').value);
  if(guess===window.secretNum){ document.getElementById('numResult').innerText="Correct!"; addKiss(2); }
  else document.getElementById('numResult').innerText="Wrong!";
}

// Planet Match
function checkPlanet() {
  let guess = document.getElementById('planetGuess').value;
  if(guess==="third"){ document.getElementById('planetResult').innerText="Correct!"; addKiss(2); }
  else document.getElementById('planetResult').innerText="Nope!";
}

// Catch the Star
function catchStar() {
  if(Math.random()>0.5){ document.getElementById('starResult').innerText="You caught a star!"; addKiss(2); }
  else document.getElementById('starResult').innerText="Missed!";
}

// Trivia
function checkTrivia() {
  let guess = document.getElementById('triviaGuess').value;
  if(guess==="28/10/10"){ document.getElementById('triviaResult').innerText="Correct!"; addKiss(2); }
  else document.getElementById('triviaResult').innerText="Wrong!";
}
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday Daksh</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(to bottom, #f8d9e0, #d9f8f0);
      font-family: 'Brush Script MT', cursive;
      text-align: center;
      overflow: hidden;
    }
    h1 {
      font-size: 60px;
      color: #ff4081;
      text-shadow: 2px 2px #fff;
      margin-top: 50px;
    }
    h2 {
      font-size: 40px;
      color: #42a5f5;
      text-shadow: 2px 2px #fff;
    }
    #bouquet {
      margin-top: 30px;
    }
    #signature {
      margin-top: 20px;
      font-size: 30px;
      color: purple;
    }
    canvas {
      position: fixed;
      top: 0;
      left: 0;
      z-index: -1;
    }
  </style>
</head>
<body>

  <h1>Happy Birthday</h1>
  <h2>Daksh!</h2>

  <!-- Bouquet Image -->
  <div id="bouquet">
    <img src="https://copilot.microsoft.com/th/id/BCO.d62bbcab-6da2-44f4-b21d-3deda0b7878d.png" alt="Bouquet and Fireworks" width="500">
  </div>

  <!-- Signature -->
  <div id="signature">
    With Love,<br>Ms. Bishnoi 💕
  </div>

  <!-- Fireworks Canvas -->
  <canvas id="fireworks"></canvas>

  <script>
    const canvas = document.getElementById('fireworks');
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    class Firework {
      constructor(x, y, colors) {
        this.x = x;
        this.y = y;
        this.colors = colors;
        this.particles = [];
        for (let i = 0; i < 100; i++) {
          this.particles.push({
            x: x,
            y: y,
            angle: Math.random() * 2 * Math.PI,
            speed: Math.random() * 5 + 2,
            radius: Math.random() * 2 + 1,
            life: 100
          });
        }
      }
      draw() {
        this.particles.forEach(p => {
          const dx = Math.cos(p.angle) * p.speed;
          const dy = Math.sin(p.angle) * p.speed;
          p.x += dx;
          p.y += dy;
          p.life--;
          ctx.beginPath();
          ctx.arc(p.x, p.y, p.radius, 0, 2 * Math.PI);
          ctx.fillStyle = this.colors[Math.floor(Math.random() * this.colors.length)];
          ctx.fill();
        });
      }
    }

    let fireworks = [];
    function animate() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      fireworks.forEach(f => f.draw());
      fireworks = fireworks.filter(f => f.particles.some(p => p.life > 0));
      requestAnimationFrame(animate);
    }

    setInterval(() => {
      const x = Math.random() * canvas.width;
      const y = Math.random() * canvas.height / 2;
      const colors = ["#ff4081", "#42a5f5", "#ffd740", "#ab47bc"];
      fireworks.push(new Firework(x, y, colors));
    }, 1000);

    animate();
  </script>

</body>
</html>
