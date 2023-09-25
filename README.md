<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Pagina de Tareas y Practicas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }

        header {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 20px;
        }

        h1 {
            font-size: 36px;
        }

        nav ul {
            list-style: none;
            padding: 0;
            text-align: center;
        }

        nav ul li {
            display: inline;
            margin-right: 20px;
        }

        nav ul li a {
            text-decoration: none;
            color: #333;
            font-weight: bold;
        }

        /* Estilos para el control de volumen */
        #volume-control {
            width: 150px;
            background-color: #fff;
            border: none;
            border-radius: 10px;
            -webkit-appearance: none;
        }

        #volume-control::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 20px;
            height: 20px;
            background-color: #333;
            border: none;
            border-radius: 50%;
        }

        /* Estilos para la seccion principal */
        .main-section {
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            padding: 20px;
            margin: 20px;
        }

        /* Estilos para los enlaces dentro de la seccion principal */
        .main-section a {
            text-decoration: none;
            color: #333;
            font-weight: bold;
            margin-right: 10px;
        }

        /* Estilos para los encabezados de las secciones de trimestres */
        .section-header {
            font-size: 24px;
            margin-top: 20px;
        }

        /* Estilos para los desplegables */
        .dropdown {
            display: none;
        }

        .dropdown-label {
            cursor: pointer;
            color: #333;
            background-color: #f0f0f0;
            padding: 10px;
            border-radius: 5px;
            margin-top: 10px;
        }

        .dropdown-label:hover {
            background-color: #ddd;
        }

        .dropdown-content {
            display: none;
            padding: 10px;
            border-radius: 5px;
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        .dropdown-label.active + .dropdown-content {
            display: block;
        }

        /* Estilos para el GIF desplazante */
        .gif-desplazante {
            position: absolute;
            top: 60%;
            left: -100px; /* Empieza fuera del área visible a la izquierda */
            width: 300px; /* Ajusta el ancho de tu GIF */
            height: auto;
            animation: desplazamientoDerecha 5s linear infinite; /* Ajusta la duración y otros valores según tus preferencias */
        }

        /* Animación para el desplazamiento de izquierda a derecha */
        @keyframes desplazamientoDerecha {
            0% {
                left: -300px; /* Comienza fuera de la pantalla a la izquierda */
            }
            100% {
                left: calc(100% + 100px); /* Termina fuera de la pantalla a la derecha */
            }
        }
    </style>		
    
</head>
<body>
    <audio autoplay loop id="background-music">
        <source src="musica_ascensor.mp3" type="audio/mpeg">
        Tu navegador no admite la reproducción de audio.
    </audio>

    <header>
        <h1>Francisco Manuel Monjo Lancharro</h1>
    </header>

    <nav>
        <ul>
            <li><a href="trimestre1.html">Primer Trimestre</a></li>
            <li><a href="trimestre2.html">Segundo Trimestre</a></li>
            <li><a href="trimestre3.html">Tercer Trimestre</a></li>
        </ul>
    </nav>

    <div class="main-section">
        <h2 class="section-header">Bienvenido</h2>
    </div>
	<img src="nyan-cat.gif" id="gifDesplazante" alt="GIF Desplazante" class="gif-desplazante">
	
    <label for="volume-control">Volumen:</label>
    <input type="range" id="volume-control" min="0" max="1" step="0.1" value="0.5">

    <div class="dropdown">
        <label class="dropdown-label" for="trimestre1-toggle">Primer Trimestre</label>
        <input type="checkbox" id="trimestre1-toggle" class="dropdown-label">
        <div class="dropdown-content">
            <a href="#">Temas</a>
            <a href="#">Practicas</a>
        </div>
    </div>

    <script>
        const audio = document.getElementById("background-music");
        // Obtén una referencia al control de volumen
        const volumeControl = document.getElementById("volume-control");
        audio.volume = volumeControl.value;
        // Agrega un evento que se activa cuando cambia el valor del control de volumen
        volumeControl.addEventListener("input", function() {
            audio.volume = volumeControl.value;
        });
    </script>
</body>
</html>




