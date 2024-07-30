<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Historial de Búsquedas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        #historial {
            margin-top: 20px;
        }
        button {
            margin: 5px;
            padding: 10px;
            font-size: 16px;
            cursor: pointer;
        }
        #resultado {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        #perdonBtn {
            margin-top: 20px;
        }
        #botonRegresar {
            display: none; /* Ocultar el botón de regresar al inicio por defecto */
        }
    </style>
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            // Mostrar el botón de "Ver historial" al cargar la página
            document.getElementById("botonVerHistorial").style.display = "inline-block";
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
                document.getElementById("botonBorrarHistorial").style.display = "inline-block"; // Muestra el botón de borrar historial
            } else {
                historialDiv.innerHTML = "<p>No hay historial de búsquedas.</p>";
                document.getElementById("botonBorrarHistorial").style.display = "none"; // Oculta el botón de borrar historial si no hay historial
            }
        }

        function agregarAlHistorial(nombre) {
            var historial = JSON.parse(localStorage.getItem("historialNombres")) || [];
            if (!historial.includes(nombre)) {
                historial.push(nombre);
                localStorage.setItem("historialNombres", JSON.stringify(historial));
            }
        }

        function eliminarHistorial() {
            localStorage.removeItem("historialNombres");
            mostrarHistorial();
        }

        function mostrarHistorialCompleto() {
            mostrarHistorial();
            document.getElementById("historial").style.display = "block";
            document.getElementById("botonBorrarHistorial").style.display = "inline-block";
            document.getElementById("botonVerHistorial").style.display = "none"; // Oculta el botón de ver historial después de buscar
        }

        function ocultarHistorial() {
            document.getElementById("historial").style.display = "none";
            document.getElementById("botonVerHistorial").style.display = "inline-block"; // Muestra el botón de ver historial
        }

        function declaracionDeAmor() {
            var nombre = document.getElementById("nombre").value.trim().toLowerCase();
            if (!nombre) return;

            var nombresReconocidos = ["francisco", "javier", "valencia", "cortés", "paco", "pako"];
            var palabras = nombre.split(/\s+/);
            var contieneNombresReconocidos = palabras.some(palabra => nombresReconocidos.includes(palabra));

            if (contieneNombresReconocidos) {
                var mensaje = `
                    <h1>¿Cómo Alux se enamoró?</h1>
                    <p>¿Cómo me enamoré de Fran?<br>
                    Para empezar, ¿Qué es el amor para Alux? Para Alux el amor es un sentimiento que está acompañado de otros, así como de acciones y comportamientos, como es la felicidad, el respeto, la honestidad, la fidelidad, la confianza, el interés, ¿entonces esto es el amor? Si y no, estos son solo unos cuantos aspectos que ramifican su ideología, porque para ser sinceros él tiene el pensamiento de que el amor a pesar de ser descriptible en ciertos rasgos en algunos otros es incomprensible, porque goza de espontaneidad, algo que no podemos controlar. ¿Pero saben qué es algo que Alux no puede controlar? El no puede controlar lo que siente por Francisco Javier Valencia Cortés.<br>
                    El primer encuentro, un momento mágico y extraordinario, al menos para él, lo que no sabía es que este acontecimiento desembarcaría en un mar de emociones y tentaciones por Fran, su primera interacción a pesar de ser algo peculiar es auténtica, quizá no sea un encuentro romántico, pero creo que comprar esa agua de jamaica fue la mejor decisión que ha tomado en su vida, entró a una tienda sin saber que iba a terminar enamorado repentinamente, al salir no sabía lo que le esperaba, un poco tímido de sí y dudoso de él no se acercó e hizo lo que tanto pensaba y deseaba “pedirle el usuario de Instagram a ese niño”, los días transcurrieron con normalidad y un poco machacones, hasta que él subió una historia, que a su opinión se veía hermoso y lindo, o quizá solo fueron sus cinco minutos de autoestima, algunos dudarán a que nos lleva todo esto, entre las conversaciones de Frida “la mejor amiga de Alux” y este último un comentario hizo que siguiera a su hermana, curioso indagó en sus seguidos y encontró un perfil de un niño magnífico, espléndido, hermoso, espectacular, brillante, que curiosamente coincidía con el niño al que dudó en pedirle su usuario, sin dudar ni pensarlo dos veces, lo siguió, todo transcurrió según la habitual y reiterada rutina de siempre, hasta la mañana siguiente.<br>
                    Por la mañana, Fran contestó una nota, de una melodía que es del agrado de Alux, esto ánimo e incitó a Alux a decir “Hola”, surgió conversación de una manera tan especial, Alux sentía que tenía una conexión con aquel niño detrás de un dispositivo electrónico. Alux comentó la posibilidad de verse, acordaron verse, Alux no quería llegar con las manos vacías entonces invitó algo a Fran, cuando se lo entregó y lo abrazaron, en ese momento fue en que Alux se dio cuenta de algo muy importante “¡Me gusta Fran!”, ese momento fue crucial porque supo que en verdad estaba empezando a sentir amor por Fran. Alux ahora estando completamente cuerdo y siendo consciente de sí mismo, afirma amar a Fran con su vida de ser necesario.</p>
                `;
                document.getElementById("resultado").innerHTML = mensaje;
            } else if (nombre.includes("alux")) {
                var mensajeAlux = `
                    <h1>Alux</h1>
                    <p>Alux, eres una persona única y especial. Tienes una luz interior que ilumina a quienes te rodean. Siempre con una sonrisa, das lo mejor de ti en todo lo que haces. Mantén siempre esa energía positiva y sigue brillando. 🌟</p>
                `;
                document.getElementById("resultado").innerHTML = mensajeAlux;
            } else {
                var mensajeGenerico = "Con todo respeto, deje de estar de chismoso y mejor haga algo productivo. Si quiere que aparezca su nombre mande dm a Alux :)";
                document.getElementById("resultado").innerHTML = mensajeGenerico;
            }

            agregarAlHistorial(nombre);

            document.getElementById("nombre").style.display = "none";
            document.getElementById("botonBuscar").style.display = "none";
            document.getElementById("labelNombre").style.display = "none";
            ocultarHistorial(); // Asegúrate de ocultar el historial
            document.getElementById("botonRegresar").style.display = "inline-block";
            document.getElementById("botonVerHistorial").style.display = "none"; // Oculta el botón de ver historial después de buscar
        }

        function aceptacion() {
            var mensaje = "¡Qué alegría! Mi corazón es tuyo, y juntos construiremos un futuro lleno de amor. 💓";
            document.getElementById("resultado").innerHTML = mensaje;
        }

        function rechazo() {
            var mensaje = "Entiendo tu decisión, pero siempre estaré aquí por si cambias de opinión. 💔";
            document.getElementById("resultado").innerHTML = mensaje;
        }

        function amistad() {
            var mensaje = "Holiii, gracias fri por escucharme cada vez que lo necesito, por estar conmigo en momentos difíciles y cuando más lo requiero, te aprecio demasiado. 💓";
            document.getElementById("resultado").innerHTML = mensaje;
        }

        function regresarInicio() {
            document.getElementById("nombre").style.display = "block";
            document.getElementById("botonBuscar").style.display = "inline-block";
            document.getElementById("labelNombre").style.display = "block";
            document.getElementById("botonRegresar").style.display = "none";
            document.getElementById("resultado").innerHTML = "";
            document.getElementById("perdonBtn").innerHTML = "";
            ocultarHistorial(); // Ocultar historial al regresar
        }
    </script>
</head>
<body>
    <label for="nombre" id="labelNombre">Pon tu nombre:</label>
    <input type="text" id="nombre" onkeydown="if (event.key === 'Enter') declaracionDeAmor()">
    <button id="botonBuscar" onclick="declaracionDeAmor()">Buscar</button>
    <button id="botonVerHistorial" onclick="mostrarHistorialCompleto()">Ver historial</button>
    <button id="botonBorrarHistorial" onclick="eliminarHistorial()" style="display:none">Borrar historial</button>
    <div id="historial" style="display:none"></div>
    <div id="resultado"></div>
    <div id="perdonBtn"></div>
    <button id="botonRegresar" onclick="regresarInicio()">Regresar al inicio</button>
</body>
</html>
