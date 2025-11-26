    /* 점수판 - 놀이동산 간판 느낌 */
    #score-board {
        position: absolute;
        top: 20px;
        left: 50%;
        transform: translateX(-50%);
        background: linear-gradient(to right, #FFD700, #FFC107);
        border: 4px solid #FFA000;
        padding: 10px 40px;
        border-radius: 15px;
        box-shadow: 0 8px 15px rgba(0,0,0,0.3);
        font-size: 32px;
        font-weight: bold;
        color: #8B4513;
        z-index: 100;
        display: flex;
        align-items: center;
        gap: 15px;
        text-shadow: 2px 2px 3px rgba(255,255,255,0.7);
        animation: bounceIn 0.8s ease-out;
    }
    @keyframes bounceIn {
        0% { transform: translateX(-50%) scale(0.3); opacity: 0; }
        50% { transform: translateX(-50%) scale(1.1); opacity: 1; }
        70% { transform: translateX(-50%) scale(0.9); }
        100% { transform: translateX(-50%) scale(1); }
    }

    /* 시작/종료 화면 - 더 화려하게 */
    #overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.75); 
        backdrop-filter: blur(5px); 
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        z-index: 200;
        color: white;
        text-align: center;
        animation: fadeIn 0.5s ease-out;
    }
    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }

    #overlay h1 { font-size: 60px; margin: 0 0 20px 0; color: #FFD700; text-shadow: 4px 4px 6px #8B4513; animation: pulse 2s infinite; }
    @keyframes pulse {
        0% { transform: scale(1); }
        50% { transform: scale(1.05); }
        100% { transform: scale(1); }
    }
    #overlay p { font-size: 26px; line-height: 1.8; color: #E0E0E0; text-shadow: 1px 1px 2px #000; }
    #start-btn {
        margin-top: 40px;
        padding: 18px 60px;
        font-size: 32px;
        background-color: #FF4500; 
        color: white;
        border: none;
        border-radius: 60px;
        cursor: pointer;
        font-family: inherit;
        box-shadow: 0 8px 0 #CD3700, 0 0 15px rgba(255,255,255,0.6);
        transition: transform 0.1s, box-shadow 0.1s;
        letter-spacing: 2px;
    }
    #start-btn:active { transform: translateY(8px); box-shadow: 0 0 0 #CD3700; }

    /* 풍선 스타일 (XL 사이즈 유지) */
    .balloon {
        position: absolute;
        bottom: -250px;
        width: 180px;
        height: 220px;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 20px;
        box-sizing: border-box;
        cursor: url('https://user-images.githubusercontent.com/120281699/281696043-982c75a4-944a-4d22-b5e1-80a9d80c1dfd.png') 25 25, pointer;
        font-size: 20px; 
        font-weight: 900;
        line-height: 1.3;
        box-shadow: inset -15px -15px 30px rgba(0,0,0,0.15);
        transition: transform 0.1s;
        color: #333;
        word-break: keep-all;
        text-shadow: 1px 1px 2px rgba(255,255,255,0.5);
    }
    
    /* 풍선 꼬리 */
    .balloon::after {
        content: '';
        position: absolute;
        bottom: -15px;
        left: 50%;
        transform: translateX(-50%);
        border-left: 15px solid transparent;
        border-right: 15px solid transparent;
        border-top: 15px solid inherit;
    }
    
    /* 풍선 실 */
    .balloon::before {
        content: '';
        position: absolute;
        bottom: -80px;
        left: 50%;
        width: 2px;
        height: 80px;
        background-color: rgba(0,0,0,0.3);
    }

    /* 터지는 효과 - 폭죽 느낌 */
    .pop-effect {
        animation: popBalloon 0.3s forwards;
        pointer-events: none;
    }
    @keyframes popBalloon {
        0% { transform: scale(1); opacity: 1; }
        50% { transform: scale(1.2); opacity: 0.8; }
        100% { transform: scale(0.1); opacity: 0; }
    }

    /* 폭죽 효과 */
    .firework {
        position: absolute;
        width: 20px;
        height: 20px;
        background-color: transparent;
        border-radius: 50%;
        transform: translate(-50%, -50%);
        animation: explode 0.8s forwards;
        pointer-events: none;
        z-index: 101;
    }
    @keyframes explode {
        0% { transform: scale(0); opacity: 1; }
        10% { box-shadow: 0 0 0 5px rgba(255, 255, 0, 0.7), 0 0 0 10px rgba(255, 165, 0, 0.5), 0 0 0 15px rgba(255, 0, 0, 0.3); }
        50% { box-shadow: 0 0 0 20px rgba(255, 255, 0, 0.7), 0 0 0 30px rgba(255, 165, 0, 0.5), 0 0 0 40px rgba(255, 0, 0, 0.3); opacity: 0.5; }
        100% { transform: scale(1); box-shadow: none; opacity: 0; }
    }

    /* 폰트 임포트 */
    @import url('https://fonts.googleapis.com/css2?family=Jua&display=swap');
</style>
