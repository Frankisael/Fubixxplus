# Fubixx - Portal de Entretenimiento

```html
<link href="https://fonts.googleapis.com/css2?family=Raleway:wght@300;400;600;700;800&amp;display=swap" rel="stylesheet" />
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet" />
<style>
    :root {
        --primary-color: #ff0000;
        --primary-dark: #009624;
        --bg-color: #121212;
        --bg-light: #1e1e1e;
        --text-color: #ffffff;
        --text-secondary: #b0b0b0;
        --card-bg: #252525;
        --card-hover: #333;
    }

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Raleway', sans-serif;
    }

    body {
        background-color: var(--bg-color);
        color: var(--text-color);
        line-height: 1.7;
        -webkit-font-smoothing: antialiased;
    }

    a {
        text-decoration: none;
        color: inherit;
        transition: all 0.3s ease;
    }

    /* Header */
    .app-header {
        display: flex;
        padding: 15px 10px;
        align-items: center;
        gap: 15px;
        background: linear-gradient(135deg, var(--bg-light) 0%, var(--bg-color) 100%);
        border-bottom: 1px solid rgba(0, 200, 83, 0.1);
    }

    .app-header img {
        width: 70px;
        height: 70px;
        border-radius: 12px;
        object-fit: cover;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    }

    .app-info h1 {
        font-size: 24px;
        font-weight: 800;
        color: var(--primary-color);
        margin-bottom: 5px;
    }

    .app-info p {
        font-size: 14px;
        color: var(--text-secondary);
        font-weight: 300;
    }

    /* Botones de dispositivo */
    .device-buttons {
        display: flex;
        overflow-x: auto;
        gap: 10px;
        padding: 15px;
        scrollbar-width: none;
    }

    .device-buttons::-webkit-scrollbar {
        display: none;
    }

    .device-btn {
        flex: 0 0 auto;
        background-color: var(--card-bg);
        color: var(--text-color);
        border: none;
        border-radius: 8px;
        padding: 12px 15px;
        font-size: 14px;
        font-weight: 600;
        cursor: pointer;
        transition: all 0.3s ease;
        display: flex;
        align-items: center;
        gap: 8px;
        white-space: nowrap;
    }

    .device-btn i {
        font-size: 16px;
    }

    .device-btn:hover, .device-btn.active {
        background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
        transform: translateY(-2px);
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    }

    .device-btn.active {
        box-shadow: 0 0 0 2px var(--primary-color);
    }

    /* Instrucciones */
    .instructions-container {
        padding: 0 15px 20px;
        display: none;
    }

    .instructions-container.active {
        display: block;
        animation: fadeIn 0.5s ease;
    }

    .instructions-title {
        font-size: 20px;
        margin-bottom: 15px;
        color: var(--primary-color);
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .instructions-title i {
        font-size: 20px;
    }

    .steps {
        background-color: var(--bg-light);
        border-radius: 10px;
        padding: 15px;
        margin-bottom: 15px;
    }

    .steps ol, .steps ul {
        padding-left: 20px;
    }

    .steps li {
        margin-bottom: 10px;
        color: var(--text-secondary);
    }

    .steps li strong {
        color: var(--text-color);
    }

    .steps a {
        color: #d4a017;
        font-weight: 600;
    }

    .steps a:hover {
        text-decoration: underline;
    }

    .video-container {
        margin-top: 20px;
        text-align: center;
    }

    .video-container iframe {
        max-width: 100%;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    }

    /* Download Button */
    .download-btn {
        display: block;
        background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
        color: #fff;
        font-size: 18px;
        font-weight: 700;
        padding: 16px 25px;
        border-radius: 12px;
        text-align: center;
        margin: 20px 15px;
        border: none;
        cursor: pointer;
        box-shadow: 0 4px 15px rgba(0, 200, 83, 0.3);
        transition: all 0.3s ease;
    }

    .download-btn:hover {
        transform: translateY(-2px);
        box-shadow: 0 6px 20px rgba(0, 200, 83, 0.4);
    }

    .download-btn i {
        margin-right: 8px;
    }

    /* Galería de posters */
    .section-title {
        padding: 0 15px;
        margin-bottom: 15px;
        font-size: 20px;
        font-weight: 700;
        color: var(--primary-color);
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .section-title i {
        font-size: 22px;
    }

    .poster-container {
        padding: 0 10px 15px;
        display: none;
    }

    .poster-container.active {
        display: block;
        animation: fadeIn 0.5s ease;
    }

    .poster {
        display: flex;
        overflow-x: auto;
        padding: 15px 5px;
        gap: 15px;
        scrollbar-width: thin;
        scrollbar-color: var(--primary-color) var(--bg-light);
    }

    .poster::-webkit-scrollbar {
        height: 6px;
    }

    .poster::-webkit-scrollbar-track {
        background: var(--bg-light);
        border-radius: 10px;
    }

    .poster::-webkit-scrollbar-thumb {
        background-color: var(--primary-color);
        border-radius: 10px;
    }

    .poster img {
        border-radius: 12px;
        width: 150px;
        height: 280px;
        object-fit: cover;
        flex-shrink: 0;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .poster img:hover {
        transform: scale(1.03);
        box-shadow: 0 8px 16px rgba(0, 200, 83, 0.3);
    }

    /* Info Section */
    .section {
        padding: 20px 15px;
        background-color: var(--bg-light);
        margin: 20px 15px;
        border-radius: 12px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    .section h3 {
        color: var(--primary-color);
        margin-bottom: 15px;
        font-size: 20px;
        font-weight: 700;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .section h3 i {
        font-size: 20px;
    }

    .section p {
        margin-bottom: 10px;
        color: var(--text-secondary);
        font-size: 15px;
        line-height: 1.6;
    }

    .section p strong {
        color: var(--text-color);
        font-weight: 600;
    }

    hr {
        border: none;
        height: 1px;
        background-color: rgba(255, 255, 255, 0.1);
        margin: 20px 0;
    }

    /* Footer */
    .footer {
        text-align: center;
        padding: 20px;
        color: var(--text-secondary);
        font-size: 13px;
        background-color: var(--bg-light);
    }

    /* Animaciones */
    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }
</style>

<!-- Encabezado App -->
<header class="app-header">
    <img src="https://i.pinimg.com/236x/d4/c2/04/d4c204ac5e62dd78f2b429f409d70d2d.jpg" alt="Logo Fubixx" />
    <div class="app-info">
        <h1>Fubixx</h1>
        <p>Tu portal de entretenimiento ilimitado</p>
    </div>
</header>

<!-- Botón de descarga dinámico -->
<div id="dynamic-download-btn"></div>

<!-- Galería de posters -->
<h3 class="section-title"><i class="fas fa-photo-video"></i> Contenido Disponible</h3>
<div id="poster-container" class="poster-container">
    <div class="poster">
        <img src="https://i.pinimg.com/736x/91/59/98/915998de79cc1965c9979c03a9d7843e.jpg" alt="Película 1" />
        <img src="https://i.pinimg.com/474x/e1/32/33/e13233235ae9a87935a6b9eff9b58e36.jpg" alt="Película 2" />
        <img src="https://i.pinimg.com/736x/67/f8/96/67f896c5249225e9a4eeabf91a7ccd29.jpg" alt="Serie 1" />
        <img src="https://i.pinimg.com/736x/0b/79/34/0b7934838de4618a576e6150b4f583b3.jpg" alt="Serie 2" />
    </div>
</div>

<!-- Información -->
<div class="section">
    <h3><i class="fas fa-info-circle"></i> Información de la app</h3>
    <p><strong>Descripción:</strong></p>
    <p>Fubixx revoluciona tu experiencia de entretenimiento con acceso ilimitado:</p>
    <ul>
        <li>Películas en alta definición</li>
        <li>Series completas y actualizadas</li>
        <li>Canales de TV en vivo</li>
    </ul>
    <p>Disfruta de una interfaz intuitiva, búsqueda avanzada y recomendaciones personalizadas.</p>
    <hr />
    <p><strong>Disponible para:</strong> Android, iPhone, PC, Smart TV, TV Box, TV Stick</p>
</div>

<!-- Selector de dispositivo -->
<div class="device-buttons">
    <button class="device-btn active" data-device="android">
        <i class="fab fa-android"></i> Android
    </button>
    <button class="device-btn" data-device="iphone">
        <i class="fab fa-apple"></i> iPhone
    </button>
    <button class="device-btn" data-device="pc">
        <i class="fas fa-desktop"></i> PC
    </button>
    <button class="device-btn" data-device="smarttv">
        <i class="fas fa-tv"></i> Smart TV
    </button>
    <button class="device-btn" data-device="tvbox">
        <i class="fas fa-tv"></i> TV Box
    </button>
    <button class="device-btn" data-device="stick">
        <i class="fas fa-sticky-note"></i> TV Stick
    </button>
</div>

<!-- Instrucciones para Android -->
<div id="android-instructions" class="instructions-container active">
    <h3 class="instructions-title"><i class="fab fa-android"></i> Instalación en Android</h3>
    <div class="steps">
        <ol>
            <li><strong>Descarga el archivo APK</strong> desde:
                <a href="https://fubixxplusapp.blogspot.com/" target="_blank">fubixxplusapp.blogspot.com</a>
            </li>
            <li><strong>Configura DNS Privado para bloquear anuncios</strong>:
                <ol type="a">
                    <li>Ve a <strong>Ajustes</strong> > <strong>Conexiones</strong></li>
                    <li>Selecciona <strong>DNS Privado</strong></li>
                    <li>Elige <strong>Nombre de host del proveedor de DNS privado</strong></li>
                    <li>Ingresa: <code>dns.adguard.com</code></li>
                    <li>Guarda los cambios</li>
                </ol>
            </li>
            <li><strong>Permite la instalación</strong> de aplicaciones de origen desconocido:
                <ul>
                    <li>Ve a Ajustes > Seguridad</li>
                    <li>Activa "Fuentes desconocidas"</li>
                </ul>
            </li>
            <li>Abre el archivo APK descargado y presiona <strong>"Instalar"</strong>.</li>
        </ol>
    </div>
    <div class="video-container">
        <iframe width="280" height="158" src="https://player.vimeo.com/video/1090236292?h=92216b53a5" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
    </div>
</div>

<!-- Instrucciones para iPhone -->
<div id="iphone-instructions" class="instructions-container">
    <h3 class="instructions-title"><i class="fab fa-apple"></i> Instalación en iPhone</h3>
    <div class="steps">
        <ol>
            <li>Abre <strong>Safari</strong> en tu iPhone.</li>
            <li>Instala el bloqueador de anuncios desde:
                <a href="https://adguard-dns.io/es/public-dns.html" target="_blank">DNS ADGUARD SAFARI</a>
            </li>
            <li>Después de instalarlo:
                <ul>
                    <li>Ve a <strong>Ajustes > Safari > Extensiones</strong></li>
                    <li>Activa <strong>AdBlock</strong></li>
                </ul>
            </li>
            <li>Visita en Safari:
                <a href="https://fubixx.blogspot.com/" target="_blank">fubixx.blogspot.com</a>
            </li>
        </ol>
    </div>
    <div class="video-container">
        <iframe width="280" height="158" src="https://player.vimeo.com/video/1090222861?h=b04777f8f4" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
    </div>
</div>

<!-- Instrucciones para PC -->
<div id="pc-instructions" class="instructions-container">
    <h3 class="instructions-title"><i class="fas fa-desktop"></i> Instalación en PC</h3>
    <div class="steps">
        <ol>
            <li>Abre tu navegador (Chrome, Firefox, Edge)</li>
            <li>Instala un bloqueador de anuncios como:
                <a href="https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm" target="_blank">uBlock Origin</a>
            </li>
            <li>Visita:
                <a href="https://fubixx.blogspot.com/" target="_blank">fubixx.blogspot.com</a>
            </li>
        </ol>
    </div>
</div>

<!-- Instrucciones para Smart TV -->
<div id="smarttv-instructions" class="instructions-container">
    <h3 class="instructions-title"><i class="fas fa-tv"></i> Instalación en Smart TV</h3>
    <div class="steps">
        <ol>
            <li><strong>Método 1:</strong> Usa el navegador integrado:
                <ul>
                    <li>Abre el navegador y visita <a href="https://fubixx.blogspot.com/" target="_blank">fubixx.blogspot.com</a></li>
                </ul>
            </li>
            <li><strong>Método 2:</strong> Usa USB:
                <ul>
                    <li>Descarga el APK en una computadora</li>
                    <li>Cópialo a una USB</li>
                    <li>Conéctalo a la TV e instala</li>
                </ul>
            </li>
        </ol>
    </div>
</div>

<!-- Instrucciones para TV Box -->
<div id="tvbox-instructions" class="instructions-container">
    <h3 class="instructions-title"><i class="fas fa-tv"></i> Instalación en TV Box</h3>
    <div class="steps">
        <ol>
            <li><strong>Descarga el APK</strong> desde:
                <a href="https://fubixxplusapp.blogspot.com/" target="_blank">fubixxplusapp.blogspot.com</a>
            </li>
            <li><strong>Abre el archivo</strong> con un gestor de archivos (como X-Plore o ES File Explorer).</li>
            <li>Si es necesario, <strong>activa "Fuentes desconocidas"</strong> en ajustes.</li>
            <li><strong>Instala la aplicación</strong> y ábrela.</li>
        </ol>
    </div>
</div>

<!-- Instrucciones para TV Stick -->
<div id="stick-instructions" class="instructions-container">
    <h3 class="instructions-title"><i class="fas fa-sticky-note"></i> Instalación en TV Stick</h3>
    <div class="steps">
        <ol>
            <li>Desde la tienda de apps, instala <strong>"Downloader"</strong>.</li>
            <li>Abre Downloader y en la barra de búsqueda ingresa:
                <a href="https://fubixxplusapp.blogspot.com/" target="_blank">fubixxplusapp.blogspot.com</a>
            </li>
            <li>Descarga el APK desde el sitio.</li>
            <li>Instala la aplicación desde el archivo descargado.</li>
        </ol>
    </div>
</div>

<!-- Footer -->
<div class="footer">
    <p>© 2025 Fubixx Ltd. Todos los derechos reservados.</p>
</div>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        const deviceButtons = document.querySelectorAll('.device-btn');
        const instructionContainers = document.querySelectorAll('.instructions-container');
        const dynamicDownloadBtn = document.getElementById('dynamic-download-btn');
        const posterContainer = document.getElementById('poster-container');
        
        // Función para actualizar el botón de descarga
        function updateDownloadButton(device) {
            if (device === 'android' || device === 'tvbox' || device === 'stick') {
                dynamicDownloadBtn.innerHTML = `
                    <a href="https://archive.org/download/fubixx-plus/FubixxPlus.apk" class="download-btn">
                        <i class="fas fa-download"></i> Descargar APK
                    </a>
                `;
            } else {
                dynamicDownloadBtn.innerHTML = `
                    <a href="https://fubixx.blogspot.com/" class="download-btn">
                        <i class="fas fa-external-link-alt"></i> Ingresar a Fubixx
                    </a>
                `;
            }
        }
        
        // Función para mostrar/ocultar posters
        function updatePosterVisibility(device) {
            if (device === 'android' || device === 'iphone') {
                posterContainer.classList.add('active');
            } else {
                posterContainer.classList.remove('active');
            }
        }
        
        // Configurar evento para cada botón
        deviceButtons.forEach(button => {
            button.addEventListener('click', function() {
                // Remover clase active de todos los botones
                deviceButtons.forEach(btn => btn.classList.remove('active'));
                // Añadir clase active al botón clickeado
                this.classList.add('active');
                
                // Ocultar todos los contenedores de instrucciones
                instructionContainers.forEach(container => {
                    container.classList.remove('active');
                });
                
                // Mostrar el contenedor correspondiente
                const device = this.getAttribute('data-device');
                document.getElementById(`${device}-instructions`).classList.add('active');
                
                // Actualizar botón de descarga
                updateDownloadButton(device);
                
                // Actualizar visibilidad de posters
                updatePosterVisibility(device);
            });
        });
        
        // Inicializar
        updateDownloadButton('android');
        updatePosterVisibility('android');
    });
</script>
