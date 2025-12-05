<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Álbum Digital de Jorge y Pauline</title>
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
            font-size: 1.8rem;
            font-weight: 300;
            letter-spacing: 3px;
            margin-bottom: 20px;
            font-family: 'Brush Script MT', cursive;
        }
        
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
        
        .delete-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: rgba(255, 0, 0, 0.7);
            color: white;
            border: none;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            cursor: pointer;
            display: none;
        }
        
        .photo-item:hover .delete-btn {
            display: block;
        }
        
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
            position: relative;
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
            position: relative;
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
        
        .config-section {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: var(--shadow);
            margin-top: 40px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .config-section h3 {
            color: var(--secondary-color);
            margin-bottom: 20px;
            text-align: center;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #555;
        }
        
        .form-group input, .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }
        
        .form-group input:focus, .form-group textarea:focus {
            border-color: var(--primary-color);
            outline: none;
        }
        
        .backup-options {
            display: flex;
            gap: 15px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        
        .backup-btn {
            flex: 1;
            min-width: 150px;
            padding: 12px;
            border: none;
            border-radius: 10px;
            background: #f0f0f0;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .backup-btn:hover {
            background: #e0e0e0;
            transform: translateY(-3px);
        }
        
        .export-btn {
            background: var(--secondary-color);
            color: white;
        }
        
        .import-btn {
            background: var(--accent-color);
            color: white;
        }
        
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
            
            .backup-options {
                flex-direction: column;
            }
        }
        
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
        
        .alert {
            padding: 15px;
            border-radius: 10px;
            margin: 15px 0;
            display: none;
        }
        
        .alert.success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
            display: block;
        }
        
        .alert.error {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
            display: block;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="logo">
                <i class="fas fa-heart"></i>
                <h1>Álbum Digital de Jorge y Pauline</h1>
                <i class="fas fa-heart"></i>
            </div>
            <div class="couple-name">Jorge ❤️ Pauline</div>
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
                    <i class="fas fa-cloud-upload-alt"></i> Subir
                </button>
                <button class="nav-btn" data-section="configuracion">
                    <i class="fas fa-cog"></i> Configuración
                </button>
            </nav>
        </div>
    </header>
    
    <main class="container">
        <!-- Sección de Fotos -->
        <section id="fotos" class="section active">
            <h2 class="section-title">Nuestros Momentos</h2>
            <div class="alert" id="photoAlert"></div>
            <div class="gallery" id="photoGallery">
                <!-- Las fotos se cargarán aquí dinámicamente -->
            </div>
        </section>
        
        <!-- Sección de Música -->
        <section id="musica" class="section">
            <h2 class="section-title">Nuestra Banda Sonora</h2>
            <div class="alert" id="musicAlert"></div>
            <div class="music-player">
                <div class="now-playing">
                    <h3>Reproduciendo ahora: <span id="currentSong">Selecciona una canción</span></h3>
                    <div class="audio-controls">
                        <audio id="audioPlayer" controls>
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
            <div class="alert" id="storyAlert"></div>
            <div class="stories-container" id="storiesContainer">
                <!-- Las historias se cargarán aquí dinámicamente -->
            </div>
        </section>
        
        <!-- Sección de Subir Contenido -->
        <section id="subir" class="section">
            <h2 class="section-title">Comparte un Recuerdo</h2>
            <div class="upload-area">
                <h3>Sube fotos, canciones o historias a nuestro álbum</h3>
                <p>Todos los archivos se guardarán localmente en tu navegador</p>
                
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
                    <p class="file-types">Soporta: JPG, PNG, MP3, WAV</p>
                    <input type="file" id="fileInput" multiple style="display: none;" accept="image/*,audio/*">
                    <button class="upload-btn" id="browseBtn">
                        <i class="fas fa-folder-open"></i> Buscar Archivos
                    </button>
                </div>
                
                <div id="uploadStatus"></div>
            </div>
        </section>
        
        <!-- Sección de Configuración -->
        <section id="configuracion" class="section">
            <h2 class="section-title">Configuración y Respaldo</h2>
            <div class="config-section">
                <h3><i class="fas fa-database"></i> Gestión de Datos</h3>
                <div class="alert" id="configAlert"></div>
                
                <div class="form-group">
                    <label for="storageInfo">Espacio utilizado:</label>
                    <input type="text" id="storageInfo" readonly>
                </div>
                
                <div class="form-group">
                    <label for="cloudinaryConfig">Configuración Cloudinary (Opcional):</label>
                    <input type="text" id="cloudinaryConfig" placeholder="cloudinary://API_KEY:API_SECRET@CLOUD_NAME">
                    <small>Configura Cloudinary para almacenamiento en la nube (gratuito hasta 25GB)</small>
                </div>
                
                <div class="backup-options">
                    <button class="backup-btn export-btn" id="exportBtn">
                        <i class="fas fa-download"></i> Exportar Datos
                    </button>
                    <button class="backup-btn import-btn" id="importBtn">
                        <i class="fas fa-upload"></i> Importar Datos
                    </button>
                    <button class="backup-btn" id="clearBtn" style="background: #ff6b8b; color: white;">
                        <i class="fas fa-trash"></i> Limpiar Todo
                    </button>
                </div>
                
                <div class="form-group" style="margin-top: 30px;">
                    <h4><i class="fas fa-info-circle"></i> Instrucciones para respaldo:</h4>
                    <ol style="text-align: left; margin-top: 10px; padding-left: 20px;">
                        <li>Exporta tus datos regularmente haciendo clic en "Exportar Datos"</li>
                        <li>Guarda el archivo JSON en un lugar seguro</li>
                        <li>Para restaurar, usa "Importar Datos" y selecciona el archivo</li>
                        <li>Opcional: Configura Cloudinary para almacenar imágenes/audio en la nube</li>
                    </ol>
                </div>
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
            <p>Hecho con <span class="heart"><i class="fas fa-heart"></i></span> para Jorge y Pauline</p>
            <p>© <span id="currentYear"></span> - Álbum Digital - Los datos se guardan en tu navegador</p>
        </div>
    </footer>

    <script>
        // Sistema de almacenamiento persistente para GitHub Pages
        class AlbumStorage {
            constructor() {
                this.STORAGE_KEYS = {
                    PHOTOS: 'jorgePauline_photos',
                    SONGS: 'jorgePauline_songs',
                    STORIES: 'jorgePauline_stories',
                    SETTINGS: 'jorgePauline_settings'
                };
                
                this.init();
            }
            
            init() {
                // Inicializar datos si no existen
                if (!this.getPhotos().length) {
                    this.saveDefaultData();
                }
            }
            
            saveDefaultData() {
                const defaultPhotos = [
                    { 
                        id: this.generateId(),
                        src: "https://images.unsplash.com/photo-1518568814500-bf0f8d125f46?ixlib=rb-4.0.3&auto=format&fit=crop&w=687&q=80",
                        caption: "Nuestro primer viaje juntos",
                        date: new Date().toISOString(),
                        uploadedBy: "Jorge"
                    },
                    { 
                        id: this.generateId(),
                        src: "https://images.unsplash.com/photo-1529254479751-fbacb4c7a587?ixlib=rb-4.0.3&auto=format&fit=crop&w=1170&q=80",
                        caption: "Celebrando nuestro aniversario",
                        date: new Date().toISOString(),
                        uploadedBy: "Pauline"
                    }
                ];
                
                const defaultSongs = [
                    {
                        id: this.generateId(),
                        title: "Nuestra Canción Especial",
                        artist: "Artista Favorito",
                        src: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3",
                        date: new Date().toISOString(),
                        uploadedBy: "Jorge"
                    }
                ];
                
                const defaultStories = [
                    {
                        id: this.generateId(),
                        title: "Cómo nos conocimos",
                        content: "Jorge y Pauline se conocieron en una cafetería un día lluvioso. Fue amor a primera vista.",
                        date: new Date().toISOString(),
                        uploadedBy: "Ambos"
                    }
                ];
                
                localStorage.setItem(this.STORAGE_KEYS.PHOTOS, JSON.stringify(defaultPhotos));
                localStorage.setItem(this.STORAGE_KEYS.SONGS, JSON.stringify(defaultSongs));
                localStorage.setItem(this.STORAGE_KEYS.STORIES, JSON.stringify(defaultStories));
            }
            
            // Métodos para fotos
            getPhotos() {
                return JSON.parse(localStorage.getItem(this.STORAGE_KEYS.PHOTOS) || '[]');
            }
            
            savePhoto(photo) {
                const photos = this.getPhotos();
                photos.unshift(photo);
                localStorage.setItem(this.STORAGE_KEYS.PHOTOS, JSON.stringify(photos));
                return photo;
            }
            
            deletePhoto(id) {
                const photos = this.getPhotos().filter(photo => photo.id !== id);
                localStorage.setItem(this.STORAGE_KEYS.PHOTOS, JSON.stringify(photos));
                return photos;
            }
            
            // Métodos para canciones
            getSongs() {
                return JSON.parse(localStorage.getItem(this.STORAGE_KEYS.SONGS) || '[]');
            }
            
            saveSong(song) {
                const songs = this.getSongs();
                songs.unshift(song);
                localStorage.setItem(this.STORAGE_KEYS.SONGS, JSON.stringify(songs));
                return song;
            }
            
            deleteSong(id) {
                const songs = this.getSongs().filter(song => song.id !== id);
                localStorage.setItem(this.STORAGE_KEYS.SONGS, JSON.stringify(songs));
                return songs;
            }
            
            // Métodos para historias
            getStories() {
                return JSON.parse(localStorage.getItem(this.STORAGE_KEYS.STORIES) || '[]');
            }
            
            saveStory(story) {
                const stories = this.getStories();
                stories.unshift(story);
                localStorage.setItem(this.STORAGE_KEYS.STORIES, JSON.stringify(stories));
                return story;
            }
            
            deleteStory(id) {
                const stories = this.getStories().filter(story => story.id !== id);
                localStorage.setItem(this.STORAGE_KEYS.STORIES, JSON.stringify(stories));
                return stories;
            }
            
            // Métodos generales
            generateId() {
                return Date.now().toString(36) + Math.random().toString(36).substr(2);
            }
            
            exportData() {
                const data = {
                    photos: this.getPhotos(),
                    songs: this.getSongs(),
                    stories: this.getStories(),
                    exportDate: new Date().toISOString(),
                    couple: "Jorge y Pauline"
                };
                
                return JSON.stringify(data, null, 2);
            }
            
            importData(jsonString) {
                try {
                    const data = JSON.parse(jsonString);
                    
                    if (data.photos) localStorage.setItem(this.STORAGE_KEYS.PHOTOS, JSON.stringify(data.photos));
                    if (data.songs) localStorage.setItem(this.STORAGE_KEYS.SONGS, JSON.stringify(data.songs));
                    if (data.stories) localStorage.setItem(this.STORAGE_KEYS.STORIES, JSON.stringify(data.stories));
                    
                    return true;
                } catch (error) {
                    console.error('Error importing data:', error);
                    return false;
                }
            }
            
            clearAll() {
                localStorage.removeItem(this.STORAGE_KEYS.PHOTOS);
                localStorage.removeItem(this.STORAGE_KEYS.SONGS);
                localStorage.removeItem(this.STORAGE_KEYS.STORIES);
                this.saveDefaultData();
                return true;
            }
            
            getStorageInfo() {
                let totalSize = 0;
                
                [this.STORAGE_KEYS.PHOTOS, this.STORAGE_KEYS.SONGS, this.STORAGE_KEYS.STORIES].forEach(key => {
                    const data = localStorage.getItem(key);
                    if (data) {
                        totalSize += new Blob([data]).size;
                    }
                });
                
                return {
                    photos: this.getPhotos().length,
                    songs: this.getSongs().length,
                    stories: this.getStories().length,
                    size: this.formatBytes(totalSize)
                };
            }
            
            formatBytes(bytes, decimals = 2) {
                if (bytes === 0) return '0 Bytes';
                
                const k = 1024;
                const dm = decimals < 0 ? 0 : decimals;
                const sizes = ['Bytes', 'KB', 'MB', 'GB'];
                
                const i = Math.floor(Math.log(bytes) / Math.log(k));
                
                return parseFloat((bytes / Math.pow(k, i)).toFixed(dm)) + ' ' + sizes[i];
            }
        }

        // Aplicación principal
        class AlbumApp {
            constructor() {
                this.storage = new AlbumStorage();
                this.currentUser = "Jorge"; // Puedes cambiar esto según quién esté subiendo
                
                // Elementos del DOM
                this.elements = {
                    sections: document.querySelectorAll('.section'),
                    navButtons: document.querySelectorAll('.nav-btn'),
                    photoGallery: document.getElementById('photoGallery'),
                    songList: document.getElementById('songList'),
                    storiesContainer: document.getElementById('storiesContainer'),
                    uploadBox: document.getElementById('uploadBox'),
                    fileInput: document.getElementById('fileInput'),
                    browseBtn: document.getElementById('browseBtn'),
                    uploadStatus: document.getElementById('uploadStatus'),
                    audioPlayer: document.getElementById('audioPlayer'),
                    currentSongElement: document.getElementById('currentSong'),
                    imageModal: document.getElementById('imageModal'),
                    modalImage: document.getElementById('modalImage'),
                    modalClose: document.getElementById('modalClose'),
                    uploadOptions: document.querySelectorAll('.upload-option'),
                    exportBtn: document.getElementById('exportBtn'),
                    importBtn: document.getElementById('importBtn'),
                    clearBtn: document.getElementById('clearBtn'),
                    storageInfo: document.getElementById('storageInfo'),
                    configAlert: document.getElementById('configAlert'),
                    photoAlert: document.getElementById('photoAlert'),
                    musicAlert: document.getElementById('musicAlert'),
                    storyAlert: document.getElementById('storyAlert')
                };
                
                this.init();
            }
            
            init() {
                // Establecer año actual
                document.getElementById('currentYear').textContent = new Date().getFullYear();
                
                // Cargar datos
                this.loadPhotos();
                this.loadSongs();
                this.loadStories();
                this.updateStorageInfo();
                
                // Configurar eventos
                this.setupNavigation();
                this.setupUploadArea();
                this.setupMusicPlayer();
                this.setupImageModal();
                this.setupBackupButtons();
                
                // Mostrar mensaje de bienvenida
                this.showAlert(this.elements.photoAlert, '¡Bienvenidos Jorge y Pauline! Todos los archivos se guardarán en tu navegador.', 'success');
            }
            
            setupNavigation() {
                this.elements.navButtons.forEach(button => {
                    button.addEventListener('click', () => {
                        const targetSection = button.getAttribute('data-section');
                        
                        // Actualizar botones activos
                        this.elements.navButtons.forEach(btn => btn.classList.remove('active'));
                        button.classList.add('active');
                        
                        // Mostrar sección correspondiente
                        this.elements.sections.forEach(section => {
                            section.classList.remove('active');
                            if (section.id === targetSection) {
                                section.classList.add('active');
                                
                                // Actualizar información de almacenamiento en configuración
                                if (targetSection === 'configuracion') {
                                    this.updateStorageInfo();
                                }
                            }
                        });
                    });
                });
            }
            
            loadPhotos() {
                const photos = this.storage.getPhotos();
                this.elements.photoGallery.innerHTML = '';
                
                if (photos.length === 0) {
                    this.elements.photoGallery.innerHTML = `
                        <div style="grid-column: 1 / -1; text-align: center; padding: 40px;">
                            <i class="fas fa-images" style="font-size: 3rem; color: #ccc; margin-bottom: 15px;"></i>
                            <h3 style="color: #666;">No hay fotos aún</h3>
                            <p>Sube tu primera foto haciendo clic en la sección "Subir"</p>
                        </div>
                    `;
                    return;
                }
                
                photos.forEach(photo => {
                    const photoElement = this.createPhotoElement(photo);
                    this.elements.photoGallery.appendChild(photoElement);
                });
            }
            
            createPhotoElement(photo) {
                const div = document.createElement('div');
                div.className = 'photo-item';
                div.innerHTML = `
                    <img src="${photo.src}" alt="${photo.caption}" data-id="${photo.id}">
                    <div class="photo-caption">
                        <p>${photo.caption}</p>
                        <small>Subido por ${photo.uploadedBy} • ${new Date(photo.date).toLocaleDateString()}</small>
                    </div>
                    <button class="delete-btn" data-id="${photo.id}" title="Eliminar foto">
                        <i class="fas fa-times"></i>
                    </button>
                `;
                
                // Evento para abrir imagen en modal
                div.querySelector('img').addEventListener('click', () => {
                    this.openImageModal(photo.src, photo.caption);
                });
                
                // Evento para eliminar foto
                div.querySelector('.delete-btn').addEventListener('click', (e) => {
                    e.stopPropagation();
                    if (confirm('¿Estás seguro de que quieres eliminar esta foto?')) {
                        this.deletePhoto(photo.id);
                    }
                });
                
                return div;
            }
            
            loadSongs() {
                const songs = this.storage.getSongs();
                this.elements.songList.innerHTML = '';
                
                if (songs.length === 0) {
                    this.elements.songList.innerHTML = `
                        <div style="text-align: center; padding: 30px; color: #666;">
                            <i class="fas fa-music" style="font-size: 2.5rem; margin-bottom: 15px; opacity: 0.5;"></i>
                            <p>No hay canciones aún</p>
                        </div>
                    `;
                    return;
                }
                
                songs.forEach((song, index) => {
                    const songElement = this.createSongElement(song, index === 0);
                    this.elements.songList.appendChild(songElement);
                });
                
                // Configurar primera canción para reproducción
                if (songs.length > 0) {
                    this.setCurrentSong(songs[0]);
                }
            }
            
            createSongElement(song, isActive = false) {
                const div = document.createElement('div');
                div.className = `song-item ${isActive ? 'active' : ''}`;
                div.innerHTML = `
                    <i class="fas fa-music"></i>
                    <div class="song-info">
                        <div class="song-title">${song.title}</div>
                        <div class="song-artist">${song.artist}</div>
                        <small>Subido por ${song.uploadedBy} • ${new Date(song.date).toLocaleDateString()}</small>
                    </div>
                    <i class="fas fa-play"></i>
                    <button class="delete-btn" data-id="${song.id}" title="Eliminar canción" style="position: absolute; right: 10px; top: 10px; background: rgba(255,0,0,0.7);">
                        <i class="fas fa-times"></i>
                    </button>
                `;
                
                div.addEventListener('click', (e) => {
                    if (!e.target.classList.contains('delete-btn')) {
                        this.playSong(song, div);
                    }
                });
                
                div.querySelector('.delete-btn').addEventListener('click', (e) => {
                    e.stopPropagation();
                    if (confirm('¿Estás seguro de que quieres eliminar esta canción?')) {
                        this.deleteSong(song.id);
                    }
                });
                
                return div;
            }
            
            loadStories() {
                const stories = this.storage.getStories();
                this.elements.storiesContainer.innerHTML = '';
                
                if (stories.length === 0) {
                    this.elements.storiesContainer.innerHTML = `
                        <div style="grid-column: 1 / -1; text-align: center; padding: 40px;">
                            <i class="fas fa-book-open" style="font-size: 3rem; color: #ccc; margin-bottom: 15px;"></i>
                            <h3 style="color: #666;">No hay historias aún</h3>
                            <p>Escribe tu primera historia en la sección "Subir"</p>
                        </div>
                    `;
                    return;
                }
                
                stories.forEach(story => {
                    const storyElement = this.createStoryElement(story);
                    this.elements.storiesContainer.appendChild(storyElement);
                });
            }
            
            createStoryElement(story) {
                const div = document.createElement('div');
                div.className = 'story-card';
                div.innerHTML = `
                    <div class="story-content">
                        <h3>${story.title}</h3>
                        <span class="story-date">
                            <i class="far fa-calendar"></i> ${new Date(story.date).toLocaleDateString()} • 
                            Subido por ${story.uploadedBy}
                        </span>
                        <p class="story-text">${story.content}</p>
                        <button class="delete-btn" data-id="${story.id}" style="margin-top: 15px; background: rgba(255,0,0,0.7); color: white; border: none; padding: 8px 15px; border-radius: 5px; cursor: pointer;">
                            <i class="fas fa-trash"></i> Eliminar historia
                        </button>
                    </div>
                `;
                
                div.querySelector('.delete-btn').addEventListener('click', () => {
                    if (confirm('¿Estás seguro de que quieres eliminar esta historia?')) {
                        this.deleteStory(story.id);
                    }
                });
                
                return div;
            }
            
            setupUploadArea() {
                // Abrir selector de archivos
                this.elements.browseBtn.addEventListener('click', () => this.elements.fileInput.click());
                this.elements.uploadBox.addEventListener('click', () => this.elements.fileInput.click());
                
                // Manejar selección de archivos
                this.elements.fileInput.addEventListener('change', (e) => this.handleFileSelect(e));
                
                // Configurar drag and drop
                this.elements.uploadBox.addEventListener('dragover', (e) => {
                    e.preventDefault();
                    this.elements.uploadBox.classList.add('dragover');
                });
                
                this.elements.uploadBox.addEventListener('dragleave', () => {
                    this.elements.uploadBox.classList.remove('dragover');
                });
                
                this.elements.uploadBox.addEventListener('drop', (e) => {
                    e.preventDefault();
                    this.elements.uploadBox.classList.remove('dragover');
                    
                    if (e.dataTransfer.files.length) {
                        this.handleFiles(e.dataTransfer.files);
                    }
                });
                
                // Configurar opciones de subida
                this.elements.uploadOptions.forEach(option => {
                    option.addEventListener('click', () => {
                        const type = option.getAttribute('data-type');
                        
                        if (type === 'story') {
                            this.showStoryForm();
                        } else {
                            let message = type === 'photo' 
                                ? 'Selecciona una foto para subir' 
                                : 'Selecciona una canción para subir';
                            
                            this.showAlert(this.elements.uploadStatus, message, 'success');
                            this.elements.fileInput.accept = type === 'photo' ? 'image/*' : 'audio/*';
                            this.elements.fileInput.click();
                        }
                    });
                });
            }
            
            handleFileSelect(e) {
                const files = Array.from(e.target.files);
                if (files.length === 0) return;
                
                this.handleFiles(files);
            }
            
            async handleFiles(files) {
                this.elements.uploadStatus.innerHTML = '';
                
                for (const file of files.slice(0, 5)) { // Limitar a 5 archivos
                    await this.processFile(file);
                }
                
                this.elements.fileInput.value = ''; // Resetear input
            }
            
            async processFile(file) {
                return new Promise((resolve) => {
                    const reader = new FileReader();
                    
                    reader.onload = (e) => {
                        if (file.type.startsWith('image/')) {
                            this.savePhotoFromFile(file, e.target.result);
                        } else if (file.type.startsWith('audio/')) {
                            this.saveSongFromFile(file, e.target.result);
                        }
                        resolve();
                    };
                    
                    if (file.type.startsWith('image/') || file.type.startsWith('audio/')) {
                        reader.readAsDataURL(file);
                    } else {
                        reader.readAsText(file);
                        resolve();
                    }
                });
            }
            
            savePhotoFromFile(file, dataUrl) {
                const photo = {
                    id: this.storage.generateId(),
                    src: dataUrl,
                    caption: `Foto subida por ${this.currentUser}`,
                    date: new Date().toISOString(),
                    uploadedBy: this.currentUser,
                    fileName: file.name,
                    fileSize: file.size
                };
                
                this.storage.savePhoto(photo);
                this.loadPhotos();
                this.updateStorageInfo();
                
                this.showAlert(this.elements.uploadStatus, 
                    `✅ Foto "${file.name}" subida exitosamente`, 'success');
                this.showAlert(this.elements.photoAlert, 
                    `Nueva foto añadida por ${this.currentUser}`, 'success');
                
                // Cambiar a sección de fotos después de 2 segundos
                setTimeout(() => {
                    document.querySelector('[data-section="fotos"]').click();
                }, 2000);
            }
            
            saveSongFromFile(file, dataUrl) {
                const song = {
                    id: this.storage.generateId(),
                    title: file.name.replace(/\.[^/.]+$/, ""), // Remover extensión
                    artist: this.currentUser,
                    src: dataUrl,
                    date: new Date().toISOString(),
                    uploadedBy: this.currentUser,
                    fileName: file.name,
                    fileSize: file.size
                };
                
                this.storage.saveSong(song);
                this.loadSongs();
                this.updateStorageInfo();
                
                this.showAlert(this.elements.uploadStatus, 
                    `✅ Canción "${song.title}" subida exitosamente`, 'success');
                this.showAlert(this.elements.musicAlert, 
                    `Nueva canción añadida por ${this.currentUser}`, 'success');
            }
            
            showStoryForm() {
                this.elements.uploadStatus.innerHTML = `
                    <div style="margin-top: 30px; text-align: left; background: #f9f9f9; padding: 25px; border-radius: 15px;">
                        <h4 style="color: var(--secondary-color); margin-bottom: 15px;">
                            <i class="fas fa-book"></i> Escribe una nueva historia
                        </h4>
                        <div class="form-group">
                            <label for="storyTitle">Título:</label>
                            <input type="text" id="storyTitle" placeholder="Ej: Nuestro primer viaje">
                        </div>
                        <div class="form-group">
                            <label for="storyContent">Historia:</label>
                            <textarea id="storyContent" rows="5" placeholder="Comparte tu historia especial..."></textarea>
                        </div>
                        <div class="form-group">
                            <label for="storyAuthor">Subido por:</label>
                            <select id="storyAuthor" style="width: 100%; padding: 12px; border: 2px solid #ddd; border-radius: 10px;">
                                <option value="Jorge">Jorge</option>
                                <option value="Pauline">Pauline</option>
                                <option value="Ambos">Ambos</option>
                            </select>
                        </div>
                        <button id="saveStoryBtn" class="upload-btn" style="margin-top: 10px;">
                            <i class="fas fa-save"></i> Guardar Historia
                        </button>
                    </div>
                `;
                
                document.getElementById('saveStoryBtn').addEventListener('click', () => this.saveStory());
            }
            
            saveStory() {
                const title = document.getElementById('storyTitle').value;
                const content = document.getElementById('storyContent').value;
                const author = document.getElementById('storyAuthor').value;
                
                if (!title.trim() || !content.trim()) {
                    alert('Por favor, completa el título y el contenido de la historia');
                    return;
                }
                
                const story = {
                    id: this.storage.generateId(),
                    title: title,
                    content: content,
                    date: new Date().toISOString(),
                    uploadedBy: author
                };
                
                this.storage.saveStory(story);
                this.loadStories();
                this.updateStorageInfo();
                
                this.showAlert(this.elements.uploadStatus, 
                    `✅ Historia "${title}" guardada exitosamente`, 'success');
                this.showAlert(this.elements.storyAlert, 
                    `Nueva historia añadida por ${author}`, 'success');
                
                // Cambiar a sección de historias después de 2 segundos
                setTimeout(() => {
                    document.querySelector('[data-section="historias"]').click();
                }, 2000);
            }
            
            deletePhoto(id) {
                this.storage.deletePhoto(id);
                this.loadPhotos();
                this.updateStorageInfo();
                this.showAlert(this.elements.photoAlert, 'Foto eliminada exitosamente', 'success');
            }
            
            deleteSong(id) {
                this.storage.deleteSong(id);
                this.loadSongs();
                this.updateStorageInfo();
                this.showAlert(this.elements.musicAlert, 'Canción eliminada exitosamente', 'success');
            }
            
            deleteStory(id) {
                this.storage.deleteStory(id);
                this.loadStories();
                this.updateStorageInfo();
                this.showAlert(this.elements.storyAlert, 'Historia eliminada exitosamente', 'success');
            }
            
            setupMusicPlayer() {
                // Configurar eventos del reproductor
                this.elements.audioPlayer.addEventListener('ended', () => {
                    // Avanzar a la siguiente canción
                    const songs = this.storage.getSongs();
                    const currentIndex = songs.findIndex(song => 
                        song.src === this.elements.audioPlayer.src);
                    
                    if (currentIndex < songs.length - 1) {
                        this.playSong(songs[currentIndex + 1]);
                    }
                });
            }
            
            setCurrentSong(song) {
                this.elements.audioPlayer.src = song.src;
                this.elements.currentSongElement.textContent = `${song.title} - ${song.artist}`;
            }
            
            playSong(song, element = null) {
                this.setCurrentSong(song);
                this.elements.audioPlayer.play();
                
                // Actualizar elemento activo
                document.querySelectorAll('.song-item').forEach(item => {
                    item.classList.remove('active');
                });
                
                if (element) {
                    element.classList.add('active');
                }
            }
            
            setupImageModal() {
                this.elements.modalClose.addEventListener('click', () => {
                    this.elements.imageModal.style.display = 'none';
                });
                
                this.elements.imageModal.addEventListener('click', (e) => {
                    if (e.target === this.elements.imageModal) {
                        this.elements.imageModal.style.display = 'none';
                    }
                });
            }
            
            openImageModal(src, caption) {
                this.elements.modalImage.src = src;
                this.elements.modalImage.alt = caption;
                this.elements.imageModal.style.display = 'flex';
            }
            
            setupBackupButtons() {
                // Exportar datos
                this.elements.exportBtn.addEventListener('click', () => {
                    const data = this.storage.exportData();
                    const blob = new Blob([data], { type: 'application/json' });
                    const url = URL.createObjectURL(blob);
                    
                    const a = document.createElement('a');
                    a.href = url;
                    a.download = `album-jorge-pauline-${new Date().toISOString().split('T')[0]}.json`;
                    document.body.appendChild(a);
                    a.click();
                    document.body.removeChild(a);
                    URL.revokeObjectURL(url);
                    
                    this.showAlert(this.elements.configAlert, 'Datos exportados exitosamente', 'success');
                });
                
                // Importar datos
                this.elements.importBtn.addEventListener('click', () => {
                    const input = document.createElement('input');
                    input.type = 'file';
                    input.accept = '.json';
                    
                    input.onchange = (e) => {
                        const file = e.target.files[0];
                        const reader = new FileReader();
                        
                        reader.onload = (e) => {
                            const success = this.storage.importData(e.target.result);
                            
                            if (success) {
                                this.loadPhotos();
                                this.loadSongs();
                                this.loadStories();
                                this.updateStorageInfo();
                                this.showAlert(this.elements.configAlert, 'Datos importados exitosamente', 'success');
                            } else {
                                this.showAlert(this.elements.configAlert, 'Error al importar datos', 'error');
                            }
                        };
                        
                        reader.readAsText(file);
                    };
                    
                    input.click();
                });
                
                // Limpiar todo
                this.elements.clearBtn.addEventListener('click', () => {
                    if (confirm('¿ESTÁS SEGURO? Esto eliminará todas las fotos, canciones e historias y restaurará los datos por defecto.')) {
                        this.storage.clearAll();
                        this.loadPhotos();
                        this.loadSongs();
                        this.loadStories();
                        this.updateStorageInfo();
                        this.showAlert(this.elements.configAlert, 'Todos los datos han sido restablecidos', 'success');
                    }
                });
            }
            
            updateStorageInfo() {
                const info = this.storage.getStorageInfo();
                this.elements.storageInfo.value = 
                    `${info.photos} fotos, ${info.songs} canciones, ${info.stories} historias (${info.size})`;
            }
            
            showAlert(element, message, type) {
                element.textContent = message;
                element.className = `alert ${type}`;
                
                // Ocultar alerta después de 5 segundos
                setTimeout(() => {
                    element.style.display = 'none';
                }, 5000);
            }
        }

        // Inicializar la aplicación cuando se carga la página
        document.addEventListener('DOMContentLoaded', () => {
            window.albumApp = new AlbumApp();
        });
    </script>
</body>
</html>
