<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Vocabulary List</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #333;
        }

        #word-list-container {
            width: 80%;
            max-width: 600px;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        h2 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 20px;
        }

        .word-item {
            background-color: #e8eaf6;
            border-left: 5px solid #3f51b5;
            margin-bottom: 8px;
            padding: 10px 20px;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: transform 0.2s ease-in-out;
        }

        .word-item:hover {
            transform: scale(1.02);
            background-color: #c5cae9;
        }

        .word-item:last-child {
            margin-bottom: 0;
        }

        .word-item span {
            font-size: 16px;
        }

        /* Responsive design adjustments */
        @media (max-width: 768px) {
            body {
                padding: 20px;
                height: auto;
                flex-direction: column;
            }

            #word-list-container {
                width: 100%;
                max-width: none;
            }
        }
    </style>
</head>
<body>

<div id="word-list-container">
    <h2>桂樂芙單字庫</h2>
    <div id="word-list"></div>
</div>

<script>
    const wordsString = `Apple; Banana; Cat; 魂不附體：形容驚嚇過度而心不能自主;`; // Your words and phrases here, separated by semicolons
    const words = wordsString.split(';').filter(Boolean); // Use semicolon as separator

    function renderWords() {
        const listElement = document.getElementById('word-list');
        listElement.innerHTML = '';

        words.forEach(word => {
            const wordDiv = document.createElement('div');
            wordDiv.classList.add('word-item');
            wordDiv.textContent = word.trim();
            listElement.appendChild(wordDiv);
        });
    }

    renderWords();
</script>

</body>
</html>
