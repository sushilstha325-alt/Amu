<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Amu ❤️</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffe6e6;
            font-family: 'Comic Sans MS', cursive, sans-serif;
            overflow: hidden;
            text-align: center;
        }

        .container {
            padding: 20px;
            background: white;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            max-width: 90%;
            width: 350px;
            position: relative;
        }

        .gif-container img {
            width: 150px;
            height: 150px;
            border-radius: 15px;
        }

        h1 {
            color: #d63384;
            font-size: 24px;
            margin: 20px 0;
        }

        .buttons {
            display: flex;
            justify-content: space-around;
            align-items: center;
            margin-top: 30px;
            height: 100px;
        }

        button {
            padding: 12px 25px;
            font-size: 18px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: 0.3s;
            font-weight: bold;
        }

        #yesBtn {
            background-color: #ff4d6d;
            color: white;
            box-shadow: 0 4px 15px rgba(255, 77, 109, 0.4);
        }

        #noBtn {
            background-color: #888;
            color: white;
            position: absolute;
        }

        .hidden {
            display: none;
        }

        #success-page h1 {
            color: #ff4d6d;
        }
    </style>
</head>
<body>

    <div id="main-card" class="container">
        <div class="gif-container">
            <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueGZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/L4lvBpHWkARu8/giphy.gif" alt="Cute Panda">
        </div>
        <h1 id="question">Hey Amu 💖<br>Will you be my Valentine?</h1>
        
        <div class="buttons">
            <button id="yesBtn">YES 💕</button>
            <button id="noBtn">No 😢</button>
        </div>
    </div>

    <div id="success-page" class="container hidden">
        <div class="gif-container">
            <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExbmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4bmZ4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1n/KztT2c4u8mYYUiCiS7/giphy.gif" alt="Happy Dance">
        </div>
        <h1>Yay! Love you Amu! 🎉</h1>
        <p>I knew you would say yes! 💖</p>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const mainCard = document.getElementById('main-card');
        const successPage = document.getElementById('success-page');

        // Logic to make "No" button move away on hover or touch
        noBtn.addEventListener('mouseover', moveButton);
        noBtn.addEventListener('touchstart', moveButton);

        function moveButton() {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            
            noBtn.style.position = 'fixed';
            noBtn.style.left = x + 'px';
            noBtn.style.top = y + 'px';
        }

        // Logic for "Yes" button
        yesBtn.addEventListener('click', () => {
            mainCard.classList.add('hidden');
            successPage.classList.remove('hidden');
            createHearts();
        });

        // Add some floating hearts background
        function createHearts() {
            for(let i=0; i<30; i++) {
                const heart = document.createElement('div');
                heart.innerHTML = '❤️';
                heart.style.position = 'fixed';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.top = '100vh';
                heart.style.fontSize = Math.random() * 20 + 20 + 'px';
                heart.style.animation = `float ${Math.random() * 3 + 2}s linear forwards`;
                document.body.appendChild(heart);
            }
        }
    </script>

    <style>
        @keyframes float {
            to {
                transform: translateY(-110vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style> </body>
</html>
