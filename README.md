<html lang="es">
<head>
    <meta charset="UTF-8">
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            mostrarHistorial();
        });

        function mostrarHistorial() {
            var historial = JSON.parse(localStorage.getItem("historialNombres")) || [];
            var historialDiv = document.getElementById("historial");
            historialDiv.innerHTML = "";

            if (historial.length > 0) {
                var lista = document.createElement("ul");
                historial.forEach(function(nombre) {
                    var item = document.createElement("li");
                    item.textContent = nombre;
                    lista.appendChild(item);
                });
                historialDiv.appendChild(lista);
            }
        }

        function agregarAlHistorial(nombre) {
            var historial = JSON.parse(localStorage.getItem("historialNombres")) || [];
            historial.push(nombre);
            localStorage.setItem("historialNombres", JSON.stringify(historial));
            mostrarHistorial();
        }

        function declaracionDeAmor() {
            var nombre = document.getElementById("nombre").value;
            if (!nombre) return;

            agregarAlHistorial(nombre);

            var mensaje = "";
            var inputNombre = document.getElementById("nombre");
            var botonBuscar = document.getElementById("botonBuscar");
            var botonRegresar = document.getElementById("botonRegresar");
            var labelNombre = document.getElementById("labelNombre");
            var historialDiv = document.getElementById("historial");

            inputNombre.style.display = "none"; // Oculta el input después de ingresar el nombre
            botonBuscar.style.display = "none"; // Oculta el botón "Buscar" después de hacer clic
            labelNombre.style.display = "none"; // Oculta el label después de ingresar el nombre
            historialDiv.style.display = "none"; // Oculta el historial después de ingresar el nombre
            botonRegresar.style.display = "inline-block"; // Muestra el botón "Regresar al inicio"

            if (nombre.toLowerCase() === "marcos") {
                mensaje = "Te amo, Marcos. Hola niño lindo hermoso, ¿cómo estás? ¿Sabes que me gustas mucho y te amo de verdad?\n";
                mensaje += "Me gustaría que en algún momento llegáramos a ser novios.\n";
                mensaje += "A veces de noche, cuando el mundo duerme, pienso en ti y me lleno de esperanza y amor.\n";
                mensaje += "¿Quieres ser mi novio? <button onclick='aceptacion()'>Sí</button> <button onclick='rechazo()'>No</button>";
            } else if (nombre.toLowerCase() === "william") {
                mensaje = "Te amo, William. Hola niño lindo hermoso, ¿cómo estás? ¿Sabes que me gustas mucho y te amo de verdad?\n";
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
                mensaje = "Hola, Frida querida. TQM. ❤";
                mensaje += "<button onclick='amistad()'>agradecimiento</button>";
            } else if (nombre.toLowerCase() === "david") {
                mensaje = "Te quiero, muchas gracias por tu amistad y los buenos momentos contigo. :3";
            } else if (nombre.toLowerCase() === "omar") {
                mensaje = "Te quiero mucho, te mereces el mundo entero omi 💗";
            } else if (nombre.toLowerCase() === "dayana") {
                mensaje = "Holi Dayana, espero que estés muy bien. Ten un excelente día, tqm. 💓";
            } else if (nombre.toLowerCase() === "rodrigo" || nombre.toLowerCase() === "aldahir") {
                mensaje = "Te quiero mucho, espero que estés muy bien. 💞";
            } else {
                mensaje = "Con todo respeto, deje de estar de chismoso y mejor haga algo productivo. Si quiere que aparezca su nombre mande dm a Alux :)";
            }
            document.getElementById("resultado").innerHTML = mensaje;
        }

        function aceptacion() {
            var mensaje = "¡Qué alegría! Mi corazón es tuyo, y juntos construiremos un futuro lleno de amor. 💓";
            document.getElementById("resultado").innerHTML = mensaje;
        }

        function rechazo() {
            var mensaje = "Entiendo tu decisión, pero siempre estaré aquí por si cambias de opinión. 💔";
            document.getElementById("resultado").innerHTML = mensaje;
            var botonPerdon = "<button onclick='perdon()'>Perdon</button>";
            document.getElementById("perdonBtn").innerHTML = botonPerdon; // Mostrar botón de perdón
        }

        function perdon() {
            var mensaje = "Se que no soy la mejor persona, aveces cometo muchos errores, no los justifico, pero también se reconocerlos y aprendo de ellos y trato de no volverlos a cometer, no soy perfecto pero, ¿Quién es perfecto? nadie, todos cometemos errores lo importante es reconocerlos y no volverlos a cometer. Te extraño demasiado, y te conozco, no como los demás te conocen, no más ni menos que ellos, te conozco a tu manera, una que solo a mi me dejaste conocer ¿cómo lo hago? Cómo te veo como los demás lo hacen, cuando ellos nunca te sintieron como yo ¿cómo extrañar algo que el mundo quiere que olvides? Te estaba pensando, no a ti, más bien estaba pensando en la manera en la que no puedo dejar de hacerlo, ya no te puedo seguir el paso, mi corazón no puede, se que dejaste marcas antes de irte pero nunca fui muy bueno siguiendo instrucciones y prefiero perderte siendo yo, que buscarte y dejarme atrás, te quería más de lo q pensé q podía y si no te conociera, diría que a ti también te duele, que nunca te quisiste ir y que tus excusas fueron tan reales como los momentos que pasamos, en serio creer que eres tu y no yo, que valgo la pena, que tal vez si algo hubiera sido diferente... no sé. Pero te conozco y lo terminé de hacer cuando te fuiste. Y aun después de tu ausencia te sigo amando, yo se que las rosas tienen espinas y créeme q mis manos están dispuestas a sangrar por ti.";
            document.getElementById("resultado").innerHTML = mensaje;
        }

        function amistad() {
            var mensaje = "Holiii, gracias fri por escucharme cada vez q lo necesito, por estar conmigo en momentos difíciles y cuando mas lo requiero, te aprecio demasiado. 💓";
            document.getElementById("resultado").innerHTML = mensaje;
        }

        function regresarInicio() {
            document.getElementById("nombre").style.display = "block"; // Mostrar input de nombre
            document.getElementById("botonBuscar").style.display = "inline-block"; // Mostrar botón "Buscar"
            document.getElementById("labelNombre").style.display = "block"; // Mostrar label
            document.getElementById("botonRegresar").style.display = "none"; // Ocultar botón "Regresar al inicio"
            document.getElementById("resultado").innerHTML = ""; // Limpiar el resultado
            document.getElementById("perdonBtn").innerHTML = ""; // Ocultar botón de perdón si está visible
            document.getElementById("historial").style.display = "block"; // Mostrar historial
        }

        window.onload = function() {
            document.getElementById("botonRegresar").style.display = "none"; // Ocultar botón "Regresar al inicio" al cargar la página
        };
    </script>
</head>
<body>
    <label for="nombre" id="labelNombre">Pon tu nombre:</label>
    <input type="text" id="nombre" onkeydown="if (event.key === 'Enter') declaracionDeAmor()">
    <button id="botonBuscar" onclick="declaracionDeAmor()">Buscar</button>
    <div id="historial"></div>
    <div id="resultado"></div>
    <div id="perdonBtn"></div>
    <button id="botonRegresar" onclick="regresarInicio()">Regresar al inicio</button>
</body>
</html>
