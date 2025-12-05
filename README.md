<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🤘 Rock Album | Jorge & Pauline 🎸</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&family=Rock+Salt&family=Bebas+Neue&family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --neon-pink: #ff00ff;
            --neon-blue: #00ffff;
            --neon-green: #00ff00;
            --neon-yellow: #ffff00;
            --rock-black: #0a0a0a;
            --rock-gray: #1a1a1a;
            --rock-red: #ff0033;
            --rock-purple: #9d00ff;
            --metal-gradient: linear-gradient(135deg, #ff0033 0%, #9d00ff 50%, #00ffff 100%);
            --grunge-texture: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%23000000' fill-opacity='0.15' fill-rule='evenodd'/%3E%3C/svg%3E");
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--rock-black);
            color: white;
            min-height: 100vh;
            background-image: var(--grunge-texture);
            overflow-x: hidden;
            position: relative;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 50%, rgba(255, 0, 51, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(157, 0, 255, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 40% 80%, rgba(0, 255, 255, 0.1) 0%, transparent 50%);
            pointer-events: none;
            z-index: -1;
        }

        /* Efectos de partículas */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            z-index: -1;
            top: 0;
            left: 0;
        }

        /* Cursor personalizado */
        .cursor {
            width: 20px;
            height: 20px;
            border: 2px solid var(--neon-pink);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            transition: transform 0.2s;
            mix-blend-mode: difference;
        }

        .cursor-follower {
            width: 40px;
            height: 40px;
            background: rgba(255, 0, 255, 0.1);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9998;
            transition: all 0.3s ease-out;
            mix-blend-mode: difference;
        }

        /* Header con efecto de neón */
        header {
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 2px solid var(--neon-pink);
            box-shadow: 0 0 30px rgba(255, 0, 255, 0.3),
                        inset 0 0 30px rgba(0, 255, 255, 0.1);
            padding: 20px 0;
            position: relative;
            overflow: hidden;
        }

        header::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--metal-gradient);
            animation: scanline 2s linear infinite;
        }

        @keyframes scanline {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 30px;
        }

        .logo-area {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }

        .logo {
            font-family: 'Rock Salt', cursive;
            font-size: 4.5rem;
            background: var(--metal-gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 20px rgba(255, 0, 255, 0.5),
                         0 0 40px rgba(0, 255, 255, 0.3);
            position: relative;
            display: inline-block;
            animation: logoGlow 3s ease-in-out infinite alternate;
        }

        @keyframes logoGlow {
            0% {
                text-shadow: 0 0 20px rgba(255, 0, 255, 0.5),
                             0 0 40px rgba(0, 255, 255, 0.3);
            }
            100% {
                text-shadow: 0 0 30px rgba(255, 0, 255, 0.8),
                             0 0 60px rgba(0, 255, 255, 0.5),
                             0 0 80px rgba(255, 255, 0, 0.3);
            }
        }

        .couple-name {
            font-family: 'Bebas Neue', cursive;
            font-size: 2.8rem;
            letter-spacing: 4px;
            color: white;
            text-shadow: 0 0 10px var(--neon-blue),
                         0 0 20px var(--neon-blue);
            margin: 15px 0;
            position: relative;
        }

        .couple-name::before,
        .couple-name::after {
            content: '🎸';
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            font-size: 2rem;
            animation: guitarFloat 3s ease-in-out infinite alternate;
        }

        .couple-name::before {
            left: -50px;
        }

        .couple-name::after {
            right: -50px;
        }

        @keyframes guitarFloat {
            0% { transform: translateY(-50%) rotate(-15deg); }
            100% { transform: translateY(-50%) rotate(15deg); }
        }

        /* Navegación estilo concierto */
        nav {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-top: 30px;
            flex-wrap: wrap;
            position: relative;
        }

        .nav-btn {
            background: rgba(26, 26, 26, 0.8);
            border: 2px solid transparent;
            border-image: var(--metal-gradient);
            border-image-slice: 1;
            color: white;
            padding: 18px 35px;
            border-radius: 0;
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            font-size: 1.1rem;
            letter-spacing: 1.5px;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            text-transform: uppercase;
            min-width: 180px;
            text-align: center;
        }

        .nav-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--metal-gradient);
            transition: left 0.4s ease;
            z-index: -1;
        }

        .nav-btn:hover::before {
            left: 0;
        }

        .nav-btn:hover, .nav-btn.active {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 30px rgba(255, 0, 51, 0.4),
                        0 0 20px rgba(157, 0, 255, 0.3),
                        inset 0 0 15px rgba(255, 255, 255, 0.1);
            color: white;
            border-color: transparent;
        }

        .nav-btn i {
            margin-right: 12px;
            font-size: 1.3rem;
        }

        /* Secciones */
        .section {
            display: none;
            padding: 60px 0;
            animation: slideUp 0.6s ease-out;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section.active {
            display: block;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
            font-family: 'Bebas Neue', cursive;
            font-size: 3.5rem;
            letter-spacing: 3px;
            color: transparent;
            background: linear-gradient(90deg, var(--neon-pink), var(--neon-blue), var(--neon-yellow));
            -webkit-background-clip: text;
            background-clip: text;
            text-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 4px;
            background: var(--metal-gradient);
            border-radius: 2px;
            box-shadow: 0 0 15px var(--neon-pink);
        }

        /* Galería estilo poster de concierto */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
            perspective: 1000px;
        }

        .photo-item {
            background: rgba(26, 26, 26, 0.9);
            border: 3px solid;
            border-image: linear-gradient(45deg, var(--neon-pink), var(--neon-blue)) 1;
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            transform-style: preserve-3d;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            cursor: pointer;
            height: 350px;
        }

        .photo-item:hover {
            transform: translateY(-20px) rotateX(10deg) rotateY(-10deg);
            box-shadow: 0 25px 50px rgba(255, 0, 51, 0.3),
                        0 0 30px rgba(0, 255, 255, 0.2);
            z-index: 10;
        }

        .photo-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent 30%, rgba(255, 0, 255, 0.1) 50%, transparent 70%);
            z-index: 2;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .photo-item:hover::before {
            opacity: 1;
            animation: shine 1s ease;
        }

        @keyframes shine {
            0% { background-position: -100px; }
            100% { background-position: 300px; }
        }

        .photo-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .photo-item:hover img {
            transform: scale(1.1);
        }

        .photo-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.9));
            padding: 25px;
            transform: translateY(100%);
            transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            z-index: 3;
        }

        .photo-item:hover .photo-caption {
            transform: translateY(0);
        }

        .delete-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            background: rgba(255, 0, 51, 0.9);
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            z-index: 4;
            opacity: 0;
            transform: scale(0.8);
            transition: all 0.3s ease;
            backdrop-filter: blur(5px);
        }

        .photo-item:hover .delete-btn {
            opacity: 1;
            transform: scale(1);
        }

        .delete-btn:hover {
            background: var(--neon-pink);
            transform: scale(1.1) rotate(90deg);
            box-shadow: 0 0 20px var(--neon-pink);
        }

        /* Reproductor estilo mesa de mezclas */
        .music-player {
            background: rgba(26, 26, 26, 0.9);
            border: 3px solid;
            border-image: linear-gradient(45deg, var(--neon-blue), var(--neon-green)) 1;
            border-radius: 20px;
            padding: 40px;
            max-width: 900px;
            margin: 0 auto 60px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.7),
                        inset 0 0 30px rgba(0, 255, 255, 0.1);
        }

        .music-player::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, var(--neon-blue), transparent 30%);
            animation: rotate 10s linear infinite;
            opacity: 0.1;
        }

        @keyframes rotate {
            100% { transform: rotate(360deg); }
        }

        .now-playing {
            background: rgba(10, 10, 10, 0.9);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
            border: 2px solid var(--neon-blue);
            position: relative;
            z-index: 2;
        }

        .now-playing h3 {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--neon-blue);
            text-shadow: 0 0 10px var(--neon-blue);
        }

        #currentSong {
            color: var(--neon-green);
            font-weight: 700;
        }

        audio {
            width: 100%;
            filter: invert(1) hue-rotate(180deg) saturate(2);
            border-radius: 10px;
            background: #000;
            padding: 10px;
        }

        audio::-webkit-media-controls-panel {
            background: linear-gradient(45deg, #222, #000);
        }

        .song-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
            position: relative;
            z-index: 2;
        }

        .song-item {
            background: rgba(40, 40, 40, 0.8);
            border-left: 4px solid var(--neon-pink);
            padding: 20px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .song-item::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 0;
            background: linear-gradient(90deg, var(--neon-pink), transparent);
            transition: width 0.3s;
            z-index: 1;
        }

        .song-item:hover::before {
            width: 100%;
        }

        .song-item:hover {
            transform: translateX(10px);
            box-shadow: 0 10px 25px rgba(255, 0, 255, 0.3);
        }

        .song-item.active {
            background: linear-gradient(90deg, rgba(255, 0, 51, 0.3), rgba(157, 0, 255, 0.3));
            border-left-color: var(--neon-yellow);
            box-shadow: 0 0 20px rgba(255, 255, 0, 0.3);
        }

        .song-item.active::before {
            width: 100%;
            background: linear-gradient(90deg, var(--neon-yellow), transparent);
        }

        /* Historias estilo graffiti */
        .stories-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 40px;
        }

        .story-card {
            background: linear-gradient(145deg, #1a1a1a, #0a0a0a);
            border: 4px solid transparent;
            border-image: linear-gradient(45deg, var(--neon-yellow), var(--neon-green)) 1;
            border-radius: 0;
            padding: 0;
            overflow: hidden;
            position: relative;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            min-height: 400px;
        }

        .story-card:hover {
            transform: translateY(-15px) rotateX(5deg);
            box-shadow: 0 25px 50px rgba(255, 255, 0, 0.2),
                        0 0 40px rgba(0, 255, 0, 0.1);
        }

        .story-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, var(--neon-yellow), var(--neon-green));
            animation: borderFlow 3s linear infinite;
        }

        @keyframes borderFlow {
            0% { background-position: 0% 50%; }
            100% { background-position: 100% 50%; }
        }

        .story-content {
            padding: 30px;
            position: relative;
            z-index: 2;
        }

        .story-content h3 {
            font-family: 'Bebas Neue', cursive;
            font-size: 2.2rem;
            color: var(--neon-yellow);
            margin-bottom: 15px;
            letter-spacing: 2px;
            position: relative;
            display: inline-block;
        }

        .story-content h3::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--neon-yellow);
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .story-card:hover .story-content h3::after {
            transform: scaleX(1);
        }

        .story-date {
            display: block;
            color: var(--neon-green);
            font-family: 'Orbitron', sans-serif;
            font-size: 0.9rem;
            margin-bottom: 20px;
            text-shadow: 0 0 10px var(--neon-green);
        }

        .story-text {
            color: #ccc;
            line-height: 1.8;
            font-size: 1.1rem;
            position: relative;
            z-index: 2;
        }

        /* Área de subida estilo estudio de grabación */
        .upload-area {
            background: rgba(26, 26, 26, 0.9);
            border: 4px dashed var(--neon-pink);
            border-radius: 25px;
            padding: 60px 40px;
            text-align: center;
            margin-bottom: 60px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 20px 50px rgba(255, 0, 255, 0.1),
                        inset 0 0 40px rgba(255, 0, 255, 0.05);
        }

        .upload-area::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 0, 255, 0.1) 0%, transparent 70%);
            animation: pulse 4s ease-in-out infinite alternate;
            z-index: 1;
        }

        @keyframes pulse {
            0% { transform: scale(0.8); opacity: 0.3; }
            100% { transform: scale(1.2); opacity: 0.6; }
        }

        .upload-box {
            position: relative;
            z-index: 2;
            padding: 50px 30px;
            background: rgba(10, 10, 10, 0.8);
            border-radius: 20px;
            margin: 40px 0;
            border: 2px solid var(--neon-blue);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .upload-box:hover {
            border-color: var(--neon-yellow);
            box-shadow: 0 0 40px rgba(255, 255, 0, 0.2),
                        inset 0 0 30px rgba(255, 255, 0, 0.1);
        }

        .upload-icon {
            font-size: 5rem;
            color: var(--neon-blue);
            margin-bottom: 25px;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .upload-btn {
            background: linear-gradient(45deg, var(--neon-pink), var(--neon-blue));
            color: white;
            border: none;
            padding: 20px 50px;
            border-radius: 0;
            font-family: 'Orbitron', sans-serif;
            font-size: 1.2rem;
            font-weight: 700;
            letter-spacing: 2px;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            margin-top: 30px;
            text-transform: uppercase;
            z-index: 2;
        }

        .upload-btn::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transform: rotate(45deg);
            transition: left 0.6s;
        }

        .upload-btn:hover::after {
            left: 100%;
        }

        .upload-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 35px rgba(255, 0, 255, 0.4),
                        0 0 30px rgba(0, 255, 255, 0.3);
        }

        /* Configuración estilo panel de control */
        .config-section {
            background: linear-gradient(145deg, #1a1a1a, #0a0a0a);
            border: 3px solid;
            border-image: linear-gradient(45deg, var(--neon-green), var(--neon-blue)) 1;
            border-radius: 20px;
            padding: 40px;
            margin-top: 40px;
            position: relative;
            overflow: hidden;
        }

        .config-section::before {
            content: '⚙️';
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 3rem;
            opacity: 0.1;
            animation: spin 10s linear infinite;
        }

        @keyframes spin {
            100% { transform: rotate(360deg); }
        }

        .backup-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .backup-btn {
            background: rgba(40, 40, 40, 0.9);
            border: 2px solid;
            border-image: linear-gradient(45deg, var(--neon-pink), var(--neon-blue)) 1;
            color: white;
            padding: 25px;
            border-radius: 15px;
            font-family: 'Orbitron', sans-serif;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 15px;
            text-align: center;
        }

        .backup-btn i {
            font-size: 2.5rem;
        }

        .backup-btn:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 15px 30px rgba(255, 0, 255, 0.3);
            background: linear-gradient(45deg, rgba(255, 0, 51, 0.2), rgba(157, 0, 255, 0.2));
        }

        /* Footer estilo escenario */
        footer {
            background: linear-gradient(to top, #0a0a0a, transparent);
            padding: 50px 0 30px;
            margin-top: 80px;
            position: relative;
            border-top: 2px solid var(--neon-pink);
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent 30%, rgba(255, 0, 255, 0.05) 50%, transparent 70%);
            animation: scanline 3s linear infinite;
        }

        .heart {
            color: var(--neon-pink);
            animation: heartbeat 1.5s infinite;
            display: inline-block;
        }

        /* Modal estilo cartel de concierto */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            backdrop-filter: blur(10px);
            z-index: 10000;
            justify-content: center;
            align-items: center;
            animation: modalFadeIn 0.4s ease;
        }

        @keyframes modalFadeIn {
            from { opacity: 0; backdrop-filter: blur(0); }
            to { opacity: 1; backdrop-filter: blur(10px); }
        }

        .modal-content {
            max-width: 90%;
            max-height: 90%;
            border: 5px solid;
            border-image: linear-gradient(45deg, var(--neon-pink), var(--neon-blue), var(--neon-yellow)) 1;
            box-shadow: 0 0 60px rgba(255, 0, 255, 0.5),
                        0 0 100px rgba(0, 255, 255, 0.3),
                        inset 0 0 40px rgba(255, 255, 0, 0.2);
            animation: modalGlow 2s ease-in-out infinite alternate;
        }

        @keyframes modalGlow {
            from { box-shadow: 0 0 40px rgba(255, 0, 255, 0.5); }
            to { box-shadow: 0 0 80px rgba(255, 0, 255, 0.8),
                             0 0 120px rgba(0, 255, 255, 0.5); }
        }

        /* Responsive */
        @media (max-width: 1200px) {
            .logo { font-size: 3.5rem; }
            .nav-btn { min-width: 160px; padding: 15px 25px; }
        }

        @media (max-width: 768px) {
            .logo { font-size: 2.8rem; }
            .couple-name { font-size: 2rem; }
            .nav-btn { min-width: 140px; padding: 12px 20px; font-size: 0.9rem; }
            .section-title { font-size: 2.5rem; }
            .gallery { grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); }
            .stories-container { grid-template-columns: 1fr; }
            .backup-options { grid-template-columns: 1fr; }
            nav { gap: 15px; }
            .music-player, .upload-area, .config-section { padding: 30px 20px; }
        }

        /* Scrollbar personalizada */
        ::-webkit-scrollbar {
            width: 12px;
        }

        ::-webkit-scrollbar-track {
            background: var(--rock-black);
            border-left: 1px solid var(--neon-pink);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--metal-gradient);
            border-radius: 0;
            border: 2px solid var(--rock-black);
        }

        ::-webkit-scrollbar-thumb:hover {
            box-shadow: 0 0 20px var(--neon-pink);
        }
    </style>
</head>
<body>
    <!-- Cursor personalizado -->
    <div class="cursor"></div>
    <div class="cursor-follower"></div>

    <!-- Partículas -->
    <div id="particles-js"></div>

    <header>
        <div class="container">
            <div class="logo-area">
                <h1 class="logo">ROCK ALBUM</h1>
                <div class="couple-name">JORGE 🤘 PAULINE</div>
                <p style="color: #ccc; font-family: 'Orbitron', sans-serif; letter-spacing: 2px;">
                    NUESTRA HISTORIA EN ACORDE MAYOR
                </p>
            </div>
            
            <nav>
                <button class="nav-btn active" data-section="fotos">
                    <i class="fas fa-guitar"></i> FOTOS
                </button>
                <button class="nav-btn" data-section="musica">
                    <i class="fas fa-volume-up"></i> MÚSICA
                </button>
                <button class="nav-btn" data-section="historias">
                    <i class="fas fa-scroll"></i> HISTORIAS
                </button>
                <button class="nav-btn" data-section="subir">
                    <i class="fas fa-bolt"></i> SUBIR
                </button>
                <button class="nav-btn" data-section="configuracion">
                    <i class="fas fa-sliders-h"></i> CONFIG
                </button>
            </nav>
        </div>
    </header>
    
    <main class="container">
        <!-- Sección de Fotos -->
        <section id="fotos" class="section active">
            <h2 class="section-title">BACKSTAGE PASS</h2>
            <div class="gallery" id="photoGallery">
                <!-- Fotos se cargan dinámicamente -->
            </div>
        </section>
        
        <!-- Sección de Música -->
        <section id="musica" class="section">
            <h2 class="section-title">SETLIST</h2>
            <div class="music-player">
                <div class="now-playing">
                    <h3>NOW PLAYING: <span id="currentSong">SELECT A TRACK</span></h3>
                    <div class="audio-controls">
                        <audio id="audioPlayer" controls>
                            Your browser does not support the audio element.
                        </audio>
                    </div>
                </div>
                
                <div class="song-list" id="songList">
                    <!-- Canciones se cargan dinámicamente -->
                </div>
            </div>
        </section>
        
        <!-- Sección de Historias -->
        <section id="historias" class="section">
            <h2 class="section-title">TOUR DIARY</h2>
            <div class="stories-container" id="storiesContainer">
                <!-- Historias se cargan dinámicamente -->
            </div>
        </section>
        
        <!-- Sección de Subir -->
        <section id="subir" class="section">
            <h2 class="section-title">DROP THE BASS</h2>
            <div class="upload-area">
                <h3 style="color: var(--neon-blue); font-family: 'Orbitron', sans-serif; margin-bottom: 20px;">
                    UPLOAD TO THE MIX
                </h3>
                <p style="color: #ccc; margin-bottom: 30px; font-size: 1.1rem;">
                    Sube fotos, canciones o escribe historias. Todo se guarda localmente en tu navegador.
                </p>
                
                <div class="upload-box" id="uploadBox">
                    <i class="fas fa-cloud-upload-alt upload-icon"></i>
                    <h4 style="color: var(--neon-green); margin-bottom: 10px; font-family: 'Orbitron', sans-serif;">
                        DRAG & DROP FILES HERE
                    </h4>
                    <p style="color: #aaa; margin-bottom: 5px;">or click to select files</p>
                    <p style="color: var(--neon-yellow); font-family: 'Orbitron', sans-serif; font-size: 0.9rem;">
                        SUPPORTED: JPG, PNG, MP3, WAV
                    </p>
                    <input type="file" id="fileInput" multiple style="display: none;" accept="image/*,audio/*">
                    <button class="upload-btn" id="browseBtn">
                        <i class="fas fa-file-import"></i> BROWSE FILES
                    </button>
                </div>
                
                <div id="uploadStatus" style="position: relative; z-index: 2;"></div>
                
                <div style="margin-top: 40px; display: flex; gap: 20px; justify-content: center; flex-wrap: wrap;">
                    <div class="upload-option" data-type="photo" style="background: rgba(255,0,51,0.1); border: 2px solid var(--neon-pink);">
                        <i class="fas fa-camera-retro" style="color: var(--neon-pink);"></i>
                        <span style="color: white; font-family: 'Orbitron', sans-serif;">UPLOAD PHOTO</span>
                    </div>
                    <div class="upload-option" data-type="music" style="background: rgba(0,255,255,0.1); border: 2px solid var(--neon-blue);">
                        <i class="fas fa-compact-disc" style="color: var(--neon-blue);"></i>
                        <span style="color: white; font-family: 'Orbitron', sans-serif;">UPLOAD TRACK</span>
                    </div>
                    <div class="upload-option" data-type="story" style="background: rgba(255,255,0,0.1); border: 2px solid var(--neon-yellow);">
                        <i class="fas fa-feather-alt" style="color: var(--neon-yellow);"></i>
                        <span style="color: white; font-family: 'Orbitron', sans-serif;">WRITE STORY</span>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Sección de Configuración -->
        <section id="configuracion" class="section">
            <h2 class="section-title">CONTROL PANEL</h2>
            <div class="config-section">
                <h3 style="color: var(--neon-green); font-family: 'Orbitron', sans-serif; margin-bottom: 30px; text-align: center;">
                    <i class="fas fa-database"></i> DATA MANAGEMENT
                </h3>
                
                <div style="background: rgba(0,0,0,0.5); padding: 25px; border-radius: 15px; margin-bottom: 30px; border: 1px solid var(--neon-green);">
                    <h4 style="color: var(--neon-blue); margin-bottom: 15px; font-family: 'Orbitron', sans-serif;">
                        <i class="fas fa-chart-pie"></i> STORAGE INFO
                    </h4>
                    <input type="text" id="storageInfo" readonly 
                           style="width: 100%; padding: 15px; background: #111; border: 2px solid var(--neon-blue); 
                                  color: var(--neon-green); font-family: 'Orbitron', sans-serif; font-size: 1.1rem;
                                  text-align: center; margin-bottom: 15px;">
                    <p style="color: #aaa; font-size: 0.9rem; text-align: center;">
                        Data is stored locally in your browser. Export regularly to backup.
                    </p>
                </div>
                
                <div class="backup-options">
                    <button class="backup-btn" id="exportBtn" style="border-image: linear-gradient(45deg, var(--neon-green), var(--neon-blue)) 1;">
                        <i class="fas fa-file-export" style="color: var(--neon-green);"></i>
                        <span>EXPORT DATA</span>
                        <small style="color: #aaa; font-size: 0.8rem;">Download JSON backup</small>
                    </button>
                    
                    <button class="backup-btn" id="importBtn" style="border-image: linear-gradient(45deg, var(--neon-blue), var(--neon-pink)) 1;">
                        <i class="fas fa-file-import" style="color: var(--neon-blue);"></i>
                        <span>IMPORT DATA</span>
                        <small style="color: #aaa; font-size: 0.8rem;">Restore from JSON</small>
                    </button>
                    
                    <button class="backup-btn" id="clearBtn" style="border-image: linear-gradient(45deg, var(--neon-pink), var(--neon-yellow)) 1;">
                        <i class="fas fa-bomb" style="color: var(--neon-pink);"></i>
                        <span>FACTORY RESET</span>
                        <small style="color: #aaa; font-size: 0.8rem;">Clear all data</small>
                    </button>
                </div>
                
                <div style="margin-top: 40px; padding: 25px; background: rgba(0,0,0,0.3); border-radius: 15px; border: 1px solid var(--neon-purple);">
                    <h4 style="color: var(--neon-purple); margin-bottom: 15px; font-family: 'Orbitron', sans-serif;">
                        <i class="fas fa-cloud"></i> CLOUD SYNC (OPTIONAL)
                    </h4>
                    <input type="text" id="cloudinaryConfig" placeholder="cloudinary://api_key:api_secret@cloud_name" 
                           style="width: 100%; padding: 15px; background: #111; border: 2px solid var(--neon-purple); 
                                  color: white; margin-bottom: 15px; font-family: 'Orbitron', sans-serif;">
                    <p style="color: #aaa; font-size: 0.9rem;">
                        Configure Cloudinary for cloud storage (free up to 25GB). Leave empty for local storage only.
                    </p>
                </div>
            </div>
        </section>
    </main>
    
    <!-- Modal para imágenes -->
    <div class="modal" id="imageModal">
        <span class="modal-close" id="modalClose" style="position: absolute; top: 30px; right: 40px; color: white; font-size: 3rem; cursor: pointer; z-index: 10001;">&times;</span>
        <img class="modal-content" id="modalImage">
    </div>
    
    <footer>
        <div class="container" style="text-align: center; position: relative; z-index: 2;">
            <p style="font-family: 'Rock Salt', cursive; font-size: 1.5rem; margin-bottom: 20px;">
                MADE WITH <span class="heart">❤️</span> FOR JORGE & PAULINE
            </p>
            <p style="color: #aaa; font-family: 'Orbitron', sans-serif; letter-spacing: 2px;">
                © <span id="currentYear"></span> ROCK ALBUM • ALL DATA STORED LOCALLY
            </p>
            <div style="margin-top: 30px; display: flex; justify-content: center; gap: 20px; font-size: 1.5rem;">
                <i class="fas fa-guitar" style="color: var(--neon-pink);"></i>
                <i class="fas fa-drum" style="color: var(--neon-blue);"></i>
                <i class="fas fa-microphone" style="color: var(--neon-yellow);"></i>
                <i class="fas fa-volume-up" style="color: var(--neon-green);"></i>
            </div>
        </div>
    </footer>

    <!-- Scripts -->
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        // Sistema de almacenamiento
        class RockStorage {
            constructor() {
                this.STORAGE_KEYS = {
                    PHOTOS: 'rockAlbum_photos',
                    SONGS: 'rockAlbum_songs',
                    STORIES: 'rockAlbum_stories'
                };
                this.init();
            }
            
            init() {
                if (!this.getPhotos().length) {
                    this.saveDefaultData();
                }
            }
            
            saveDefaultData() {
                const defaultPhotos = [
                    { 
                        id: this.generateId(),
                        src: "https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1170&q=80",
                        caption: "Nuestro primer concierto juntos",
                        date: new Date().toISOString(),
                        uploadedBy: "Jorge"
                    },
                    { 
                        id: this.generateId(),
                        src: "https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1170&q=80",
                        caption: "Backstage en el festival",
                        date: new Date().toISOString(),
                        uploadedBy: "Pauline"
                    }
                ];
                
                const defaultSongs = [
                    {
                        id: this.generateId(),
                        title: "Sweet Child O' Mine",
                        artist: "Guns N' Roses",
                        src: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3",
                        date: new Date().toISOString(),
                        uploadedBy: "Jorge"
                    },
                    {
                        id: this.generateId(),
                        title: "Back in Black",
                        artist: "AC/DC",
                        src: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-2.mp3",
                        date: new Date().toISOString(),
                        uploadedBy: "Pauline"
                    }
                ];
                
                const defaultStories = [
                    {
                        id: this.generateId(),
                        title: "Noche de Rock en el Garage",
                        content: "Esa noche en el garage de Jorge, con solo una guitarra y mucha pasión, descubrimos nuestra banda sonora. Pauline en los coros, Jorge en la guitarra, y el mundo desapareció alrededor nuestro.",
                        date: new Date().toISOString(),
                        uploadedBy: "Ambos"
                    },
                    {
                        id: this.generateId(),
                        title: "Festival de Verano",
                        content: "Sudor, luces y acordes distorsionados. 50,000 personas cantando al unísono y nosotros dos, perdidos en la multitud pero encontrándonos en cada mirada. El rock nos unió esa noche.",
                        date: new Date().toISOString(),
                        uploadedBy: "Pauline"
                    }
                ];
                
                localStorage.setItem(this.STORAGE_KEYS.PHOTOS, JSON.stringify(defaultPhotos));
                localStorage.setItem(this.STORAGE_KEYS.SONGS, JSON.stringify(defaultSongs));
                localStorage.setItem(this.STORAGE_KEYS.STORIES, JSON.stringify(defaultStories));
            }
            
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
            
            generateId() {
                return Date.now().toString(36) + Math.random().toString(36).substr(2);
            }
            
            exportData() {
                const data = {
                    photos: this.getPhotos(),
                    songs: this.getSongs(),
                    stories: this.getStories(),
                    exportDate: new Date().toISOString(),
                    version: "2.0",
                    couple: "Jorge & Pauline"
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
                    if (data) totalSize += new Blob([data]).size;
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
        class RockAlbumApp {
            constructor() {
                this.storage = new RockStorage();
                this.currentUser = "Jorge";
                
                // Inicializar elementos
                this.initElements();
                this.init();
            }
            
            initElements() {
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
                    storageInfo: document.getElementById('storageInfo')
                };
            }
            
            init() {
                // Año actual
                document.getElementById('currentYear').textContent = new Date().getFullYear();
                
                // Cargar datos
                this.loadPhotos();
                this.loadSongs();
                this.loadStories();
                this.updateStorageInfo();
                
                // Eventos
                this.setupNavigation();
                this.setupUploadArea();
                this.setupMusicPlayer();
                this.setupImageModal();
                this.setupBackupButtons();
                this.setupCustomCursor();
                this.initParticles();
                
                // Efecto de carga inicial
                this.showNotification('🤘 ¡Bienvenidos al Rock Album de Jorge y Pauline!', 'success');
            }
            
            setupNavigation() {
                this.elements.navButtons.forEach(btn => {
                    btn.addEventListener('click', () => {
                        const target = btn.dataset.section;
                        
                        this.elements.navButtons.forEach(b => b.classList.remove('active'));
                        btn.classList.add('active');
                        
                        this.elements.sections.forEach(section => {
                            section.classList.remove('active');
                            if (section.id === target) {
                                section.classList.add('active');
                                if (target === 'configuracion') this.updateStorageInfo();
                            }
                        });
                        
                        // Efecto de sonido
                        this.playSoundEffect();
                    });
                });
            }
            
            playSoundEffect() {
                const audio = new Audio('data:audio/wav;base64,UklGRigAAABXQVZFZm10IBIAAAABAAEARKwAAIhYAQACABAAZGF0YQQAAAAAAA==');
                audio.volume = 0.1;
                audio.play().catch(() => {});
            }
            
            loadPhotos() {
                const photos = this.storage.getPhotos();
                this.elements.photoGallery.innerHTML = '';
                
                if (!photos.length) {
                    this.elements.photoGallery.innerHTML = `
                        <div style="grid-column: 1/-1; text-align: center; padding: 60px; background: rgba(0,0,0,0.3); border: 2px dashed var(--neon-pink);">
                            <i class="fas fa-camera-retro" style="font-size: 4rem; color: var(--neon-pink); margin-bottom: 20px;"></i>
                            <h3 style="color: var(--neon-blue); font-family: 'Orbitron', sans-serif;">NO PHOTOS YET</h3>
                            <p style="color: #aaa;">Upload your first rock memory!</p>
                        </div>
                    `;
                    return;
                }
                
                photos.forEach(photo => {
                    const element = this.createPhotoElement(photo);
                    this.elements.photoGallery.appendChild(element);
                });
            }
            
            createPhotoElement(photo) {
                const div = document.createElement('div');
                div.className = 'photo-item';
                div.innerHTML = `
                    <img src="${photo.src}" alt="${photo.caption}" loading="lazy">
                    <div class="photo-caption">
                        <h4 style="color: white; margin-bottom: 5px;">${photo.caption}</h4>
                        <small style="color: #ccc;">By ${photo.uploadedBy} • ${new Date(photo.date).toLocaleDateString()}</small>
                    </div>
                    <button class="delete-btn" title="Delete">
                        <i class="fas fa-trash"></i>
                    </button>
                `;
                
                div.querySelector('img').addEventListener('click', () => {
                    this.openImageModal(photo.src, photo.caption);
                });
                
                div.querySelector('.delete-btn').addEventListener('click', (e) => {
                    e.stopPropagation();
                    if (confirm('¿Delete this rock memory?')) {
                        this.storage.deletePhoto(photo.id);
                        this.loadPhotos();
                        this.updateStorageInfo();
                        this.showNotification('Photo deleted!', 'info');
                    }
                });
                
                return div;
            }
            
            loadSongs() {
                const songs = this.storage.getSongs();
                this.elements.songList.innerHTML = '';
                
                if (!songs.length) {
                    this.elements.songList.innerHTML = `
                        <div style="text-align: center; padding: 40px; color: #aaa;">
                            <i class="fas fa-music" style="font-size: 3rem; opacity: 0.5; margin-bottom: 15px;"></i>
                            <p>No tracks yet. Drop some beats!</p>
                        </div>
                    `;
                    return;
                }
                
                songs.forEach((song, index) => {
                    const element = this.createSongElement(song, index === 0);
                    this.elements.songList.appendChild(element);
                });
                
                if (songs.length > 0) {
                    this.setCurrentSong(songs[0]);
                }
            }
            
            createSongElement(song, isActive = false) {
                const div = document.createElement('div');
                div.className = `song-item ${isActive ? 'active' : ''}`;
                div.innerHTML = `
                    <div style="display: flex; align-items: center; width: 100%; position: relative; z-index: 2;">
                        <i class="fas fa-play" style="margin-right: 15px; color: ${isActive ? 'var(--neon-yellow)' : 'var(--neon-pink)'};"></i>
                        <div style="flex: 1;">
                            <div style="font-weight: bold; color: ${isActive ? 'var(--neon-yellow)' : 'white'};">${song.title}</div>
                            <div style="color: #aaa; font-size: 0.9rem;">${song.artist} • ${new Date(song.date).toLocaleDateString()}</div>
                        </div>
                        <button class="delete-btn" style="position: static; opacity: 1; background: transparent; border: none; color: #ff0033; font-size: 1.2rem; padding: 5px;">
                            <i class="fas fa-times"></i>
                        </button>
                    </div>
                `;
                
                div.addEventListener('click', (e) => {
                    if (!e.target.closest('.delete-btn')) {
                        this.playSong(song, div);
                    }
                });
                
                div.querySelector('.delete-btn').addEventListener('click', (e) => {
                    e.stopPropagation();
                    if (confirm('¿Delete this track?')) {
                        this.storage.deleteSong(song.id);
                        this.loadSongs();
                        this.updateStorageInfo();
                        this.showNotification('Track deleted!', 'info');
                    }
                });
                
                return div;
            }
            
            loadStories() {
                const stories = this.storage.getStories();
                this.elements.storiesContainer.innerHTML = '';
                
                if (!stories.length) {
                    this.elements.storiesContainer.innerHTML = `
                        <div style="grid-column: 1/-1; text-align: center; padding: 60px; background: rgba(0,0,0,0.3); border: 2px dashed var(--neon-yellow);">
                            <i class="fas fa-book-open" style="font-size: 4rem; color: var(--neon-yellow); margin-bottom: 20px;"></i>
                            <h3 style="color: var(--neon-green); font-family: 'Orbitron', sans-serif;">NO STORIES YET</h3>
                            <p style="color: #aaa;">Write your first rock diary entry!</p>
                        </div>
                    `;
                    return;
                }
                
                stories.forEach(story => {
                    const element = this.createStoryElement(story);
                    this.elements.storiesContainer.appendChild(element);
                });
            }
            
            createStoryElement(story) {
                const div = document.createElement('div');
                div.className = 'story-card';
                div.innerHTML = `
                    <div class="story-content">
                        <h3>${story.title}</h3>
                        <span class="story-date">
                            <i class="far fa-calendar"></i> ${new Date(story.date).toLocaleDateString()} • By ${story.uploadedBy}
                        </span>
                        <p class="story-text">${story.content}</p>
                        <button class="delete-btn" style="margin-top: 20px; background: rgba(255,0,51,0.8); color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; font-family: 'Orbitron', sans-serif;">
                            <i class="fas fa-trash"></i> DELETE STORY
                        </button>
                    </div>
                `;
                
                div.querySelector('.delete-btn').addEventListener('click', () => {
                    if (confirm('¿Delete this story?')) {
                        this.storage.deleteStory(story.id);
                        this.loadStories();
                        this.updateStorageInfo();
                        this.showNotification('Story deleted!', 'info');
                    }
                });
                
                return div;
            }
            
            setupUploadArea() {
                this.elements.browseBtn.addEventListener('click', () => this.elements.fileInput.click());
                this.elements.uploadBox.addEventListener('click', () => this.elements.fileInput.click());
                
                this.elements.fileInput.addEventListener('change', (e) => this.handleFiles(e.target.files));
                
                // Drag and drop
                this.elements.uploadBox.addEventListener('dragover', (e) => {
                    e.preventDefault();
                    this.elements.uploadBox.style.borderColor = 'var(--neon-yellow)';
                });
                
                this.elements.uploadBox.addEventListener('dragleave', () => {
                    this.elements.uploadBox.style.borderColor = 'var(--neon-blue)';
                });
                
                this.elements.uploadBox.addEventListener('drop', (e) => {
                    e.preventDefault();
                    this.elements.uploadBox.style.borderColor = 'var(--neon-blue)';
                    if (e.dataTransfer.files.length) {
                        this.handleFiles(e.dataTransfer.files);
                    }
                });
                
                // Opciones de subida
                this.elements.uploadOptions.forEach(option => {
                    option.addEventListener('click', () => {
                        const type = option.dataset.type;
                        if (type === 'story') {
                            this.showStoryForm();
                        } else {
                            this.elements.fileInput.accept = type === 'photo' ? 'image/*' : 'audio/*';
                            this.elements.fileInput.click();
                        }
                    });
                });
            }
            
            handleFiles(files) {
                Array.from(files).slice(0, 5).forEach(file => {
                    const reader = new FileReader();
                    reader.onload = (e) => {
                        if (file.type.startsWith('image/')) {
                            this.savePhoto(file, e.target.result);
                        } else if (file.type.startsWith('audio/')) {
                            this.saveSong(file, e.target.result);
                        }
                    };
                    
                    if (file.type.startsWith('image/') || file.type.startsWith('audio/')) {
                        reader.readAsDataURL(file);
                    }
                });
            }
            
            savePhoto(file, dataUrl) {
                const photo = {
                    id: this.storage.generateId(),
                    src: dataUrl,
                    caption: `Rock memory by ${this.currentUser}`,
                    date: new Date().toISOString(),
                    uploadedBy: this.currentUser,
                    fileName: file.name
                };
                
                this.storage.savePhoto(photo);
                this.loadPhotos();
                this.updateStorageInfo();
                this.showNotification(`📸 Photo "${file.name}" uploaded!`, 'success');
                
                setTimeout(() => {
                    document.querySelector('[data-section="fotos"]').click();
                }, 1500);
            }
            
            saveSong(file, dataUrl) {
                const song = {
                    id: this.storage.generateId(),
                    title: file.name.replace(/\.[^/.]+$/, ""),
                    artist: this.currentUser,
                    src: dataUrl,
                    date: new Date().toISOString(),
                    uploadedBy: this.currentUser,
                    fileName: file.name
                };
                
                this.storage.saveSong(song);
                this.loadSongs();
                this.updateStorageInfo();
                this.showNotification(`🎵 Track "${song.title}" uploaded!`, 'success');
            }
            
            showStoryForm() {
                this.elements.uploadStatus.innerHTML = `
                    <div style="background: rgba(0,0,0,0.8); padding: 30px; border-radius: 15px; border: 2px solid var(--neon-yellow); position: relative; z-index: 2;">
                        <h4 style="color: var(--neon-yellow); font-family: 'Orbitron', sans-serif; margin-bottom: 20px;">
                            <i class="fas fa-feather-alt"></i> WRITE ROCK STORY
                        </h4>
                        <input type="text" id="storyTitle" placeholder="Story title..." style="width: 100%; padding: 15px; margin-bottom: 15px; background: #111; border: 2px solid var(--neon-yellow); color: white;">
                        <textarea id="storyContent" placeholder="Tell your rock story..." rows="5" style="width: 100%; padding: 15px; margin-bottom: 15px; background: #111; border: 2px solid var(--neon-yellow); color: white; resize: vertical;"></textarea>
                        <select id="storyAuthor" style="width: 100%; padding: 15px; margin-bottom: 20px; background: #111; border: 2px solid var(--neon-yellow); color: white;">
                            <option value="Jorge">Jorge</option>
                            <option value="Pauline">Pauline</option>
                            <option value="Ambos">Both</option>
                        </select>
                        <button id="saveStoryBtn" class="upload-btn">
                            <i class="fas fa-save"></i> SAVE STORY
                        </button>
                    </div>
                `;
                
                document.getElementById('saveStoryBtn').addEventListener('click', () => this.saveStory());
            }
            
            saveStory() {
                const title = document.getElementById('storyTitle').value;
                const content = document.getElementById('storyContent').value;
                const author = document.getElementById('storyAuthor').value;
                
                if (!title || !content) {
                    alert('Please fill all fields!');
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
                this.showNotification(`📖 Story "${title}" saved!`, 'success');
                
                setTimeout(() => {
                    document.querySelector('[data-section="historias"]').click();
                }, 1500);
            }
            
            setCurrentSong(song) {
                this.elements.audioPlayer.src = song.src;
                this.elements.currentSongElement.textContent = `${song.title} - ${song.artist}`;
            }
            
            playSong(song, element) {
                this.setCurrentSong(song);
                this.elements.audioPlayer.play();
                
                document.querySelectorAll('.song-item').forEach(item => {
                    item.classList.remove('active');
                });
                
                if (element) {
                    element.classList.add('active');
                }
                
                // Efecto visual
                if (element) {
                    element.style.animation = 'none';
                    setTimeout(() => {
                        element.style.animation = '';
                    }, 10);
                }
            }
            
            setupMusicPlayer() {
                this.elements.audioPlayer.addEventListener('ended', () => {
                    const songs = this.storage.getSongs();
                    const currentIndex = songs.findIndex(song => song.src === this.elements.audioPlayer.src);
                    if (currentIndex < songs.length - 1) {
                        this.playSong(songs[currentIndex + 1]);
                    }
                });
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
                this.elements.exportBtn.addEventListener('click', () => {
                    const data = this.storage.exportData();
                    const blob = new Blob([data], { type: 'application/json' });
                    const url = URL.createObjectURL(blob);
                    const a = document.createElement('a');
                    a.href = url;
                    a.download = `rock-album-backup-${new Date().toISOString().split('T')[0]}.json`;
                    document.body.appendChild(a);
                    a.click();
                    document.body.removeChild(a);
                    URL.revokeObjectURL(url);
                    
                    this.showNotification('💾 Backup exported!', 'success');
                });
                
                this.elements.importBtn.addEventListener('click', () => {
                    const input = document.createElement('input');
                    input.type = 'file';
                    input.accept = '.json';
                    input.onchange = (e) => {
                        const file = e.target.files[0];
                        const reader = new FileReader();
                        reader.onload = (e) => {
                            if (this.storage.importData(e.target.result)) {
                                this.loadPhotos();
                                this.loadSongs();
                                this.loadStories();
                                this.updateStorageInfo();
                                this.showNotification('📂 Backup imported!', 'success');
                            } else {
                                this.showNotification('❌ Invalid backup file', 'error');
                            }
                        };
                        reader.readAsText(file);
                    };
                    input.click();
                });
                
                this.elements.clearBtn.addEventListener('click', () => {
                    if (confirm('⚠️ WARNING: This will delete ALL data and restore defaults. Continue?')) {
                        this.storage.clearAll();
                        this.loadPhotos();
                        this.loadSongs();
                        this.loadStories();
                        this.updateStorageInfo();
                        this.showNotification('🔄 Data reset to defaults', 'info');
                    }
                });
            }
            
            updateStorageInfo() {
                const info = this.storage.getStorageInfo();
                this.elements.storageInfo.value = 
                    `${info.photos} Photos | ${info.songs} Tracks | ${info.stories} Stories | ${info.size}`;
            }
            
            showNotification(message, type = 'info') {
                const colors = {
                    success: 'var(--neon-green)',
                    error: 'var(--neon-pink)',
                    info: 'var(--neon-blue)'
                };
                
                const notification = document.createElement('div');
                notification.style.cssText = `
                    position: fixed;
                    top: 100px;
                    right: 30px;
                    background: rgba(10,10,10,0.95);
                    border: 2px solid ${colors[type]};
                    color: white;
                    padding: 20px 30px;
                    border-radius: 10px;
                    font-family: 'Orbitron', sans-serif;
                    z-index: 10000;
                    animation: slideIn 0.3s ease;
                    box-shadow: 0 10px 30px rgba(0,0,0,0.5);
                    max-width: 400px;
                    backdrop-filter: blur(10px);
                `;
                notification.innerHTML = `
                    <div style="display: flex; align-items: center; gap: 15px;">
                        <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'error' ? 'exclamation-circle' : 'info-circle'}" 
                           style="color: ${colors[type]}; font-size: 1.5rem;"></i>
                        <div>${message}</div>
                    </div>
                `;
                
                document.body.appendChild(notification);
                
                setTimeout(() => {
                    notification.style.animation = 'slideOut 0.3s ease';
                    setTimeout(() => notification.remove(), 300);
                }, 3000);
                
                // Agregar keyframes CSS si no existen
                if (!document.getElementById('notification-styles')) {
                    const style = document.createElement('style');
                    style.id = 'notification-styles';
                    style.textContent = `
                        @keyframes slideIn {
                            from { transform: translateX(100%); opacity: 0; }
                            to { transform: translateX(0); opacity: 1; }
                        }
                        @keyframes slideOut {
                            from { transform: translateX(0); opacity: 1; }
                            to { transform: translateX(100%); opacity: 0; }
                        }
                    `;
                    document.head.appendChild(style);
                }
            }
            
            setupCustomCursor() {
                const cursor = document.querySelector('.cursor');
                const follower = document.querySelector('.cursor-follower');
                
                document.addEventListener('mousemove', (e) => {
                    cursor.style.left = e.clientX + 'px';
                    cursor.style.top = e.clientY + 'px';
                    
                    setTimeout(() => {
                        follower.style.left = e.clientX + 'px';
                        follower.style.top = e.clientY + 'px';
                    }, 50);
                });
                
                document.addEventListener('mousedown', () => {
                    cursor.style.transform = 'scale(0.5)';
                    follower.style.transform = 'scale(1.5)';
                });
                
                document.addEventListener('mouseup', () => {
                    cursor.style.transform = 'scale(1)';
                    follower.style.transform = 'scale(1)';
                });
                
                // Cambiar cursor en elementos interactivos
                const interactive = document.querySelectorAll('button, .photo-item, .song-item, .story-card, .upload-box');
                interactive.forEach(el => {
                    el.addEventListener('mouseenter', () => {
                        cursor.style.transform = 'scale(1.5)';
                        cursor.style.borderColor = 'var(--neon-yellow)';
                        follower.style.transform = 'scale(1.5)';
                        follower.style.background = 'rgba(255, 255, 0, 0.1)';
                    });
                    
                    el.addEventListener('mouseleave', () => {
                        cursor.style.transform = 'scale(1)';
                        cursor.style.borderColor = 'var(--neon-pink)';
                        follower.style.transform = 'scale(1)';
                        follower.style.background = 'rgba(255, 0, 255, 0.1)';
                    });
                });
            }
            
            initParticles() {
                particlesJS('particles-js', {
                    particles: {
                        number: { value: 80, density: { enable: true, value_area: 800 } },
                        color: { value: ["#ff00ff", "#00ffff", "#00ff00", "#ffff00"] },
                        shape: { type: "circle" },
                        opacity: { value: 0.5, random: true },
                        size: { value: 3, random: true },
                        line_linked: {
                            enable: true,
                            distance: 150,
                            color: "#ffffff",
                            opacity: 0.2,
                            width: 1
                        },
                        move: {
                            enable: true,
                            speed: 2,
                            direction: "none",
                            random: true,
                            straight: false,
                            out_mode: "out",
                            bounce: false
                        }
                    },
                    interactivity: {
                        detect_on: "canvas",
                        events: {
                            onhover: { enable: true, mode: "repulse" },
                            onclick: { enable: true, mode: "push" }
                        }
                    }
                });
            }
        }

        // Inicializar aplicación
        document.addEventListener('DOMContentLoaded', () => {
            window.rockAlbum = new RockAlbumApp();
        });
    </script>
</body>
</html>
