<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Nikita!</title>
    <style>
        body {
            text-align: center;
            background: #f8e1da;
            font-family: 'Comic Sans MS', 'Comic Sans', cursive;
            overflow: hidden;
            padding-top: 20px;
        }
        h1 {
            font-size: 4em;
            color: #ff6f61;
            margin: 0;
            font-family: 'Brush Script MT', cursive;
            margin-top: 50px;
        }
        #message-container {
            display: none;
            background: #ffeb3b;
            color: #ff6f61;
            padding: 20px;
            border-radius: 10px;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 10;
            font-size: 1.5em;
            font-weight: bold;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            max-width: 80%;
            text-align: center;
        }
        .emoji {
            position: absolute;
            font-size: 30px;
            animation: fall 3s linear infinite;
            z-index: 5;
        }
        @keyframes fall {
            0% {
                transform: translateY(-50px) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }
        .corner-hearts {
            position: absolute;
            z-index: 5;
        }
        .corner-hearts.top-left {
            top: 10px;
            left: 10px;
        }
        .corner-hearts.top-right {
            top: 10px;
            right: 10px;
        }
        .corner-hearts.bottom-left {
            bottom: 10px;
            left: 10px;
        }
        .corner-hearts.bottom-right {
            bottom: 10px;
            right: 10px;
        }
    </style>
</head>
<body onclick="revealMessage()">
    <h1>Happy Birthday Nikita!</h1>
    <div id="message-container">
        <p>Wishing you the most magical birthday filled with love, laughter, and all your favorite things! 💖</p>
    </div>

    <!-- Heart Corners -->
    <div class="corner-hearts top-left"></div>
    <div class="corner-hearts top-right"></div>
    <div class="corner-hearts bottom-left"></div>
    <div class="corner-hearts bottom-right"></div>

    <script>
        function revealMessage() {
            const messageContainer = document.getElementById('message-container');
            messageContainer.style.display = 'block';
            createFallingEmojis();
        }

        function createFallingEmojis() {
            for (let i = 0; i < 50; i++) {
                const emoji = document.createElement('div');
                emoji.classList.add('emoji');
                emoji.textContent = '❤️'; // Emoji character
                emoji.style.left = Math.random() * window.innerWidth + 'px';
                emoji.style.animationDelay = Math.random() * 2 + 's';
                document.body.appendChild(emoji);

                // Remove the emoji after animation
                setTimeout(() => emoji.remove(), 3000);
            }
        }

        function createCornerHearts(selector) {
            const container = document.querySelector(selector);
            for (let i = 0; i < 10; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.style.left = `${Math.random() * 50}px`;
                heart.style.animationDelay = `${Math.random() * 2}s`;
                container.appendChild(heart);
            }
        }

        window.onload = () => {
            createCornerHearts('.corner-hearts.top-left');
            createCornerHearts('.corner-hearts.top-right');
            createCornerHearts('.corner-hearts.bottom-left');
            createCornerHearts('.corner-hearts.bottom-right');
        };
    </script>
</body>
</html>
