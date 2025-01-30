#Prueba
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Encuesta Personal</title>
    <style>
        /* Estilo general */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            background-color: #f7f7f7;
        }

        /* Sección de video */
        #videoInicio, #videoFinal {
            background-color: #e3f2fd; /* Color pastel azul */
            padding: 20px;
            margin: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            width: 60%;
            text-align: center;
        }

        /* Sección de preguntas */
        #formulario {
            background-color: #fce4ec; /* Color pastel rosa */
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            width: 60%;
            margin-bottom: 20px;
        }

        /* Sección de resultados */
        #resultado {
            background-color: #c8e6c9; /* Color pastel verde */
            padding: 20px;
            margin-top: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            width: 60%;
            text-align: left;
        }

        h3, h2 {
            color: #333;
        }

        label {
            display: block;
            margin: 10px 0 5px;
        }

        input, select {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
            border-radius: 4px;
            border: 1px solid #ddd;
        }

        button {
            background-color: #4caf50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

    </style>
</head>
<body>

    <!-- Video al inicio (Pausado) -->
    <div id="videoInicio">
        <h3>Video de Introducción</h3>
        <iframe width="400" height="225" src="https://www.youtube.com/embed/u8wdk-_cRA0?autoplay=0" frameborder="0" allowfullscreen></iframe>
    </div>

    <div id="formulario">
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
    </div>

    <!-- Datos Ingresados -->
    <div id="resultado">
        <h3>Datos Ingresados:</h3>
        <p id="resultado"></p>
    </div>

    <!-- Video después de completar el formulario -->
    <div id="videoFinal" style="display: none;">
        <h3>Video Final</h3>
        <iframe width="400" height="225" src="https://www.youtube.com/embed/u8wdk-_cRA0?autoplay=1" frameborder="0" allowfullscreen></iframe>
    </div>

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

            // Mostrar el video final
            document.getElementById("videoFinal").style.display = "block";
        }
    </script>

</body>
</html>
