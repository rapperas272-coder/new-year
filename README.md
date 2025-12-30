<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy New Year, ANCHAL</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to bottom, #000, #001122);
            color: white;
            text-align: center;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }
        h1 {
            font-size: 3em;
            margin-top: 20px;
        }
        #countdown {
            font-size: 2em;
            margin: 20px;
        }
        .time-unit {
            display: inline-block;
            margin: 0 10px;
        }
        .firework {
            position: absolute;
            width: 5px;
            height: 5px;
            background: yellow;
            border-radius: 50%;
            animation: explode 2s infinite;
        }
        @keyframes explode {
            0% { transform: scale(0); opacity: 1; }
            50% { transform: scale(1); opacity: 0.5; }
            100% { transform: scale(2); opacity: 0; }
        }
        #message {
            font-size: 1.5em;
            margin-top: 50px;
        }
    </style>
</head>
<body>
    <h1>Happy New Year, ANCHAL!</h1>
    <div id="countdown">
        <div class="time-unit"><span id="days">00</span> Days</div>
        <div class="time-unit"><span id="hours">00</span> Hours</div>
        <div class="time-unit"><span id="minutes">00</span> Minutes</div>
        <div class="time-unit"><span id="seconds">00</span> Seconds</div>
    </div>
    <p id="message">Here's to a year of adventures, laughter, and unforgettable memories together. You're the best friend anyone could ask for! 🎉</p>

    <script>
        // Set the date we're counting down to (New Year)
        const countDownDate = new Date(new Date().getFullYear() + 1, 0, 1).getTime();

        // Update the count down every 1 second
        const x = setInterval(function() {
            const now = new Date().getTime();
            const distance = countDownDate - now;

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerHTML = days;
            document.getElementById("hours").innerHTML = hours;
            document.getElementById("minutes").innerHTML = minutes;
            document.getElementById("seconds").innerHTML = seconds;

            // If the count down is over, write some text 
            if (distance < 0) {
                clearInterval(x);
                document.getElementById("countdown").innerHTML = "HAPPY NEW YEAR!";
                // Add fireworks
                for (let i = 0; i < 50; i++) {
                    const firework = document.createElement("div");
                    firework.className = "firework";
                    firework.style.left = Math.random() * 100 + "%";
                    firework.style.top = Math.random() * 100 + "%";
                    firework.style.animationDelay = Math.random() * 2 + "s";
                    document.body.appendChild(firework);
                }
            }
        }, 1000);
    </script>
</body>
</html>
