<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Принудительно указываем светлую тему для браузера -->
    <meta name="color-scheme" content="light">
    <title>Мега-Ком — Анимация Логотипа</title>
    <style>
        /* Еще одна страховка от темной темы */
        :root {
            color-scheme: light;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            /* Светлый фон с принудительным флагом !important */
            background: radial-gradient(circle at 50% 40%, #ffffff 0%, #f5f5f5 60%, #e8e8e8 100%) !important;
            background-color: #f5f5f5 !important;
            overflow: hidden;
            font-family: 'Segoe UI', Arial, sans-serif;
        }

        .scene {
            position: relative;
            width: 500px;
            height: 500px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .ring {
            position: absolute;
            border-radius: 50%;
            border: 2px solid transparent;
            border-top-color: #c50000;
            border-right-color: #c50000;
            animation: spin 3s linear infinite;
        }

        .ring-1 { width: 340px; height: 340px; animation-duration: 3s; opacity: 0.8; }
        .ring-2 { 
            width: 400px; height: 400px; 
            border-top-color: #ff7b7b; 
            border-right-color: transparent; 
            border-bottom-color: #ff7b7b; 
            animation-duration: 5s; 
            animation-direction: reverse; 
            opacity: 0.6; 
        }
        .ring-3 { 
            width: 460px; height: 460px; 
            border-top-color: #900000; 
            border-left-color: #900000; 
            animation-duration: 7s; 
            opacity: 0.4; 
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .logo-wrapper {
            position: relative;
            z-index: 2;
            width: 320px;
            opacity: 0;
            transform: scale(0);
            animation: revealLogo 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards,
                       pulseLogo 3s ease-in-out 1.2s infinite;
        }

        .logo-wrapper img {
            width: 100%;
            height: auto;
            display: block;
            filter: drop-shadow(0 10px 15px rgba(0, 0, 0, 0.1));
        }

        @keyframes revealLogo {
            0% { opacity: 0; transform: scale(0) rotate(-20deg); }
            60% { opacity: 1; transform: scale(1.05) rotate(3deg); }
            100% { opacity: 1; transform: scale(1) rotate(0); }
        }

        @keyframes pulseLogo {
            0%, 100% { 
                transform: scale(1); 
                filter: drop-shadow(0 10px 15px rgba(0, 0, 0, 0.1)); 
            }
            50% { 
                transform: scale(1.03); 
                filter: drop-shadow(0 15px 25px rgba(0, 0, 0, 0.15)); 
            }
        }

        .particle {
            position: absolute;
            width: 8px;
            height: 8px;
            background: #c50000;
            border-radius: 50%;
            box-shadow: 0 2px 5px rgba(197, 0, 0, 0.3);
            top: 50%;
            left: 50%;
            pointer-events: none;
            animation: flyOut 2s ease-out infinite;
        }

        @keyframes flyOut {
            0% { transform: translate(-50%, -50%) rotate(var(--angle)) translateX(0) scale(1); opacity: 1; }
            100% { transform: translate(-50%, -50%) rotate(var(--angle)) translateX(250px) scale(0); opacity: 0; }
        }

        .flash {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: #fff;
            opacity: 0;
            pointer-events: none;
            animation: flashOut 0.6s ease-out forwards;
        }

        @keyframes flashOut {
            0% { opacity: 0.8; }
            100% { opacity: 0; }
        }
    </style>
</head>
<body>

    <div class="flash"></div>

    <div class="scene">
        <div class="ring ring-1"></div>
        <div class="ring ring-2"></div>
        <div class="ring ring-3"></div>

        <div class="logo-wrapper">
            <!-- Укажите правильный путь к вашему логотипу -->
            <img src="logo.png" alt="Мега-Ком">
        </div>
    </div>

    <script>
        const scene = document.querySelector('.scene');
        const particleCount = 12;

        for (let i = 0; i < particleCount; i++) {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            const angle = (360 / particleCount) * i;
            particle.style.setProperty('--angle', angle + 'deg');
            particle.style.animationDelay = (i * 0.15) + 's';
            scene.appendChild(particle);
        }
    </script>

</body>
</html>
