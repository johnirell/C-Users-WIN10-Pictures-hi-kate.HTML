<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Confession Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-image: url('https://source.unsplash.com/1600x900/?flowers');
            background-color: #aa0aa283; /* Fallback for background image */
            background-size: cover;
            background-repeat: no-repeat;
            background-attachment: fixed;
            color: white;
            text-align: center;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background: rgba(0, 0, 0, 0.8);
            border-radius: 15px;
            width: 80%;
            max-width: 600px;
            padding: 40px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.5);
            text-align: center;
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 20px;
            letter-spacing: 1px;
        }
        p {
            font-size: 1.2em;
            margin-bottom: 30px;
        }
        .button-container {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 20px;
        }
        button {
            background-color: #f54a3b;
            color: rgb(250, 250, 250);
            border: none;
            padding: 15px 40px;
            border-radius: 8px;
            font-size: 18px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.2s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        button:hover {
            background-color: #e65c50;
            transform: translateY(-5px);
        }
        #noButton {
            position: absolute;
        }
        /* Media Queries for responsiveness */
        @media (max-width: 768px) {
            .container {
                width: 90%;
            }
            button {
                padding: 12px 30px;
            }
        }
    </style>
</head>
<body>
    <div class="container" id="questionContainer" role="dialog" aria-labelledby="questionTitle" aria-describedby="questionText">
        <h1 id="questionTitle">Hi Kate!</h1>
        <p id="questionText">I have questions for u. to start pls tap YES <3 </p>
        <div class="button-container">
            <button id="yesButton" aria-label="Yes" onclick="nextQuestion(true)">Yes</button>
            <button id="noButton" aria-label="No" onclick="moveNoButton()">No</button>
        </div>
    </div>

    <script>
 
 const questions = [
 "Do you like coffee?",
            "Would you like to visit the coffee shop with me?",
            "How about trying some new pastries?",   
 
            "eto na talaga mga tanong hehe <3",
            "tap yes mo lang para mag next",
            "I'm sorry kung natagalan ako",
            "eh hinihintay mo ba ako? haha ouch ;<",
            "eto na talaga hehehehe <3",
            "I HAVE SOMETHING TO SAY", 
            "DO I STILL HAVE A CHANCE WITH YOU?",
            "CAN I COURT YOU?",
            "gusto kong ibalik yung dating bond natin",
            "at higitan pa ron",
            "I'll be honest",
            "lagi kitang naiisip, lagi kang tumatakbo sa utak ko di ka ba napapagod? charot hehehe lab u <3",
            "pero totoo, relate ako sa everything reminds me of u haha ;<",
            "I miss you Kate :< ",
            "so",
            "CAN I COURT YOU KATE?",
            
        ];

        let currentQuestionIndex = 0;
        const questionTitle = document.getElementById('questionTitle');
        const questionText = document.getElementById('questionText');
        const noButton = document.getElementById('noButton');

        function moveNoButton() {
            const randomX = Math.random() * (window.innerWidth - noButton.offsetWidth);
            const randomY = Math.random() * (window.innerHeight - noButton.offsetHeight);
            noButton.style.left = randomX + 'px';
            noButton.style.top = randomY + 'px';
        }

        function nextQuestion(yes) {
            if (yes) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questions.length) {
                    questionTitle.textContent = "Question " + (currentQuestionIndex + 1);
                    questionText.textContent = questions[currentQuestionIndex];
                } else {
                    questionTitle.textContent = "Thank you Kate!";
                    questionText.textContent = "I hope you appreciate this";
                    document.querySelector('.button-container').style.display = 'none';
                }
            }
        }

        window.addEventListener('resize', moveNoButton);
    </script>
</body>
</html>
