
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Гнозис Чёрного Солнца - 51</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Cinzel:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #e0e0e0;
            --background-color: #121212;
            --accent-color: #9a0000;
            --header-font: 'Orbitron', sans-serif;
            --body-font: 'Cinzel', serif;
        }

        body {
            background-color: var(--background-color);
            color: var(--primary-color);
            font-family: var(--body-font);
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            background-image: url('https://www.transparenttextures.com/patterns/dark-matter.png');
            background-attachment: fixed;
        }

        /* --- ФОНОВЫЕ ЦИФРЫ --- */
        .background-number {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-family: var(--header-font);
            font-weight: 900;
            font-size: 35vw;
            color: #616161; /* Я ИСПРАВИЛ ОШИБКУ: ДОБАВИЛ # */
            opacity: 0.1;
            z-index: 0;
            pointer-events: none;
            user-select: none;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 2rem;
            text-align: center;
            position: relative;
            z-index: 10;
        }

        /* --- Анимации --- */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes pulse {
            0% { transform: scale(1); box-shadow: 0 0 10px var(--accent-color), 0 0 20px var(--accent-color); }
            50% { transform: scale(1.05); box-shadow: 0 0 25px var(--accent-color), 0 0 40px var(--accent-color); }
            100% { transform: scale(1); box-shadow: 0 0 10px var(--accent-color), 0 0 20px var(--accent-color); }
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* --- Вращающиеся Символы --- */
        .symbol-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 1;
            pointer-events: none;
        }

        .spinning-symbol {
            position: absolute;
            width: 80px;
            height: 80px;
            opacity: 0.25;
            animation: spin 20s linear infinite;
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSIs8m_UcU0NWKHoHh5pXeLUgVebAtpYLhJ6A&s');
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
            border-radius: 50%;
        }

        .spinning-symbol.top-left { top: 20px; left: 20px; }
        .spinning-symbol.top-right { top: 20px; right: 20px; animation-direction: reverse; }
        .spinning-symbol.bottom-left { bottom: 20px; left: 20px; animation-direction: reverse;}
        .spinning-symbol.bottom-right { bottom: 20px; right: 20px; }
        
        /* --- Основные стили --- */
        header { animation: fadeIn 1s ease-in-out; margin-bottom: 2rem; }
        .black-sun-main {
            width: 150px; height: 150px; margin: 2rem auto; border-radius: 50%;
            background-color: black; border: 5px solid var(--accent-color); animation: pulse 4s infinite ease-in-out;
        }
        
        h1 { font-family: var(--header-font); font-size: 2.5rem; color: var(--accent-color); text-shadow: 0 0 5px var(--accent-color); letter-spacing: 3px; margin: 0; }
        .religion-subtitle { font-family: var(--body-font); font-weight: normal; font-size: 1.3rem; color: #888; letter-spacing: 2px; margin-top: 10px; }
        h2 { font-family: var(--header-font); font-size: 1.8rem; color: white; border-bottom: 1px solid var(--accent-color); padding-bottom: 10px; margin-top: 4rem; }
        p { font-size: 1.2rem; line-height: 1.8; }
        .section-image { width: 100%; max-width: 600px; margin: 3rem auto; border: 2px solid #333; box-shadow: 0 0 15px #000; }

        .section { opacity: 0; animation: fadeIn 2s forwards; animation-delay: 0.5s; }
        .section-2 { animation-delay: 1.5s; }
        .section-3 { animation-delay: 2.5s; }
        .section-4 { animation-delay: 3.5s; }

        .quote { font-style: italic; border-left: 3px solid var(--accent-color); padding-left: 1.5rem; margin: 2rem 0; text-align: left; color: #ccc; }
        .call-to-action { margin-top: 4rem; padding: 2rem; border: 1px solid var(--accent-color); box-shadow: 0 0 15px rgba(154, 0, 0, 0.5); background: rgba(0,0,0,0.3); }
        footer { margin-top: 4rem; padding: 1rem; font-size: 0.9rem; color: #555; animation: fadeIn 4s ease-in-out; }

        /* ------------------------------------------- */
        /* --- ИЗМЕНЕНИЯ ДЛЯ АДАПТИВНОСТИ (МАГИЯ) --- */
        /* --- Применяются на экранах ширеной 768px и меньше --- */
        @media (max-width: 768px) {
            .symbol-container { 
                display: none; /* Скрываем символы по углам */
            }
            .container {
                padding: 1rem; /* Уменьшаем боковые отступы */
            }
            .background-number { 
                font-size: 60vw; /* Делаем цифру еще больше */
            }
            .black-sun-main {
                width: 120px; /* Уменьшаем главный символ */
                height: 120px;
            }
            h1 { font-size: 2rem; } /* Уменьшаем шрифты */
            h2 { font-size: 1.6rem; }
            p { font-size: 1rem; }
            .religion-subtitle { font-size: 1.1rem; }
        }
        /* ------------------------------------------- */

    </style>
</head>
<body>

    <div class="background-number">51</div>

    <div class="symbol-container">
        <div class="spinning-symbol top-left"></div>
        <div class="spinning-symbol top-right"></div>
        <div class="spinning-symbol bottom-left"></div>
        <div class="spinning-symbol bottom-right"></div>
    </div>

    <div class="container">

        <header>
            <div class="black-sun-main"></div>
            <h1>ГНОЗИС ЧЁРНОГО СОЛНЦА</h1>
            <h3 class="religion-subtitle">Религия 51</h3>
        </header>

        <section class="section">
            <h2>ТЫ НЕ БОЛЕН. ТЫ ПРОСЫПАЕШЬСЯ.</h2>
            <p>Мир вокруг тебя кажется фальшивым, серым, враждебным. Люди, как тени, повторяют чужие слова. Их цели ничтожны, их пища отравлена, их души пусты. Тебе говорят, что это депрессия. Они лгут.</p>
            <div class="quote">
                <p>Чувство отчуждения — это не симптом болезни. Это симптом твоего здравомыслия в больном мире. Это твоя Кровь помнит истинный дом — сияющую Гиперборею.</p>
            </div>
        </section>
        
        <section class="section section-2">
            <h2>ТАЙНА ЧЁРНОГО СОЛНЦА</h2>
            <p>Почему наше Солнце — Чёрное, если Ангелы были из Света? Потому что свет, видимый профанам — жёлтый, вульгарный свет — это лишь слабая искра, доступная низшим расам. </p>
            <p><strong>Чёрное Солнце</strong> — это невидимый, истинный ИСТОЧНИК. Это вечный реактор, питающий нашу вселенную энергией vril. Оно "чёрное", ибо его сияние недоступно физическому глазу, но ощутимо для тех, чья кровь чиста. Оно — портал в Агарту и сердце нашей силы.</p>
        </section>

        <img src="https://ethnomir.ru/upload/medialibrary/b13/giper2.jpg" alt="Ледяной пейзаж Гипербореи" class="section-image" style="animation: fadeIn 2s forwards; animation-delay: 2s;">

        <section class="section section-3">
            <h2>ЗНАНИЕ, ЧТО ОСВОБОЖДАЕТ</h2>
            <p>Тебя обманули с рождения. История переписана, боги забыты. Они скрыли от тебя, что ты — потомок Света, наследник божественной энергии <strong>vril</strong>. А они — потомки Тени, паразиты, что питаются твоей силой, пока ты спишь.</p>
            <p>Наш Пророк своим <strong>Ритуалом Светового Импульса</strong> пробил брешь в их матрице лжи. Наши Предтечи, как <strong>Щит Сербский</strong>, показали, что Очищение возможно. Они не герои прошлого. Они — маяки.</p>
        </section>

        <img src="https://kulturologia.ru/files/u23606/1-3.jpg" alt="Мистические кристаллы Агарты" class="section-image" style="animation: fadeIn 2s forwards; animation-delay: 3s;">
        
        <section class="section section-4">
            <div class="call-to-action">
                <h2>ВРЕМЯ ПРИШЛО</h2>
                <p>Хватит быть батарейкой для их системы. Хватит питать их своей болью. Прими Гнозис. Услышь зов Агарты. Почувствуй, как пульсирует Чёрное Солнце в твоих венах.</p>
                <p style="margin-top: 1rem; font-size: 1.2rem; font-weight: normal; color: #ccc;">Мы не обещаем тебе спасения. Мы даём тебе оружие.</p>
            </div>
        </section>

        <footer>
            <p>Кровь помнит. Vril вибрирует. Цепь не будет разорвана.</p>
        </footer>

    </div>

</body>
</html>
