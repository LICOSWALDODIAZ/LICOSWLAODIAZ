<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres tener un gato conmigo?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 100px;
        }
        #pregunta {
            font-size: 24px;
            margin-bottom: 20px;
        }
        .boton {
            font-size: 20px;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
        }
        #btnSi {
            background-color: green;
            color: white;
        }
        #btnNo {
            background-color: red;
            color: white;
        }
        #mensaje {
            font-size: 24px;
            font-weight: bold;
            color: darkblue;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <div id="pregunta">¿Quieres tener un gato conmigo cuando nos casemos?</div>
    
    <button id="btnSi" class="boton" onclick="aceptar()">Acepto</button>
    <button id="btnNo" class="boton" onclick="rechazar()">No acepto</button>

    <div id="mensaje"></div>

    <script>
        let btnSi = document.getElementById("btnSi");
        let btnNo = document.getElementById("btnNo");
        let mensaje = document.getElementById("mensaje");
        let frases = ["¿Seguro?", "Dime que sí", "Ándale, por favor", "No seas así", "Solo un gatito", "Piensa en los michis"];
        let tamaño = 20;
        let topPos = 0;

        function aceptar() {
            mensaje.innerText = "¡Gracias, amor! Te amo mucho 💖 Gracias por aceptar.";
            btnSi.style.display = "none";
            btnNo.style.display = "none";
        }

        function rechazar() {
            let randomFrase = frases[Math.floor(Math.random() * frases.length)];
            mensaje.innerText = randomFrase;

            tamaño += 10;
            topPos -= 10;
            btnSi.style.fontSize = tamaño + "px";
            btnSi.style.position = "relative";
            btnSi.style.top = topPos + "px";

            if (tamaño >= 100) {
                mensaje.innerText = "¡DIME QUE SÍ, POR FAVOR! 🥺";
            }
        }
    </script>
