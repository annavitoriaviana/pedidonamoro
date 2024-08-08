<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pedido de Namoro Divertido</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Press+Start+2P&display=swap');

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(135deg, #FFC1CC, #FF4081); /* Fundo gradiente rosa */
            font-family: 'Press Start 2P', cursive;
            margin: 0;
            overflow: hidden;
        }

        .container {
            position: relative;
            padding: 40px;
            border: 4px dashed #fff;
            border-radius: 20px;
            background-color: #FFEBEE;
            box-shadow: 0 0 25px rgba(0, 0, 0, 0.4);
            text-align: center;
            width: 350px;
            height: 350px;
            overflow: hidden;
            animation: popIn 1s ease-in-out;
        }

        h1 {
            font-size: 24px;
            margin-bottom: 30px;
            color: #E91E63;
            font-family: 'Great Vibes', cursive;
        }

        .btn {
            background-color: #FF4081;
            color: #fff;
            border: 2px solid #fff;
            padding: 15px 30px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 16px;
            margin: 10px;
            position: relative;
            transition: background-color 0.3s, transform 0.3s;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            text-transform: uppercase;
        }

        .btn:hover {
            background-color: #E91E63;
            transform: scale(1.1) rotate(10deg);
        }

        .heart {
            position: absolute;
            width: 120px;
            height: 100px;
            background-color: #FF4081;
            border-radius: 50px 50px 0 0;
            transform: rotate(-45deg);
            top: -50px;
            left: 50%;
            margin-left: -60px;
            animation: heartbeat 1s infinite;
        }

        .heart::before,
        .heart::after {
            content: "";
            position: absolute;
            width: 120px;
            height: 100px;
            background-color: #FF4081;
            border-radius: 50%;
        }

        .heart::before {
            top: -70px;
            left: 0;
        }

        .heart::after {
            top: 0;
            right: -60px;
        }

        /* Floating hearts animation */
        .floating-heart {
            position: absolute;
            width: 25px;
            height: 25px;
            background-color: #FF4081;
            transform: rotate(45deg);
            border-radius: 50% 50% 0 0;
            animation: float 4s infinite;
            opacity: 0.8;
        }

        .floating-heart::before,
        .floating-heart::after {
            content: "";
            position: absolute;
            width: 25px;
            height: 25px;
            background-color: #FF4081;
            border-radius: 50%;
        }

        .floating-heart::before {
            top: -12.5px;
            left: 0;
        }

        .floating-heart::after {
            top: 0;
            left: 12.5px;
        }

        @keyframes float {
            0% {
                bottom: 0;
                opacity: 0;
                transform: translateX(0) rotate(45deg);
            }
            50% {
                opacity: 1;
            }
            100% {
                bottom: 100vh;
                opacity: 0;
                transform: translateX(-50px) rotate(45deg);
            }
        }

        @keyframes popIn {
            0% {
                transform: scale(0);
            }
            100% {
                transform: scale(1);
            }
        }

        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1) rotate(-45deg);
            }
            50% {
                transform: scale(1.2) rotate(-45deg);
            }
        }

        .floating-heart:nth-child(2) {
            animation-delay: 1s;
        }

        .floating-heart:nth-child(3) {
            animation-delay: 2s;
        }

        .floating-heart:nth-child(4) {
            animation-delay: 3s;
        }

        .floating-heart:nth-child(5) {
            animation-delay: 4s;
        }
    </style>
</head>
<body>
    <div class="floating-heart"></div>
    <div class="floating-heart"></div>
    <div class="floating-heart"></div>
    <div class="floating-heart"></div>
    <div class="floating-heart"></div>

    <div class="container" id="questionContainer">
        <div class="heart"></div>
        <h1>Quer ser minha namorada?</h1>
        <button class="btn" id="yesBtn">Sim</button>
        <button class="btn" id="noBtn">Não</button>
    </div>
    <script>
        document.getElementById('yesBtn').addEventListener('click', function() {
            window.location.href = "https://www.youtube.com/watch?v=dQw4w9WgXcQ";
        });

        const noBtn = document.getElementById('noBtn');
        noBtn.addEventListener('mouseover', function() {
            const container = noBtn.parentElement;
            const containerRect = container.getBoundingClientRect();
            const noBtnRect = noBtn.getBoundingClientRect();

            let newLeft, newTop;

            do {
                newLeft = Math.random() * (containerRect.width - noBtnRect.width);
                newTop = Math.random() * (containerRect.height - noBtnRect.height);
            } while (
                Math.abs(newLeft - noBtnRect.left + containerRect.left) < noBtnRect.width &&
                Math.abs(newTop - noBtnRect.top + containerRect.top) < noBtnRect.height
            );

            noBtn.style.position = 'absolute';
            noBtn.style.left = `${newLeft}px`;
            noBtn.style.top = `${newTop}px`;
        });
    </script>
</body>
</html>
