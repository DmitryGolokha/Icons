<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="color-scheme" content="light">
    <title>Мега-Ком — Сканирование по контуру</title>
    
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
            padding: 10px 20px;
            animation: pulseFinal 4s ease-in-out 2.5s infinite;
        }

        /* --- ИКОНКА И ЕЕ СКАНИРОВАНИЕ --- */
        .icon-wrapper {
            position: relative;
            height: 65px;
            display: flex;
            align-items: center;
        }

        .logo-icon {
            height: 65px; 
            width: auto;
            opacity: 0;
            animation: slideInLeft 0.8s cubic-bezier(0.25, 1, 0.5, 1) forwards;
        }

        /* Слой света поверх иконки */
        .icon-wrapper::after {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            
            background: linear-gradient(90deg, 
                transparent 0%, 
                transparent 40%, 
                rgba(255, 255, 255, 1) 50%, 
                transparent 60%, 
                transparent 100%
            );
            background-size: 300% 100%;
            background-position: 200% 0;
            
            -webkit-mask-image: url('icon.png');
            mask-image: url('icon.png');
            -webkit-mask-size: contain;
            mask-size: contain;
            -webkit-mask-repeat: no-repeat;
            mask-repeat: no-repeat;
            -webkit-mask-position: center;
            mask-position: center;
            
            /* ИЗНАЧАЛЬНО СКРЫТ */
            opacity: 0; 
            
            /* Сначала проявляем (через 2с), потом запускаем движение (через 2.2с) */
            animation: 
                showScanner 0.3s ease-out 2s forwards,
                scanEffect 4s linear infinite 2.2s;
            pointer-events: none;
        }

        /* --- ТЕКСТ И ЕГО СКАНИРОВАНИЕ --- */
        .logo-text {
            display: flex;
            font-size: 48px; 
            color: #222222;  
            font-family: 'Averta Cyrillic', sans-serif; 
            font-weight: bold;
            line-height: 1;
            letter-spacing: -0.5px; 
            position: relative; 
        }

        .logo-text span {
            display: inline-block;
            opacity: 0;
            animation: assembleLetter 0.8s cubic-bezier(0.25, 1, 0.5, 1) forwards;
        }

        /* Слой сканирования для текста */
        .logo-text::after {
            content: 'Мега-Ком';
            position: absolute;
            top: 0; left: 0;
            width: 100%; height: 100%;
            font-family: 'Averta Cyrillic', sans-serif;
            font-size: 48px;
            font-weight: bold;
            letter-spacing: -0.5px;
            line-height: 1;
            white-space: nowrap;
            
            background: linear-gradient(90deg, 
                transparent 0%, 
                transparent 40%, 
                rgba(255, 255, 255, 1) 50%, 
                transparent 60%, 
                transparent 100%
            );
            background-size: 300% 100%;
            background-position: 200% 0;
            
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            -webkit-text-fill-color: transparent;
            
            /* ИЗНАЧАЛЬНО СКРЫТ */
            opacity: 0;
            
            /* Сначала проявляем (через 2с), потом запускаем движение (через 2.2с) */
            animation: 
                showScanner 0.3s ease-out 2s forwards,
                scanEffect 4s linear infinite 2.2s;
            pointer-events: none;
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

        /* Появление сканера */
        @keyframes showScanner {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Движение света */
        @keyframes scanEffect {
            0% { background-position: 200% 0; }
            100% { background-position: -100% 0; }
        }
    </style>
</head>
<body>

    <div class="logo-container">
        
        <!-- Обертка для иконки -->
        <div class="icon-wrapper">
            <img src="icon.png" class="logo-icon" alt="Mega-Kom Icon">
        </div>

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
