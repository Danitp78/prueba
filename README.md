#Prueba

<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Encuesta Personal</title>
</head>
<body>
    <h2>Responde las preguntas:</h2>
    <form id="formulario">
        <label>¿Cuál es tu nombre?</label><br>
        <input type="text" id="nombre"><br>

        <label>¿Qué edad tienes?</label><br>
        <input type="number" id="edad"><br>

        <label>¿Estudias?</label><br>
        <select id="estudias">
            <option value="si">Sí</option>
            <option value="no">No</option>
        </select><br>

        <label id="labelEstudio">¿Qué estudias?</label><br>
        <input type="text" id="estudio"><br>

        <label id="labelTrabajo">¿Trabajas?</label><br>
        <select id="trabajas">
            <option value="si">Sí</option>
            <option value="no">No</option>
        </select><br>

        <label id="labelTrabajo2">¿En qué trabajas?</label><br>
        <input type="text" id="trabajo"><br>

        <label id="labelRazon">¿Por qué no trabajas?</label><br>
        <input type="text" id="razon"><br>

        <button type="button" onclick="mostrarDatos()">Enviar</button>
    </form>

    <h3>Datos Ingresados:</h3>
    <p id="resultado"></p>

    <!-- Video desde un archivo local -->
    <h3>Video 1 (Archivo Local)</h3>
    <video width="400" controls>
        <source src="video1.mp4" type="video/mp4">
        Tu navegador no soporta el elemento de video.
    </video>

    <!-- Video desde YouTube -->
    <h3>Video 2 (Desde YouTube)</h3>
    <iframe width="400" height="225" src="https://www.youtube.com/embed/VIDEO_ID" frameborder="0" allowfullscreen></iframe>

    <script>
        function mostrarDatos() {
            var nombre = document.getElementById("nombre").value;
            var edad = document.getElementById("edad").value;
            var estudias = document.getElementById("estudias").value;
            var estudio = document.getElementById("estudio").value;
            var trabajas = document.getElementById("trabajas").value;
            var trabajo = document.getElementById("trabajo").value;
            var razon = document.getElementById("razon").value;

            var resultado = "Nombre: " + nombre + "<br>Edad: " + edad + "<br>";

            if (estudias === "si") {
                resultado += "Estudios: " + estudio + "<br>";
            }

            if (trabajas === "si") {
                resultado += "Trabajo: " + trabajo + "<br>";
            } else {
                resultado += "Razón por la que no trabaja: " + razon + "<br>";
            }

            document.getElementById("resultado").innerHTML = resultado;
        }
    </script>
</body>
</html>
