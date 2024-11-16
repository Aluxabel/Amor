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
        #botonRegresar {
            display: none; /* Ocultar el botón de regresar al inicio por defecto */
        }
    </style>
    <script>
        document.addEventListener("DOMContentLoaded", function() {
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
                document.getElementById("botonBorrarHistorial").style.display = "inline-block";
            } else {
                historialDiv.innerHTML = "<p>No hay historial de búsquedas.</p>";
                document.getElementById("botonBorrarHistorial").style.display = "none";
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
            document.getElementById("botonVerHistorial").style.display = "none";
        }

        function ocultarHistorial() {
            document.getElementById("historial").style.display = "none";
            document.getElementById("botonVerHistorial").style.display = "inline-block";
        }

        function declaracionDeAmor() {
            var nombre = document.getElementById("nombre").value.trim().toLowerCase();
            if (nombre === "erik") {
                var mensaje = `
                    <h1>¡Holaaaa!</h1>
                    <p>Niño, eres una persona increíble, y me agradas mucho. 
                    Tu luz y carisma son únicos, y no hay palabras suficientes para describir cuánto me fascina conversar contigo. 🌟
                    Posdata: me agrada que me digas nn</p>
                `;
                document.getElementById("resultado").innerHTML = mensaje;
            } else {
                var mensajeGenerico = "Este sitio solo funciona con el nombre Erik. ¡Inténtalo de nuevo!";
                document.getElementById("resultado").innerHTML = mensajeGenerico;
            }

            agregarAlHistorial(nombre);
            document.getElementById("nombre").style.display = "none";
            document.getElementById("botonBuscar").style.display = "none";
            document.getElementById("labelNombre").style.display = "none";
            ocultarHistorial();
            document.getElementById("botonRegresar").style.display = "inline-block";
            document.getElementById("botonVerHistorial").style.display = "none";
        }

        function regresarInicio() {
            document.getElementById("nombre").style.display = "block";
            document.getElementById("botonBuscar").style.display = "inline-block";
            document.getElementById("labelNombre").style.display = "block";
            document.getElementById("botonRegresar").style.display = "none";
            document.getElementById("resultado").innerHTML = "";
            ocultarHistorial();
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
    <button id="botonRegresar" onclick="regresarInicio()">Regresar al inicio</button>
</body>
</html>
