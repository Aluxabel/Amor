<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <style>
        /* Estilos para los corazones */
        .corazon {
            font-size: 24px;
            color: red;
        }
    </style>
    <script>
        function declaracionDeAmor(event) {
            if (event.key === "Enter" || event.type === "click") {
                var nombre = document.getElementById("nombre").value.toLowerCase();
                var mensaje = "";

                if (nombre === "marcos") {
                    for (var i = 0; i < 1000; i++) {
                        mensaje += "Te amo, ";
                    }
                    mensaje += "Te amo.\n";
                    mensaje += "Hola niño lindo hermoso, ¿cómo estás? ¿Sabes que me gustas mucho y te amo de verdad?\n";
                    mensaje += "Me gustaría que en algún momento llegáramos a ser novios.\n";
                    mensaje += "A veces de noche, cuando el mundo duerme, pienso en ti y me lleno de esperanza y amor.\n";
                    mensaje += "¿Quieres ser mi novio? <button onclick='aceptacion()'>Sí</button> <button onclick='rechazo()'>No</button>";
                } else if (nombre === "alux") {
                    mensaje = "El amor de tu vida y el dueño de tu corazón.";
                } else {
                    mensaje = "Vete a la vrg plis";
                }

                document.getElementById("resultado").innerHTML = mensaje;
            }
        }

        function aceptacion() {
            var mensaje = "¡Qué alegría! Mi corazón es tuyo, y juntos construiremos un futuro lleno de amor.";
            document.getElementById("resultado").innerText = mensaje;
        }

        function rechazo() {
            var mensaje = "Entiendo tu decisión, pero siempre estaré aquí por si cambias de opinión.";
            document.getElementById("resultado").innerText = mensaje;
        }
    </script>
</head>
<body>
<h1>Declaración de Amor</h1>
<label for="nombre">Pon tu nombre:</label>
<input type="text" id="nombre" onkeydown="declaracionDeAmor(event)">
<button onclick="declaracionDeAmor()">Declarar</button>
<p id="resultado"></p>

<!-- Imágenes de corazones -->
<div class="corazon">❤</div>
<div class="corazon">💗</div>
<div class="corazon">🧡</div>
</body>
</html>
