<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine? ❤️</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #ffe4e1;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            text-align: center;
            overflow: hidden;
        }
        .container {
            padding: 20px;
        }
        h1 { color: #d63384; font-size: 2.5rem; }
        .gif-container img { width: 250px; border-radius: 15px; }
        .buttons { margin-top: 30px; position: relative; height: 100px; }
        
        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: 0.3s;
            font-weight: bold;
        }
        #yesBtn { background-color: #ff4d6d; color: white; margin-right: 10px; }
        #noBtn { background-color: #808080; color: white; position: absolute; }
    </style>
</head>
<body>

    <div class="container" id="main-content">
        <div class="gif-container">
            <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueGZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1n/c76IJLufpNUMo/giphy.gif" alt="Cute Cat">
        </div>
        <h1>Will you be my Valentine? ❤️</h1>
        <div class="buttons">
            <button id="yesBtn">Yes!</button>
            <button id="noBtn">No</button>
        </div>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const mainContent = document.getElementById('main-content');

        // The "Moving No" Logic
        noBtn.addEventListener('mouseover', () => {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        });

        // The "Yes" Celebration
        yesBtn.addEventListener('click', () => {
            mainContent.innerHTML = `
                <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueGZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3bmZ3JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1n/KzDGRp86p6I/giphy.gif" width="300">
                <h1 style="color: #ff4d6d;">Yay! See you on the 14th! 😘</h1>
            `;
            confetti({
                particleCount: 150,
                spread: 70,
                origin: { y: 0.6 }
            });
        });
    </script>
</body>
</html>
