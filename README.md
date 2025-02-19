<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HSC Exam Countdown</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #282c36;
            color: #ffffff;
            padding: 50px;
        }
        #countdown {
            font-size: 2em;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>HSC Exam Countdown</h1>
    <p>Time remaining until your HSC exam starts:</p>
    <div id="countdown"></div>

    <script>
        function updateCountdown() {
            const examDate = new Date('June 26, 2025 00:00:00').getTime();
            const now = new Date().getTime();
            const timeLeft = examDate - now;

            const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

            document.getElementById('countdown').innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;

            if (timeLeft <= 0) {
                document.getElementById('countdown').innerHTML = "HSC Exam Started!";
            }
        }

        setInterval(updateCountdown, 1000);
    </script>
</body>
</html>
