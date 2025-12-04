<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nuestro Álbum Digital</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary-color: #ff6b8b;
            --secondary-color: #6a5af9;
            --accent-color: #4ecdc4;
            --light-color: #fff9fb;
            --dark-color: #333;
            --shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            --gradient: linear-gradient(135deg, #ff6b8b 0%, #6a5af9 100%);
        }
        
        body {
            background-color: #f9f5f7;
            color: var(--dark-color);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background: var(--gradient);
            color: white;
            padding: 30px 0;
            text-align: center;
            box-shadow: var(--shadow);
            border-radius: 0 0 30px 30px;
            margin-bottom: 40px;
        }
        
        .logo {
            font-size: 2.8rem;
            margin-bottom: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
        }
        
        .logo i {
            color: #ffeb3b;
        }
        
        .couple-name {
            font-size: 1.5rem;
            font-weight: 300;
            letter-spacing: 3px;
            margin-bottom: 20px;
        }
        
        /* Navegación */
        nav {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 25px;
            flex-wrap: wrap;
        }
        
        .nav-btn {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: white;
            padding: 12px 25px;
            border-radius: 50px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .nav-btn:hover, .nav-btn.active {
            background: white;
            color: var(--primary-color);
            transform: translateY(-3px);
        }
        
        /* Secciones */
        .section {
            display: none;
            padding: 40px 0;
            animation: fadeIn 0.8s ease;
        }
        
        .section.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            color: var(--primary-color);
            font-size: 2.2rem;
            position: relative;
            padding-bottom: 15px;
        }
        
        .section-title:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--gradient);
            border-radius: 2px;
        }
        
        /* Galería de fotos */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }
        
        .photo-item {
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
            height: 250px;
            position: relative;
        }
        
        .photo-item:hover {
            transform: translateY(-10px);
        }
        
        .photo-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .photo-item:hover img {
            transform: scale(1.05);
        }
        
        .photo-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 15px;
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }
        
        .photo-item:hover .photo-caption {
            transform: translateY(0);
        }
        
        /* Reproductor de música */
        .music-player {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: var(--shadow);
            max-width: 800px;
            margin: 0 auto 40px;
        }
        
        .song-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-top: 25px;
        }
        
        .song-item {
            display: flex;
            align-items: center;
            padding: 15px;
            border-radius: 10px;
            background: #f8f8f8;
            transition: background 0.3s ease;
        }
        
        .song-item:hover {
            background: #f0f0f0;
        }
        
        .song-item.active {
            background: #e6f7ff;
            border-left: 4px solid var(--secondary-color);
        }
        
        .song-info {
            flex: 1;
            margin-left: 15px;
        }
        
        .song-title {
            font-weight: 600;
            color: var(--dark-color);
        }
        
        .song-artist {
            font-size: 0.9rem;
            color: #666;
        }
        
        /* Historias */
        .stories-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .story-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
        }
        
        .story-card:hover {
            transform: translateY(-10px);
        }
        
        .story-img {
            height: 200px;
            width: 100%;
            object-fit: cover;
        }
        
        .story-content {
            padding: 25px;
        }
        
        .story-date {
            color: var(--primary-color);
            font-size: 0.9rem;
            margin-bottom: 10px;
            display: block;
        }
        
        .story-text {
            color: #555;
            line-height: 1.7;
        }
        
        /* Área de subida */
        .upload-area {
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: var(--shadow);
            text-align: center;
            margin-bottom: 40px;
        }
        
        .upload-box {
            border: 3px dashed #ddd;
            border-radius: 15px;
            padding: 60px 20px;
            margin: 30px 0;
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .upload-box:hover, .upload-box.dragover {
            border-color: var(--primary-color);
            background: #fff5f7;
        }
        
        .upload-icon {
            font-size: 4rem;
            color: var(--primary-color);
            margin-bottom: 20px;
        }
        
        .upload-btn {
            background: var(--gradient);
            color: white;
            border: none;
            padding: 15px 40px;
            border-radius: 50px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 20px;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }
        
        .upload-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 7px 15px rgba(255, 107, 139, 0.4);
        }
        
        .upload-options {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 30px;
        }
        
        .upload-option {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            border-radius: 15px;
            background: #f9f9f9;
            width: 180px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .upload-option:hover {
            background: #f0f0f0;
            transform: translateY(-5px);
        }
        
        .upload-option i {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }
        
        .photo-option i { color: #ff6b8b; }
        .music-option i { color: #6a5af9; }
        .story-option i { color: #4ecdc4; }
        
        /* Footer */
        footer {
            background: var(--dark-color);
            color: white;
            text-align: center;
            padding: 30px 0;
            margin-top: 60px;
            border-radius: 30px 30px 0 0;
        }
        
        .heart {
            color: var(--primary-color);
            animation: heartbeat 1.5s infinite;
        }
        
        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .gallery {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
            
            .stories-container {
                grid-template-columns: 1fr;
            }
            
            .upload-options {
                flex-direction: column;
                align-items: center;
            }
            
            nav {
                gap: 10px;
            }
            
            .nav-btn {
                padding: 10px 20px;
                font-size: 0.9rem;
            }
        }
        
        /* Modal para previsualización */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            animation: fadeIn 0.3s ease;
        }
        
        .modal-content {
            max-width: 90%;
            max-height: 90%;
            border-radius: 10px;
            overflow: hidden;
        }
        
        .modal-close {
            position: absolute;
            top: 20px;
            right: 30px;
            color: white;
            font-size: 2.5rem;
            cursor: pointer;
            transition: color 0.3s ease;
        }
        
        .modal-close:hover {
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="logo">
                <i class="fas fa-heart"></i>
                <h1>Nuestro Álbum Digital</h1>
                <i class="fas fa-heart"></i>
            </div>
            <div class="couple-name">Alex & María</div>
            <p>Un espacio para guardar nuestros momentos especiales</p>
            
            <nav>
                <button class="nav-btn active" data-section="fotos">
                    <i class="fas fa-images"></i> Fotos
                </button>
                <button class="nav-btn" data-section="musica">
                    <i class="fas fa-music"></i> Música
                </button>
                <button class="nav-btn" data-section="historias">
                    <i class="fas fa-book-open"></i> Historias
                </button>
                <button class="nav-btn" data-section="subir">
                    <i class="fas fa-cloud-upload-alt"></i> Subir Contenido
                </button>
            </nav>
        </div>
    </header>
    
    <main class="container">
        <!-- Sección de Fotos -->
        <section id="fotos" class="section active">
            <h2 class="section-title">Nuestros Momentos</h2>
            <div class="gallery" id="photoGallery">
                <!-- Las fotos se cargarán aquí dinámicamente -->
            </div>
        </section>
        
        <!-- Sección de Música -->
        <section id="musica" class="section">
            <h2 class="section-title">Nuestra Banda Sonora</h2>
            <div class="music-player">
                <div class="now-playing">
                    <h3>Reproduciendo ahora: <span id="currentSong">Canción Especial</span></h3>
                    <div class="audio-controls">
                        <audio id="audioPlayer" controls>
                            <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
                            Tu navegador no soporta el elemento de audio.
                        </audio>
                    </div>
                </div>
                
                <div class="song-list" id="songList">
                    <!-- Las canciones se cargarán aquí dinámicamente -->
                </div>
            </div>
        </section>
        
        <!-- Sección de Historias -->
        <section id="historias" class="section">
            <h2 class="section-title">Nuestras Historias</h2>
            <div class="stories-container" id="storiesContainer">
                <!-- Las historias se cargarán aquí dinámicamente -->
            </div>
        </section>
        
        <!-- Sección de Subir Contenido -->
        <section id="subir" class="section">
            <h2 class="section-title">Comparte un Recuerdo</h2>
            <div class="upload-area">
                <h3>Sube fotos, canciones o historias a nuestro álbum</h3>
                <p>Selecciona el tipo de contenido que quieres compartir</p>
                
                <div class="upload-options">
                    <div class="upload-option photo-option" data-type="photo">
                        <i class="fas fa-camera"></i>
                        <span>Subir Foto</span>
                    </div>
                    <div class="upload-option music-option" data-type="music">
                        <i class="fas fa-music"></i>
                        <span>Subir Canción</span>
                    </div>
                    <div class="upload-option story-option" data-type="story">
                        <i class="fas fa-book"></i>
                        <span>Escribir Historia</span>
                    </div>
                </div>
                
                <div class="upload-box" id="uploadBox">
                    <i class="fas fa-cloud-upload-alt upload-icon"></i>
                    <h4>Arrastra y suelta archivos aquí</h4>
                    <p>o haz clic para seleccionar archivos</p>
                    <p class="file-types">Soporta: JPG, PNG, MP3, PDF, TXT</p>
                    <input type="file" id="fileInput" multiple style="display: none;">
                    <button class="upload-btn" id="browseBtn">
                        <i class="fas fa-folder-open"></i> Buscar Archivos
                    </button>
                </div>
                
                <div id="uploadStatus"></div>
            </div>
        </section>
    </main>
    
    <!-- Modal para previsualización de imágenes -->
    <div class="modal" id="imageModal">
        <span class="modal-close" id="modalClose">&times;</span>
        <img class="modal-content" id="modalImage">
    </div>
    
    <footer>
        <div class="container">
            <p>Hecho con <span class="heart"><i class="fas fa-heart"></i></span> para guardar nuestros recuerdos</p>
            <p>© 2023 - Nuestro Álbum Digital</p>
        </div>
    </footer>

    <script>
        // Datos iniciales del álbum (simulados)
        const albumData = {
            photos: [
                { id: 1, src: "https://images.unsplash.com/photo-1518568814500-bf0f8d125f46?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=687&q=80", caption: "Nuestro primer viaje juntos" },
                { id: 2, src: "https://images.unsplash.com/photo-1529254479751-fbacb4c7a587?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80", caption: "Celebrando nuestro aniversario" },
                { id: 3, src: "https://images.unsplash.com/photo-1492684223066-e9e4aab4d25e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1171&q=80", caption: "Atardecer en la playa" },
                { id: 4, src: "https://images.unsplash.com/photo-1470252649374-6d73cd8cd714?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80", caption: "Noche de películas" },
                { id: 5, src: "https://images.unsplash.com/photo-1511795409834-ef04bbd61622?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1169&q=80", caption: "Cena romántica" },
                { id: 6, src: "https://images.unsplash.com/photo-1511988617509-a57c8a288659?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1171&q=80", caption: "Día de campo" }
            ],
            songs: [
                { id: 1, title: "Nuestra Canción", artist: "Artista Especial", src: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" },
                { id: 2, title: "Melodía de Amor", artist: "Banda Romántica", src: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-2.mp3" },
                { id: 3, title: "Recuerdos", artist: "Cantante Favorito", src: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-3.mp3" }
            ],
            stories: [
                { id: 1, title: "Cómo nos conocimos", date: "15 de Enero, 2022", content: "Fue en una cafetería cerca del parque. Ella llevaba un vestido azul y yo estaba leyendo mi libro favorito. Nuestras miradas se cruzaron y supe que ese momento cambiaría todo.", image: "https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" },
                { id: 2, title: "Nuestro primer viaje", date: "20 de Julio, 2022", content: "Fuimos a la montaña y pasamos tres días increíbles. Hicimos caminatas, cocinamos juntos y vimos las estrellas cada noche. Fue entonces cuando supe que quería pasar toda mi vida con ella.", image: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" },
                { id: 3, title: "La sorpresa de cumpleaños", date: "5 de Noviembre, 2022", content: "Organicé una fiesta sorpresa con todos sus amigos. Su expresión cuando entró y todos gritaron '¡Feliz cumpleaños!' fue priceless. Ese día me di cuenta de lo mucho que la amo.", image: "https://images.unsplash.com/photo-1530103862676-de8c9debad1d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" }
            ]
        };

        // Elementos del DOM
        const sections = document.querySelectorAll('.section');
        const navButtons = document.querySelectorAll('.nav-btn');
        const photoGallery = document.getElementById('photoGallery');
        const songList = document.getElementById('songList');
        const storiesContainer = document.getElementById('storiesContainer');
        const uploadBox = document.getElementById('uploadBox');
        const fileInput = document.getElementById('fileInput');
        const browseBtn = document.getElementById('browseBtn');
        const uploadStatus = document.getElementById('uploadStatus');
        const audioPlayer = document.getElementById('audioPlayer');
        const currentSongElement = document.getElementById('currentSong');
        const imageModal = document.getElementById('imageModal');
        const modalImage = document.getElementById('modalImage');
        const modalClose = document.getElementById('modalClose');
        const uploadOptions = document.querySelectorAll('.upload-option');

        // Inicializar la página
        document.addEventListener('DOMContentLoaded', function() {
            // Cargar datos iniciales
            loadPhotos();
            loadSongs();
            loadStories();
            
            // Configurar navegación
            setupNavigation();
            
            // Configurar área de subida
            setupUploadArea();
            
            // Configurar reproductor de música
            setupMusicPlayer();
            
            // Configurar modal de imágenes
            setupImageModal();
        });

        // Configurar navegación entre secciones
        function setupNavigation() {
            navButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const targetSection = this.getAttribute('data-section');
                    
                    // Actualizar botones activos
                    navButtons.forEach(btn => btn.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Mostrar sección correspondiente
                    sections.forEach(section => {
                        section.classList.remove('active');
                        if (section.id === targetSection) {
                            section.classList.add('active');
                        }
                    });
                });
            });
        }

        // Cargar fotos en la galería
        function loadPhotos() {
            photoGallery.innerHTML = '';
            albumData.photos.forEach(photo => {
                const photoElement = document.createElement('div');
                photoElement.className = 'photo-item';
                photoElement.innerHTML = `
                    <img src="${photo.src}" alt="${photo.caption}" data-id="${photo.id}">
                    <div class="photo-caption">
                        <p>${photo.caption}</p>
                    </div>
                `;
                photoElement.querySelector('img').addEventListener('click', function() {
                    openImageModal(this.src, photo.caption);
                });
                photoGallery.appendChild(photoElement);
            });
        }

        // Cargar canciones en la lista
        function loadSongs() {
            songList.innerHTML = '';
            albumData.songs.forEach((song, index) => {
                const songElement = document.createElement('div');
                songElement.className = `song-item ${index === 0 ? 'active' : ''}`;
                songElement.innerHTML = `
                    <i class="fas fa-music"></i>
                    <div class="song-info">
                        <div class="song-title">${song.title}</div>
                        <div class="song-artist">${song.artist}</div>
                    </div>
                    <i class="fas fa-play"></i>
                `;
                songElement.addEventListener('click', function() {
                    playSong(song, this);
                });
                songList.appendChild(songElement);
            });
        }

        // Cargar historias
        function loadStories() {
            storiesContainer.innerHTML = '';
            albumData.stories.forEach(story => {
                const storyElement = document.createElement('div');
                storyElement.className = 'story-card';
                storyElement.innerHTML = `
                    <img src="${story.image}" alt="${story.title}" class="story-img">
                    <div class="story-content">
                        <h3>${story.title}</h3>
                        <span class="story-date">${story.date}</span>
                        <p class="story-text">${story.content}</p>
                    </div>
                `;
                storiesContainer.appendChild(storyElement);
            });
        }

        // Configurar área de subida
        function setupUploadArea() {
            // Abrir selector de archivos al hacer clic en el botón o en el área
            browseBtn.addEventListener('click', () => fileInput.click());
            uploadBox.addEventListener('click', () => fileInput.click());
            
            // Manejar la selección de archivos
            fileInput.addEventListener('change', handleFileSelect);
            
            // Manejar arrastrar y soltar
            uploadBox.addEventListener('dragover', function(e) {
                e.preventDefault();
                this.classList.add('dragover');
            });
            
            uploadBox.addEventListener('dragleave', function() {
                this.classList.remove('dragover');
            });
            
            uploadBox.addEventListener('drop', function(e) {
                e.preventDefault();
                this.classList.remove('dragover');
                
                if (e.dataTransfer.files.length) {
                    handleFiles(e.dataTransfer.files);
                }
            });
            
            // Configurar opciones de subida
            uploadOptions.forEach(option => {
                option.addEventListener('click', function() {
                    const type = this.getAttribute('data-type');
                    
                    // Mostrar mensaje según el tipo seleccionado
                    let message = '';
                    if (type === 'photo') {
                        message = 'Selecciona una foto para subir a nuestro álbum';
                    } else if (type === 'music') {
                        message = 'Sube una canción especial para nuestra banda sonora';
                    } else if (type === 'story') {
                        message = 'Escribe una historia sobre nosotros';
                        // Para historias, mostrar un área de texto
                        showStoryTextArea();
                        return;
                    }
                    
                    uploadStatus.innerHTML = `<p style="color: var(--secondary-color); margin-top: 20px;"><i class="fas fa-info-circle"></i> ${message}</p>`;
                    fileInput.click();
                });
            });
        }

        // Manejar la selección de archivos
        function handleFileSelect(e) {
            const files = e.target.files;
            handleFiles(files);
        }

        // Procesar archivos seleccionados
        function handleFiles(files) {
            uploadStatus.innerHTML = '';
            
            if (files.length === 0) return;
            
            // Limitar a 5 archivos a la vez
            const fileArray = Array.from(files).slice(0, 5);
            
            fileArray.forEach((file, index) => {
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    // Simular subida de archivo
                    simulateUpload(file, e.target.result);
                };
                
                if (file.type.startsWith('image/')) {
                    reader.readAsDataURL(file);
                } else if (file.type.startsWith('audio/')) {
                    reader.readAsDataURL(file);
                } else {
                    reader.readAsText(file);
                }
            });
        }

        // Simular subida de archivo (en un caso real, aquí iría la lógica para subir a un servidor)
        function simulateUpload(file, content) {
            const fileId = Date.now();
            const statusElement = document.createElement('div');
            statusElement.className = 'upload-status-item';
            statusElement.innerHTML = `
                <div style="display: flex; align-items: center; justify-content: space-between; padding: 10px; background: #f0f0f0; border-radius: 10px; margin-bottom: 10px;">
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <i class="fas fa-file" style="color: var(--primary-color);"></i>
                        <span>${file.name}</span>
                    </div>
                    <span class="upload-progress">Subiendo...</span>
                </div>
            `;
            
            uploadStatus.appendChild(statusElement);
            
            // Simular progreso de subida
            setTimeout(() => {
                const progressElement = statusElement.querySelector('.upload-progress');
                progressElement.innerHTML = '<i class="fas fa-check" style="color: green;"></i> Subido exitosamente';
                progressElement.style.color = 'green';
                
                // Agregar a la galería correspondiente según el tipo
                if (file.type.startsWith('image/')) {
                    addNewPhoto(content, `Foto subida el ${new Date().toLocaleDateString()}`);
                } else if (file.type.startsWith('audio/')) {
                    addNewSong(content, file.name.replace(/\.[^/.]+$/, ""), "Subido por ti");
                }
            }, 1500);
        }

        // Mostrar área de texto para historias
        function showStoryTextArea() {
            uploadStatus.innerHTML = `
                <div style="margin-top: 30px; text-align: left;">
                    <h4 style="color: var(--secondary-color); margin-bottom: 15px;">Escribe tu historia:</h4>
                    <input type="text" id="storyTitle" placeholder="Título de la historia" style="width: 100%; padding: 12px; border: 2px solid #ddd; border-radius: 10px; margin-bottom: 15px;">
                    <textarea id="storyContent" placeholder="Comparte tu historia especial..." style="width: 100%; height: 200px; padding: 15px; border: 2px solid #ddd; border-radius: 10px; margin-bottom: 15px; resize: vertical;"></textarea>
                    <button id="saveStoryBtn" class="upload-btn" style="margin-top: 0;">
                        <i class="fas fa-save"></i> Guardar Historia
                    </button>
                </div>
            `;
            
            document.getElementById('saveStoryBtn').addEventListener('click', saveStory);
        }

        // Guardar nueva historia
        function saveStory() {
            const title = document.getElementById('storyTitle').value;
            const content = document.getElementById('storyContent').value;
            
            if (!title || !content) {
                alert('Por favor, completa el título y el contenido de la historia');
                return;
            }
            
            // Agregar la nueva historia
            const newStory = {
                id: albumData.stories.length + 1,
                title: title,
                date: new Date().toLocaleDateString('es-ES', { day: 'numeric', month: 'long', year: 'numeric' }),
                content: content,
                image: "https://images.unsplash.com/photo-1513475382585-d06e58bcb0e0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80"
            };
            
            albumData.stories.unshift(newStory);
            loadStories();
            
            uploadStatus.innerHTML = `<p style="color: green; margin-top: 20px;"><i class="fas fa-check-circle"></i> ¡Historia guardada exitosamente!</p>`;
            
            // Cambiar a la sección de historias
            document.querySelector('[data-section="historias"]').click();
        }

        // Agregar nueva foto
        function addNewPhoto(src, caption) {
            const newPhoto = {
                id: albumData.photos.length + 1,
                src: src,
                caption: caption
            };
            
            albumData.photos.unshift(newPhoto);
            loadPhotos();
        }

        // Agregar nueva canción
        function addNewSong(src, title, artist) {
            const newSong = {
                id: albumData.songs.length + 1,
                title: title,
                artist: artist,
                src: src
            };
            
            albumData.songs.unshift(newSong);
            loadSongs();
        }

        // Configurar reproductor de música
        function setupMusicPlayer() {
            // Reproducir primera canción por defecto
            if (albumData.songs.length > 0) {
                audioPlayer.src = albumData.songs[0].src;
                currentSongElement.textContent = `${albumData.songs[0].title} - ${albumData.songs[0].artist}`;
            }
        }

        // Reproducir canción seleccionada
        function playSong(song, element) {
            // Actualizar elemento activo
            document.querySelectorAll('.song-item').forEach(item => {
                item.classList.remove('active');
            });
            element.classList.add('active');
            
            // Actualizar reproductor
            audioPlayer.src = song.src;
            currentSongElement.textContent = `${song.title} - ${song.artist}`;
            audioPlayer.play();
        }

        // Configurar modal de imágenes
        function setupImageModal() {
            modalClose.addEventListener('click', function() {
                imageModal.style.display = 'none';
            });
            
            imageModal.addEventListener('click', function(e) {
                if (e.target === imageModal) {
                    imageModal.style.display = 'none';
                }
            });
        }

        // Abrir modal con imagen
        function openImageModal(src, caption) {
            modalImage.src = src;
            modalImage.alt = caption;
            imageModal.style.display = 'flex';
        }
    </script>
</body>
</html>
