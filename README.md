<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Generador de Historias Aleatorias</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }

        .container {
            max-width: 600px;
            margin: 50px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }

        h1 {
            text-align: center;
        }

        #story-container {
            border: 1px solid #ccc;
            padding: 10px;
            margin-bottom: 20px;
        }

        button {
            display: block;
            margin: 0 auto;
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Generador de Historias Aleatorias</h1>
        <div id="story-container">
            <!-- Aquí se mostrará la historia generada -->
        </div>
        <button id="generate-btn">Generar Historia</button>
    </div>

    <script>
        // Definir listas de palabras para construir la historia
        const personajes = ['Juan', 'María', 'Pedro', 'Ana', 'Luisa', 'Carlos', 'Sofía', 'Miguel', 'Lucía', 'Diego'];
        const acciones = ['comió', 'corrió', 'saltó', 'cantó', 'bailó', 'leyó', 'escribió', 'cocinó', 'dibujó', 'estudió'];
        const objetos = ['un libro', 'una pelota', 'una flor', 'una guitarra', 'un pastel', 'un cuadro', 'un poema', 'un plato de pasta', 'un avión de papel', 'una bicicleta'];

        // Función para generar una historia aleatoria
        function generarHistoria() {
            const numPersonajes = Math.floor(Math.random() * 3) + 2; // Entre 2 y 4 personajes
            const numAcciones = Math.floor(Math.random() * 3) + 2; // Entre 2 y 4 acciones
            const numObjetos = Math.floor(Math.random() * 3) + 2; // Entre 2 y 4 objetos

            let historia = '';

            for (let i = 0; i < numPersonajes; i++) {
                historia += personajes[Math.floor(Math.random() * personajes.length)];
                if (i < numPersonajes - 1) {
                    historia += ', ';
                }
            }
            historia += ' ';

            for (let i = 0; i < numAcciones; i++) {
                historia += acciones[Math.floor(Math.random() * acciones.length)];
                if (i < numAcciones - 1) {
                    historia += ', ';
                }
            }
            historia += ' con ';

            for (let i = 0; i < numObjetos; i++) {
                historia += objetos[Math.floor(Math.random() * objetos.length)];
                if (i < numObjetos - 1) {
                    historia += ', ';
                }
            }
            historia += '.';

            document.getElementById('story-container').innerText = historia;
        }

        // Escuchar eventos del botón de generación de historias
        document.getElementById('generate-btn').addEventListener('click', generarHistoria);

        // Generar una historia al cargar la página
        generarHistoria();
    </script>
</body>
</html>
