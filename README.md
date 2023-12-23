# Simple-Countdown-Time
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Countdown Timer</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="timer">
        <div id="countdown">10:00</div>
        <button onclick="startTimer()">Start Countdown</button>
    </div>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: 'Arial', sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.timer {
    text-align: center;
}

#countdown {
    font-size: 2em;
    margin-bottom: 10px;
}

button {
    padding: 10px 20px;
    font-size: 1em;
    cursor: pointer;
}
let timer;
let timeLeft = 600; // 10 minutes in seconds

function startTimer() {
    if (!timer) {
        timer = setInterval(updateTimer, 1000);
    }
}

function updateTimer() {
    const minutes = Math.floor(timeLeft / 60);
    const seconds = timeLeft % 60;

    document.getElementById('countdown').textContent = `${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;

    if (timeLeft > 0) {
        timeLeft--;
    } else {
        clearInterval(timer);
        timer = null;
        alert('Countdown finished!');
    }
}
