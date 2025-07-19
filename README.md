<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TransHuaycán</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
<img src="https://transmar.pe/img/puntos%20de%20venta/tocache.jpg" alt="Logo TransHuaycán" style="width: 120px; display: block; margin: 0 auto 20px auto;">

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      background-color: #f2f2f2;
    }

    header {
      background-color: #004aad;
      padding: 20px;
      color: white;
      text-align: center;
    }

    nav {
      background-color: #0066cc;
      display: flex;
      justify-content: center;
      gap: 20px;
      padding: 15px 0;
    }

    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      padding: 10px 15px;
      border-radius: 5px;
      transition: background 0.3s;
    }

    nav a:hover {
      background-color: #003366;
    }

    #contenido {
      padding: 30px;
      background-color: white;
      margin: 20px auto;
      max-width: 900px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      border-radius: 10px;
      min-height: 300px;
    }

    footer {
      background-color: #004aad;
      color: white;
      text-align: center;
      padding: 15px;
      margin-top: 40px;
    }

    .formulario input {
      display: block;
      margin-bottom: 10px;
      padding: 8px;
      width: 100%;
    }

    .formulario button {
      padding: 10px 20px;
      background-color: #004aad;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

  #boletaPDF {
  display: none;
  padding: 30px 40px;
  color: #000;
  background-image: url('https://s1.rdbuz.com/bo-images/PER/WM/15786/938/FR/DS/webp/8UqrDY.webp'); /* Fondo bus elegante */
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  background-color: rgba(255, 255, 255, 0.95);
  border: 3px solid #004aad;
  border-radius: 12px;
  width: 100%;
  max-width: 700px;
  margin: auto;
  font-family: 'Arial', sans-serif;
  box-shadow: 0 0 15px rgba(0,0,0,0.3);
  backdrop-filter: blur(3px);
}

#boletaPDF h2 {
  text-align: center;
  font-size: 24px;
  margin-bottom: 20px;
  color: #004aad;
  border-bottom: 2px dashed #004aad;
  padding-bottom: 10px;
}

#boletaPDF p {
  background-color: rgba(255, 255, 255, 0.85);
  padding: 8px 15px;
  margin: 10px 0;
  border-left: 4px solid #004aad;
  border-radius: 6px;
  font-size: 16px;
}


  </style>
</head>
<body>
  <header>
    <h1>TransHuaycán</h1>
    <p>Transporte interprovincial desde Huaycán</p>
  </header>
<p style="text-align: center; font-style: italic; margin-top: 30px;">
  ¡Esperamos que disfrute su viaje con nosotros!<br>
  <strong>TransHuaycán - Tu ruta confiable</strong>
</p>

  <nav>
    <a href="#" onclick="mostrarContenido('inicio')">Inicio</a>
    <a href="#" onclick="mostrarContenido('nosotros')">Nosotros</a>
    <a href="#" onclick="mostrarContenido('servicios')">Servicios</a>
    <a href="#" onclick="mostrarContenido('rutas')">Rutas</a>
    <a href="#" onclick="mostrarContenido('galeria')">Galería</a>
    <a href="#" onclick="mostrarContenido('contacto')">Contacto</a>
    <a href="#" onclick="mostrarContenido('reservar')">Reservar</a>
  </nav>

  <div id="contenido"></div>

  <!-- BOLETA PDF -->
  <div id="boletaPDF">
    <h2>BOLETA DE RESERVA DE VIAJE </h2>
    <p><strong>Nombre:</strong> <span id="pdf-nombre"></span></p>
    <p><strong>Apellidos:</strong> <span id="pdf-apellidos"></span></p>
    <p><strong>DNI:</strong> <span id="pdf-dni"></span></p>
    <p><strong>Teléfono:</strong> <span id="pdf-telefono"></span></p>
    <p><strong>Destino:</strong> <span id="pdf-destino"></span></p>
    <p><strong>Fecha de viaje:</strong> <span id="pdf-fecha"></span></p>
    <p><strong>Hora de salida:</strong> <span id="pdf-hora"></span></p>
    <p style="margin-top:20px;">Gracias por viajar con <strong>TransHuaycán</strong>.</p>
  </div>

  <footer>
    <p>&copy; 2025 TransHuaycán. Todos los derechos reservados.</p>
  </footer>

  <script>
    function mostrarContenido(seccion) {
      const contenido = document.getElementById('contenido');

      switch (seccion) {
        case 'inicio':
          contenido.innerHTML = `
            <h2>Inicio</h2>
            <p>Bienvenido a TransHuaycán, tu mejor opción en transporte seguro, cómodo y rápido.</p>
            <iframe width="100%" height="400" src="	https://s51.aconvert.com/convert/p3r68-cdx67/yjxpl-xyxim.mp4" frameborder="0" allowfullscreen style="margin-top: 20px; border-radius: 10px;"></iframe>
          `;
          break;

        case 'nosotros':
          contenido.innerHTML = `
            <h2>Nosotros</h2>
            <p>Somos una empresa con más de 10 años de experiencia en transporte interprovincial desde Huaycán.</p>
            <img src="https://s1.rdbuz.com/bo-images/PER/WM/17601/13/FR/DS/webp/vWLU6V.webp" alt="Nosotros" style="width:100%; border-radius:10px; margin-top:15px;">
          `;
          break;

        case 'servicios':
          contenido.innerHTML = `
            <h2>Servicios</h2>
            <ul>
              <li>Transporte Interprovincial</li>
              <li>Envío de encomiendas</li>
              <li>Viajes turísticos programados</li>
              <li>Atención al cliente 24/7</li>
            </ul>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQL3FRKL0KLXGfGgTjUiM4QIhIl7u85zSvc3g&s" style="width:100%; border-radius:10px; margin-top:15px;">
          `;
          break;

        case 'rutas':
          contenido.innerHTML = `
            <h2>Rutas</h2>
            <ul>
              <li>Huaycán - Huancayo</li>
              <iframe src="https://www.google.com/maps?q=Huancayo,+Perú&output=embed" width="100%" height="300" style="border:0; border-radius:10px; margin-bottom:20px;"></iframe>
              <li>Huaycán - Tarma</li>
              <iframe src="https://www.google.com/maps?q=Tarma,+Perú&output=embed" width="100%" height="300" style="border:0; border-radius:10px; margin-bottom:20px;"></iframe>
              <li>Huaycán - La Merced</li>
              <iframe src="https://www.google.com/maps?q=La+Merced,+Chanchamayo,+Perú&output=embed" width="100%" height="300" style="border:0; border-radius:10px; margin-bottom:20px;"></iframe>
              <li>Huaycán - Satipo</li>
              <iframe src="https://www.google.com/maps?q=Satipo,+Perú&output=embed" width="100%" height="300" style="border:0; border-radius:10px;"></iframe>
            </ul>
          `;
          break;

        case 'galeria':
          contenido.innerHTML = `
            <h2>Galería</h2>
            <p>Conoce nuestras modernas unidades y momentos del viaje.</p>
            <img src="https://s11.aconvert.com/convert/p3r68-cdx67/ip3a1-4rlq1.webp" style="width:100%; border-radius:10px; margin-top:10px;">
            <img src="https://s1.rdbuz.com/bo-images/PER/WM/15782/13/FR/DS/webp/Szc357.webp" style="width:100%; border-radius:10px; margin-top:10px;">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ3LEQSq15AXOAyaccakI70PfaoQiJ4-aeL6A&s" style="width:100%; border-radius:10px; margin-top:10px;">
          `;
          break;

        case 'contacto':
          contenido.innerHTML = `
            <h2>Contacto</h2>
            <ul>
              <li>Teléfono: 01 234 5678</li>
              <li>Correo: contacto@transhuaycan.pe</li>
              <li>Dirección: Av. Principal 123, Huaycán</li>
            </ul>
            <iframe src="https://www.google.com/maps?q=Huaycán,+Perú&output=embed" width="100%" height="300" style="border:0; margin-top:15px; border-radius:10px;"></iframe>
          `;
          break;

        case 'reservar':
          contenido.innerHTML = `
            <h2>Reserva tu pasaje</h2>
            <form class="formulario" onsubmit="generarPDF(event)">
              <input type="text" id="nombre" placeholder="Nombre" required>
              <input type="text" id="apellidos" placeholder="Apellidos" required>
              <input type="text" id="dni" placeholder="DNI" required>
              <input type="text" id="telefono" placeholder="Teléfono" required>
              <input type="text" id="destino" placeholder="Destino" required>
              <input type="date" id="fecha" required>
              <input type="time" id="hora" required>
              <button type="submit">Generar PDF</button>
            </form>
          `;
          break;
      }
    }

    function generarPDF(event) {
      event.preventDefault();

      const nombre = document.getElementById('nombre').value;
      const apellidos = document.getElementById('apellidos').value;
      const dni = document.getElementById('dni').value;
      const telefono = document.getElementById('telefono').value;
      const destino = document.getElementById('destino').value;
      const fecha = document.getElementById('fecha').value;
      const hora = document.getElementById('hora').value;

      document.getElementById('pdf-nombre').textContent = nombre;
      document.getElementById('pdf-apellidos').textContent = apellidos;
      document.getElementById('pdf-dni').textContent = dni;
      document.getElementById('pdf-telefono').textContent = telefono;
      document.getElementById('pdf-destino').textContent = destino;
      document.getElementById('pdf-fecha').textContent = fecha;
      document.getElementById('pdf-hora').textContent = hora;

      const boleta = document.getElementById('boletaPDF');
      boleta.style.display = "block";

      setTimeout(() => {
        const opciones = {
          margin: 0.5,
          filename: `Boleta_${nombre}_${dni}.pdf`,
          image: { type: 'jpeg', quality: 0.98 },
          html2canvas: { scale: 2 },
          jsPDF: { unit: 'in', format: 'letter', orientation: 'portrait' }
        };

        html2pdf().set(opciones).from(boleta).save().then(() => {
          boleta.style.display = "none";
        });
      }, 500);
    }

    // Cargar "Nosotros" por defecto
    window.onload = function () {
      mostrarContenido('nosotros');
    };
  </script>
</body>
</html>
