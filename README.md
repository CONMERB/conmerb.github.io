<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CONMERB - Registro de Datos</title>
</head>
<body>
    <h1>Bienvenido a CONMERB</h1>
    <p>Datos del usuario:</p>
    <ul>
        <li><strong>Nombre:</strong> Abdon Mamani Rojas</li>
        <li><strong>CI:</strong> 10018548</li>
    </ul>
    <h2>Registro de Datos</h2>
    <form id="registroForm">
        <label for="nombre">Nombre:</label>
        <input type="text" id="nombre" required><br><br>
        <label for="ci">CI:</label>
        <input type="text" id="ci" required><br><br>
        <button type="submit">Guardar</button>
    </form>
    <h3>Datos Guardados:</h3>
    <p id="datosGuardados"></p>

    <script>
        document.getElementById('registroForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const nombre = document.getElementById('nombre').value;
            const ci = document.getElementById('ci').value;
            localStorage.setItem('usuarioNombre', nombre);
            localStorage.setItem('usuarioCI', ci);
            mostrarDatos();
        });

        function mostrarDatos() {
            const nombre = localStorage.getItem('usuarioNombre') || "No registrado";
            const ci = localStorage.getItem('usuarioCI') || "No registrado";
            document.getElementById('datosGuardados').innerText = `Nombre: ${nombre}, CI: ${ci}`;
        }
        
        mostrarDatos();
    </script>
</body>
</html>
