<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Special for Ncell ✨</title>
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@500;700&display=swap" rel="stylesheet">
    <style>
        body {
            background: linear-gradient(135deg, #e3f2fd 0%, #bbdefb 100%);
            font-family: 'Quicksand', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            color: #1565c0;
        }

        .card {
            background: rgba(255, 255, 255, 0.9);
            padding: 30px;
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            text-align: center;
            border: 5px solid #ffffff;
            max-width: 350px;
            z-index: 10;
            position: relative;
        }

        .photo-placeholder {
            width: 100px;
            height: 100px;
            background: #64b5f6;
            border-radius: 50%;
            margin: 0 auto 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 50px;
            border: 4px solid #fff;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        h1 { font-size: 1.4rem; margin: 0; color: #0d47a1; }
        p { font-size: 0.9rem; margin: 15px 0; color: #546e7a; }

        .btn {
            background: #42a5f5;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            font-family: 'Quicksand', sans-serif;
            transition: 0.3s;
            box-shadow: 0 4px 15px rgba(66, 165, 245, 0.4);
        }

        .btn:hover { background: #1e88e5; transform: translateY(-3px); }

        /* Pop-up */
        #popup {
            display: none;
            position: fixed;
            top: 50%; left: 50%;
            transform: translate(-50%, -50%) scale(0.9);
            background: white;
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 0 100px rgba(0,0,0,0.2);
            z-index: 100;
            text-align: center;
            width: 280px;
            border: 4px solid #90caf9;
            animation: popIn 0.3s forwards;
        }

        @keyframes popIn {
            to { transform: translate(-50%, -50%) scale(1); }
        }

        #overlay {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(13, 71, 161, 0.3);
            backdrop-filter: blur(4px);
            z-index: 99;
        }

        .emoji {
            position: absolute;
            pointer-events: none;
            animation: fall linear forwards;
        }

        @keyframes fall {
            to { transform: translateY(110vh) rotate(360deg); }
        }
    </style>
</head>
<body>

    <div id="overlay"></div>

    <div class="card">
        <div class="photo-placeholder">🐱</div>
        <h1>Halo, Ncuu!</h1>
        <p><b>Stella Najelita Aurelikhan</b><br>Si paling sibuk sedunia ya?</p>
        <button class="btn" onclick="showPopup()">Klik ini bentar!</button>
    </div>

    <div id="popup">
        <h2 style="margin-top: 0;">Happy Valentine! 💙</h2>
        <p>Gak usah Ge-er, ini ucapan buat temen doang kok! Hahaha.</p>
        <p>Makasih ya udah jadi temen yang seru (walaupun kadang random). Tetep jadi Ncell yang receh!</p>
        <button class="btn" onclick="closePopup()">Oke, traktir!</button>
    </div>

    <script>
        function showPopup() {
            document.getElementById('popup').style.display = 'block';
            document.getElementById('overlay').style.display = 'block';
            createHearts();
        }

        function closePopup() {
            document.getElementById('popup').style.display = 'none';
            document.getElementById('overlay').style.display = 'none';
            alert('Awas ya Ncell kalau gak traktir! 😂');
        }

        function createHearts() {
            const emojis = ['💙', '☁️', '🍭', '❄️', '✨'];
            for(let i=0; i<30; i++) {
                setTimeout(() => {
                    const e = document.createElement('div');
                    e.className = 'emoji';
                    e.innerHTML = emojis[Math.floor(Math.random()*emojis.length)];
                    e.style.left = Math.random() * 100 + 'vw';
                    e.style.top = '-50px';
                    e.style.fontSize = (Math.random() * 20 + 20) + 'px';
                    e.style.duration = (Math.random() * 3 + 2) + 's';
                    e.style.animation = `fall ${e.style.duration} linear forwards`;
                    document.body.appendChild(e);
                    setTimeout(() => e.remove(), 5000);
                }, i * 100);
            }
        }
    </script>
</body>
</html>
