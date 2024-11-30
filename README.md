<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Win Amazing Prizes</title>
    <style>
        :root {
            --primary: #F59E0B;
            --secondary: #D97706;
            --accent: #EA580C;
            --confetti1: #60A5FA;
            --confetti2: #34D399;
            --confetti3: #F472B6;
            --dark: #171717;
            --card-bg: #262626;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, sans-serif;
        }

        body {
            min-height: 100vh;
            min-height: -webkit-fill-available;
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--dark);
            padding: 0.5rem;
            position: relative;
            overflow: hidden;
        }
        html {
    height: -webkit-fill-available;
}
        .confetti {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            overflow: hidden;
            pointer-events: none;
        }

        .confetti-piece {
            position: absolute;
            width: 8px;
            height: 8px;
            background: var(--confetti1);
            top: -10px;
            opacity: 0;
            animation: confetti 3s ease-in-out infinite;
        }

        @keyframes confetti {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }

        .container {
            width: 100%;
            max-width: 340px;
            padding: clamp(1.2rem, 4vw, 2rem);
            margin: 0.5rem auto;
            display: flex;
            flex-direction: column;
            gap: 1rem;
            background: var(--card-bg);
            border-radius: 24px;
            border: 1px solid rgba(245, 158, 11, 0.2);
            box-shadow: 
                0 8px 32px rgba(0, 0, 0, 0.3),
                0 0 80px rgba(245, 158, 11, 0.15);
            position: relative;
            overflow: hidden;
        }

.prize-badge {
    background: linear-gradient(135deg, #FF8A00, #FF5733);
    color: white;
    padding: 0.7rem 1.5rem;
    border-radius: 50px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.7rem;
    font-weight: 700;
    font-size: 1rem;
    margin-bottom: 1.5rem;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    position: relative;
    overflow: hidden;
    box-shadow: 
        0 4px 15px rgba(255, 138, 0, 0.3),
        inset 0 0 20px rgba(255, 255, 255, 0.15);
    border: 1px solid rgba(255, 255, 255, 0.1);
    transform: translateZ(0);
    backface-visibility: hidden;
    -webkit-font-smoothing: antialiased;
    width: 95%;
    margin-left: auto;
    margin-right: auto;
}
.prize-badge::before {
    content: "🎁";
    font-size: 1.2rem;
    margin-right: 0.3rem;
    animation: iconGlow 2s infinite;
}
.prize-badge::after {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(
        45deg,
        transparent,
        rgba(255, 255, 255, 0.2),
        transparent
    );
    transform: rotate(45deg);
    animation: shimmerEffect 3s infinite;
}
/* تأثيرات حركية */
@keyframes iconGlow {
    0%, 100% { text-shadow: 0 0 5px rgba(255, 255, 255, 0.5); }
    50% { text-shadow: 0 0 15px rgba(255, 255, 255, 0.8); }
}

@keyframes shimmerEffect {
    0% {
        transform: rotate(45deg) translateX(-150%);
    }
    100% {
        transform: rotate(45deg) translateX(150%);
    }
}

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .prize-amount {
            font-size: clamp(2.5rem, 7vw, 3rem);
            font-weight: 800;
            background: linear-gradient(135deg, #FFD700, #FFA500);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: clamp(0.8rem, 2.5vw, 1rem) 0;
            text-align: center;
            text-shadow: 0 2px 10px rgba(245, 158, 11, 0.3);
            animation: glow 2s infinite;
        }

        @keyframes glow {
            0%, 100% { filter: brightness(100%); }
            50% { filter: brightness(120%); }
        }

        h1 {
            font-size: clamp(1.8rem, 5vw, 2.2rem);
            color: white;
            margin-bottom: clamp(0.6rem, 2vw, 1rem);
            line-height: 1.2;
            font-weight: 800;
            text-align: center;
        }

        .tagline {
            color: #D4D4D4;
            font-size: clamp(0.9rem, 2.5vw, 1.1rem);
            margin-bottom: clamp(1rem, 3vw, 1.5rem);
            text-align: center;
            line-height: 1.5;
        }

        .prize-list {
            background: rgba(245, 158, 11, 0.1);
            border: 1px solid rgba(245, 158, 11, 0.2);
            border-radius: 12px;
            padding: clamp(0.8rem, 2.5vw, 1rem);
            margin-bottom: clamp(1rem, 3vw, 1.5rem);
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: clamp(0.6rem, 2vw, 1rem);
        }

        .prize-item {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: #E5E5E5;
            font-size: clamp(0.8rem, 2.2vw, 0.9rem);
        }

        .prize-icon {
            font-size: clamp(1.2rem, 3.5vw, 1.5rem);
            animation: shake 3s infinite;
        }

        @keyframes shake {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(-10deg); }
            75% { transform: rotate(10deg); }
        }

        .timer {
            background: rgba(245, 158, 11, 0.1);
            border: 1px solid rgba(245, 158, 11, 0.2);
            color: white;
            padding: clamp(0.8rem, 2.5vw, 1rem);
            border-radius: 12px;
            font-size: clamp(0.9rem, 2.5vw, 1rem);
            font-weight: 600;
            margin-bottom: clamp(1rem, 3vw, 1.5rem);
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.02); }
        }

        .cta-button {
            width: 100%;
            padding: clamp(1rem, 3vw, 1.2rem);
            font-size: clamp(1rem, 2.5vw, 1.1rem);
            font-weight: 700;
            color: white;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            border: none;
            border-radius: 12px;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease;
            box-shadow: 0 4px 15px rgba(245, 158, 11, 0.3);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(245, 158, 11, 0.4);
        }

        .cta-button::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                45deg,
                transparent,
                rgba(255, 255, 255, 0.3),
                transparent
            );
            transform: rotate(45deg);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { transform: rotate(45deg) translateX(-150%); }
            100% { transform: rotate(45deg) translateX(150%); }
        }

        .chance-text {
            color: #A3A3A3;
            font-size: clamp(0.8rem, 2.2vw, 0.9rem);
            text-align: center;
            margin-top: clamp(0.8rem, 2.5vw, 1rem);
        }
        @media (max-height: 700px) {
    .container {
        gap: 0.8rem;
        padding: 1rem;
    }

    .prize-badge {
        margin-bottom: 0.8rem;
    }

    .prize-amount {
        margin: 0.6rem 0;
    }

    .prize-list {
        padding: 0.8rem;
        margin-bottom: 0.8rem;
    }

    .timer {
        margin-bottom: 0.8rem;
    }
}

@media (max-width: 360px) {
    .container {
        padding: 1rem;
    }

    .prize-list {
        grid-template-columns: 1fr 1fr;
        gap: 0.6rem;
    }

    .prize-item {
        font-size: 0.8rem;
    }

    .prize-icon {
        font-size: 1.2rem;
    }

    .timer, .cta-button {
        padding: 0.8rem;
    }
}
.prize-badge {
        font-size: 0.9rem;
        padding: 0.6rem 1.2rem;
    }
    .prize-badge::before {
        font-size: 1.1rem;
    }
    .prize-badge:hover {
    transform: translateY(-1px);
    box-shadow: 
        0 6px 20px rgba(255, 138, 0, 0.4),
        inset 0 0 25px rgba(255, 255, 255, 0.2);
    transition: all 0.3s ease;
}

/* تحسينات للشاشات الصغيرة جداً */
@media (max-height: 600px) {
    body {
        align-items: flex-start;
        padding-top: 0.5rem;
    }

    .container {
        padding: 0.8rem;
        gap: 0.6rem;
    }

    .prize-badge {
        padding: 0.5rem 1.2rem;
        margin-bottom: 1rem;
    }

    .prize-amount {
        font-size: 2.2rem;
        margin: 0.4rem 0;
    }

    .prize-list {
        padding: 0.6rem;
        margin-bottom: 0.6rem;
    }
}
    .prize-badge {
        padding: 0.5rem 1.2rem;
        margin-bottom: 1rem;
    }
/* تحسينات للشاشات العريضة */
@media (min-width: 361px) and (max-width: 400px) {
    .container {
        max-width: 360px;
    }

    .prize-list {
        gap: 0.8rem;
    }
}
.prize-badge {
        width: 90%;
    }

/* تحسينات للشاشات الطويلة */
@media (min-height: 701px) {
    .container {
        gap: 1.2rem;
    }

    .prize-badge {
        margin-bottom: 1.2rem;
    }

    .prize-list {
        margin-bottom: 1.2rem;
    }
}
    </style>
</head>
<body>
    <div class="confetti"></div>
    <div class="container">
        <div class="prize-badge">
            MEGA GIVEAWAY
        </div>
        
        <h1>Win Big Prizes!</h1>
        
        <div class="prize-amount">$1,000</div>
        
        <p class="tagline">Limited Time Sweepstakes - Don't Miss Out!</p>

        <div class="prize-list">
            <div class="prize-item">
                <span class="prize-icon">💰</span>
                Cash Prizes
            </div>
            <div class="prize-item">
                <span class="prize-icon">🎮</span>
                Gaming Gear
            </div>
            <div class="prize-item">
                <span class="prize-icon">📱</span>
                Latest Tech
            </div>
            <div class="prize-item">
                <span class="prize-icon">🎯</span>
                Gift Cards
            </div>
        </div>

        <div class="timer" id="countdown">
            <span>⏰</span>
            <span>Ends In: 2:45</span>
        </div>
        
        <button class="cta-button" id="ctaButton">
            Enter Now! 🎉
        </button>

        <p class="chance-text">Your Chance to Win is Just One Click Away!</p>
    </div>

    <script>
        // Create confetti
        function createConfetti() {
            const colors = ['var(--confetti1)', 'var(--confetti2)', 'var(--confetti3)'];
            const confettiContainer = document.querySelector('.confetti');
            
            for(let i = 0; i < 50; i++) {
                const piece = document.createElement('div');
                piece.className = 'confetti-piece';
                piece.style.background = colors[Math.floor(Math.random() * colors.length)];
                piece.style.left = Math.random() * 100 + 'vw';
                piece.style.animationDelay = Math.random() * 3 + 's';
                piece.style.animationDuration = (Math.random() * 3 + 2) + 's';
                confettiContainer.appendChild(piece);
            }
        }

        // Start countdown
        function startCountdown() {
            let timeLeft = 165; // 2:45 in seconds
            const countdownElement = document.getElementById('countdown');
            
            const timer = setInterval(() => {
                const minutes = Math.floor(timeLeft / 60);
                const seconds = timeLeft % 60;
                countdownElement.innerHTML = `
                    <span>⏰</span>
                    <span>Ends In: ${minutes}:${seconds < 10 ? '0' : ''}${seconds}</span>
                `;
                
                if (timeLeft <= 0) {
                    clearInterval(timer);
                    countdownElement.innerHTML = `
                        <span>⏰</span>
                        <span>Giveaway Ended!</span>
                    `;
                }
                
                timeLeft--;
            }, 1000);
        }

        document.getElementById('ctaButton').addEventListener('click', function() {
            window.location.href = 'https://www.google.com';
        });

        // Initialize
        createConfetti();
        startCountdown();
    </script>
</body>


</html>

