
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Declaración de Amor</title>
    <script>
        function declaracionDeAmor() {
            var nombre = document.getElementById("nombre").value;
            var mensaje = "";
            if (nombre.toLowerCase() === "marcos") {
                mensaje = "Te amo, Marcos. Hola niño lindo hermoso, ¿cómo estás? ¿Sabes que me gustas mucho y te amo de verdad?\n";
                mensaje += "Me gustaría que en algún momento llegáramos a ser novios.\n";
                mensaje += "A veces de noche, cuando el mundo duerme, pienso en ti y me lleno de esperanza y amor.\n";
                mensaje += "¿Quieres ser mi novio? <button onclick='aceptacion()'>Sí</button> <button onclick='rechazo()'>No</button>";
            } else if (nombre.toLowerCase() === "alux") {
                mensaje = "El amor de tu vida y el dueño de tu corazón.";
            } else if (nombre.toLowerCase() === "sheyla") {
                mensaje = "Sheyla, mi dulce amor, te amo con todo mi corazón. Eres la razón de mis sonrisas y mi felicidad. 💖";
            } else if (nombre.toLowerCase() === "kevin") {
                mensaje = "Kevin, I love you. Eres mi todo, mi razón de ser. ❤️";
            } else if (nombre.toLowerCase() === "frida") {
                mensaje = "Hola, Frida querida. TQM (Te quiero mucho) ❤️.";
            } else if (nombre.toLowerCase() === "david") {
                mensaje = "Te quiero, muchas gracias por tu amistad y los buenos momentos contigo. :3";
            } else if (nombre.toLowerCase() === "omar") {
                mensaje = "Te quiero mucho, te mereces el mundo entero omi 💗";
            } else {
                mensaje = "Vete a la vrg plis";
            }
            document.getElementById("resultado").innerHTML = mensaje;
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
<label for="nombre">Pon tu nombre:</label>
<input type="text" id="nombre" onkeydown="if (event.key === 'Enter') declaracionDeAmor()">
<button onclick="declaracionDeAmor()">Declarar</button>
<p id="resultado"></p>
</body>
</html>
