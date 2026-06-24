<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday My Love ❤️</title>
    <style>
        :root {
            --primary-color: #ff477e;
            --secondary-color: #ff85a1;
            --bg-color: #fff0f3;
            --text-color: #4a4a4a;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            overflow-x: hidden;
        }

        /* --- Fullpage Sections --- */
        section {
            min-height: 100vh;
            width: 100vw;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 40px 20px;
            text-align: center;
            position: relative;
        }

        h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 30px;
        }

        /* --- 1. Birthday Cake & Candle Animation --- */
        #birthday-intro {
            background: linear-gradient(135deg, #ffe5ec, #ffc2d1);
        }

        .cake-container {
            position: relative;
            margin-bottom: 30px;
        }

        /* Pure CSS Candle & Flame Animation */
        .candle {
            width: 16px;
            height: 60px;
            background: linear-gradient(to top, #ffb3c1, #fff);
            border-radius: 4px;
            margin: 0 auto;
            position: relative;
        }

        .flame {
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 14px;
            height: 24px;
            background: #ffb703;
            border-radius: 50% 50% 20% 20%;
            box-shadow: 0 0 10px #ffb703, 0 0 20px #fb8500;
            animation: flicker 1s ease-in-out infinite alternate;
        }

        .cake-text {
            font-size: 2.5rem;
            color: var(--primary-color);
            font-weight: bold;
            margin-top: 20px;
            animation: popIn 1.5s ease;
        }

        /* --- 2. Home & Countdown --- */
        #home {
            background-color: #fff0f3;
        }

        .countdown-container {
            background: white;
            padding: 35px 40px;
            border-radius: 30px;
            box-shadow: 0 10px 30px rgba(255, 71, 126, 0.15);
            margin-top: 20px;
            max-width: 500px;
            width: 90%;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* Couple Image Styling */
        .couple-pic {
            width: 130px;
            height: 130px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid var(--secondary-color);
            margin-bottom: 20px;
            box-shadow: 0 8px 20px rgba(255, 71, 126, 0.2);
        }

        #timer {
            font-size: 1.6rem;
            font-weight: bold;
            color: var(--primary-color);
            margin-top: 15px;
            line-height: 1.4;
        }

        /* --- 3. Memory Gallery --- */
        #gallery {
            background-color: #ffe5ec;
        }

        .gallery-container {
            display: flex;
            flex-direction: column;
            gap: 40px;
            width: 100%;
            max-width: 600px;
        }

        .gallery-card {
            background: white;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
            transition: transform 0.4s;
        }

        .gallery-card:hover {
            transform: scale(1.03) rotate(1deg);
        }

        .gallery-card img {
            width: 100%;
            max-height: 550px;
            object-fit: cover;
            border-radius: 15px;
        }

        .gallery-caption {
            margin-top: 15px;
            font-size: 1.1rem;
            font-style: italic;
            color: #555;
            line-height: 1.4;
        }

        /* --- 4. Love Letter --- */
        #letter {
            background-color: #fff0f3;
        }

        .btn {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 15px 35px;
            font-size: 1.2rem;
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
            max-width: 550px;
            width: 90%;
            background: white;
            padding: 35px;
            border-radius: 25px;
            margin-top: 30px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.06);
            line-height: 1.8;
            text-align: left;
            border-left: 8px solid var(--primary-color);
            animation: fadeIn 1s ease forwards;
        }

        /* --- 5. Reasons Why I Love You --- */
        #reasons {
            background-color: #ffe5ec;
        }

        .reasons-stack {
            display: flex;
            flex-direction: column;
            gap: 20px;
            max-width: 500px;
            width: 90%;
        }

        .reason-card {
            background: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.04);
            border-bottom: 4px solid var(--secondary-color);
            transition: 0.3s;
        }

        .reason-card:hover {
            transform: translateY(-5px);
        }

        /* --- 6. Birthday Wish & Final Surprise --- */
        #surprise {
            background: linear-gradient(to bottom, #fff0f3, #fbc4ab);
        }

        .final-title {
            font-size: 2.3rem;
            color: var(--primary-color);
            margin-bottom: 25px;
            line-height: 1.3;
        }

        .final-text {
            font-size: 1.2rem;
            max-width: 600px;
            line-height: 1.8;
            margin-bottom: 40px;
            background: rgba(255, 255, 255, 0.5);
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.02);
        }

        /* --- Next Button Navigation --- */
        .next-btn {
            background: rgba(255, 255, 255, 0.8);
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
            padding: 10px 25px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 30px;
            transition: 0.3s;
        }

        .next-btn:hover {
            background: var(--primary-color);
            color: white;
        }

        /* --- Animations --- */
        @keyframes flicker {
            0% { transform: translateX(-50%) scale(1); }
            100% { transform: translateX(-50%) scale(1.1) rotate(2deg); }
        }

        @keyframes popIn {
            0% { transform: scale(0.5); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <!-- 1. Birthday Cake & Candle Animation -->
    <section id="birthday-intro">
        <div class="cake-container">
            <div class="candle">
                <div class="flame"></div>
            </div>
        </div>
        <h1 class="cake-text">Happy Birthday, My Love! 🎂✨</h1>
        <p style="font-size: 1.2rem; margin-top: 10px;">May all your sweetest dreams come true today.</p>
        <button class="next-btn" onclick="scrollToSection('home')">Let's Begin Our Journey ✨</button>
    </section>

    <!-- 2. Home & Countdown -->
    <section id="home">
        <h2>Our Beautiful Journey ❤️</h2>
        <div class="countdown-container">
            <!-- Couple Image Added Here -->
            <img class="couple-pic" src="https://i.ibb.co/rGFMCGyb/att-Oxdcw-Ceg7jk-Sk2tla-Uef-NTzu-D4kx-X9l6ta3pp-iwwo.jpg" alt="Us ❤️">
            <p style="font-size: 1.1rem;">Time passed since we became "Us" (08 Dec 2024) 💕</p>
            <div id="timer">Loading counter...</div>
        </div>
        <button class="next-btn" onclick="scrollToSection('gallery')">See Your Beautiful Pictures 📸</button>
    </section>

    <!-- 3. Memory Gallery -->
    <section id="gallery">
        <h2>Memory Gallery 📸</h2>
        <div class="gallery-container">
            <!-- First Image (Yellow/Paisley Saree) -->
            <div class="gallery-card">
                <img src="https://i.ibb.co/SSph5Ry/att-GD1qj3gh-FI4f-Ey-Q7-JUL4-W3n-Ka-Mn-UF2-TPJZxau-NMTg-N4.jpg" alt="Beautiful Wifey">
                <div class="gallery-caption">"Your elegance in this saree completely takes my breath away. Absolutely ethereal... 😍✨"</div>
            </div>
            <!-- Second Image (Brown Dress/Dupatta looking back) -->
            <div class="gallery-card">
                <img src="https://i.ibb.co/hxhR8HdY/att-h-QHk3-DE732jnvcn9njh5kb-E-Q6b-3p-EOods-N4-T5g9o-M.jpg" alt="Sweetest Smile">
                <div class="gallery-caption">"That gentle gaze and shy smile of yours can melt my heart in a split second. 💕"</div>
            </div>
            <!-- Third Image (Red and Yellow Bandhani Saree) -->
            <div class="gallery-card">
                <img src="https://i.ibb.co/x8DWYhVV/att-0x-UWtg-E-8u8-LTTL7-Fk-BUT3j2-VYe-W6d-Fi71-W1d4-Brk5-I.jpg" alt="Stunning Look">
                <div class="gallery-caption">"Pure perfection. Every single time I look at you, I fall in love all over again. ❤️🌟"</div>
            </div>
        </div>
        <button class="next-btn" onclick="scrollToSection('letter')">Read a Surprise Letter 💌</button>
    </section>

    <!-- 4. Digital Love Letter -->
    <section id="letter">
        <h2>A Message From My Heart ✨</h2>
        <button class="btn" onclick="toggleLetter()">Click here for a surprise 👉👈</button>
        
        <div id="love-letter" class="hidden-letter">
            <p><strong>My dear wifey,</strong></p>
            <br>
            <p>I wanted to make something unique to express how much I love you. It took a lott of time but it's definitely worth it if you are happy 👉👈 continuum Words truly fail to describe how much I love you so I built this little corner of the internet just for us..</p>
            <p>Thank you for being mine, supporting me, loving me. You are my best friend, my wifeyy, my soulmate, my everything..</p>
            <p>You are the most precious thing of my life..</p>
            <br>
            <p><strong>Forever and always yourss,</strong><br>Mihirrr from your heartt 💋</p>
        </div>
        <button class="next-btn" style="margin-top: 40px;" onclick="scrollToSection('reasons')">Why I Love You 💌</button>
    </section>

    <!-- 5. Reasons Why I Love You -->
    <section id="reasons">
        <h2>Reasons Why I Love You 🎀</h2>
        <div class="reasons-stack">
            <div class="reason-card">
                <h3>Reason #1</h3>
                <p style="margin-top: 8px; font-size: 1.1rem; font-weight: 500;">You are so cute, loving and caring..</p>
            </div>
            <div class="reason-card">
                <h3>Reason #2</h3>
                <p style="margin-top: 8px; font-size: 1.1rem; font-weight: 500;">You always understand me, respect me, and listen to me</p>
            </div>
            <div class="reason-card">
                <h3>Reason #3</h3>
                <p style="margin-top: 8px; font-size: 1.1rem; font-weight: 500;">I love you for your everything—your behavior, your character, your soul, your smile... everything made me fall in love with you</p>
            </div>
        </div>
        <button class="next-btn" onclick="scrollToSection('surprise')">One Last Thing... 🌙</button>
    </section>

    <!-- 6. Birthday Wish & Final Surprise -->
    <section id="surprise">
        <h1 class="final-title">Happy Birthday to the girl who changed my whole world 👉🏻👈🏻</h1>
        <div class="final-text">
            <p>I didn't just fall in love with you; I fell in love with your pure heart, your gentle ways, that adorable smile always made my day beautiful 🥹💝</p>
            <br>
            <p>Every single thing about you is so precious to me. You are my greatest blessing, and I hope today shows you just how deeply you are loved... Love you a lotttt pakhiiii 🥹🫶🏻🌸</p>
        </div>
        <p style="font-size: 2.2rem; font-weight: bold; color: var(--primary-color);">Forever & Always Your Mihir ❤️</p>
    </section>

    <script>
        // --- 1. Navigation Flow Logic ---
        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        // --- 2. Relationship Countdown Timer Logic (Starts from 8th Dec 2024) ---
        const anniversaryDate = new Date(2024, 11, 8, 0, 0, 0); // 11 means December in JS

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
        updateCountdown(); // Run instantly

        // --- 3. Toggle Love Letter ---
        function toggleLetter() {
            const letter = document.getElementById("love-letter");
            if (letter.style.display === "block") {
                letter.style.display = "none";
            } else {
                letter.style.display = "block";
                letter.scrollIntoView({ behavior: 'smooth' });
            }
        }
    </script>
</body>
</html>
