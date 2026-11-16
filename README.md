<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="color-scheme" content="light">
    <title>Мега-Ком — Анимация с бликом</title>
    
    <style>
        /* --- ПОДКЛЮЧАЕМ ВАШ ШРИФТ --- */
        @font-face {
            font-family: 'Averta Cyrillic';
            src: url('Averta Cyrillic Bold.otf') format('opentype');
            font-weight: bold;
            font-style: normal;
            font-display: swap;
        }

        :root { color-scheme: light; }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #f4f5f7 !important;
            margin: 0;
            overflow: hidden;
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 15px;
            
            /* ДОБАВЛЕНО: относительное позиционирование для блика и обрезка лишнего */
            position: relative;
            overflow: hidden; 
            padding: 10px 20px; /* Отступы, чтобы блик было видно по краям */

            /* Легкая пульсация после сборки */
            animation: pulseFinal 3s ease-in-out 2s infinite;
        }

        /* --- БЛИК (ПСЕВДОЭЛЕМЕНТ) --- */
        .logo-container::after {
            content: '';
            position: absolute;
            top: 0;
            left: -150%; /* Начинаем за левым краем */
            width: 50%;
            height: 100%;
            /* Градиент от прозрачного к белому и обратно */
            background: linear-gradient(
                90deg,
                rgba(255, 255, 255, 0) 0%,
                rgba(255, 255, 255, 0.6) 50%,
                rgba(255, 255, 255, 0) 100%
            );
            transform: skewX(-25deg); /* Наклоняем блик */
            pointer-events: none; /* Чтобы не мешал кликам */
            
            /* Запускаем блик с задержкой 2 секунды (когда буквы уже собрались) */
            animation: shine 4s infinite 2s; 
        }

        /* --- ИКОНКА --- */
        .logo-icon {
            height: 65px; 
            width: auto;
            opacity: 0;
            /* Тень сделает иконку объемной на любом фоне */
            filter: drop-shadow(0px 4px 6px rgba(0,0,0,0.1));
            animation: slideInLeft 0.8s cubic-bezier(0.25, 1, 0.5, 1) forwards;
        }

        /* --- ТЕКСТ --- */
        .logo-text {
            display: flex;
            font-size: 48px; 
            color: #222222;  
            font-family: 'Averta Cyrillic', sans-serif; 
            font-weight: bold;
            line-height: 1;
            letter-spacing: -0.5px; 
        }

        .logo-text span {
            display: inline-block;
            opacity: 0;
            animation: assembleLetter 0.8s cubic-bezier(0.25, 1, 0.5, 1) forwards;
        }

        /* Задержки букв */
        .logo-text span:nth-child(1) { animation-delay: 0.2s; --x: -40px; --y: -60px; --r: -20deg; }
        .logo-text span:nth-child(2) { animation-delay: 0.3s; --x: 30px;  --y: 50px;  --r: 15deg; }
        .logo-text span:nth-child(3) { animation-delay: 0.4s; --x: -50px; --y: 30px;  --r: -10deg; }
        .logo-text span:nth-child(4) { animation-delay: 0.5s; --x: 40px;  --y: -40px; --r: 25deg; }
        .logo-text span:nth-child(5) { animation-delay: 0.6s; --x: 0px;   --y: -70px; --r: 0deg; }
        .logo-text span:nth-child(6) { animation-delay: 0.7s; --x: 50px;  --y: 30px;  --r: 20deg; }
        .logo-text span:nth-child(7) { animation-delay: 0.8s; --x: -30px; --y: -50px; --r: -15deg; }
        .logo-text span:nth-child(8) { animation-delay: 0.9s; --x: 60px;  --y: 0px;   --r: 10deg; }

        /* --- АНИМАЦИИ --- */
        @keyframes assembleLetter {
            0% { opacity: 0; transform: translate(var(--x), var(--y)) rotate(var(--r)) scale(0.5); }
            100% { opacity: 1; transform: translate(0, 0) rotate(0) scale(1); }
        }

        @keyframes slideInLeft {
            0% { opacity: 0; transform: translateX(-80px) scale(0.8); }
            100% { opacity: 1; transform: translateX(0) scale(1); }
        }

        @keyframes pulseFinal {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.02); }
        }

        /* --- НОВАЯ АНИМАЦИЯ БЛИКА --- */
        @keyframes shine {
            0% { left: -150%; } /* Стоит слева за экраном */
            15% { left: 150%; } /* Быстро пробегает вправо */
            100% { left: 150%; } /* Ждет, пока не начнется следующий цикл */
        }
    </style>
</head>
<body>

    <div class="logo-container">
        
        <!-- ВАЖНО: Убедитесь, что файл icon.png имеет ПРОЗРАЧНЫЙ фон -->
        <img src="icon.png" class="logo-icon" alt="Mega-Kom Icon">

        <div class="logo-text">
            <span>М</span>
            <span>е</span>
            <span>г</span>
            <span>а</span>
            <span>-</span>
            <span>К</span>
            <span>о</span>
            <span>м</span>
        </div>
        
    </div>

</body>
</html>
