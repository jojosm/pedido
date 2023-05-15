# pedido
<!DOCTYPE html>
<html>

<head>
    <title>Pedido</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,500&display=swap" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@900&display=swap');

        body {
            margin: 0;
            padding: 0;
            background-image: linear-gradient(to top right, rgb(219, 72, 72), rgb(221, 68, 101));
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            height: 100vh;
            font-family: 'Roboto', sans-serif;
            ;

        }

        #question {
            color: #ffffff;
            font-size: 24px;
            text-align: center;
            font-family: 'Roboto', sans-serif;
        }

        #noContainer {
            height: 180px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        #no {
            margin-left: 10px;
            font-weight: bold;
            background: rgb(216, 106, 106);
            color: white;
            font-size: 1.5rem;
            border-radius: 8px;
            border: 2px solid black;
            padding: 5px;
            text-transform: uppercase;
        }

        #yes {
            font-weight: bold;
            margin-right: 5px;
            background: rgb(132, 207, 132);
            color: white;
            font-size: 1.5rem;
            border: 2px solid black;
            border-radius: 8px;
            padding: 5px;
            text-transform: uppercase;
        }
    </style>
</head>

<body>
    <div id="question">Quer comer meu cuzinho Hoje?</div>
    <div id="options">
        <div id="noContainer">
            <a href="https://www.youtube.com/watch?v=orWnzqBA63w"><button id="yes" class="button">Sim 🙂</button></a>
            <button id="no" class="button">Não 😔</button>
        </div>
    </div>

    <script>
        var noButton = document.getElementById("no");
        var noContainer = document.getElementById("noContainer");

        function moveNoButton() {
            var containerWidth = noContainer.offsetWidth - noButton.offsetWidth;
            var containerHeight = noContainer.offsetHeight - noButton.offsetHeight;

            var newLeft = Math.random() * containerWidth;
            var newTop = Math.random() * containerHeight;

            newLeft = Math.max(newLeft, 0);
            newLeft = Math.min(newLeft, containerWidth);
            newTop = Math.max(newTop, 0);
            newTop = Math.min(newTop, containerHeight);

            noButton.style.transform = `translate(${newLeft}px, ${newTop}px)`;
        }

        noButton.addEventListener("mouseover", moveNoButton);

        noButton.addEventListener("mouseleave", function () {
            setTimeout(moveNoButton, 2000);
        });
    </script>
</body>

</html>
