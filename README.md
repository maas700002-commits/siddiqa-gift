<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine Proposal for Siddiqa</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to bottom, #ff69b4, #ffb6c1);
            color: #fff;
            text-align: center;
            margin: 0;
            padding: 20px;
            overflow-x: hidden;
        }
        h1, h2 { color: #ff1493; }
        .heart { font-size: 2em; animation: float 3s ease-in-out infinite; }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }
        .game { margin: 20px; padding: 20px; background: rgba(255, 255, 255, 0.2); border-radius: 10px; }
        button { background: #ff1493; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; font-size: 1.2em; }
        button:hover { background: #ff69b4; }
        #proposal { display: none; margin-top: 50px; }
        .box { display: inline-block; width: 120px; height: 120px; background: #ff1493; margin: 10px; border-radius: 10px; cursor: pointer; transition: transform 0.3s; text-align: center; line-height: 120px; font-size: 0.8em; }
        .box:hover { transform: scale(1.1); }
        .spin-wheel { font-size: 3em; transition: transform 2s; }
        .spin-wheel.spin { transform: rotate(360deg); }
        #final-proposal { display: none; }
        .popup { position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%); background: rgba(255, 255, 255, 0.9); color: #ff1493; padding: 20px; border-radius: 10px; display: none; z-index: 10; }
        .heart-popup { font-size: 3em; animation: pop 1s; }
        @keyframes pop { 0% { transform: scale(0); } 50% { transform: scale(1.5); } 100% { transform: scale(1); } }
    </style>
</head>
<body>
    <h1>Happy Valentine's Day, Siddiqa! 💖</h1>
    <p>Let's play games, open surprises, read wishes, and discover our love...</p>
    
    <!-- Game 1: Love Quiz -->
    <div class="game">
        <h2>Game 1: Love Quiz 💕</h2>
        <p>Answer these questions about us!</p>
        <div id="quiz">
            <p>What’s my favorite color? <button onclick="checkAnswer('red')">Red</button> <button onclick="checkAnswer('blue')">Blue</button></p>
            <p id="quizResult"></p>
        </div>
    </div>
    
    <!-- Game 2: Heart Clicker -->
    <div class="game">
        <h2>Game 2: Heart Clicker ❤️</h2>
        <p>Click the hearts to collect love points!</p>
        <button id="heartBtn" class="heart">💖</button>
        <p id="counter">Love Points: 0</p>
    </div>
    
    <!-- Game 3: Spin the Wheel -->
    <div class="game">
        <h2>Game 3: Spin the Wheel 🎡</h2>
        <p>Spin for a romantic prize!</p>
        <div class="spin-wheel" id="wheel">🎡</div>
        <button onclick="spinWheel()">Spin!</button>
        <p id="wheelResult"></p>
    </div>
    
    <!-- Game 4: Memory Game -->
    <div class="game">
        <h2>Game 4: Memory Game 🧠</h2>
        <p>Match the hearts! Click to flip.</p>
        <div id="memoryBoard"></div>
        <p id="memoryResult"></p>
    </div>
    
    <!-- Game 5: Virtual Rose Garden -->
    <div class="game">
        <h2>Game 5: Virtual Rose Garden 🌹</h2>
        <p>Drag roses to build your bouquet!</p>
        <div id="garden" style="height: 200px; background: rgba(255,255,255,0.1); position: relative;"></div>
        <button onclick="addRose()">Add Rose</button>
    </div>
    
    <!-- Game 6: Love Calculator -->
    <div class="game">
        <h2>Game 6: Love Calculator 💑</h2>
        <p>Enter our names for a love score!</p>
        <input id="name1" placeholder="Your Name"><input id="name2" placeholder="Siddiqa">
        <button onclick="calculateLove()">Calculate!</button>
        <p id="loveScore"></p>
    </div>
    
    <!-- Game 7: Kiss Catcher -->
    <div class="game">
        <h2>Game 7: Kiss Catcher 💋</h2>
        <p>Catch falling kisses! Click them.</p>
        <div id="kissArea" style="height: 200px; background: rgba(255,255,255,0.1); position: relative; overflow: hidden;"></div>
        <button onclick="startKisses()">Start Catching!</button>
        <p id="kissCount">Kisses Caught: 0</p>
    </div>
    
    <!-- Game 8: Hug Counter -->
    <div class="game">
        <h2>Game 8: Hug Counter 🤗</h2>
        <p>Click for virtual hugs!</p>
        <button onclick="giveHug()">Hug Me!</button>
        <p id="hugCount">Hugs Given: 0</p>
    </div>
    
    <!-- Surprise Boxes -->
    <div class="game">
        <h2>Surprise Boxes 🎁</h2>
        <p>Open 6 boxes for surprises!</p>
        <div id="boxes">
            <div class="box" onclick="openBox(0)">Box 1</div>
            <div class="box" onclick="openBox(1)">Box 2</div>
            <div class="box" onclick="openBox(2)">Box 3</div>
            <div class="box" onclick="openBox(3)">Box 4</div>
            <div class="box" onclick="openBox(4)">Box 5</div>
            <div class="box" onclick="openBox(5)">Box 6</div>
        </div>
        <p id="boxResult"></p>
    </div>
    
    <!-- 20 Wishes in Boxes -->
    <div class="game">
        <h2>20 Wishes Just for You 🌹</h2>
        <p>Click each box to reveal a wish!</p>
        <div id="wishBoxes">
            <div class="box" onclick="openWish(0)">Wish 1</div>
            <div class="box" onclick="openWish(1)">Wish 2</div>
            <div class="box" onclick="openWish(2)">Wish 3</div>
            <div class="box" onclick="openWish(3)">Wish 4</div>
            <div class="box" onclick="openWish(4)">Wish 5</div>
            <div class="box" onclick="openWish(5)">Wish 6</div>
            <div class="box" onclick="openWish(6)">Wish 7</div>
            <div class="box" onclick="openWish(7)">Wish 8</div>
            <div class="box" onclick="openWish(8)">Wish 9</div>
            <div class="box" onclick="openWish(9)">Wish 10</div>
            <div class="box" onclick="openWish(10)">Wish 11</div>
            <div class="box" onclick="openWish(11)">Wish 12</div>
            <div class="box" onclick="openWish(12)">Wish 13</div>
            <div class="box" onclick="openWish(13)">Wish 14</div>
            <div class="box" onclick="openWish(14)">Wish 15</div>
            <div class="box" onclick="openWish(15)">Wish 16</div>
            <div class="box" onclick="openWish(16)">Wish 17</div>
            <div class="box" onclick="openWish(17)">Wish 18</div>
            <div class="box" onclick="openWish(18)">Wish 19</div>
            <div class="box" onclick="openWish(19)">Wish 20</div>
        </div>
        <p id="wishResult"></p>
    </div>
    
    <!-- Popup for Heart -->
    <div id="popup" class="popup">
        <div class="heart-popup">💖</div>
        <p id="popupText"></p>
        <button onclick="closePopup()">Close</button>
    </div>
    
    <!-- Proposal Button -->
    <button onclick="showProposal()">Ready for the Big Question? 💍</button>
    
    <!-- Proposal Section -->
    <div id="proposal">
        <h1>Will You Be My Valentine?</h1>
        <p>Siddiqa, you've stolen my heart. Will you be mine forever?</p>
        <button onclick="showFinal()">Yes! Forever Yes!</button>
        <button onclick="showFinal()">Maybe... but I love you!</button>
    </div>
    
    <!-- Final Proposal -->
    <div id="final-proposal">
        <h2>Please accept my Valentine proposal 💍</h2>
        <button onclick="alert('Yay! I love you forever! 💖 Celebration time!')">Yes Forever</button>
    </div>
    
    <script>
        // Quiz Game
        function checkAnswer(answer) {
            if (answer === 'red') {
                document.getElementById('quizResult').innerText = 'Correct! You know me so well. 💕';
            } else {
                document.getElementById('quizResult').innerText = 'Oops! But I still love you. 😘';
            }
        }
        
        // Heart Clicker Game
        let count = 0;
        document.getElementById('heartBtn').onclick = () => {
            count++;
            document.getElementById('counter').innerText = `Love Points: ${count}`;
            if (count === 10) {
                alert('You\'ve collected my heart! 💖');
            }
        };
        
        // Spin the Wheel Game
        function spinWheel() {
            const wheel = document.getElementById('wheel');
            wheel.classList.add('spin');
            setTimeout(() => wheel.classList.remove('spin'), 2000);
            const prizes = ['A Kiss 💋', 'Dinner Date 🍽️', 'Forever Love 💕', 'Hugs 🤗'];
            const result = prizes[Math.floor(Math.random() * prizes.length)];
            document.getElementById('wheelResult').innerText = `You won: ${result}`;
        }
        
        // Memory Game
        let memoryCards = ['💖', '💖', '❤️', '❤️', '💕', '💕'];
        let flipped = [];
        function initMemory() {
            const board = document.getElementById('memoryBoard');
            memoryCards.forEach((card, i) => {
                const div = document.createElement('div');
                div.className = 'box';
                div.onclick = () => flipCard(i, div);
                board.appendChild(div);
            });
        }
        initMemory();
        function flipCard(index, div) {
            if (flipped.length < 2) {
                div.innerText = memoryCards[index];
                flipped.push({index, div});
                if (flipped.length === 2) {
                    setTimeout(() => {
                        if (memoryCards[flipped[0].index] === memoryCards[flipped[1].index]) {
                            flipped.forEach(f => f.div.style.visibility = 'hidden');
                        } else {
                            flipped.forEach(f => f.div.innerText = '');
                        }
                        flipped = [];
                    }, 1000);
                }
            }
        }
        
        // Virtual Rose Garden
        function addRose() {
            const garden = document.getElementById('garden');
            const rose = document.createElement('div');
            rose.innerText = '🌹';
            rose.style.position = 'absolute';
            rose.style.left = Math.random() * 80 + '%';
            rose.style.top = Math.random() * 80 + '%';
            rose.draggable = true;
            garden.appendChild(rose);
        }
        
        // Love Calculator
        function calculateLove() {
            const name1 = document.getElementById('name1').value;
            const name2 = document.getElementById('name2').value;
            const score = Math.floor(Math.random() * 100) + 1;
            document.getElementById('loveScore').innerText = `${name1} and ${name2} have ${score}% love compatibility! 💑`;
        }
        
        // Kiss Catcher
        let kissInterval;
        function startKisses() {
            const area = document.getElementById('kissArea');
            let caught = 0;
            kissInterval = setInterval(() => {
                const kiss = document.createElement('div');
                kiss.innerText = '💋';
                kiss.style.position = 'absolute';
                kiss.style.left = Math.random() * 80 + '%';
                kiss.style.top = '0';
                kiss.onclick = () => { caught++; document.getElementById('kissCount').innerText = `Kisses Caught: ${caught}`; kiss.remove(); };
                area.appendChild(kiss);
                setTimeout(() => kiss.remove(), 3000);
            }, 1000);
            setTimeout(() => clearInterval(kissInterval), 10000);
        }
        
        // Hug Counter
        let hugs = 0;
        function giveHug() {
            hugs++;
            document.getElementById('hugCount').innerText = `Hugs Given: ${hugs}`;
            if (hugs === 10) alert('You\'re the best hugger! 🤗');
        }
        
        // Surprise Boxes
        const surprises = ['A Big Hug 🤗', 'A Sweet Kiss 💋', 'Romantic Quote: "Love is not about how many days, but how much you love."', 'Heart Emoji 💖', 'Love Note: You\'re amazing!', 'Animation: 💕💕💕'];
        function openBox(index) {
            document.getElementById('boxResult').innerText = `Box ${index+1}: ${surprises[index]}`;
        }
        
        // 20 Wishes in Boxes
        const wishes = [
            "1. You make my world brighter every day. I love you endlessly!",
            "2. Roses are red, violets are blue, my heart is yours, forever true.",
            "3. Every moment with you is a treasure. Happy Valentine's, my love!",
            "4. You're my sunshine on cloudy days. I cherish you always.",
            "5. In your eyes, I see my future. Will you be my forever?",
            "6. Your smile lights up my life like a thousand stars.",
            "7. I fall in love with you all over again every day.",
            "8. You're the best part of my day, every single day.",
            "9. With you, every adventure is magical.",
            "10. My love for you grows stronger with each heartbeat.",
            "11. You're my dream come true, Siddiqa.",
            "12. Let's make more memories together. I love you!",
            "13. Your laughter is my favorite melody.",
            "14. I promise to love you through thick and thin.",
            "15. You're the reason I believe in soulmates.",
            "16. Every kiss from you is pure magic.",
            "17. I can't imagine life without you by my side.",
            "18. You're my everything, my love.",
            "19. Happy Valentine's! Let's celebrate our love.",
            "20. Will you be my Valentine forever? I love you more than words can say."
        ];
        function openWish(index) {
            document.getElementById('popupText').innerText = wishes[index];
            document.getElementById('popup').style.display = 'block';
        }
        function closePopup() {
            document.getElementById('popup').style.display = 'none';
        }
        
        // Show Proposal
        function showProposal() {
            document.getElementById('proposal').style.display = 'block';
        }
        
        // Show Final Proposal
        function showFinal() {
            document.getElementById('proposal').style.display = 'none';
            document.getElementById('final-proposal').style.display = 'block';
        }
    </script>
</body>
</html>
