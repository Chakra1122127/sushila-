<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Happy Birthday Sushila 🎂</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            min-height: 100vh;
            overflow: hidden;
            font-family: Arial, sans-serif;

            display: flex;
            align-items: center;
            justify-content: center;

            background: linear-gradient(
                135deg,
                #ffe6f2,
                #e8f4ff
            );

            color: #333;
        }

        /* Main Birthday Card */
        .card {
            width: min(90%, 620px);
            padding: 45px 28px;
            text-align: center;

            background: rgba(255, 255, 255, 0.86);

            border-radius: 28px;

            box-shadow:
                0 15px 45px rgba(80, 80, 120, 0.18);

            position: relative;
            z-index: 2;
        }

        /* Birthday Heading */
        h1 {
            font-size: clamp(2.2rem, 8vw, 4.5rem);
            margin: 10px 0;
            color: #ff5c9a;
        }

        h2 {
            font-size: 1.5rem;
            color: #555;
        }

        /* Birthday Message */
        .message {
            font-size: 1.08rem;
            line-height: 1.7;
            margin: 24px auto;
            max-width: 500px;
        }

        /* Celebrate Button */
        button {
            border: none;

            padding: 13px 24px;

            border-radius: 30px;

            cursor: pointer;

            background: #ff6fa8;
            color: white;

            font-size: 1rem;

            box-shadow:
                0 7px 18px #ff6fa855;

            transition: 0.3s;
        }

        button:hover {
            transform: scale(1.05);
        }

        /* Sender */
        .from {
            margin-top: 25px;
            font-weight: bold;
            color: #777;
        }

        /* Balloons */
        .balloon {
            position: absolute;

            bottom: -120px;

            width: 42px;
            height: 55px;

            border-radius: 50%;

            animation:
                float 9s linear infinite;

            opacity: 0.8;

            z-index: 1;
        }

        /* Balloon String */
        .balloon::after {
            content: "";

            position: absolute;

            bottom: -18px;
            left: 20px;

            width: 1px;
            height: 22px;

            background: #777;
        }

        /* Balloon Animation */
        @keyframes float {

            from {
                transform:
                    translateY(0)
                    rotate(0deg);
            }

            to {
                transform:
                    translateY(-120vh)
                    rotate(18deg);
            }
        }

        /* Confetti */
        .confetti {
            position: fixed;

            top: -15px;

            width: 9px;
            height: 14px;

            z-index: 5;

            animation:
                fall 3s linear forwards;
        }

        /* Confetti Animation */
        @keyframes fall {

            to {
                transform:
                    translateY(110vh)
                    rotate(720deg);

                opacity: 0;
            }
        }
    </style>
</head>

<body>

    <!-- Birthday Card -->
    <div class="card">

        <div style="font-size: 3rem;">
            🎂🎈✨
        </div>

        <h1>
            Happy Birthday!
        </h1>

        <h2>
            Dear SUSHILA 💖
        </h2>

        <p class="message">

            Wishing you a very Happy Birthday! 🎉
            <br>

            May your day be filled with happiness,
            laughter, beautiful memories and lots of
            reasons to smile. 😊

            <br>

            Keep shining and always stay happy! 🌸

        </p>

        <button onclick="celebrate()">
            🎉 Celebrate!
        </button>

        <p class="from">

            With best wishes,

            <br>

            <strong>
                Chakra Dev Badu 💫
            </strong>

        </p>

    </div>


    <script>

        /* --------------------------------
           CREATE FLOATING BALLOONS
        -------------------------------- */

        function makeBalloon(i) {

            const balloon =
                document.createElement("div");

            balloon.className =
                "balloon";

            /* Random horizontal position */

            balloon.style.left =
                (Math.random() * 100) + "vw";


            /* Balloon colors */

            const colors = [
                "#ff8fab",
                "#ffd166",
                "#8ecae6",
                "#b8e986",
                "#cdb4db"
            ];

            balloon.style.background =
                colors[i % colors.length];


            /* Random animation speed */

            balloon.style.animationDuration =
                (7 + Math.random() * 5) + "s";


            /* Random animation delay */

            balloon.style.animationDelay =
                (Math.random() * 5) + "s";


            document.body.appendChild(
                balloon
            );
        }


        /* Create 14 balloons */

        for (let i = 0; i < 14; i++) {

            makeBalloon(i);

        }



        /* --------------------------------
           CELEBRATE BUTTON
        -------------------------------- */

        function celebrate() {

            /* Create 90 confetti pieces */

            for (let i = 0; i < 90; i++) {

                const confetti =
                    document.createElement("div");

                confetti.className =
                    "confetti";


                /* Random position */

                confetti.style.left =
                    Math.random() * 100 + "vw";


                /* Confetti colors */

                const colors = [
                    "#ff6fa8",
                    "#ffd166",
                    "#6ecbff",
                    "#9be564",
                    "#b28dff"
                ];

                confetti.style.background =
                    colors[i % colors.length];


                /* Random falling delay */

                confetti.style.animationDelay =
                    Math.random() * 1.2 + "s";


                /* Random rotation */

                confetti.style.transform =
                    "rotate(" +
                    Math.random() * 360 +
                    "deg)";


                document.body.appendChild(
                    confetti
                );


                /* Remove after animation */

                setTimeout(() => {

                    confetti.remove();

                }, 4500);

            }

        }

    </script>

</body>
</html>
