<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мега-Ком — Анимация Логотипа</title>
    <style>
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
            /* Темный фон, чтобы светящиеся кольца и частицы смотрелись круто */
            background: radial-gradient(circle at 50% 40%, #2a0a0a 0%, #0d0000 60%, #000 100%);
            overflow: hidden;
            font-family: 'Segoe UI', Arial, sans-serif;
        }

        /* Контейнер для всей сцены */
        .scene {
            position: relative;
            width: 500px;
            height: 500px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Светящиеся кольца вокруг иконки */
        .ring {
            position: absolute;
            border-radius: 50%;
            border: 2px solid transparent;
            border-top-color: #ff2b2b;
            border-right-color: #ff2b2b;
            animation: spin 3s linear infinite;
            filter: drop-shadow(0 0 15px #ff2b2b);
        }

        .ring-1 {
            width: 340px;
            height: 340px;
            animation-duration: 3s;
        }

        .ring-2 {
            width: 400px;
            height: 400px;
            border-top-color: #ff6b6b;
            border-right-color: transparent;
            border-bottom-color: #ff6b6b;
            animation-duration: 5s;
            animation-direction: reverse;
            opacity: 0.7;
        }

        .ring-3 {
            width: 460px;
            height: 460px;
            border-top-color: #b00000;
            border-left-color: #b00000;
            animation-duration: 7s;
            opacity: 0.5;
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Контейнер для логотипа */
        .logo-wrapper {
            position: relative;
            z-index: 2;
            /* Настройте ширину, чтобы логотип вписался в кольца */
            width: 280px; 
            opacity: 0;
            transform: scale(0);
            /* Анимация появления и последующей пульсации */
            animation: revealLogo 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards,
                       pulseLogo 3s ease-in-out 1.2s infinite;
        }

        /* Сам логотип */
        .logo-wrapper img {
            width: 100%;
            height: auto;
            display: block;
            /* Добавляем легкое свечение, чтобы черный логотип было видно на темном фоне */
            filter: drop-shadow(0 0 20px rgba(255, 255, 255, 0.2));
        }

        /* Появление логотипа (с поворотом) */
        @keyframes revealLogo {
            0% {
                opacity: 0;
                transform: scale(0) rotate(-20deg);
            }
            60% {
                opacity: 1;
                transform: scale(1.05) rotate(3deg);
            }
            100% {
                opacity: 1;
                transform: scale(1) rotate(0);
            }
        }

        /* Пульсация логотипа */
        @keyframes pulseLogo {
            0%, 100% {
                transform: scale(1);
                filter: drop-shadow(0 0 20px rgba(255, 255, 255, 0.2));
            }
            50% {
                transform: scale(1.03);
                filter: drop-shadow(0 0 30px rgba(255, 255, 255, 0.4));
            }
        }

        /* Летящие частицы */
        .particle {
            position: absolute;
            width: 6px;
            height: 6px;
            background: #ff6b6b;
            border-radius: 50%;
            box-shadow: 0 0 10px #ff2b2b;
            top: 50%;
            left: 50%;
            pointer-events: none;
            animation: flyOut 2s ease-out infinite;
        }

        @keyframes flyOut {
            0% {
                transform: translate(-50%, -50%) rotate(var(--angle)) translateX(0) scale(1);
                opacity: 1;
            }
            100% {
                transform: translate(-50%, -50%) rotate(var(--angle)) translateX(250px) scale(0);
                opacity: 0;
            }
        }

        /* Вспышка при загрузке */
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
            0% { opacity: 0.5; }
            100% { opacity: 0; }
        }
    </style>
</head>
<body>

    <!-- Вспышка -->
    <div class="flash"></div>

    <div class="scene">
        <!-- Светящиеся кольца -->
        <div class="ring ring-1"></div>
        <div class="ring ring-2"></div>
        <div class="ring ring-3"></div>

        <!-- Логотип -->
        <div class="logo-wrapper">
            <!-- ЗАМЕНИТЕ ССЫЛКУ В src НА ПУТЬ К ВАШЕМУ ЛОГОТИПУ -->
            <img src="ВАШ_ПУТЬ_К_ЛОГОТИПУ.png" alt="Мега-Ком">
        </div>
    </div>

    <script>
        // Создаем летящие частицы
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
