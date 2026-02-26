# Wedding-Invitation-Card
AI wedding invitation card generator
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Wedding Invitation</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Playfair+Display:ital@0;1&family=Poppins:wght@300&display=swap" rel="stylesheet">
    <style>
        :root {
            /* Pink Palette */
            --baby-pink: #fce4ec;
            --soft-pink: #f8bbd0;
            --rose-pink: #f06292;
            --deep-rose: #880e4f;
            --gold-accent: #c5a059;
            --white-silk: #ffffff;
        }

        body, html {
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            background-color: var(--baby-pink);
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }

        /* Curtain Transition Effect */
        .section {
            height: 100vh;
            width: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            text-align: center;
            padding: 40px;
            box-sizing: border-box;
            /* Subtle gradient to look like fabric */
            background: linear-gradient(180deg, var(--white-silk) 0%, var(--baby-pink) 100%);
        }

        /* Decorative Border */
        .card-frame {
            border: 2px solid var(--soft-pink);
            padding: 40px;
            border-radius: 50% 50% 0 0; /* Arched top look */
            background: rgba(255, 255, 255, 0.4);
            backdrop-filter: blur(5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }

        /* Animation */
        .reveal {
            opacity: 0;
            transform: scale(0.95) translateY(40px);
            transition: all 1.5s cubic-bezier(0.2, 1, 0.3, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: scale(1) translateY(0);
        }

        h1 { font-family: 'Dancing Script', cursive; color: var(--rose-pink); font-size: 3.8rem; margin: 10px 0; }
        h2 { font-family: 'Playfair Display', serif; color: var(--deep-rose); font-size: 2.8rem; letter-spacing: 1px; }
        p { font-size: 1.1rem; color: #5d4037; max-width: 500px; line-height: 1.6; }
        
        .date-box {
            border-top: 1px solid var(--gold-accent);
            border-bottom: 1px solid var(--gold-accent);
            padding: 15px 0;
            margin: 20px 0;
            color: var(--deep-rose);
            font-weight: 600;
        }

        /* QR Code Styling */
        .qr-container {
            margin-top: 20px;
            padding: 10px;
            background: white;
            display: inline-block;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(240, 98, 146, 0.2);
        }

        .scroll-hint {
            position: absolute;
            bottom: 30px;
            color: var(--rose-pink);
            font-size: 0.8rem;
            letter-spacing: 3px;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
            40% {transform: translateY(-10px);}
        }
    </style>
</head>
<body>

    <section class="section">
        <div class="reveal active card-frame">
            <p style="text-transform: uppercase; letter-spacing: 4px; color: var(--gold-accent);">The Wedding of</p>
            <h1>Save the Date</h1>
            <p>With hearts full of love, we invite you to join us as we say "I Do".</p>
            <div class="scroll-hint">SCROLL TO OPEN</div>
        </div>
    </section>

    <section class="section" style="background: var(--soft-pink);">
        <div class="reveal card-frame">
            <h2>Julian Carter</h2>
            <h1 style="font-size: 2.5rem; color: var(--white-silk);">&</h1>
            <h2>Amelia Rose</h2>
            <p>Two lives, two hearts, joined together in friendship, united forever in love.</p>
        </div>
    </section>

    <section class="section">
        <div class="reveal card-frame">
            <h2>The Celebration</h2>
            <div class="date-box">
                SATURDAY | JUNE 20, 2026 | 4:30 PM
            </div>
            <p><strong>The Rosewood Estate</strong><br>
            123 Blossom Lane, Garden Valley</p>
            
            <div class="qr-container">
                <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=YOUR_LINK_HERE" alt="Venue Map">
            </div>
            <p style="font-size: 0.7rem; margin-top: 10px; color: var(--rose-pink);">SCAN FOR DIRECTIONS</p>
        </div>
    </section>

    <script>
        function reveal() {
            var reveals = document.querySelectorAll(".reveal");
            for (var i = 0; i < reveals.length; i++) {
                var windowHeight = window.innerHeight;
                var elementTop = reveals[i].getBoundingClientRect().top;
                var elementVisible = 100;
                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add("active");
                }
            }
        }
        window.addEventListener("scroll", reveal);
    </script>
</body>
</html>
