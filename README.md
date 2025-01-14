<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>volta comigo?</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            text-align: center;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            color: #ffffff;
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }
        h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
        }
        p {
            font-size: 1.5rem;
            margin: 20px 0;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
        }
        #options {
            margin-top: 30px;
            display: flex;
            justify-content: space-between;
            width: 60%;
            position: relative;
        }
        .button {
            padding: 15px 40px;
            font-size: 1.5rem;
            margin: 10px;
            cursor: pointer;
            border: none;
            border-radius: 50px;
            transition: all 0.3s ease-in-out;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.3);
        }
        #yes {
            background-color: #4a90e2;
            color: #fff;
            flex: 1;
            margin-right: 20px;
        }
        #yes:hover {
            background-color: #357abf;
            transform: scale(1.1);
        }
        #no {
            background-color: #6ec1e4;
            color: #fff;
            flex: 1;
            position: relative;
        }
        .message {
            margin-top: 40px;
            font-size: 2rem;
            font-weight: bold;
            color: #fff;
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.3);
        }
        footer {
            position: absolute;
            bottom: 10px;
            font-size: 1rem;
            color: #cce7ff;
        }

        @media (max-width: 768px) {
            #options {
                width: 80%;
                flex-direction: column;
                align-items: center;
            }
            .button {
                width: 80%;
                margin: 10px 0;
            }
        }

        #image-container {
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        #image-container img {
            width: 300px;
            height: auto;
            margin-bottom: 20px;
        }
    </style>
    <script>
        function playMusicAndShowMessage() {
            const audio = new Audio('file:///C:/Users/rebek/Downloads/Flatline.mp3');
            audio.play();
            showImageAndMessage();
        }

        function showImageAndMessage() {
            // Esconde os botões
            document.getElementById("options").style.display = "none";
            
            // Exibe a imagem e a nova mensagem
            document.getElementById("image-container").style.display = "flex";
            document.getElementById("message").innerHTML = "desculpa por qualquer coisa, vai corinthians ❤️.";
        }

        function moveNoButton(event) {
            const noButton = document.getElementById('no');
            const distance = 100; // Distância para o movimento
            const x = event.clientX;
            const y = event.clientY;

            // Calculando novas posições aleatórias para o botão "Não"
            const noButtonRect = noButton.getBoundingClientRect();
            const noButtonCenterX = noButtonRect.left + noButtonRect.width / 2;
            const noButtonCenterY = noButtonRect.top + noButtonRect.height / 2;

            // Movendo o botão para longe do cursor
            const deltaX = x - noButtonCenterX;
            const deltaY = y - noButtonCenterY;

            if (Math.abs(deltaX) < distance && Math.abs(deltaY) < distance) {
                const moveX = deltaX > 0 ? distance : -distance;
                const moveY = deltaY > 0 ? distance : -distance;
                noButton.style.left = `${noButton.offsetLeft + moveX}px`;
                noButton.style.top = `${noButton.offsetTop + moveY}px`;
            }
        }

        // Função para adicionar o evento de movimentação do botão "Não"
        document.addEventListener('DOMContentLoaded', () => {
            const noButton = document.getElementById('no');
            noButton.addEventListener('mousemove', moveNoButton);
        });
    </script>
</head>
<body>
    <h1>volta comigo marina?😭😭</h1>
    <p>nem tente tocar no não, você não vai conseguir otaria</p>

    <div id="options">
        <button id="yes" class="button" onclick="playMusicAndShowMessage()">Sim</button>
        <button id="no" class="button">Não</button>
    </div>

    <div id="image-container">
        <img src="c:\Users\rebek\Downloads\3UHNPVVUXNLNNLL7FISVIW4TAM.jpg" alt="Imagem do Corinthians">
        <div id="message" class="message"></div>
    </div>

    <footer>feito com ❤️, nunca fui tão romântica</footer>
</body>
</html>
