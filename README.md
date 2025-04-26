
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arsenij | 15SAVAGE </title>
    <style>
        body {
            font-family: Candara, sans-serif;
            margin: 0;
            padding: 0;
            text-align: center;
            color: white;
        }
        #video-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: -1;
        }
        section {
            position: relative;
            z-index: 1;
            padding: 20px;
            max-width: 800px;
            margin: auto;
            background: rgba(51, 51, 51, 0.8);
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            margin-top: 20px;
        }
        .info-box {
            background: rgba(40, 40, 40, 0.9);
            backdrop-filter: blur(10px);
            padding: 20px;
            margin: 20px auto;
            border-radius: 10px;
            max-width: 800px;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 1s ease-out, transform 1s ease-out;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
            border-left: 5px solid #ff6f61;
            position: relative;
            overflow: hidden; 
        }
        .info-box:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 30px rgba(255, 255, 255, 0.8);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .info-box img {
            max-width: 45%;
            border-radius: 10px;
            margin-right: 20px;
            float: left; 
        }
        .info-box h2 {
            font-size: 24px;
            color: #ff6f61;
            margin-top: 0;
            margin-bottom: 15px;
        }
        .info-box p {
            font-size: 16px;
            text-align: left;
            color: #fff;
            margin: 0 0 15px 0;
            line-height: 1.5;
        }
        .info-box ul {
            text-align: left;
            color: white;
            padding-left: 20px;
            margin-bottom: 15px;
        }
        .info-box li {
            margin-bottom: 8px;
        }
        .info-box-button {
            position: absolute;
            bottom: 10px;
            right: 10px;
            padding: 8px 16px;
            font-size: 14px;
            color: white;
            background: #666;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s, transform 0.2s;
        }
        .info-box-button:hover {
            background: #999;
            transform: scale(1.05);
        }
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }
        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }
        .modal {
            background: rgba(51, 51, 51, 0.9);
            padding: 20px;
            border-radius: 10px;
            max-width: 400px;
            text-align: center;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.2);
        }
        .modal h1 {
            font-size: 24px;
            color: #ff6f61;
            margin-bottom: 15px;
        }
        .modal p {
            font-size: 16px;
            color: white;
            margin: 10px 0;
            line-height: 1.5;
        }
        .button {
            display: inline-block;
            margin: 10px;
            padding: 15px 25px;
            font-size: 18px;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: background 0.3s, transform 0.2s, box-shadow 0.3s;
            background: #666;
            width: 300px;
        }
        .button:hover {
            background: #999;
            transform: scale(1.1);
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.5);
        }
        footer {
            background: #222;
            color: white;
            padding: 10px;
            position: relative;
            width: 100%;
            text-align: center;
            opacity: 0.7;
            margin-top: 40px;
        }
    </style>
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            const infoBoxes = document.querySelectorAll(".info-box");
            infoBoxes.forEach((box, index) => {
                setTimeout(() => {
                    box.style.opacity = "1";
                    box.style.transform = "translateY(0)";
                }, index * 500);
            });

            const infoBoxButtons = document.querySelectorAll(".info-box-button");
            const modalOverlay = document.querySelector(".modal-overlay");

            infoBoxButtons.forEach(button => {
                button.addEventListener("click", () => {
                    modalOverlay.classList.add("active");
                });
            });

            modalOverlay.addEventListener("click", (event) => {
                if (event.target === modalOverlay) {
                    modalOverlay.classList.remove("active");
                }
            });
        });
    </script>
</head>
<body>
    <video id="video-background" autoplay muted loop>
        <source src="https://media.istockphoto.com/id/1320462805/ru/%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE/%D0%B2%D1%8B%D1%81%D0%BE%D0%BA%D0%BE%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%87%D0%BD%D1%8B%D0%B5-%D0%B3%D1%80%D0%B0%D1%84%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D1%84%D0%BE%D0%BD%D1%8B-%D0%B4%D0%B2%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D1%80%D0%B0%D1%81%D0%B8%D0%B2%D1%8B%D0%B9-%D0%BA%D1%80%D0%B0%D1%81%D0%BE%D1%87%D0%BD%D1%8B%D0%B9-%D1%84%D0%BE%D0%BD.mp4?s=mp4-640x640-is&k=20&c=sNw8mDxxjT7AFsS_jR-3ufd_ue5qHrLn7pCi09MAgiE=" type="video/mp4">
    </video>
    <section>
        <h1>Добро пожаловать в моё цифровое портфолио!</h1>
        <p>Меня зовут Арсений, и это история моего пути в мире программирования</p>
        
        <div class="info-box">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQum8sFl1RkwcG9CENO9m7rVKX5cQCH_o5mZw&s" alt="Начало пути">
            <h2>Мои первые шаги в IT</h2>
            <p>В 2021 году я открыл для себя мир программирования. Начав с основ HTML и CSS, я создал свои первые веб-страницы и разместил их на GitHub.</p>
            <p>Этот год запомнился мне участием в первых хакатонах, где я получил бесценный опыт командной работы и решения реальных задач.</p>
            
            <h2>Прорыв и новые технологии</h2>
            <p>2023 год стал переломным моментом: я освоил Python и C++, а также погрузился в разработку игр на Unity с C#.</p>
            <p>Среди моих проектов:</p>
            <ul>
                <li>3D дудл-игра с собственной графикой</li>
                <li>2D платформер с уникальной механикой</li>
                <li>3D шахматы с кастомными моделями</li>
                <li>Интерактивный 3D калькулятор</li>
            </ul>
            <button class="info-box-button">Узнать больше</button>
        </div>
        
        <div class="info-box">
            <img src="https://i.pinimg.com/564x/92/99/dd/9299dd89a8ebdf253d2c36702f11e9c4.jpg" alt="Планы на будущее">
            <h2>Мои цели и планы развития</h2>
            <p>Сейчас я сосредоточен на углубленном изучении языка C++ и системного программирования. В ближайших планах:</p>
            <ul>
                <li>Освоение Java script для создания интерактивности на сайтах</li>
                <li>Изучение Machine Learning на Python</li>
                <li>Разработка собственного игрового движка</li>
                <li>Участие в крупных open-source проектах</li>
            </ul>
            <p>Особый интерес для меня представляет область искусственного интеллекта и его практическое применение.</p>
            <button class="info-box-button">Мои навыки</button>
        </div>
        
        <a href="https://github.com/15SAVAGE" class="button">Посмотреть мои проекты на GitHub</a>
        <a href="#" class="button" style="background: #ff6f61;">Связаться со мной</a>
    </section>

    <div class="modal-overlay">
        <div class="modal">
            <h1>Дополнительные детали</h1>
            <p>В 2023 году я обзавелся мощным ноутбуком, что позволило мне работать над более сложными проектами. Именно на этом устройстве было создано большинство моих работ.</p>
            <p>В моих архивах хранятся несколько перспективных незавершенных проектов с инновационными идеями. К сожалению, некоторые разработки пришлось удалить из-за ограниченного места на диске.</p>
            <p>Наиболее продуктивный период начался в 2024 году, когда я смог сосредоточиться на серьезном программировании и создании лучшийх решений.</p>
        </div>
    </div>
    
   
</body>
</html>
