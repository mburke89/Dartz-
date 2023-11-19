# Dartz-
Simple dart game. 
echo "# Dartz-" >> README.md
  git init
  git add README.md
  git commit -m "first commit"
  git branch -M main
  git remote add origin https://github.com/mburke89/Dartz-.git
  git push -u origin main
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Darts Game</title>
    <style>
        #dartboard {
            width: 400px;
            height: 400px;
            background: url('dartboard.jpg'); /* Replace with your dartboard image */
            background-size: cover;
            position: relative;
        }

        #player-image {
            position: absolute;
            width: 50px; /* Adjust size as needed */
            height: 50px; /* Adjust size as needed */
        }
    </style>
</head>
<body>
    <div id="dartboard" onclick="throwDart(event)">
        <img id="player-image" src="" alt="Player" draggable="false">
    </div>

    <div id="score-container">
        <h2>Score:</h2>
        <p id="score">0</p>
        <p id="insult">Ready for a challenge?</p>
    </div>

    <script>
        let score = 0;

        function throwDart(event) {
            const dartboard = document.getElementById('dartboard');
            const playerImage = document.getElementById('player-image');
            const scoreContainer = document.getElementById('score');
            const insultContainer = document.getElementById('insult');

            // Get click coordinates
            const x = event.clientX - dartboard.getBoundingClientRect().left;
            const y = event.clientY - dartboard.getBoundingClientRect().top;

            // Move player image to click position
            playerImage.style.left = x + 'px';
            playerImage.style.top = y + 'px';

            // Simulate scoring (random score for simplicity)
            const roundScore = Math.floor(Math.random() * 21); // Score between 0 and 20
            score += roundScore;

            // Display score
            scoreContainer.textContent = score;

            // Display a random insult
            const insults = ['Nice try!', 'Not bad!', 'Keep it up!', 'Almost there!', 'You got this!'];
            insultContainer.textContent = insults[Math.floor(Math.random() * insults.length)];
        }
    </script>
</body>
</html>
