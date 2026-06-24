<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Favorite Person ❤️</title>
    <style>
        :root {
            --primary-color: #ff477e;
            --secondary-color: #ff85a1;
            --bg-color: #ffe5ec;
            --text-color: #4a4a4a;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            overflow-x: hidden;
        }

        /* --- Navbar --- */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            padding: 15px 0;
            display: flex;
            justify-content: center;
            gap: 15px;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            flex-wrap: wrap;
        }

        nav a {
            text-decoration: none;
            color: var(--primary-color);
            font-weight: bold;
            font-size: 0.9rem;
            transition: 0.3s;
            padding: 5px 10px;
            border-radius: 15px;
        }

        nav a:hover {
            background: var(--primary-color);
            color: white;
        }

        /* --- Sections General --- */
        section {
            padding: 100px 20px 60px 20px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 30px;
            position: relative;
        }

        /* --- Home & Countdown --- */
        #home {
            background: linear-gradient(135deg, #ffe5ec, #ffc2d1);
        }

        .main-title {
            font-size: 3.5rem;
            color: var(--primary-color);
            margin-bottom: 20px;
            animation: heartBeat 2s infinite;
        }

        .countdown-container {
            background: white;
            padding: 20px 40px;
            border-radius: 50px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
            margin-top: 20px;
        }

        #timer {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--text-color);
        }

        /* --- Our Story (Timeline) --- */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 4px;
            background: var(--primary-color);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
        }

        .timeline-item {
            padding: 10px 40px;
            position: relative;
            background-color: inherit;
            width: 50%;
        }

        .timeline-item::after {
            content: '❤️';
            position: absolute;
            width: 25px;
            height: 25px;
            right: -17px;
            top: 15px;
            background-color: white;
            border-radius: 50%;
            z-index: 1;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .left { left: 0; text-align: right; }
        .right { left: 50%; text-align: left; }
        .right::after { left: -12px; }

        .content {
            padding: 20px;
            background: white;
            position: relative;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        /* --- Gallery --- */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            width: 100%;
            max-width: 1000px;
        }

        .gallery-item {
            background: white;
            padding: 15px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }

        .gallery-item:hover {
            transform: scale(1.05) rotate(2deg);
        }

        .gallery-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
        }

        .gallery-item p {
            margin-top: 10px;
            font-style: italic;
        }

        /* --- Love Letter --- */
        .btn {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1rem;
            border-radius: 30px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(255, 71, 126, 0.4);
            transition: 0.3s;
        }

        .btn:hover {
            background: #ff0a54;
            transform: translateY(-3px);
        }

        .hidden-letter {
            display: none;
            max-width: 600px;
            background: white;
            padding: 40px;
            border-radius: 20px;
            margin-top: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            line-height: 1.8;
            text-align: left;
            border-left: 8px solid var(--primary-color);
            animation: fadeIn 1s ease;
        }

        /* --- Reasons I Love You --- */
        .reasons-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            max-width: 800px;
        }

        .reason-card {
            background: white;
            padding: 20px;
            border-radius: 15px;
            width: 220px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: 0.3s;
            border-bottom: 4px solid var(--secondary-color);
        }

        .reason-card:hover {
            transform: translateY(-5px);
        }

        /* --- Quiz & Interactive --- */
        .quiz-container {
            background: white;
            padding: 30px;
            border-radius: 20px;
            max-width: 500px;
            width: 100%;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
        }

        .quiz-btn {
            background: #f0f0f0;
            border: 2px solid var(--secondary-color);
            padding: 10px 20px;
            margin: 10px 5px;
            border-radius: 20px;
            cursor: pointer;
            width: 80%;
            transition: 0.2s;
        }

        .quiz-btn:hover {
            background: var(--secondary-color);
            color: white;
        }

        /* --- Music Floating --- */
        .music-box {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: white;
            padding: 10px;
            border-radius: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            z-index: 1000;
        }

        /* --- Animations --- */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes heartBeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Responsive */
        @media screen and (max-width: 600px) {
            .timeline::after { left: 31px; }
            .timeline-item { width: 100%; padding-left: 70px; padding-right: 25px; }
            .timeline-item::after { left: 18px; }
            .left, .right { text-align: left; left: 0; }
            .main-title { font-size: 2.3rem; }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav>
        <a href="#home">Home</a>
        <a href="#story">Our Story</a>
        <a href="#gallery">Gallery</a>
        <a href="#letter">Love Letter</a>
        <a href="#reasons">Reasons</a>
        <a href="#quiz">Fun Quiz</a>
        <a href="#surprise">Birthday Wish</a>
    </nav>

    <!-- Music Player (Replace URL with her favorite song link if you want, or keep standard) -->
    <div class="music-box">
        🎵 <audio id="bg-music" src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" controls style="width: 150px; height: 30px;"></audio>
    </div>

    <!-- 1. Home & Countdown -->
    <section id="home">
        <h1 class="main-title">Hey Beautiful ✨</h1>
        <p>Welcome to our own little corner of the internet.</p>
        <div class="countdown-container">
            <p>Time passed since we became "Us" ❤️</p>
            <div id="timer">Loading counter...</div>
        </div>
    </section>

    <!-- 2. Our Story (Timeline) -->
    <section id="story">
        <h2>Our Story Timeline ❤️</h2>
        <div class="timeline">
            <div class="timeline-item left">
                <div class="content">
                    <h3>How We Met 🌟</h3>
                    <p>[তারিখ বা দিন] - সেই প্রথম তোমাকে দেখা। দুনিয়াটা হঠাৎ করেই সুন্দর হয়ে গিয়েছিল।</p>
                </div>
            </div>
            <div class="timeline-item right">
                <div class="content">
                    <h3>First Conversation 💬</h3>
                    <p>আমাদের প্রথম হাই-হ্যালো, প্রথম টেক্সট। কথা বলতে বলতে কখন যে রাত পার হয়ে যেত!</p>
                </div>
            </div>
            <div class="timeline-item left">
                <div class="content">
                    <h3>First Photo Together 📸</h3>
                    <p>প্রথম একসাথে ছবি তোলার সেই মিষ্টি লজ্জা আর তোমার ওই সুন্দর হাসিটা!</p>
                </div>
            </div>
            <div class="timeline-item right">
                <div class="content">
                    <h3>Special Memories ✨</h3>
                    <p>সবগুলো ডেট, ঝগড়া, মান-অভিমান আর দিনশেষে আরও গভীরভাবে কাছে আসা।</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 3. Memory Gallery -->
    <section id="gallery">
        <h2>Memory Gallery 📸</h2>
        <div class="gallery-grid">
            <!-- Replace 'https://via.placeholder.com/300' with your actual image URLs -->
            <div class="gallery-item">
                <img src="https://via.placeholder.com/300" alt="Memory 1">
                <p>আমাদের সেই সুন্দর দিনটি 🌸</p>
            </div>
            <div class="gallery-item">
                <img src="https://via.placeholder.com/300" alt="Memory 2">
                <p>তোমার হাসির প্রেমে পড়ার দিন 💕</p>
            </div>
            <div class="gallery-item">
                <img src="https://via.placeholder.com/300" alt="Memory 3">
                <p>সবচেয়ে প্রিয় স্মৃতি 🌙</p>
            </div>
        </div>
    </section>

    <!-- 4. Digital Love Letter -->
    <section id="letter">
        <h2>Digital Love Letters ✨</h2>
        <p style="margin-bottom: 20px;">I wrote something from the bottom of my heart...</p>
        <button class="btn" onclick="toggleLetter()">Click here for a surprise</button>
        
        <div id="love-letter" class="hidden-letter">
            <h3>My Dearest,</h3>
            <br>
            <p>তুমি আমার জীবনে আসার পর থেকে প্রতিটি দিন একদম বদলে গেছে। তোমার ওই মিষ্টি হাসি, আমার মন খারাপের দিনে তোমার কথা বলা, আর সব পরিস্থিতিতে আমার পাশে থাকা—আমি সত্যিই অনেক ভাগ্য করে তোমাকে পেয়েছি।</p>
            <p>আজকের এই বিশেষ দিনে আমি তোমাকে জানাতে চাই, আমি তোমাকে কতটা ভালোবাসি। সারাজীবন এভাবেই তোমার হাতটা ধরে পাশে থাকতে চাই।</p>
            <br>
            <p><strong>ইতি,</strong><br>তোমার চিরকালের [তোমার নাম]</p>
        </div>
    </section>

    <!-- 5. Reasons Why I Love You -->
    <section id="reasons">
        <h2>Reasons Why I Love You 💌</h2>
        <div class="reasons-container">
            <div class="reason-card">
                <h3>Reason #1</h3>
                <p>Your smile makes my worst days so much better.</p>
            </div>
            <div class="reason-card">
                <h3>Reason #2</h3>
                <p>You always listen to me, even when I talk nonsense.</p>
            </div>
            <div class="reason-card">
                <h3>Reason #3</h3>
                <p>The way you care for me like no one else can.</p>
            </div>
            <div class="reason-card">
                <h3>Reason #4</h3>
                <p>Your kindness and the beautiful soul you have.</p>
            </div>
        </div>
    </section>

    <!-- 6. Fun Quiz -->
    <section id="quiz">
        <h2>How Well Do You Know Us? 🎁</h2>
        <div class="quiz-container">
            <p id="quiz-question">Where did we talk for the very first time?</p>
            <button class="quiz-btn" onclick="checkAnswer(true)">Facebook/Instagram 📱</button>
            <button class="quiz-btn" onclick="checkAnswer(false)">In Person 🏫</button>
            <p id="quiz-result" style="margin-top: 15px; font-weight: bold; color: var(--primary-color);"></p>
        </div>
    </section>

    <!-- 7. Final Surprise Section -->
    <section id="surprise" style="background: linear-gradient(to bottom, #ffe5ec, #fbc4ab);">
        <h2 style="font-size: 3rem;">Happy Birthday, My Love! 🌙</h2>
        <p style="font-size: 1.3rem; max-width: 600px; margin-top: 20px;">
            Thank you for being part of my life. Thank you for being YOU. 
            May all your dreams come true, and I promise to be there to celebrate every single one of them with you.
        </p>
        <p style="font-size: 2rem; margin-top: 30px;">Forever & Always ❤️</p>
    </section>

    <script>
        // --- 1. Countdown Timer Logic ---
        // Set the date when you started dating (Year, Month [0-11], Day, Hour, Minute)
        // Note: January is 0, February is 1, etc.
        const anniversaryDate = new Date(2024, 4, 15, 0, 0, 0); 

        function updateCountdown() {
            const now = new Date();
            const diff = now - anniversaryDate;

            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((diff % (1000 * 60)) / 1000);

            document.getElementById("timer").innerHTML = 
                `${days} Days, ${hours} Hours, ${minutes} Mins, ${seconds} Secs`;
        }
        setInterval(updateCountdown, 1000);

        // --- 2. Toggle Love Letter ---
        function toggleLetter() {
            const letter = document.getElementById("love-letter");
            if (letter.style.display === "block") {
                letter.style.display = "none";
            } else {
                letter.style.display = "block";
                letter.scrollIntoView({ behavior: 'smooth' });
            }
        }

        // --- 3. Simple Quiz Logic ---
        function checkAnswer(isCorrect) {
            const result = document.getElementById("quiz-result");
            if(isCorrect) {
                result.innerHTML = "Correct! 🌟 You remember everything!";
            } else {
                result.innerHTML = "Oops! 🙈 Try recalling our early days again!";
            }
        }
    </script>
</body>
</html>
