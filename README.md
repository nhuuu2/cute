<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cute Love Page</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #f7d4d4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Courier New', Courier, monospace;
            overflow: hidden;
        }
        .container {
            text-align: center;
        }
        img {
            width: 100px;
            margin-bottom: 20px;
            transition: all 0.3s ease;
            mix-blend-mode: multiply;
        }
        h1 {
            font-size: 24px;
            color: #333;
            margin-bottom: 20px;
        }
        .button {
            background-color: #ec8b8b;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            font-size: 18px;
            cursor: pointer;
            margin: 5px;
            transition: all 0.3s ease;
        }
        .button:hover {
            background-color: #d86b6b;
        }
        .blue-button {
            background-color: #8aaed4;
        }
        .message {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 36px;
            color: #333;
            background: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
            display: none;
        }
    </style>
    <script>
        let clickCount = 0;
        const images = [
            'https://i.pinimg.com/736x/c8/8d/1f/c88d1f8560ff470b8d86949f0f94e57a.jpg',
            'https://i.pinimg.com/736x/75/87/83/758783fdf900d5404d298cd992cc8369.jpg',
            'https://i.pinimg.com/736x/a8/15/15/a815154158bb2b321ed45737edb9a9c1.jpg',
            'https://i.pinimg.com/736x/55/0a/e5/550ae5af90765f34df671e3aed16a00b.jpg'
        ];
        const messages = [
            'Không',
            'Anh không giúp em dỗi',
            'Bùn nhaa',
            'Có giúp không thì bảo'
        ];

        function handleNoButtonClick() {
            const noButton = document.querySelector('.button.blue-button');
            const yesButton = document.querySelector('.button:not(.blue-button)');
            const image = document.querySelector('img');
            if (clickCount < 4) {
                yesButton.style.transform = `scale(${1 - clickCount * 0.1})`;
                noButton.style.transform = `scale(${1 + clickCount * 0.1})`;
                image.src = images[clickCount];
                noButton.textContent = messages[clickCount];
                clickCount++;
            }
        }

        function handleYesButtonClick() {
            const message = document.querySelector('.message');
            document.querySelectorAll('h1, img, .button').forEach(el => el.style.display = 'none');
            message.style.display = 'block';
        }
    </script>
</head>
<body>
    <div class="container">
        <img src="https://i.pinimg.com/736x/c8/8d/1f/c88d1f8560ff470b8d86949f0f94e57a.jpg" alt="Cute character">
        <h1>Anh có thể làm bài tập giúp em được không?</h1>
        <button class="button" onclick="handleYesButtonClick()">Có thể</button>
        <button class="button blue-button" onclick="handleNoButtonClick()">Không</button>
        <div class="message">Cảm ơn anh nhiều! 😘</div>
    </div>
</body>
</html>

