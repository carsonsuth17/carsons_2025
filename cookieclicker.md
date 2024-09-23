---
layout: page
title: Cookie Clicker
description: Cookie Clicker Game
permalink: /cookieclicker/
---
<html>
    <link href="https://fonts.googleapis.com/css2?family=Cookie&display=swap" rel="stylesheet">
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start;
            background-color: #f1e7d6;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            padding-top: 120px; /* Space for fixed header */
        }
        header {
            width: 100%;
            height: 100px;
            background-color: #333;
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
        }
        h1 {
            font-family: 'Cookie', cursive;
            color: #964B00;
            font-size: 3rem;
            margin: 20px 0;
        }
        #gameContainer {
            text-align: center;
            margin-top: 50px;
        }
        #cookie {
            width: 150px;
            height: 150px;
            cursor: pointer;
            transition: transform 0.1s ease;
        }
        #cookie:active {
            transform: scale(0.9);
        }
        #score {
            margin-top: 20px;
            font-size: 24px;
            color: #333;
        }
        #upgrades {
            margin-top: 30px;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }
        .upgrade {
            background-color: #f1c40f;
            padding: 10px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            color: #fff;
            font-size: 16px;
            width: 200px;
        }
        #youWin {
            font-size: 32px;
            color: #E74C3C;
            margin-top: 50px;
            display: none;
        }
        #playAgain {
            background-color: #2ecc71;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            display: none;
            margin-top: 20px;
        }
    </style>
<body>
    <h1>Cookie Clicker</h1>
    <div id="gameContainer">
        <img id="cookie" src="https://prettysimplesweet.com/wp-content/uploads/2020/07/Big-Chocolate-Chip-Cookies-150x150.jpg" alt="Cookie">
        <div id="score">Cookies: 0</div>
        <div id="upgrades">
            <button class="upgrade" onclick="buyUpgrade(10, 1)">+1 Cookie per Click (Cost: 10)</button>
            <button class="upgrade" onclick="buyUpgrade(100, 10)">+10 Cookies per Click (Cost: 100)</button>
            <button class="upgrade" onclick="buyUpgrade(500, 25)">+25 Cookies per Click (Cost: 500)</button>
            <button class="upgrade" onclick="buyUpgrade(1000, 50)">+50 Cookies per Click (Cost: 1000)</button>
            <button class="upgrade" onclick="buyUpgrade(5000, 100)">+100 Cookies per Click (Cost: 5000)</button>
            <button class="upgrade" onclick="buyAutoClicker(500)">Auto Clicker (Cost: 500)</button>
            <button class="upgrade" onclick="buyGoldenCookie(3000)">Golden Cookie (Cost: 3000)</button>
        </div>
        <div id="youWin">You Win! Cookies are raining down!</div>
        <button id="playAgain" onclick="resetGame()">Play Again</button>
    </div>

<audio id="cookiecrunch.mp3" src="http://sounds/cookiecrunch.mp3"></audio>

</body>
<script>
    let cookies = 0;
    let cookiesPerClick = 1;
    let autoClicker = null;
    const scoreElement = document.getElementById("score");
    const cookieElement = document.getElementById("cookie");
    const youWinElement = document.getElementById("youWin");
    const playAgainButton = document.getElementById("playAgain");
    const clickSound = document.getElementById("cookiesound"); // Use the correct ID
    cookieElement.addEventListener("click", function () {
        cookies += cookiesPerClick;
        updateScore();
        checkWinCondition();
        playClickSound(); // Play sound on click
    });
    function buyUpgrade(cost, increment) {
        if (cookies >= cost) {
            cookies -= cost;
            cookiesPerClick += increment;
            updateScore();
        }
    }
    function buyAutoClicker(cost) {
        if (cookies >= cost && !autoClicker) {
            cookies -= cost;
            updateScore();
            autoClicker = setInterval(() => {
                cookies += cookiesPerClick;
                updateScore();
                checkWinCondition();
            }, 1000);
        }
    }
    function buyGoldenCookie(cost) {
        if (cookies >= cost) {
            cookies -= cost;
            cookiesPerClick *= 2;
            updateScore();
        }
    }
    function updateScore() {
        scoreElement.textContent = `Cookies: ${cookies}`;
    }
    function playClickSound() {
        clickSound.currentTime = 0; // Reset sound to start
        clickSound.play(); // Play the sound
    }
    function checkWinCondition() {
        if (cookies >= 10000) { // Example win condition
            youWinElement.style.display = "block";
            playAgainButton.style.display = "block";
            clearInterval(autoClicker); // Stop auto clicker if active
        }
    }
    function resetGame() {
        cookies = 0;
        cookiesPerClick = 1;
        updateScore();
        youWinElement.style.display = "none";
        playAgainButton.style.display = "none";
        clearInterval(autoClicker); // Clear any active auto clickers
    }
</script>
</html>
