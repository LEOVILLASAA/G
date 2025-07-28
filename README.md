<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Descargador de Páginas Web - backup recuperacion web</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            color: #333;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .logo {
            font-size: 2.5rem;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        h1 {
            color: #333;
            margin-bottom: 10px;
            font-size: 2rem;
        }

        .subtitle {
            color: #666;
            font-size: 1.1rem;
            margin-bottom: 30px;
        }

        .url-section {
            background: #f8f9ff;
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 30px;
            border-left: 4px solid #667eea;
        }

        .input-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #555;
        }

        .url-input {
            width: 100%;
            padding: 15px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .url-input:focus {
            outline: none;
            border-color: #667eea;
            box-shadow: 0 0 10px rgba(102, 126, 234, 0.2);
        }

        .button-group {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            padding: 15px 25px;
            border: none;
            border-radius: 10px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }

        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .btn-secondary {
            background: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
            color: white;
        }

        .btn-success {
            background: linear-gradient(135deg, #56ab2f 0%, #a8e6cf 100%);
            color: white;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
        }

        .warning-section {
            background: #fff3cd;
            border: 1px solid #ffeaa7;
            border-radius: 10px;
            padding: 20px;
            margin: 30px 0;
        }

        .warning-section h3 {
            color: #856404;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .warning-section p {
            color: #856404;
            line-height: 1.6;
            margin-bottom: 10px;
        }

        .info-section {
            background: #d1ecf1;
            border: 1px solid #bee5eb;
            border-radius: 10px;
            padding: 20px;
            margin: 30px 0;
        }

        .info-section h3 {
            color: #0c5460;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .info-section ul {
            color: #0c5460;
            padding-left: 20px;
        }

        .info-section li {
            margin-bottom: 8px;
            line-height: 1.5;
        }

        .iframe-container {
            margin: 30px 0;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            display: none;
        }

        .iframe-container iframe {
            width: 100%;
            height: 400px;
            border: none;
        }

        .status-message {
            padding: 15px;
            border-radius: 10px;
            margin: 20px 0;
            display: none;
        }

        .status-success {
            background: #d4edda;
            border: 1px solid #c3e6cb;
            color: #155724;
        }

        .status-error {
            background: #f8d7da;
            border: 1px solid #f5c6cb;
            color: #721c24;
        }

        .status-info {
            background: #d1ecf1;
            border: 1px solid #bee5eb;
            color: #0c5460;
        }

        @media (max-width: 600px) {
            .container {
                padding: 20px;
                margin: 10px;
            }
            
            .button-group {
                flex-direction: column;
            }
            
            .btn {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="logo">🌐ventas repuestos automotriz</div>
            <h1>Descargador de Páginas Web</h1>
            <p class="subtitle">Ingresa una URL para navegar y descargar su contenido HTML</p>
        </div>

        <div class="url-section">
            <div class="input-group">
                <label for="urlInput">🔗 URL de la página web:</label>
                <input 
                    type="url" 
                    id="urlInput" 
                    class="url-input" 
                    placeholder="https://ejemplo.com" 
                  
                >
            </div>

            <div class="button-group">
                <button class="btn btn-primary" onclick="navigateToUrl()">
                    🚀 Ir a la Página
                </button>
                <button class="btn btn-secondary" onclick="downloadPageHTML()">
                    📥 Descargar HTML
                </button>
                <button class="btn btn-success" onclick="downloadCurrentPage()">
                    💾 Backup de Esta Página
                </button>
            </div>
        </div>

        <div id="statusMessage" class="status-message"></div>

        <div class="warning-section">
            <h3>⚠️ Restricciones de Seguridad</h3>
            <p><strong>Importante:</strong> Debido a las políticas de seguridad de los navegadores (CORS - Cross-Origin Resource Sharing), no es posible descargar directamente el HTML de sitios web externos desde JavaScript.</p>
            <p><strong>Alternativas disponibles:</strong></p>
            <ul>
                <li>Usar el botón "Ir a la Página" para navegar al sitio</li>
                <li>Una vez en el sitio, usar Ctrl+S para guardar la página</li>
                <li>Usar herramientas del navegador (F12 → Elements → Copiar HTML)</li>
                <li>Usar extensiones del navegador especializadas</li>
            </ul>
        </div>

        <div class="info-section">
            <h3>ℹ️ Cómo Usar Esta Herramienta</h3>
            <ul>
                <li><strong>Paso 1:</strong> Ingresa la URL completa (incluyendo https://)</li>
                <li><strong>Paso 2:</strong> Haz clic en "Ir a la Página" para navegar al sitio</li>
                <li><strong>Paso 3:</strong> Una vez en el sitio, usa las herramientas del navegador para guardar</li>
                <li><strong>Alternativa:</strong> Usa "Backup de Esta Página" para descargar esta herramienta</li>
            </ul>
        </div>

        <div class="iframe-container" id="iframeContainer">
            <iframe id="websiteFrame" src=""></iframe>
        </div>
    </div>

    <script>
        function showStatus(message, type = 'info') {
            const statusDiv = document.getElementById('statusMessage');
            statusDiv.className = `status-message status-${type}`;
            statusDiv.textContent = message;
            statusDiv.style.display = 'block';
            
            // Ocultar después de 5 segundos
            setTimeout(() => {
                statusDiv.style.display = 'none';
            }, 5000);
        }

        function validateUrl(url) {
            try {
                new URL(url);
                return true;
            } catch {
                return false;
            }
        }

        function navigateToUrl() {
            const urlInput = document.getElementById('urlInput');
            let url = urlInput.value.trim();
            
            if (!url) {
                showStatus('Por favor, ingresa una URL válida.', 'error');
                return;
            }
            
            // Agregar https:// si no tiene protocolo
            if (!url.startsWith('http://') && !url.startsWith('https://')) {
                url = 'https://' + url;
                urlInput.value = url;
            }
            
            if (!validateUrl(url)) {
                showStatus('La URL ingresada no es válida.', 'error');
                return;
            }
            
            showStatus('Navegando a: ' + url, 'success');
            
            // Abrir en nueva pestaña
            window.open(url, '_blank');
        }

        function downloadPageHTML() {
            const urlInput = document.getElementById('urlInput');
            let url = urlInput.value.trim();
            
            if (!url) {
                showStatus('Por favor, ingresa una URL válida.', 'error');
                return;
            }
            
            // Agregar https:// si no tiene protocolo
            if (!url.startsWith('http://') && !url.startsWith('https://')) {
                url = 'https://' + url;
            }
            
            if (!validateUrl(url)) {
                showStatus('La URL ingresada no es válida.', 'error');
                return;
            }
            
            showStatus('Intentando descargar HTML...', 'info');
            
            // Intentar fetch (probablemente fallará por CORS)
            fetch(url)
                .then(response => {
                    if (!response.ok) {
                        throw new Error(`HTTP ${response.status}: ${response.statusText}`);
                    }
                    return response.text();
                })
                .then(html => {
                    // Si llegamos aquí, el fetch funcionó
                    downloadHtmlContent(html, url);
                    showStatus('¡HTML descargado exitosamente!', 'success');
                })
                .catch(error => {
                    console.error('Error al descargar:', error);
                    showStatus(
                        'No se pudo descargar el HTML debido a restricciones CORS. ' +
                        'Usa el botón "Ir a la Página" y luego Ctrl+S para guardar.', 
                        'error'
                    );
                    
                    // Ofrecer alternativa: abrir la página
                    setTimeout(() => {
                        if (confirm('¿Quieres abrir la página en una nueva pestaña para guardarla manualmente?')) {
                            window.open(url, '_blank');
                        }
                    }, 2000);
                });
        }

        function downloadHtmlContent(htmlContent, sourceUrl) {
            try {
                const blob = new Blob([htmlContent], { type: 'text/html;charset=utf-8' });
                const downloadLink = document.createElement('a');
                downloadLink.href = URL.createObjectURL(blob);
                
                // Generar nombre de archivo basado en la URL
                const urlObj = new URL(sourceUrl);
                const domain = urlObj.hostname.replace(/[^a-zA-Z0-9]/g, '_');
                const timestamp = new Date().toISOString().slice(0, 19).replace(/[:-]/g, '');
                downloadLink.download = `${domain}_${timestamp}.html`;
                
                document.body.appendChild(downloadLink);
                downloadLink.click();
                document.body.removeChild(downloadLink);
                URL.revokeObjectURL(downloadLink.href);
                
            } catch (error) {
                console.error('Error al crear descarga:', error);
                showStatus('Error al crear el archivo de descarga.', 'error');
            }
        }

        function downloadCurrentPage() {
            try {
                const htmlContent = document.documentElement.outerHTML;
                const blob = new Blob([htmlContent], { type: 'text/html;charset=utf-8' });
                const downloadLink = document.createElement('a');
                downloadLink.href = URL.createObjectURL(blob);
                
                const timestamp = new Date().toISOString().slice(0, 19).replace(/[:-]/g, '');
                downloadLink.download = `descargador_web_leovs_${timestamp}.html`;
                
                document.body.appendChild(downloadLink);
                downloadLink.click();
                document.body.removeChild(downloadLink);
                URL.revokeObjectURL(downloadLink.href);
                
                showStatus('¡Backup de esta página descargado exitosamente!', 'success');
                
            } catch (error) {
                console.error('Error al descargar backup:', error);
                showStatus('Error al descargar el backup.', 'error');
            }
        }

        // Permitir presionar Enter en el input para navegar
        document.getElementById('urlInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                navigateToUrl();
            }
        });

        // Mostrar mensaje de bienvenida
        window.onload = function() {
            showStatus('Herramienta cargada. Ingresa una URL para comenzar.', 'info');
        };
    </script>
</body>
</html>

