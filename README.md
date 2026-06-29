html_content = '''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Leecha! 🐟</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@1,400;1,500&family=Patrick+Hand&display=swap" rel="stylesheet">
    <style>
        /* ============================================
           RESET & BASE
           ============================================ */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Patrick Hand', cursive;
            min-height: 100vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            background: #87CEEB;
        }

        /* ============================================
           OCEAN BACKGROUND
           ============================================ */
        .ocean-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background:
                radial-gradient(ellipse at 20% 80%, rgba(255, 182, 193, 0.3) 0%, transparent 50%),
                radial-gradient(ellipse at 80% 20%, rgba(135, 206, 235, 0.4) 0%, transparent 50%),
                radial-gradient(ellipse at 50% 50%, rgba(72, 209, 204, 0.2) 0%, transparent 70%),
                linear-gradient(180deg,
                    #87CEEB 0%,
                    #48D1CC 30%,
                    #20B2AA 60%,
                    #008B8B 100%);
            z-index: 0;
        }

        /* ============================================
           WAVES
           ============================================ */
        .wave {
            position: absolute;
            width: 200%;
            height: 100px;
            background-repeat: repeat-x;
            opacity: 0.6;
        }

        .wave-1 {
            bottom: 0;
            background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1200 120' preserveAspectRatio='none'%3E%3Cpath d='M0,60 C150,120 350,0 600,60 C850,120 1050,0 1200,60 L1200,120 L0,120 Z' fill='%23FF6B6B' opacity='0.3'/%3E%3C/svg%3E");
            background-size: 600px 100px;
            animation: waveMove 8s linear infinite;
        }

        .wave-2 {
            bottom: 10px;
            background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1200 120' preserveAspectRatio='none'%3E%3Cpath d='M0,40 C200,100 400,20 600,60 C800,100 1000,20 1200,60 L1200,120 L0,120 Z' fill='%23FFB6C1' opacity='0.4'/%3E%3C/svg%3E");
            background-size: 500px 100px;
            animation: waveMove 6s linear infinite reverse;
        }

        .wave-3 {
            bottom: 20px;
            background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1200 120' preserveAspectRatio='none'%3E%3Cpath d='M0,50 C180,10 360,90 600,50 C840,10 1020,90 1200,50 L1200,120 L0,120 Z' fill='%23FFD93D' opacity='0.3'/%3E%3C/svg%3E");
            background-size: 700px 100px;
            animation: waveMove 10s linear infinite;
        }

        @keyframes waveMove {
            0%   { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        /* ============================================
           CLOUDS
           ============================================ */
        .cloud {
            position: absolute;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 100px;
            filter: blur(1px);
        }

        .cloud::before,
        .cloud::after {
            content: '';
            position: absolute;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 100px;
        }

        .cloud-1 {
            width: 120px;
            height: 50px;
            top: 10%;
            left: 10%;
            animation: cloudFloat 20s ease-in-out infinite;
        }

        .cloud-1::before {
            width: 60px;
            height: 60px;
            top: -30px;
            left: 15px;
        }

        .cloud-1::after {
            width: 80px;
            height: 50px;
            top: -20px;
            right: 10px;
        }

        .cloud-2 {
            width: 100px;
            height: 40px;
            top: 20%;
            right: 15%;
            animation: cloudFloat 25s ease-in-out infinite reverse;
        }

        .cloud-2::before {
            width: 50px;
            height: 50px;
            top: -25px;
            left: 20px;
        }

        .cloud-2::after {
            width: 70px;
            height: 40px;
            top: -15px;
            right: 15px;
        }

        .cloud-3 {
            width: 140px;
            height: 55px;
            top: 5%;
            left: 50%;
            animation: cloudFloat 30s ease-in-out infinite;
        }

        .cloud-3::before {
            width: 70px;
            height: 70px;
            top: -35px;
            left: 25px;
        }

        .cloud-3::after {
            width: 90px;
            height: 55px;
            top: -25px;
            right: 20px;
        }

        @keyframes cloudFloat {
            0%, 100% { transform: translateX(0) translateY(0); }
            25%      { transform: translateX(30px) translateY(-10px); }
            50%      { transform: translateX(-20px) translateY(5px); }
            75%      { transform: translateX(20px) translateY(-5px); }
        }

        /* ============================================
           OPENING OVERLAY
           ============================================ */
        .opening-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(180deg, rgba(26, 58, 92, 0.85) 0%, rgba(13, 33, 55, 0.9) 100%);
            z-index: 1000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: opacity 2s ease-out, visibility 2s;
        }

        .opening-overlay.hidden {
            opacity: 0;
            visibility: hidden;
        }

        .opening-bubble {
            width: 200px;
            height: 200px;
            background: radial-gradient(circle at 30% 30%,
                rgba(255, 255, 255, 0.9) 0%,
                rgba(135, 206, 235, 0.6) 40%,
                rgba(72, 209, 204, 0.4) 100%);
            border-radius: 50%;
            border: 3px solid rgba(255, 255, 255, 0.5);
            box-shadow:
                0 0 30px rgba(135, 206, 235, 0.5),
                inset -10px -10px 20px rgba(255, 182, 193, 0.3),
                inset 10px 10px 20px rgba(255, 255, 255, 0.4);
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            animation: bubbleFloat 3s ease-in-out infinite;
            cursor: pointer;
        }

        .opening-bubble::before {
            content: '';
            position: absolute;
            width: 30px;
            height: 20px;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 50%;
            top: 25px;
            left: 35px;
            transform: rotate(-20deg);
        }

        @keyframes bubbleFloat {
            0%, 100% { transform: translateY(0) scale(1); }
            50%      { transform: translateY(-20px) scale(1.02); }
        }

        .ponyo-cake {
            font-size: 4rem;
            filter: drop-shadow(0 5px 10px rgba(0, 0, 0, 0.2));
        }

        .candles-row {
            display: flex;
            gap: 15px;
            margin-top: 20px;
            justify-content: center;
        }

        .ponyo-candle {
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .candle-body {
            width: 8px;
            height: 30px;
            background: linear-gradient(to right, #FF6B6B, #FFB6C1, #FF6B6B);
            border-radius: 4px;
            position: relative;
        }

        .candle-body::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%);
            width: 14px;
            height: 5px;
            background: #8B4513;
            border-radius: 2px;
        }

        .ponyo-flame {
            width: 16px;
            height: 24px;
            background: radial-gradient(ellipse at bottom,
                #FF4757 0%,
                #FFA502 40%,
                #FFDD59 70%,
                transparent 100%);
            border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
            position: absolute;
            top: -28px;
            left: 50%;
            transform: translateX(-50%);
            animation: flameDance 0.3s ease-in-out infinite alternate;
            box-shadow: 0 0 15px #FFA502, 0 0 30px #FF4757;
        }

        @keyframes flameDance {
            0%   { transform: translateX(-50%) scale(1) rotate(-5deg) skewX(-3deg); }
            100% { transform: translateX(-50%) scale(1.1) rotate(5deg) skewX(3deg); }
        }

        .opening-text {
            color: #FFD93D;
            font-size: 1.8rem;
            margin-top: 30px;
            text-shadow: 0 0 10px rgba(255, 217, 61, 0.5);
            animation: textPulse 2s ease-in-out infinite;
        }

        .hint-text {
            color: #87CEEB;
            font-size: 1rem;
            margin-top: 15px;
            opacity: 0;
            animation: fadeInHint 1s ease-out 2s forwards;
        }

        @keyframes textPulse {
            0%, 100% { opacity: 0.8; }
            50%      { opacity: 1; }
        }

        @keyframes fadeInHint {
            to { opacity: 0.7; }
        }

        /* ============================================
           MAIN CONTAINER
           ============================================ */
        .container {
            text-align: center;
            z-index: 10;
            opacity: 0;
            display: none;
            position: relative;
            padding: 20px;
            width: 100%;
            max-width: 100vw;
            overflow-x: hidden;
        }

        .container.visible {
            display: block;
            animation: gentleAppear 2s ease-out forwards;
        }

        @keyframes gentleAppear {
            from { opacity: 0; transform: translateY(40px) scale(0.95); }
            to   { opacity: 1; transform: translateY(0) scale(1); }
        }

        h1 {
            font-size: 3rem;
            color: #fff;
            text-shadow:
                3px 3px 0px #FF6B6B,
                6px 6px 0px rgba(0, 0, 0, 0.1);
            margin-bottom: 10px;
            letter-spacing: 2px;
            animation: titleBounce 3s ease-in-out infinite;
        }

        @keyframes titleBounce {
            0%, 100% { transform: translateY(0); }
            50%      { transform: translateY(-8px); }
        }

        .name {
            font-size: 4.5rem;
            color: #FF6B6B;
            text-shadow:
                0 0 20px rgba(255, 107, 107, 0.4),
                3px 3px 0px rgba(0, 0, 0, 0.1);
            margin: 10px 0;
            font-weight: bold;
            letter-spacing: 4px;
            animation: nameGlow 4s ease-in-out infinite;
        }

        @keyframes nameGlow {
            0%, 100% {
                text-shadow:
                    0 0 20px rgba(255, 107, 107, 0.4),
                    3px 3px 0px rgba(0, 0, 0, 0.1);
            }
            50% {
                text-shadow:
                    0 0 40px rgba(255, 107, 107, 0.7),
                    0 0 60px rgba(255, 182, 193, 0.4),
                    3px 3px 0px rgba(0, 0, 0, 0.1);
            }
        }

        /* ============================================
           BUNNY ASCII ART
           ============================================ */
        .bunny-art {
            font-family: monospace;
            font-size: 1.1rem;
            color: #4a4a4a;
            line-height: 1.6;
            white-space: pre;
            margin: 15px 0;
            background: rgba(255, 255, 255, 0.6);
            display: inline-block;
            padding: 15px 25px;
            border-radius: 15px;
            border: 2px dashed #FFB6C1;
        }

        /* ============================================
           BOUQUET
           ============================================ */
        .bouquet-container {
            position: relative;
            display: inline-block;
            margin: 15px 0;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .bouquet-container:hover {
            transform: scale(1.05) rotate(2deg);
        }

        .bouquet {
            font-size: 5rem;
            filter: drop-shadow(0 8px 16px rgba(0, 0, 0, 0.15));
            animation: bouquetSway 4s ease-in-out infinite;
            position: relative;
            z-index: 2;
            white-space: nowrap;
        }

        @keyframes bouquetSway {
            0%, 100% { transform: rotate(-3deg); }
            50%      { transform: rotate(3deg); }
        }

        .bouquet-ribbon {
            position: absolute;
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 22px;
            background: linear-gradient(135deg, #FF6B6B, #FFB6C1);
            border-radius: 0 0 25px 25px;
            z-index: 1;
            box-shadow: 0 2px 8px rgba(255, 107, 107, 0.3);
        }

        .bouquet-ribbon::before {
            content: '🎀';
            position: absolute;
            top: -12px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 1.2rem;
            filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
        }

        /* ============================================
           CAKE
           ============================================ */
        .cake-wrapper {
            position: relative;
            display: inline-block;
            margin: 10px 0;
            cursor: pointer;
        }

        .main-cake {
            font-size: 4.5rem;
            filter: drop-shadow(0 5px 10px rgba(0, 0, 0, 0.2));
            transition: transform 0.3s;
            display: inline-block;
        }

        .main-cake:hover {
            transform: scale(1.1);
        }

        .main-candles {
            position: absolute;
            top: -5px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 12px;
        }

        /* ============================================
           MESSAGE CARD
           ============================================ */
        .message-card {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px 20px 20px 5px;
            padding: 25px 30px;
            max-width: 90vw;
            width: 520px;
            margin: 15px auto;
            position: relative;
            box-shadow:
                5px 5px 0px rgba(255, 107, 107, 0.3),
                10px 10px 0px rgba(255, 182, 193, 0.2);
            border: 2px solid rgba(255, 107, 107, 0.2);
            transform: rotate(-1deg);
            transition: transform 0.3s;
            word-wrap: break-word;
            overflow-wrap: break-word;
        }

        .message-card:hover {
            transform: rotate(0deg) scale(1.02);
        }

        .message-card::before {
            content: '🌷';
            position: absolute;
            top: -18px;
            right: 25px;
            font-size: 2.2rem;
            transform: rotate(15deg);
            filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
        }

        .message-text {
            font-size: 1.25rem;
            color: #4a4a4a;
            line-height: 1.9;
            white-space: normal;
            word-wrap: break-word;
            overflow-wrap: break-word;
            hyphens: auto;
        }

        /* ============================================
           BUTTON
           ============================================ */
        .btn {
            display: inline-block;
            margin-top: 20px;
            padding: 12px 35px;
            font-size: 1.2rem;
            font-family: 'Patrick Hand', cursive;
            color: #fff;
            background: linear-gradient(135deg, #FF6B6B, #FF8E8E);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow:
                0 5px 15px rgba(255, 107, 107, 0.4),
                3px 3px 0px rgba(0, 0, 0, 0.1);
            letter-spacing: 1px;
        }

        .btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow:
                0 10px 25px rgba(255, 107, 107, 0.5),
                3px 3px 0px rgba(0, 0, 0, 0.1);
        }

        .btn:active {
            transform: translateY(0) scale(0.98);
        }

        /* ============================================
           BUBBLES
           ============================================ */
        .bubble {
            position: absolute;
            border-radius: 50%;
            background: radial-gradient(circle at 30% 30%,
                rgba(255, 255, 255, 0.9) 0%,
                rgba(135, 206, 235, 0.4) 40%,
                rgba(72, 209, 204, 0.2) 100%);
            border: 2px solid rgba(255, 255, 255, 0.6);
            box-shadow:
                inset -5px -5px 10px rgba(255, 182, 193, 0.2),
                inset 5px 5px 10px rgba(255, 255, 255, 0.5),
                0 0 15px rgba(135, 206, 235, 0.3);
            animation: bubbleRise linear infinite;
            pointer-events: none;
        }

        .bubble::before {
            content: '';
            position: absolute;
            width: 25%;
            height: 20%;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            top: 15%;
            left: 20%;
            transform: rotate(-20deg);
        }

        @keyframes bubbleRise {
            0% {
                transform: translateY(100vh) translateX(0) scale(1);
                opacity: 0;
            }
            10% { opacity: 0.8; }
            90% { opacity: 0.6; }
            100% {
                transform: translateY(-20vh) translateX(50px) scale(1.2);
                opacity: 0;
            }
        }

        /* ============================================
           WATER BALLOONS
           ============================================ */
        .water-balloon {
            position: absolute;
            border-radius: 50% 50% 50% 50% / 55% 55% 45% 45%;
            animation: waterBalloonBounce linear infinite;
            cursor: pointer;
            z-index: 5;
            box-shadow:
                inset -8px -8px 15px rgba(0, 0, 0, 0.1),
                inset 8px 8px 15px rgba(255, 255, 255, 0.4),
                0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .water-balloon::before {
            content: '';
            position: absolute;
            width: 20%;
            height: 15%;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 50%;
            top: 20%;
            left: 25%;
            transform: rotate(-30deg);
        }

        .water-balloon::after {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 50%;
            transform: translateX(-50%);
            width: 8px;
            height: 4px;
            background: rgba(0, 0, 0, 0.1);
            border-radius: 50%;
        }

        @keyframes waterBalloonBounce {
            0% {
                transform: translateY(-100px) translateX(0) rotate(0deg);
                opacity: 0;
            }
            10% { opacity: 0.9; }
            25% { transform: translateY(20vh) translateX(20px) rotate(90deg); }
            50% { transform: translateY(50vh) translateX(-10px) rotate(180deg); }
            75% { transform: translateY(80vh) translateX(30px) rotate(270deg); }
            100% {
                transform: translateY(110vh) translateX(0) rotate(360deg);
                opacity: 0;
            }
        }

        .water-balloon.pop {
            animation: balloonPop 0.3s ease-out forwards !important;
        }

        @keyframes balloonPop {
            0%   { transform: scale(1); opacity: 0.9; }
            50%  { transform: scale(1.3); opacity: 0.5; }
            100% { transform: scale(0); opacity: 0; }
        }

        .splash {
            position: absolute;
            width: 6px;
            height: 6px;
            border-radius: 50%;
            animation: splashDrop 0.6s ease-out forwards;
            pointer-events: none;
        }

        @keyframes splashDrop {
            0%   { transform: translate(0, 0) scale(1); opacity: 0.8; }
            100% { transform: translate(var(--tx), var(--ty)) scale(0); opacity: 0; }
        }

        /* ============================================
           FISH
           ============================================ */
        .fish {
            position: absolute;
            font-size: 2rem;
            animation: fishSwim linear infinite;
            filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
            pointer-events: none;
            z-index: 2;
        }

        @keyframes fishSwim {
            0%   { transform: translateX(-100px) translateY(0) scaleX(1); }
            45%  { transform: translateX(50vw) translateY(-20px) scaleX(1); }
            50%  { transform: translateX(50vw) translateY(-20px) scaleX(-1); }
            95%  { transform: translateX(-100px) translateY(0) scaleX(-1); }
            100% { transform: translateX(-100px) translateY(0) scaleX(1); }
        }

        /* ============================================
           SPARKLES
           ============================================ */
        .sparkle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #FFD93D;
            border-radius: 50%;
            animation: sparkleTwinkle 2s ease-in-out infinite;
            box-shadow: 0 0 6px #FFD93D;
        }

        @keyframes sparkleTwinkle {
            0%, 100% { opacity: 0; transform: scale(0) rotate(0deg); }
            50%      { opacity: 1; transform: scale(1) rotate(180deg); }
        }

        /* ============================================
           STARFISH
           ============================================ */
        .starfish {
            position: absolute;
            font-size: 1.5rem;
            animation: starfishWiggle 5s ease-in-out infinite;
            filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
        }

        @keyframes starfishWiggle {
            0%, 100% { transform: rotate(-10deg) translateY(0); }
            50%      { transform: rotate(10deg) translateY(-10px); }
        }

        /* ============================================
           CONFETTI
           ============================================ */
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            top: -10px;
            animation: confettiFall linear forwards;
            border-radius: 2px;
        }

        @keyframes confettiFall {
            0%   { transform: translateY(0) rotate(0deg) scale(1); opacity: 1; }
            100% { transform: translateY(100vh) rotate(720deg) scale(0.5); opacity: 0; }
        }

        /* ============================================
           MAGIC PARTICLES
           ============================================ */
        .magic-particle {
            position: absolute;
            width: 6px;
            height: 6px;
            border-radius: 50%;
            animation: magicFloat 3s ease-out forwards;
            pointer-events: none;
        }

        @keyframes magicFloat {
            0%   { transform: translate(0, 0) scale(1); opacity: 1; }
            100% { transform: translate(var(--mx), var(--my)) scale(0); opacity: 0; }
        }

        /* ============================================
           EASTER EGG
           ============================================ */
        .easter-egg {
            position: fixed;
            bottom: 22px;
            right: 18px;
            font-size: 16px;
            opacity: 0.12;
            cursor: pointer;
            z-index: 50;
            transition: opacity 0.3s, transform 0.3s;
            animation: eggWobble 7s ease-in-out infinite;
            user-select: none;
            -webkit-user-select: none;
        }

        .easter-egg:hover {
            opacity: 0.55;
            transform: scale(1.4) rotate(15deg);
        }

        @keyframes eggWobble {
            0%, 100% { transform: rotate(-8deg) translateY(0); }
            50%      { transform: rotate(8deg) translateY(-4px); }
        }

        .secret-toast {
            position: fixed;
            bottom: 55px;
            left: 50%;
            transform: translateX(-50%) translateY(18px);
            background: rgba(255, 255, 255, 0.97);
            color: #4a4a4a;
            font-family: 'Patrick Hand', cursive;
            font-size: 1.15rem;
            padding: 13px 26px;
            border-radius: 40px;
            border: 2px solid #FF6B6B;
            box-shadow:
                0 6px 24px rgba(255, 107, 107, 0.35),
                3px 3px 0px rgba(255, 182, 193, 0.4);
            z-index: 9999;
            opacity: 0;
            transition: opacity 0.4s, transform 0.4s;
            pointer-events: none;
            white-space: nowrap;
        }

        .secret-toast.show {
            opacity: 1;
            transform: translateX(-50%) translateY(0);
        }

        .flying-item {
            position: fixed;
            pointer-events: none;
            z-index: 9998;
            animation: itemFly 2.8s ease-out forwards;
        }

        @keyframes itemFly {
            0%   { transform: translate(0, 0) rotate(0deg) scale(0.6); opacity: 1; }
            35%  { transform: translate(var(--fx), var(--fy)) rotate(200deg) scale(1.3); opacity: 1; }
            100% { transform: translate(var(--fx2), var(--fy2)) rotate(440deg) scale(0.2); opacity: 0; }
        }

        @keyframes smokeRise {
            0%   { transform: translateX(-50%) translateY(0) scale(1); opacity: 0.6; }
            100% { transform: translateX(-50%) translateY(-50px) scale(2.5); opacity: 0; }
        }

        /* ============================================
           ENVELOPE OVERLAY
           ============================================ */
        .envelope-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(ellipse 80% 70% at 50% 40%,
                #f9ebe8 0%,
                #f2d8d2 55%,
                #e8c5bc 100%);
            z-index: 2000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 40px;
            transition: opacity 1.8s cubic-bezier(0.4, 0, 0.2, 1), visibility 1.8s;
            will-change: opacity;
        }

        .envelope-overlay.hidden {
            opacity: 0;
            visibility: hidden;
            pointer-events: none;
        }

        .envelope-bob {
            animation: envelopeBob 4s ease-in-out infinite;
            will-change: transform;
        }

        .envelope-bob.open {
            animation: envelopeSettle 0.6s cubic-bezier(0.34, 1.4, 0.64, 1) forwards;
        }

        @keyframes envelopeBob {
            0%, 100% { transform: translateY(0px); }
            50%      { transform: translateY(-10px); }
        }

        @keyframes envelopeSettle {
            0%   { transform: translateY(var(--bob-offset, 0px)); }
            100% { transform: translateY(0px); }
        }

        .envelope-wrapper {
            position: relative;
            width: 320px;
            height: 230px;
            cursor: pointer;
            perspective: 1200px;
            perspective-origin: 50% 0%;
            filter:
                drop-shadow(0 18px 40px rgba(190, 130, 120, 0.28))
                drop-shadow(0 4px 8px rgba(190, 130, 120, 0.15));
        }

        .env-body {
            position: absolute;
            inset: 0;
            border-radius: 14px;
            background: linear-gradient(160deg, #fdf0ee 40%, #f8e0da 100%);
            border: 1.2px solid rgba(210, 155, 145, 0.55);
            box-shadow:
                0 2px 0px rgba(210, 155, 145, 0.4),
                inset 0 1px 2px rgba(255, 255, 255, 0.8);
            overflow: hidden;
        }

        .env-body::before {
            content: '';
            position: absolute;
            inset: 0;
            background:
                linear-gradient(135deg, rgba(195, 145, 135, 0.13) 0%, transparent 42%),
                linear-gradient(225deg, rgba(195, 145, 135, 0.10) 0%, transparent 42%),
                linear-gradient(0deg, rgba(195, 145, 135, 0.16) 0%, transparent 38%);
            pointer-events: none;
        }

        .env-body::after {
            content: '';
            position: absolute;
            inset: 6px;
            border-radius: 9px;
            border: 1px solid rgba(255, 255, 255, 0.55);
            pointer-events: none;
        }

        .env-letter {
            position: absolute;
            bottom: 10px;
            left: 14px;
            right: 14px;
            height: 0;
            overflow: hidden;
            background: linear-gradient(170deg, #fffcfb 60%, #fef0ee);
            border-radius: 8px;
            border: 1px solid rgba(220, 170, 160, 0.4);
            transition: height 1.05s 0.45s cubic-bezier(0.34, 1.15, 0.64, 1);
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow:
                0 -2px 12px rgba(190, 130, 120, 0.12),
                0 4px 16px rgba(190, 130, 120, 0.10);
            z-index: 2;
            will-change: height;
        }

        .envelope-wrapper.open .env-letter {
            height: 130px;
        }

        .env-letter-inner {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            opacity: 0;
            transform: translateY(10px);
            transition:
                opacity 0.55s 1.2s ease,
                transform 0.55s 1.2s cubic-bezier(0.34, 1.2, 0.64, 1);
        }

        .envelope-wrapper.open .env-letter-inner {
            opacity: 1;
            transform: translateY(0);
        }

        .env-letter-emoji {
            font-size: 2.2rem;
            line-height: 1;
        }

        .env-letter-text {
            font-size: 1rem;
            color: #c47a7a;
            font-family: 'Patrick Hand', cursive;
            letter-spacing: 1.5px;
            text-align: center;
        }

        .env-flap-container {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 130px;
            z-index: 6;
            pointer-events: none;
            perspective: 1200px;
            perspective-origin: 50% 0%;
        }

        .env-flap {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 130px;
            background: linear-gradient(175deg, #f5d5ce 0%, #eec5bc 50%, #e8b8ae 100%);
            border-radius: 14px 14px 0 0;
            clip-path: polygon(0 0, 100% 0, 50% 78%);
            border: 1.2px solid rgba(210, 155, 145, 0.5);
            transform-origin: top center;
            transform: rotateX(0deg);
            transition: transform 1.0s cubic-bezier(0.25, 0.85, 0.25, 1);
            will-change: transform;
            backface-visibility: hidden;
            box-shadow: inset 0 -8px 20px rgba(180, 110, 100, 0.12);
        }

        .env-flap::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 28px;
            background: linear-gradient(to bottom, rgba(255, 255, 255, 0.35) 0%, transparent 100%);
            border-radius: 14px 14px 0 0;
            pointer-events: none;
        }

        .env-flap::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(175deg, rgba(0, 0, 0, 0.0) 0%, rgba(140, 80, 70, 0.10) 100%);
            transition: opacity 1.0s ease;
            pointer-events: none;
        }

        .envelope-wrapper.open .env-flap {
            transform: rotateX(-178deg);
        }

        .envelope-wrapper.open .env-flap::after {
            opacity: 0;
        }

        .env-seal {
            position: absolute;
            top: calc(130px * 0.78 - 20px);
            left: 50%;
            transform: translateX(-50%);
            font-size: 2rem;
            z-index: 7;
            pointer-events: none;
            transition:
                opacity 0.3s 0.05s ease,
                transform 0.3s 0.05s cubic-bezier(0.34, 1.2, 0.64, 1);
            will-change: opacity, transform;
            filter: drop-shadow(0 2px 6px rgba(190, 130, 120, 0.3));
        }

        .envelope-wrapper.open .env-seal {
            opacity: 0;
            transform: translateX(-50%) scale(0.5) translateY(-6px);
        }

        .envelope-label {
            font-family: 'Cormorant Garamond', Georgia, serif;
            font-style: italic;
            font-weight: 500;
            font-size: 1.25rem;
            color: rgba(160, 110, 100, 0.75);
            letter-spacing: 0.05em;
            text-align: center;
            animation: labelBreath 3s ease-in-out infinite;
        }

        .envelope-label .sparkle-gold {
            color: #d4a843;
            font-style: normal;
            font-size: 0.9rem;
        }

        @keyframes labelBreath {
            0%, 100% { opacity: 0.7; }
            50%      { opacity: 1.0; }
        }

        .envelope-click-hint {
            display: none;
        }

        @keyframes flowerRain {
            0%   { transform: translateY(-60px) rotate(-10deg) scale(0.6); opacity: 0; }
            5%   { opacity: 1; }
            90%  { opacity: 0.9; }
            100% { transform: translateY(110vh) rotate(20deg) scale(0.9); opacity: 0; }
        }

        /* ============================================
           RESPONSIVE
           ============================================ */
        @media (max-width: 600px) {
            h1           { font-size: 2rem; }
            .name        { font-size: 3rem; }
            .bouquet     { font-size: 3.5rem; }
            .main-cake   { font-size: 3.5rem; }
            .message-card {
                width: 92vw;
                max-width: 92vw;
                padding: 20px 18px;
                margin: 15px auto;
            }
            .message-text { font-size: 1.05rem; }
            .bunny-art   { font-size: 0.9rem; padding: 10px 15px; }
            .btn         { padding: 10px 28px; font-size: 1.1rem; }
        }
    </style>
</head>
<body>
    <!-- ============================================
         BACKGROUND
         ============================================ -->
    <div class="ocean-bg"></div>

    <!-- Waves -->
    <div class="wave wave-1"></div>
    <div class="wave wave-2"></div>
    <div class="wave wave-3"></div>

    <!-- Clouds -->
    <div class="cloud cloud-1"></div>
    <div class="cloud cloud-2"></div>
    <div class="cloud cloud-3"></div>

    <!-- ============================================
         ENVELOPE OVERLAY
         ============================================ -->
    <div class="envelope-overlay" id="envelopeOverlay">
        <div class="envelope-bob" id="envelopeBob">
            <div class="envelope-wrapper" id="envelopeWrapper">
                <div class="env-body"></div>
                <div class="env-letter">
                    <div class="env-letter-inner">
                        <div class="env-letter-emoji">🎂🌷</div>
                        <div class="env-letter-text">For Leecha ✨</div>
                    </div>
                </div>
                <div class="env-flap-container">
                    <div class="env-flap" id="envFlap"></div>
                </div>
                <div class="env-seal" id="envSeal">💌</div>
            </div>
        </div>
        <div class="envelope-label">A surprise awaits...</div>
        <div class="envelope-click-hint">Click to open 💌</div>
    </div>

    <!-- ============================================
         OPENING OVERLAY
         ============================================ -->
    <div class="opening-overlay" id="openingOverlay">
        <div class="opening-bubble" id="openingBubble">
            <div class="ponyo-cake">🎂</div>
        </div>
        <div class="candles-row">
            <div class="ponyo-candle">
                <div class="ponyo-flame" id="oFlame1"></div>
                <div class="candle-body"></div>
            </div>
            <div class="ponyo-candle">
                <div class="ponyo-flame" id="oFlame2"></div>
                <div class="candle-body"></div>
            </div>
            <div class="ponyo-candle">
                <div class="ponyo-flame" id="oFlame3"></div>
                <div class="candle-body"></div>
            </div>
        </div>
        <div class="opening-text">Make a wish, Leecha...</div>
        <div class="hint-text">Blow the candles or click the bubble ✨</div>
    </div>

    <!-- ============================================
         MAIN CONTENT
         ============================================ -->
    <div class="container" id="mainContent">
        <h1>Happy Birthday</h1>
        <div class="name">Leecha 🥳🎉</div>

        <!-- Bunny ASCII Art -->
        <div class="bunny-art">(\_(/)
(• .•)
(&gt;🌷</div>

        <!-- Bouquet -->
        <div class="bouquet-container" id="bouquet" onclick="shakeBouquet()">
            <div class="bouquet">💐</div>
            <div class="bouquet-ribbon"></div>
        </div>

        <!-- Cake -->
        <div class="cake-wrapper" id="cakeWrapper" onclick="blowMainCandles()">
            <div class="main-cake" id="mainCake">🎂</div>
            <div class="main-candles">
                <div class="ponyo-candle">
                    <div class="ponyo-flame" id="mFlame1"></div>
                    <div class="candle-body"></div>
                </div>
                <div class="ponyo-candle">
                    <div class="ponyo-flame" id="mFlame2"></div>
                    <div class="candle-body"></div>
                </div>
                <div class="ponyo-candle">
                    <div class="ponyo-flame" id="mFlame3"></div>
                    <div class="candle-body"></div>
                </div>
            </div>
        </div>

        <!-- Message -->
        <div class="message-card">
            <div class="message-text">
                Wishing you a day as bright and wonderful as you are —
                may this year bring you joy, laughter, and all the little
                things that make you smile.
            </div>
        </div>

        <button class="btn" onclick="celebrate()">click here to celebrate 🌷</button>
    </div>

    <!-- ============================================
         EASTER EGG
         ============================================ -->
    <div class="easter-egg" id="easterEgg">🐡</div>
    <div class="secret-toast" id="secretToast">🍖 Ponyo found you! She just wants ham! 🐟✨</div>

    <!-- ============================================
         SCRIPTS
         ============================================ -->
    <script>
        /* ============================================
           CONSTANTS
           ============================================ */
        const ponyoColors  = ['#FF6B6B', '#4ECDC4', '#FFD93D', '#FF8E8E', '#95E1D3', '#F38181', '#AA96DA', '#FCBAD3'];
        const fishEmojis   = ['🐟', '🐠', '🐡', '🦈', '🐬', '🐳', '🦑', '🐙'];
        const flowerEmojis = ['🌷', '🪷', '🌷', '🪷', '🌷', '🪷', '🌷'];

        // Store interval IDs for cleanup
        let intervals = [];

        /* ============================================
           BUBBLES
           ============================================ */
        function createBubble() {
            const bubble = document.createElement('div');
            bubble.className = 'bubble';
            const size = Math.random() * 40 + 15;
            bubble.style.width  = size + 'px';
            bubble.style.height = size + 'px';
            bubble.style.left   = Math.random() * 100 + 'vw';
            bubble.style.animationDuration = (Math.random() * 8 + 6) + 's';
            bubble.style.animationDelay    = Math.random() * 5 + 's';
            document.body.appendChild(bubble);
            setTimeout(() => bubble.remove(), 15000);
        }

        /* ============================================
           WATER BALLOONS
           ============================================ */
        function createWaterBalloon() {
            const balloon = document.createElement('div');
            balloon.className = 'water-balloon';
            const size = Math.random() * 35 + 25;
            balloon.style.width  = size + 'px';
            balloon.style.height = size * 1.1 + 'px';
            balloon.style.left   = Math.random() * 90 + 5 + 'vw';
            balloon.style.background = `radial-gradient(
                circle at 35% 35%,
                ${ponyoColors[Math.floor(Math.random() * ponyoColors.length)]} 0%,
                ${ponyoColors[Math.floor(Math.random() * ponyoColors.length)]}80 100%
            )`;
            balloon.style.animationDuration = (Math.random() * 4 + 5) + 's';
            balloon.style.animationDelay    = Math.random() * 3 + 's';
            balloon.addEventListener('click', (e) => {
                e.stopPropagation();
                popBalloon(balloon, e.clientX, e.clientY);
            });
            document.body.appendChild(balloon);
            setTimeout(() => { if (balloon.parentNode) balloon.remove(); }, 10000);
        }

        function popBalloon(element, x, y) {
            element.classList.add('pop');
            for (let i = 0; i < 8; i++) {
                const splash = document.createElement('div');
                splash.className = 'splash';
                splash.style.left   = x + 'px';
                splash.style.top    = y + 'px';
                splash.style.background = ponyoColors[Math.floor(Math.random() * ponyoColors.length)];
                splash.style.setProperty('--tx', (Math.random() * 100 - 50) + 'px');
                splash.style.setProperty('--ty', (Math.random() * 80 + 20) + 'px');
                document.body.appendChild(splash);
                setTimeout(() => splash.remove(), 600);
            }
            setTimeout(() => element.remove(), 300);
        }

        /* ============================================
           FISH
           ============================================ */
        function createFish() {
            const fish = document.createElement('div');
            fish.className = 'fish';
            fish.textContent = fishEmojis[Math.floor(Math.random() * fishEmojis.length)];
            fish.style.top              = Math.random() * 80 + 10 + '%';
            fish.style.animationDuration = (Math.random() * 15 + 10) + 's';
            fish.style.animationDelay    = Math.random() * 10 + 's';
            fish.style.fontSize          = (Math.random() * 1.5 + 1.5) + 'rem';
            document.body.appendChild(fish);
            setTimeout(() => fish.remove(), 25000);
        }

        /* ============================================
           SPARKLES
           ============================================ */
        function createSparkle() {
            const sparkle = document.createElement('div');
            sparkle.className = 'sparkle';
            sparkle.style.left = Math.random() * 100 + 'vw';
            sparkle.style.top  = Math.random() * 100 + 'vh';
            sparkle.style.animationDelay = Math.random() * 2 + 's';
            document.body.appendChild(sparkle);
            setTimeout(() => sparkle.remove(), 3000);
        }

        /* ============================================
           STARFISH
           ============================================ */
        function createStarfish() {
            const starfish = document.createElement('div');
            starfish.className = 'starfish';
            starfish.textContent = '⭐';
            starfish.style.left              = Math.random() * 90 + 5 + '%';
            starfish.style.top               = Math.random() * 90 + 5 + '%';
            starfish.style.animationDelay    = Math.random() * 5 + 's';
            starfish.style.animationDuration = (Math.random() * 3 + 4) + 's';
            document.body.appendChild(starfish);
        }

        /* ============================================
           CONFETTI
           ============================================ */
        function createConfetti() {
            const confetti = document.createElement('div');
            confetti.className = 'confetti';
            confetti.style.left = Math.random() * 100 + 'vw';
            confetti.style.background = ponyoColors[Math.floor(Math.random() * ponyoColors.length)];
            confetti.style.animationDuration = (Math.random() * 3 + 2) + 's';
            confetti.style.borderRadius = Math.random() > 0.5 ? '50%' : '2px';
            document.body.appendChild(confetti);
            setTimeout(() => confetti.remove(), 6000);
        }

        /* ============================================
           MAGIC PARTICLES
           ============================================ */
        function createMagicParticle(x, y) {
            const particle = document.createElement('div');
            particle.className = 'magic-particle';
            particle.style.left = x + 'px';
            particle.style.top  = y + 'px';
            particle.style.background = ponyoColors[Math.floor(Math.random() * ponyoColors.length)];
            particle.style.setProperty('--mx', (Math.random() * 200 - 100) + 'px');
            particle.style.setProperty('--my', (Math.random() * 200 - 100) + 'px');
            document.body.appendChild(particle);
            setTimeout(() => particle.remove(), 3000);
        }

        /* ============================================
           CANDLES
           ============================================ */
        function blowOutOpeningCandles() {
            const flames = document.querySelectorAll('#openingOverlay .ponyo-flame');
            flames.forEach((flame, i) => {
                setTimeout(() => {
                    flame.style.animation = 'none';
                    flame.style.transform = 'translateX(-50%) scale(0)';
                    flame.style.opacity   = '0';
                    flame.style.transition = 'all 0.5s ease-out';
                    const smoke = document.createElement('div');
                    smoke.style.cssText = `
                        position: absolute;
                        width: 10px;
                        height: 10px;
                        background: rgba(200, 200, 200, 0.5);
                        border-radius: 50%;
                        top: -30px;
                        left: 50%;
                        transform: translateX(-50%);
                        animation: smokeRise 1.5s ease-out forwards;
                    `;
                    flame.parentNode.appendChild(smoke);
                    setTimeout(() => smoke.remove(), 1500);
                }, i * 200);
            });

            setTimeout(() => {
                document.getElementById('openingOverlay').classList.add('hidden');
                document.getElementById('mainContent').classList.add('visible');
                startMainScene();
            }, 1200);
        }

        let mainCandlesBlown = false;

        function blowMainCandles() {
            if (mainCandlesBlown) return;
            mainCandlesBlown = true;
            const flames = document.querySelectorAll('#mainContent .ponyo-flame');
            flames.forEach((flame, i) => {
                setTimeout(() => {
                    flame.style.animation = 'none';
                    flame.style.transform = 'translateX(-50%) scale(0)';
                    flame.style.opacity   = '0';
                    flame.style.transition = 'all 0.5s ease-out';
                }, i * 150);
            });
            setTimeout(() => {
                document.getElementById('mainCake').textContent = '🍰';
                document.querySelector('.name').style.color = '#FFD93D';
            }, 800);
        }

        /* ============================================
           BOUQUET INTERACTION
           ============================================ */
        function shakeBouquet() {
            const bouquet = document.querySelector('.bouquet');
            bouquet.style.animation = 'none';
            bouquet.offsetHeight;
            bouquet.style.animation = 'bouquetSway 0.5s ease-in-out 3';
            const rect = document.getElementById('bouquet').getBoundingClientRect();
            for (let i = 0; i < 12; i++) {
                setTimeout(() => {
                    createMagicParticle(
                        rect.left + rect.width / 2,
                        rect.top  + rect.height / 2
                    );
                }, i * 50);
            }
        }

        /* ============================================
           CELEBRATION EFFECTS
           ============================================ */
        function createFlowerItem() {
            const el = document.createElement('div');
            el.style.cssText = `
                position: fixed;
                font-size: ${1.5 + Math.random() * 2}rem;
                left: ${Math.random() * 95}vw;
                top: -50px;
                z-index: 998;
                pointer-events: none;
                animation: flowerRain ${2.2 + Math.random() * 2.2}s ease-in forwards;
            `;
            el.textContent = flowerEmojis[Math.floor(Math.random() * flowerEmojis.length)];
            document.body.appendChild(el);
            setTimeout(() => el.remove(), 5500);
        }

        function celebrate() {
            for (let i = 0; i < 35; i++) setTimeout(createFlowerItem, i * 55);
            for (let i = 0; i < 60; i++) setTimeout(createConfetti, i * 30);
            for (let i = 0; i < 15; i++) setTimeout(createBubble, i * 100);
            for (let i = 0; i < 10; i++) setTimeout(createWaterBalloon, i * 200);
            const name = document.querySelector('.name');
            name.style.animation = 'none';
            name.offsetHeight;
            name.style.animation = 'nameGlow 1s ease-in-out 3';
        }

        /* ============================================
           MAIN SCENE
           ============================================ */
        function startMainScene() {
            for (let i = 0; i < 15; i++) createBubble();
            for (let i = 0; i < 8;  i++) setTimeout(createWaterBalloon, i * 500);
            for (let i = 0; i < 5;  i++) setTimeout(createFish, i * 2000);
            for (let i = 0; i < 10; i++) createSparkle();
            for (let i = 0; i < 6;  i++) createStarfish();
            intervals.push(setInterval(createBubble, 1500));
            intervals.push(setInterval(createWaterBalloon, 3000));
            intervals.push(setInterval(createFish, 8000));
            intervals.push(setInterval(createSparkle, 800));
        }

        /* ============================================
           ENVELOPE OPENING
           ============================================ */
        let envelopeOpened = false;

        function openEnvelope() {
            if (envelopeOpened) return;
            envelopeOpened = true;

            const bob     = document.getElementById('envelopeBob');
            const wrapper = document.getElementById('envelopeWrapper');

            const bobY = bob.getBoundingClientRect().top
                       - bob.parentElement.getBoundingClientRect().top;
            bob.style.setProperty('--bob-offset', bobY + 'px');

            bob.classList.add('open');

            setTimeout(() => {
                wrapper.classList.add('open');
            }, 180);

            setTimeout(() => {
                document.getElementById('envelopeOverlay').classList.add('hidden');
            }, 2400);
        }

        document.getElementById('envelopeOverlay').addEventListener('click', openEnvelope);
        setTimeout(() => { if (!envelopeOpened) openEnvelope(); }, 5000);

        /* ============================================
           OPENING OVERLAY HANDLERS
           ============================================ */
        document.getElementById('openingOverlay').addEventListener('click', blowOutOpeningCandles);
        document.getElementById('openingBubble').addEventListener('click', (e) => {
            e.stopPropagation();
            blowOutOpeningCandles();
        });

        /* ============================================
           EASTER EGG
           ============================================ */
        document.getElementById('easterEgg').addEventListener('click', function (e) {
            e.stopPropagation();
            const toast = document.getElementById('secretToast');
            toast.classList.add('show');
            setTimeout(() => toast.classList.remove('show'), 3800);

            const burst = ['🍖', '🐟', '🍖', '🐡', '🍖', '🌊', '🍖', '🐠'];
            burst.forEach((emoji, i) => {
                setTimeout(() => {
                    const el = document.createElement('div');
                    el.className = 'flying-item';
                    el.textContent = emoji;
                    el.style.fontSize = (1.4 + Math.random() * 0.8) + 'rem';
                    el.style.right  = (10 + Math.random() * 20) + 'px';
                    el.style.bottom = '30px';
                    const angle = (Math.random() * 120 + 120) * (Math.PI / 180);
                    const dist1 = 100 + Math.random() * 150;
                    const dist2 = 200 + Math.random() * 250;
                    el.style.setProperty('--fx',  (-Math.cos(angle) * dist1) + 'px');
                    el.style.setProperty('--fy',  (-Math.sin(angle) * dist1) + 'px');
                    el.style.setProperty('--fx2', (-Math.cos(angle) * dist2 + (Math.random() * 60 - 30)) + 'px');
                    el.style.setProperty('--fy2', (-Math.sin(angle) * dist2 + (Math.random() * 60 - 30)) + 'px');
                    document.body.appendChild(el);
                    setTimeout(() => el.remove(), 2900);
                }, i * 110);
            });
        });
    </script>
</body>
</html>
'''

with open('/mnt/agents/output/happy_birthday_leecha.html', 'w', encoding='utf-8') as f:
    f.write(html_content)

print("File saved successfully!")
print(f"File size: {len(html_content)} characters")
