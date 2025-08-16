<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>hehe</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f9ff;
            overflow: hidden; /* Prevent scrollbars from showing */
        }
        .letter-container {
            background: #fff;
            padding: 2.5rem;
            border-radius: 1.5rem;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            position: relative;
            z-index: 10;
        }
        .confession-text {
            line-height: 1.75;
            text-align: center;
        }
        .floating-emoji {
            position: absolute;
            animation: float 10s infinite linear, fade-in-out 10s infinite;
            z-index: 5;
            font-size: 2.5rem; /* Large enough to be seen */
        }

        /* Define the floating animation */
        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            50% { transform: translateY(-50px) rotate(10deg); }
            100% { transform: translateY(0) rotate(0deg); opacity: 1; }
        }

        /* Define the fade in and out animation */
        @keyframes fade-in-out {
            0% { opacity: 0; }
            20% { opacity: 1; }
            80% { opacity: 1; }
            100% { opacity: 0; }
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen p-4">

    <!-- The main letter container -->
    <div class="letter-container max-w-2xl w-full mx-auto">
        <h1 class="text-4xl font-bold text-center text-rose-500 mb-6"> ❤️</h1>
        <div class="confession-text text-gray-700 space-y-4">
            <p>HI</p>
        </div>
    </div>

    <!-- Cat and heart emojis that will be animated with JavaScript -->
    <div class="absolute inset-0 z-0" id="emoji-container"></div>
    
    <script>
        const emojis = ['❤️', '😻', '✨', '🐾'];
        const container = document.getElementById('emoji-container');

        // Function to create and add a sing, le emoji element
        function createEmoji() {
            const emoji = document.createElement('span');
            emoji.classList.add('floating-emoji');
            emoji.textContent = emojis[Math.floor(Math.random() * emojis.length)];

            // Set random starting position
            const startX = Math.random() * window.innerWidth;
            const startY = Math.random() * window.innerHeight;
            emoji.style.left = `${startX}px`;
            emoji.style.top = `${startY}px`;

            // Randomize animation duration and delay
            const duration = Math.random() * 5 + 8; // Between 8 and 13 seconds
            const delay = Math.random() * 5; // Between 0 and 5 seconds
            emoji.style.animationDuration = `${duration}s`;
            emoji.style.animationDelay = `${delay}s`;

            container.appendChild(emoji);
        }

        // Create a bunch of emojis on load
        window.onload = function() {
            for (let i = 0; i < 30; i++) {
                createEmoji();
            }
        };

    </script>

</body>
</html>

