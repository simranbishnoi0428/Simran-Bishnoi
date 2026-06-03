<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Daksh!</title>
    <style>
        :root {
            --bg-pastel-pink: #FFE5EC;
            --bg-pastel-blue: #E8F0FE;
            --bg-pastel-purple: #F3E5F5;
            --pastel-primary: #FFB7B2;
            --pastel-secondary: #BDB2FF;
            --pastel-accent: #FFDAC1;
            --text-color: #4A4A4A;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-pastel-pink);
            color: var(--text-color);
            overflow-x: hidden;
            position: relative;
            min-height: 100vh;
        }

        /* Canvas Backgrounds */
        #starsCanvas, #fireworksCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -1;
            pointer-events: none;
        }

        #confettiCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 999;
            pointer-events: none;
            display: none;
        }

        /* Password Screen */
        #passwordScreen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--bg-pastel-blue);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            transition: opacity 0.5s ease;
        }

        .card {
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            text-align: center;
            max-width: 400px;
            width: 90%;
        }

        h1, h2, h3 {
            color: #6C5B7B;
            margin-bottom: 20px;
        }

        input[type="password"], input[type="text"] {
            width: 100%;
            padding: 12px 20px;
            margin: 15px 0;
            border: 2px solid var(--pastel-primary);
            border-radius: 25px;
            outline: none;
            font-size: 16px;
            text-align: center;
        }

        button {
            background-color: var(--pastel-secondary);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            transition: transform 0.2s, background-color 0.2s;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        button:hover {
            transform: translateY(-2px);
            background-color: #9a8cff;
        }

        /* Main Content */
        #mainContent {
            display: none;
            padding: 20px;
            max-width: 1000px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            margin-bottom: 40px;
            padding: 40px 20px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 30px;
            backdrop-filter: blur(5px);
        }

        /* Interactive Birthday Elements */
        .interactive-section {
            background: rgba(255, 255, 255, 0.85);
            padding: 30px;
            border-radius: 30px;
            margin-bottom: 40px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.02);
        }

        .cake-container {
            position: relative;
            width: 200px;
            height: 200px;
            margin: 40px auto;
            cursor: pointer;
        }

        .cake {
            position: absolute;
            bottom: 0;
            width: 200px;
            height: 100px;
            background: #F3C68F;
            border-radius: 20px 20px 0 0;
            box-shadow: inset 0 10px 0 #E29A6B;
        }

        .cake-layer {
            position: absolute;
            bottom: 30px;
            width: 200px;
            height: 200px;
            background: #FFF0F5;
            border-radius: 50%;
            z-index: 1;
        }

        .candle {
            position: absolute;
            top: -40px;
            left: 90px;
            width: 20px;
            height: 50px;
            background: linear-gradient(to right, #FFB7B2, #FFDAC1);
            border-radius: 5px;
            z-index: 2;
        }

        .flame {
            position: absolute;
            top: -20px;
            left: 3px;
            width: 14px;
            height: 25px;
            background: #FFB347;
            border-radius: 50% 50% 20% 20%;
            animation: flicker 0.1s infinite alternate;
        }

        @keyframes flicker {
            0% { transform: scale(1); }
            100% { transform: scale(1.1) rotate(2deg); }
        }

        .cut-line {
            position: absolute;
            top: 50%;
            left: 0;
            width: 100%;
            height: 4px;
            background: transparent;
            z-index: 3;
        }

        .cake.cut .cut-line {
            background: rgba(0,0,0,0.1);
        }

        /* Kiss Counter */
        #kissCounterContainer {
            position: fixed;
            top: 20px;
            right: 20px;
            background: white;
            padding: 15px 25px;
            border-radius: 50px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            z-index: 900;
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: bold;
            font-size: 18px;
        }

        .kiss-icon {
            color: #FF6B6B;
            font-size: 24px;
            animation: heartbeat 1.5s infinite;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.15); }
        }

        /* Dashboard Grid */
        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .game-card {
            background: white;
            padding: 25px;
            border-radius: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            box-shadow: 0 5px 15px rgba(0,0,0,0.02);
        }

        .game-card:hover {
            transform: translateY(-5px);
            border-color: var(--pastel-primary);
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
        }

        .game-icon {
            font-size: 40px;
            margin-bottom: 15px;
        }

        /* Game Modal Overlay */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.4);
            z-index: 1001;
            justify-content: center;
            align-items: center;
            backdrop-filter: blur(4px);
        }

        .modal-content {
            background: white;
            padding: 30px;
            border-radius: 25px;
            max-width: 600px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 20px;
            right: 25px;
            font-size: 30px;
            cursor: pointer;
            color: #aaa;
        }

        /* Bouquet Section */
        .bouquet-container {
            font-size: 80px;
            margin: 20px 0;
            animation: sway 3s ease-in-out infinite alternate;
        }

        @keyframes sway {
            0% { transform: rotate(-5deg); }
            100% { transform: rotate(5deg); }
        }

        /* Music Playlist Layout */
        .playlist-container {
            margin: 30px 0;
            border-radius: 15px;
            overflow: hidden;
        }

        /* Secret Note Locked Area */
        .secret-note-area {
            background: #FFF9E6;
            border: 2px dashed #FFD54F;
        }

        /* Game Implementation Spaces */
        .game-stage {
            background: #fdfdfd;
            border-radius: 15px;
            padding: 20px;
            margin-top: 20px;
            min-height: 250px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        /* Specific Game CSS Styles */
        .ttt-grid {
            display: grid;
            grid-template-columns: repeat(3, 80px);
            grid-template-rows: repeat(3, 80px);
            gap: 5px;
        }
        .ttt-cell {
            background: var(--bg-pastel-blue);
            border: none;
            border-radius: 10px;
            font-size: 32px;
            font-weight: bold;
            cursor: pointer;
        }
        
        .memory-grid {
            display: grid;
            grid-template-columns: repeat(4, 60px);
            gap: 10px;
        }
        .memory-card {
            width: 60px;
            height: 60px;
            background: var(--pastel-secondary);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: transparent;
            cursor: pointer;
        }
        .memory-card.flipped {
            color: white;
            background: var(--pastel-primary);
        }

        .snake-canvas {
            background: #e0e0e0;
            border-radius: 5px;
        }

        .balloon-container {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            justify-content: center;
        }
        .balloon {
            width: 50px;
            height: 70px;
            border-radius: 50% 50% 50% 50% / 40% 40% 60% 60%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        .maze-container {
            display: grid;
            grid-template-columns: repeat(10, 25px);
            gap: 1px;
            background: #ccc;
        }
        .maze-cell {
            width: 25px;
            height: 25px;
            background: white;
        }
        .maze-wall { background: #6C5B7B; }
        .maze-player { background: #FFB7B2; border-radius: 50%; }
        .maze-goal { background: #FFD166; }

        .wheel-container {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 5px solid #ccc;
            position: relative;
            transition: transform 3s cubic-bezier(0.1, 0.8, 0.3, 1);
            background: conic-gradient(red 0 60deg, orange 60deg 120deg, yellow 120deg 180deg, green 180deg 240deg, blue 240deg 300deg, purple 300deg 360deg);
        }

        .slider-grid {
            display: grid;
            grid-template-columns: repeat(3, 60px);
            gap: 5px;
        }
        .slider-cell {
            width: 60px;
            height: 60px;
            background: var(--pastel-primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            cursor: pointer;
            border-radius: 5px;
        }

        /* Footer Decoration */
        footer {
            margin-top: 50px;
            padding: 40px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 30px 30px 0 0;
            text-align: center;
        }
        
        .footer-photo-placeholder {
            width: 150px;
            height: 150px;
            background: var(--pastel-primary);
            border-radius: 50%;
            margin: 20px auto;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 50px;
            border: 5px solid white;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>

    <canvas id="starsCanvas"></canvas>
    <canvas id="fireworksCanvas"></canvas>
    <canvas id="confettiCanvas"></canvas>

    <div id="kissCounterContainer">
        <span class="kiss-icon">💋</span> Space: <span id="kissCount">0</span> Kisses
    </div>

    <div id="passwordScreen">
        <div class="card">
            <h2>Surprise!</h2>
            <p>Please enter the verification password to proceed:</p>
            <input type="password" id="initialPassword" placeholder="Enter Password">
            <button onclick="checkInitialPassword()">Unlock Surprise</button>
            <p id="passwordError" style="color: red; margin-top: 10px; display: none;">Incorrect password. Try again!</p>
        </div>
    </div>

    <div id="mainContent">
        <header>
            <h1>Happy Birthday Daksh</h1>
            <p style="font-style: italic; color: #888;">This One is special hope you know why...</p>
            
            <div class="cake-container" onclick="interactCake()">
                <div class="candle" id="candle"><div class="flame" id="flame"></div></div>
                <div class="cake-layer"></div>
                <div class="cake" id="cakeElement"><div class="cut-line"></div></div>
            </div>
            <p id="cakeInstruction" style="font-weight: 500;">Click the cake to blow the candle and cut it!</p>
        </header>

        <div class="interactive-section">
            <h3>A Special Bouquet For You 💐</h3>
            <div class="bouquet-container">💐🌹🌷🌻🌼</div>
            <p>Enjoy the endless pastel fireworks shifting across your special day dashboard!</p>
        </div>

        <div class="interactive-section">
            <h3>🎵 Soundtrack of the Day</h3>
            <div class="playlist-container">
                <iframe width="100%" height="150" src="https://www.youtube.com/embed/videoseries?list=PLy32nUMhA3riuWTxvIFuI29GSuysi2snd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
            </div>
        </div>

        <h2 style="text-align: center; margin-bottom: 20px;">🎮 Play to Win Rewards for Ms. Bishnoi</h2>
        <div class="games-grid">
            <div class="game-card" onclick="openGame('ttt')"><div class="game-icon">❌</div><h4>Tic Tac Toe</h4></div>
            <div class="game-card" onclick="openGame('snake')"><div class="game-icon">🐍</div><h4>Snake Game</h4></div>
            <div class="game-card" onclick="openGame('memory')"><div class="game-icon">🃏</div><h4>Memory Card Match</h4></div>
            <div class="game-card" onclick="openGame('hangman')"><div class="game-icon">🪓</div><h4>Hangman</h4></div>
            <div class="game-card" onclick="openGame('balloon')"><div class="game-icon">🎈</div><h4>Balloon Pop Treasure Hunt</h4></div>
            <div class="game-card" onclick="openGame('rps')"><div class="game-icon">✊</div><h4>Rock Paper Scissors</h4></div>
            <div class="game-card" onclick="openGame('maze')"><div class="game-icon">🌀</div><h4>Maze Runner</h4></div>
            <div class="game-card" onclick="openGame('guess')"><div class="game-icon">🔮</div><h4>Number Guessing</h4></div>
            <div class="game-card" onclick="openGame('planet')"><div class="game-icon">🪐</div><h4>Planet Match</h4></div>
            <div class="game-card" onclick="openGame('scramble')"><div class="game-icon">🔤</div><h4>Word Scramble</h4></div>
            <div class="game-card" onclick="openGame('wheel')"><div class="game-icon">🎡</div><h4>Lucky Wheel</h4></div>
            <div class="game-card" onclick="openGame('slider')"><div class="game-icon">🧩</div><h4>Puzzle Slider</h4></div>
            <div class="game-card" onclick="openGame('star')"><div class="game-icon">⭐</div><h4>Catch the Star</h4></div>
            <div class="game-card" onclick="openGame('trivia')"><div class="game-icon">📝</div><h4>Birthday Trivia for Daksh</h4></div>
        </div>

        <div class="interactive-section secret-note-area">
            <h3>🔒 Locked Personal Letter from Ms. Bishnoi</h3>
            <p>Enter Daksh's special birthdate password (DD/MM/YY format) to unlock this deep letter.</p>
            <input type="text" id="notePassword" placeholder="Enter password (e.g. 28/10/10)">
            <button onclick="unlockNote()">Unlock Note</button>
            <div id="secretNoteContent" style="display:none; margin-top:20px; padding:20px; background:white; border-radius:15px; text-align:left; line-height:1.6;">
                <strong>Note:</strong> Happiest Birthday to the person who is the reason for my happiness. And this month I would not throw tantrums. Will not annoy you as this is ur Birthday Month. <br><br><em>From: Ms. Bishnoi</em>
            </div>
        </div>

        <footer>
            <div class="footer-photo-placeholder">👑</div>
            <h2>Happy Birthday Daksh!</h2>
            <p style="font-size: 20px; color: #FF6B6B; margin-top: 10px;">👑 Sending endless love and kisses 💋</p>
            <p style="font-weight: bold; margin-top: 5px;">From: Ms. Bishnoi</p>
        </footer>
    </div>

    <div class="modal" id="gameModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeGame()">&times;</span>
            <h2 id="modalGameTitle">Game Arena</h2>
            <div id="modalGameWrapper" class="game-stage"></div>
        </div>
    </div>

    <script>
        // Core Variables
        let kisses = 0;
        let candleBlown = false;
        let cakeCut = false;

        // Canvas setups
        const starsCanvas = document.getElementById('starsCanvas');
        const sCtx = starsCanvas.getContext('2d');
        const fwCanvas = document.getElementById('fireworksCanvas');
        const fCtx = fwCanvas.getContext('2d');
        const confCanvas = document.getElementById('confettiCanvas');
        const cCtx = confCanvas.getContext('2d');

        function resizeCanvases() {
            starsCanvas.width = fwCanvas.width = confCanvas.width = window.innerWidth;
            starsCanvas.height = fwCanvas.height = confCanvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvases);
        resizeCanvases();

        // 1. Password Verification Gateway
        function checkInitialPassword() {
            const pass = document.getElementById('initialPassword').value;
            if (pass === "MINE") {
                document.getElementById('passwordScreen').style.opacity = '0';
                setTimeout(() => {
                    document.getElementById('passwordScreen').style.display = 'none';
                    document.getElementById('mainContent').style.display = 'block';
                    initBackgroundEffects();
                }, 500);
            } else {
                document.getElementById('passwordError').style.display = 'block';
            }
        }

        // Reward Processor
        function addRewardKisses(amount) {
            kisses += amount;
            document.getElementById('kissCount').innerText = kisses;
        }

        // 2. Interactive Cake Setup
        function interactCake() {
            if (!candleBlown) {
                document.getElementById('flame').style.display = 'none';
                candleBlown = true;
                document.getElementById('cakeInstruction').innerText = "Candle blown! Now tap to cut the cake.";
                triggerConfettiBurst();
            } else if (!cakeCut) {
                document.getElementById('cakeElement').classList.add('cut');
                cakeCut = true;
                document.getElementById('cakeInstruction').innerText = "Happy Birthday Daksh! Enjoy your day!";
                triggerConfettiBurst();
            }
        }

        // 3. Unlock Note Area
        function unlockNote() {
            const pass = document.getElementById('notePassword').value;
            if (pass === "28/10/10") {
                document.getElementById('secretNoteContent').style.display = 'block';
            } else {
                alert("Incorrect date password keys! Please try again.");
            }
        }

        // Background FX: Shooting Stars and Pastel Fireworks engine
        let stars = [];
        let fireworks = [];
        let confettis = [];

        function initBackgroundEffects() {
            // Generate steady stars background
            for(let i=0; i<40; i++) {
                stars.push({
                    x: Math.random() * starsCanvas.width,
                    y: Math.random() * starsCanvas.height,
                    len: Math.random() * 80 + 50,
                    speed: Math.random() * 4 + 2
                });
            }
            animateBackgrounds();
        }

        function animateBackgrounds() {
            // Draw Shooting Stars
            sCtx.clearRect(0,0,starsCanvas.width, starsCanvas.height);
            sCtx.strokeStyle = 'rgba(255, 255, 255, 0.4)';
            sCtx.lineWidth = 1.5;
            stars.forEach(star => {
                sCtx.beginPath();
                sCtx.moveTo(star.x, star.y);
                sCtx.lineTo(star.x - star.len, star.y + star.len);
                sCtx.stroke();
                star.x += star.speed;
                star.y += star.speed;
                if(star.x > starsCanvas.width || star.y > starsCanvas.height) {
                    star.x = Math.random() * starsCanvas.width;
                    star.y = -50;
                }
            });

            // Handle Active Fireworks Rendering
            fCtx.clearRect(0,0,fwCanvas.width, fwCanvas.height);
            if(Math.random() < 0.03) { // Continual passive burst rate
                launchFirework();
            }
            fireworks.forEach((fw, index) => {
                fw.particles.forEach(p => {
                    fCtx.fillStyle = p.color;
                    fCtx.fillRect(p.x, p.y, p.size, p.size);
                    p.x += p.vx;
                    p.y += p.vy;
                    p.vy += 0.04; // gravity elements
                    p.alpha -= 0.01;
                });
                fw.particles = fw.particles.filter(p => p.alpha > 0);
                if(fw.particles.length === 0) fireworks.splice(index, 1);
            });

            // Handle Active Confetti Rendering
            if(confettis.length > 0) {
                cCtx.clearRect(0,0,confCanvas.width, confCanvas.height);
                confettis.forEach((c, index) => {
                    cCtx.fillStyle = c.color;
                    cCtx.save();
                    cCtx.translate(c.x, c.y);
                    cCtx.rotate(c.rotation);
                    cCtx.fillRect(-c.size/2, -c.size/2, c.size, c.size);
                    cCtx.restore();
                    
                    c.x += c.vx;
                    c.y += c.vy;
                    c.rotation += c.vRotation;
                    if(c.y > confCanvas.height) confettis.splice(index, 1);
                });
            }

            requestAnimationFrame(animateBackgrounds);
        }

        function launchFirework() {
            const colors = ['#FFB7B2', '#FFDAC1', '#E2F0CB', '#BDB2FF', '#FFC6FF', '#E8F0FE'];
            const targetX = Math.random() * fwCanvas.width;
            const targetY = Math.random() * (fwCanvas.height * 0.5);
            const pCount = 40;
            let particles = [];
            const chosenColor = colors[Math.floor(Math.random() * colors.length)];
            for(let i=0; i<pCount; i++) {
                const angle = (Math.PI * 2 / pCount) * i;
                const speed = Math.random() * 3 + 1;
                particles.push({
                    x: targetX,
                    y: targetY,
                    vx: Math.cos(angle) * speed,
                    vy: Math.sin(angle) * speed,
                    size: Math.random() * 3 + 2,
                    color: chosenColor,
                    alpha: 1
                });
            }
            fireworks.push({particles});
        }

        function triggerConfettiBurst() {
            confCanvas.style.display = 'block';
            const pastelColors = ['#FFB7B2', '#FFDAC1', '#E2F0CB', '#BDB2FF', '#FFC6FF'];
            for(let i=0; i<100; i++) {
                confettis.push({
                    x: window.innerWidth / 2,
                    y: window.innerHeight * 0.4,
                    vx: (Math.random() - 0.5) * 10,
                    vy: (Math.random() - 0.7) * 12,
                    size: Math.random() * 8 + 6,
                    color: pastelColors[Math.floor(Math.random() * pastelColors.length)],
                    rotation: Math.random() * Math.PI,
                    vRotation: (Math.random() - 0.5) * 0.2
                });
            }
        }

        // 4. Multi-Games System Implementation Core
        const wrapper = document.getElementById('modalGameWrapper');
        
        function openGame(gameKey) {
            document.getElementById('gameModal').style.display = 'flex';
            wrapper.innerHTML = ''; // clean old engine contents
            
            if(gameKey === 'ttt') {
                document.getElementById('modalGameTitle').innerText = "Tic Tac Toe";
                setupTicTacToe();
            } else if(gameKey === 'snake') {
                document.getElementById('modalGameTitle').innerText = "Snake Game";
                setupSnake();
            } else if(gameKey === 'memory') {
                document.getElementById('modalGameTitle').innerText = "Memory Match";
                setupMemory();
            } else if(gameKey === 'hangman') {
                document.getElementById('modalGameTitle').innerText = "Hangman";
                setupHangman();
            } else if(gameKey === 'balloon') {
                document.getElementById('modalGameTitle').innerText = "Balloon Pop";
                setupBalloon();
            } else if(gameKey === 'rps') {
                document.getElementById('modalGameTitle').innerText = "Rock Paper Scissors";
                setupRPS();
            } else if(gameKey === 'maze') {
                document.getElementById('modalGameTitle').innerText = "Maze Runner";
                setupMaze();
            } else if(gameKey === 'guess') {
                document.getElementById('modalGameTitle').innerText = "Number Guessing";
                setupGuess();
            } else if(gameKey === 'planet') {
                document.getElementById('modalGameTitle').innerText = "Planet Match";
                setupPlanet();
            } else if(gameKey === 'scramble') {
                document.getElementById('modalGameTitle').innerText = "Word Scramble";
                setupScramble();
            } else if(gameKey === 'wheel') {
                document.getElementById('modalGameTitle').innerText = "Lucky Wheel";
                setupWheel();
            } else if(gameKey === 'slider') {
                document.getElementById('modalGameTitle').innerText = "Puzzle Slider";
                setupSlider();
            } else if(gameKey === 'star') {
                document.getElementById('modalGameTitle').innerText = "Catch the Star";
                setupStar();
            } else if(gameKey === 'trivia') {
                document.getElementById('modalGameTitle').innerText = "Daksh Birthday Trivia";
                setupTrivia();
            }
        }

        function closeGame() {
            document.getElementById('gameModal').style.display = 'none';
            // Clear running intervals if active
            if(window.gameInterval) clearInterval(window.gameInterval);
        }

        /* --- GAME ENGINE MODULES --- */

        // 1. Tic Tac Toe
        function setupTicTacToe() {
            wrapper.innerHTML = '<div class="ttt-grid" id="tttGrid"></div>';
            let board = ["","","","","","","","",""];
            const grid = document.getElementById('tttGrid');
            for(let i=0; i<9; i++) {
                let cell = document.createElement('button');
                cell.className = 'ttt-cell';
                cell.addEventListener('click', () => {
                    if(board[i] === "") {
                        board[i] = "X";
                        cell.innerText = "X";
                        if(checkTTT(board, "X")) { alert("Daksh wins!"); addRewardKisses(1); return; }
                        // Basic Bot move
                        let empty = board.map((v,idx) => v === "" ? idx : null).filter(v => v !== null);
                        if(empty.length > 0) {
                            let move = empty[Math.floor(Math.random() * empty.length)];
                            board[move] = "O";
                            grid.children[move].innerText = "O";
                            if(checkTTT(board, "O")) { alert("Bot wins!"); }
                        }
                    }
                });
                grid.appendChild(cell);
            }
        }
        function checkTTT(b, p) {
            const w = [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]];
            return w.some(comb => comb.every(idx => b[idx] === p));
        }

        // 2. Snake Game
        function setupSnake() {
            wrapper.innerHTML = '<canvas id="sc" class="snake-canvas" width="200" height="200"></canvas><p>Click board, use keys (W,A,S,D)</p>';
            const canvas = document.getElementById('sc');
            const ctx = canvas.getContext('2d');
            let snake = [{x:100, y:100}];
            let dx = 10, dy = 0;
            let food = {x: 40, y: 40};

            window.addEventListener('keydown', (e) => {
                if(e.key==='w'||e.key==='ArrowUp') { dx=0; dy=-10; }
                if(e.key==='s'||e.key==='ArrowDown') { dx=0; dy=10; }
                if(e.key==='a'||e.key==='ArrowLeft') { dx=-10; dy=0; }
                if(e.key==='d'||e.key==='ArrowRight') { dx=10; dy=0; }
            });

            window.gameInterval = setInterval(() => {
                let head = {x: snake[0].x + dx, y: snake[0].y + dy};
                snake.unshift(head);
                if(head.x === food.x && head.y === food.y) {
                    food = {x: Math.floor(Math.random()*19)*10, y: Math.floor(Math.random()*19)*10};
                    addRewardKisses(1);
                } else {
                    snake.pop();
                }
                ctx.clearRect(0,0,200,200);
                ctx.fillStyle = "red"; ctx.fillRect(food.x, food.y, 10, 10);
                ctx.fillStyle = "green"; snake.forEach(p => ctx.fillRect(p.x, p.y, 10, 10));
                if(head.x<0||head.x>=200||head.y<0||head.y>=200) { clearInterval(window.gameInterval); alert("Game Over!"); }
            }, 150);
        }

        // 3. Memory Match Game
        function setupMemory() {
            wrapper.innerHTML = '<div class="memory-grid" id="mg"></div>';
            let items = ['🌸','🌸','🎈','🎈','🎁','🎁','👑','👑'];
            items.sort(() => Math.random() - 0.5);
            let choice = null;
            const mg = document.getElementById('mg');
            items.forEach((item, idx) => {
                let card = document.createElement('div');
                card.className = 'memory-card';
                card.innerText = item;
                card.onclick = () => {
                    card.classList.add('flipped');
                    if(!choice) { choice = card; }
                    else {
                        if(choice.innerText === card.innerText) {
                            addRewardKisses(1);
                            choice = null;
                        } else {
                            let prev = choice; choice = null;
                            setTimeout(() => { card.classList.remove('flipped'); prev.classList.remove('flipped'); }, 500);
                        }
                    }
                };
                mg.appendChild(card);
            });
        }

        // 4. Hangman Game
        function setupHangman() {
            let secret = "DAKSH";
            let guessed = [];
            wrapper.innerHTML = '<h3 id="hWord">_ _ _ _ _</h3><input type="text" id="hIn" maxlength="1" style="width:50px;"><button id="hBtn">Guess</button>';
            const hWord = document.getElementById('hWord');
            const hIn = document.getElementById('hIn');
            document.getElementById('hBtn').onclick = () => {
                let char = hIn.value.toUpperCase();
                if(char && !guessed.includes(char)) {
                    guessed.push(char);
                    let display = secret.split('').map(c => guessed.includes(c) ? c : '_').join(' ');
                    hWord.innerText = display;
                    if(!display.includes('_')) { alert("You solved it!"); addRewardKisses(1); }
                }
                hIn.value = '';
            };
        }

        // 5. Balloon Pop
        function setupBalloon() {
            wrapper.innerHTML = '<div class="balloon-container" id="bc"></div>';
            const bc = document.getElementById('bc');
            const colors = ['#FFB7B2','#BDB2FF','#FFDAC1'];
            for(let i=0; i<6; i++) {
                let b = document.createElement('div');
                b.className = 'balloon';
                b.style.backgroundColor = colors[i%3];
                b.innerText = "?";
                b.onclick = () => {
                    b.style.visibility = 'hidden';
                    if(Math.random() > 0.4) { alert("Found a hidden kiss inside!"); addRewardKisses(1); }
                };
                bc.appendChild(b);
            }
        }

        // 6. Rock Paper Scissors
        function setupRPS() {
            wrapper.innerHTML = '<button onclick="playRPS(\'rock\')">✊ Rock</button><button onclick="playRPS(\'paper\')">✋ Paper</button><button onclick="playRPS(\'scissors\')">✌️ Scissors</button><p id="rpsRes"></p>';
        }
        window.playRPS = function(player) {
            const choices = ['rock', 'paper', 'scissors'];
            let bot = choices[Math.floor(Math.random()*3)];
            let res = "";
            if(player === bot) res = "Tie!";
            else if((player==='rock'&&bot==='scissors')||(player==='paper'&&bot==='rock')||(player==='scissors'&&bot==='paper')) {
                res = "You Win!"; addRewardKisses(1);
            } else res = "Bot Wins!";
            document.getElementById('rpsRes').innerText = `You chose ${player}, Bot chose ${bot}. Result: ${res}`;
        };

        // 7. Maze Runner
        function setupMaze() {
            wrapper.innerHTML = '<div class="maze-container" id="mc"></div><p>Tap cells near pink to reach yellow goal!</p>';
            const mc = document.getElementById('mc');
            let layout = [
                2,0,1,1,1,1,1,1,1,1,
                0,0,0,0,0,1,0,0,0,1,
                1,1,1,1,0,1,0,1,0,1,
                1,0,0,0,0,0,0,1,0,1,
                1,1,1,1,1,1,1,1,0,3
            ];
            let pPos = 0;
            layout.forEach((cell, idx) => {
                let div = document.createElement('div');
                div.className = 'maze-cell';
                if(cell===1) div.classList.add('maze-wall');
                if(cell===2) div.classList.add('maze-player');
                if(cell===3) div.classList.add('maze-goal');
                div.onclick = () => {
                    if(Math.abs(idx - pPos) === 1 || Math.abs(idx - pPos) === 10) {
                        if(layout[idx] !== 1) {
                            mc.children[pPos].classList.remove('maze-player');
                            pPos = idx;
                            mc.children[pPos].classList.add('maze-player');
                            if(layout[pPos] === 3) { alert("Maze Solved!"); addRewardKisses(1); }
                        }
                    }
                };
                mc.appendChild(div);
            });
        }

        // 8. Number Guessing
        function setupGuess() {
            let secret = Math.floor(Math.random()*10)+1;
            wrapper.innerHTML = '<p>Guess between 1 and 10</p><input type="number" id="gIn" style="width:60px;"><button id="gBtn">Guess</button>';
            document.getElementById('gBtn').onclick = () => {
                let val = parseInt(document.getElementById('gIn').value);
                if(val === secret) { alert("Perfect guess!"); addRewardKisses(1); setupGuess(); }
                else if(val < secret) alert("Too Low!");
                else alert("Too High!");
            };
        }

        // 9. Planet Match
        function setupPlanet() {
            wrapper.innerHTML = '<p>Which planet is known as the Red Planet?</p><button onclick="checkPlanet(true)">Mars</button><button onclick="checkPlanet(false)">Venus</button>';
        }
        window.checkPlanet = function(isMars) {
            if(isMars) { alert("Correct match!"); addRewardKisses(1); } else { alert("Try again!"); }
        };

        // 10. Word Scramble
        function setupScramble() {
            wrapper.innerHTML = '<p>Unscramble: <b>HDBYITAR</b></p><input type="text" id="sIn"><button id="sBtn">Verify</button>';
            document.getElementById('sBtn').onclick = () => {
                if(document.getElementById('sIn').value.toUpperCase() === "BIRTHDAY") {
                    alert("Awesome word recognition!"); addRewardKisses(1);
                } else alert("Try again!");
            };
        }

        // 11. Lucky Wheel
        function setupWheel() {
            wrapper.innerHTML = '<div class="wheel-container" id="wheelElement"></div><button style="margin-top:15px;" onclick="spinWheel()">Spin Wheel</button>';
        }
        window.spinWheel = function() {
            let deg = Math.floor(Math.random() * 360) + 1440;
            document.getElementById('wheelElement').style.transform = `rotate(${deg}deg)`;
            setTimeout(() => { alert("You won a gift Kiss reward!"); addRewardKisses(1); }, 3100);
        };

        // 12. Puzzle Slider
        function setupSlider() {
            wrapper.innerHTML = '<div class="slider-grid" id="sg"></div>';
            const sg = document.getElementById('sg');
            let layout = [1, 2, 3, 4, 5, 6, 7, "", 8];
            layout.forEach((num, idx) => {
                let cell = document.createElement('div');
                cell.className = 'slider-cell';
                cell.innerText = num;
                cell.onclick = () => {
                    let emptyIdx = layout.indexOf("");
                    if([idx-1, idx+1, idx-3, idx+3].includes(emptyIdx)) {
                        layout[emptyIdx] = num;
                        layout[idx] = "";
                        setupSlider();
                        if(layout.join('') === "12345678") { alert("Puzzle finished!"); addRewardKisses(1); }
                    }
                };
                sg.appendChild(cell);
            });
        }

        // 13. Catch the Star
        function setupStar() {
            wrapper.innerHTML = '<button id="starTarget" style="position:absolute; padding:5px 10px;">⭐</button><p style="margin-top:80px;">Catch the moving star!</p>';
            const target = document.getElementById('starTarget');
            target.onclick = () => {
                alert("Caught it!"); addRewardKisses(1);
                target.style.top = Math.random()*150 + "px";
                target.style.left = Math.random()*150 + "px";
            };
        }

        // 14. Birthday Trivia For Daksh (10 Complete customized questions)
        let currentTriviaIdx = 0;
        const triviaQuestions = [
            { q: "What is Daksh's favorite celebration month?", a: "October" },
            { q: "Who is the primary provider of your absolute happiness?", a: "Ms. Bishnoi" },
            { q: "Complete the statement phrase: 'This One is...'", a: "special" },
            { q: "What date does Daksh celebrate birth on?", a: "28" },
            { q: "Which year marks Daksh's birth year according to note keys?", a: "2010" },
            { q: "Who promised not to throw any tantrum episodes this month?", a: "Ms. Bishnoi" },
            { q: "What specific month theme is designated as non-annoying?", a: "Birthday Month" },
            { q: "What is the primary unlock sequence password code used initially?", a: "MINE" },
            { q: "What item gets blown out first during standard celebrations?", a: "Candle" },
            { q: "Who is the final ultimate recipient of this interactive site layout?", a: "Daksh" }
        ];

        function setupTrivia() {
            currentTriviaIdx = 0;
            renderTriviaQuestion();
        }

        function renderTriviaQuestion() {
            if(currentTriviaIdx < triviaQuestions.length) {
                let qItem = triviaQuestions[currentTriviaIdx];
                wrapper.innerHTML = `<h5>Question ${currentTriviaIdx + 1}/10</h5><p style="margin:15px 0;">${qItem.q}</p><input type="text" id="tAns"><button onclick="checkTriviaAnswer()">Submit Answer</button>`;
            } else {
                wrapper.innerHTML = '<h4>Congratulations! You have successfully completed the full trivia run!</h4>';
            }
        }

        window.checkTriviaAnswer = function() {
            let playerAns = document.getElementById('tAns').value.trim().toLowerCase();
            let realAns = triviaQuestions[currentTriviaIdx].a.toLowerCase();
            if(playerAns === realAns) {
                alert("Correct! You earned 2 specialized kisses!");
                addRewardKisses(2); // unique double reward factor for Trivia items
            } else {
                alert(`Not quite! The expected correct response was: ${triviaQuestions[currentTriviaIdx].a}`);
            }
            currentTriviaIdx++;
            renderTriviaQuestion();
        };

    </script>
</body>
</html>
