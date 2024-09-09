<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seplict - Game</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: black;
            color: white;
            text-align: center;
        }
        .container {
            padding: 50px;
        }
        .screen {
            display: none;
        }
        .visible {
            display: block;
        }
        button {
            background-color: #555;
            border: none;
            color: white;
            padding: 15px 30px;
            margin: 10px;
            font-size: 16px;
            cursor: pointer;
        }
        button:hover {
            background-color: #777;
        }
        .level-button {
            background-color: #444;
        }
        .level-button:hover {
            background-color: #666;
        }
    </style>
</head>
<body>
    <div class="container">
        <div id="start-screen" class="screen visible">
            <h1>Seplict</h1>
            <button id="start-button">Start Game</button>
        </div>
        <div id="level-screen" class="screen">
            <h1>Select Level</h1>
            <button class="level-button" data-level="1">Level 1</button>
            <button class="level-button" data-level="2">Level 2</button>
            <button class="level-button" data-level="3">Level 3</button>
        </div>
        <div id="game-screen" class="screen">
            <h1>Game Screen</h1>
            <!-- Game content goes here -->
            <button id="back-button">Back to Menu</button>
        </div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const startButton = document.getElementById('start-button');
            const levelScreen = document.getElementById('level-screen');
            const startScreen = document.getElementById('start-screen');
            const gameScreen = document.getElementById('game-screen');
            const backButton = document.getElementById('back-button');
            const levelButtons = document.querySelectorAll('.level-button');

            startButton.addEventListener('click', () => {
                startScreen.classList.remove('visible');
                levelScreen.classList.add('visible');
            });

            levelButtons.forEach(button => {
                button.addEventListener('click', () => {
                    const level = button.getAttribute('data-level');
                    startGame(level);
                });
            });

            backButton.addEventListener('click', () => {
                gameScreen.classList.remove('visible');
                startScreen.classList.add('visible');
            });

            function startGame(level) {
                levelScreen.classList.remove('visible');
                gameScreen.classList.add('visible');
                console.log(`Starting game at level ${level}`);
                // Here you can add the code to start your game at the selected level
            }
        });
    </script>
</body>
</html>
