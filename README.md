<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Dhanush</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            text-align: center;
            color: #24292f;
        }

        h1 {
            font-size: 28px;
            margin: 20px 0;
        }

        .welcome {
            font-size: 28px;
            font-weight: bold;
            font-family: monospace;
            letter-spacing: 2px;
            margin: 25px 0;

            background: linear-gradient(
                90deg,
                #00d9ff,
                #007bff,
                #7b61ff,
                #b14eff,
                #d946ef,
                #ff4f81
            );

            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .tagline {
            font-size: 18px;
            font-weight: 600;
            margin: 20px 0;
        }
    </style>
</head>

<body>

    <h1>👋 Hey, I'm Dhanush</h1>

    <div class="welcome" id="welcome"></div>

    <div class="tagline">
        Just building things & enjoying the process 🚀
    </div>


    <script>

        const phrases = [
            "Welcome",
            "Welcome to",
            "Welcome to my",
            "Welcome to my GitHub 🚀"
        ];

        const welcome = document.getElementById("welcome");

        let phraseIndex = 0;
        let charIndex = 0;
        let deleting = false;

        function typeEffect() {

            const currentPhrase = phrases[phraseIndex];

            if (!deleting) {

                welcome.textContent =
                    currentPhrase.substring(0, charIndex + 1);

                charIndex++;

                if (charIndex === currentPhrase.length) {

                    setTimeout(() => {
                        deleting = true;
                        typeEffect();
                    }, 1000);

                    return;
                }

            } else {

                welcome.textContent =
                    currentPhrase.substring(0, charIndex - 1);

                charIndex--;

                if (charIndex === 0) {

                    deleting = false;
                    phraseIndex++;

                    if (phraseIndex >= phrases.length) {
                        phraseIndex = 0;
                    }
                }
            }

            setTimeout(typeEffect, deleting ? 50 : 100);
        }

        typeEffect();

    </script>

</body>
</html>
