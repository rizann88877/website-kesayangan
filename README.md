<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday My Love</title>
    <script src=""></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap');
        
        body {
            background: linear-gradient(135deg, #4690ff 0%, #4690ff 50%, #4690ff 100%);
            font-family: 'Poppins', sans-serif;
            min-height: 100vh;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }
        
        .birthday-card {
            position: relative;
            width: 90%;
            max-width: 500px;
            margin: 30px auto;
            padding: 30px;
            background: white;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            text-align: center;
            overflow: hidden;
            transform-style: preserve-3d;
            transition: all 0.5s ease;
        }
        
        .birthday-card:hover {
            transform: translateY(-10px) rotateY(5deg);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }
        
        .heart {
            position: absolute;
            background-color: #4690ff;
            display: inline-block;
            height: 20px;
            width: 20px;
            transform: rotate(-45deg);
            animation: float 4s ease-in-out infinite;
        }
        
        .heart:before, .heart:after {
            content: "";
            background-color: #4690ff;
            border-radius: 50%;
            height: 20px;
            position: absolute;
            width: 20px;
        }
        
        .heart:before {
            top: -10px;
            left: 0;
        }
        
        .heart:after {
            left: 10px;
            top: 0;
        }
        
        @keyframes float {
            0%, 100% {
                transform: translateY(0) rotate(-45deg);
            }
            50% {
                transform: translateY(-20px) rotate(-45deg);
            }
        }
        
        .title {
            font-family: 'Dancing Script', cursive;
            color: #4690ff;
            font-size: 2.8rem;
            margin: 15px 0;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.1);
        }
        
        .subtitle {
            color: #495057;
            font-size: 1.2rem;
            margin-bottom: 20px;
        }
        
        .message {
            font-size: 1.1rem;
            line-height: 1.6;
            color: #495057;
            margin-bottom: 25px;
            text-align: left;
        }
        
        .signature {
            font-family: 'Dancing Script', cursive;
            font-size: 1.8rem;
            color: #4690ff;
            margin-top: 30px;
        }
        
        .cake-container {
            width: 150px;
            height: 150px;
            margin: 0 auto 25px;
            position: relative;
        }
        
        .cake {
            position: relative;
            width: 100%;
            height: 100%;
        }
        
        .candle {
            position: absolute;
            width: 8px;
            height: 40px;
            background: linear-gradient(to bottom, #ff9a9e 0%, #fad0c4 100%);
            border-radius: 4px;
            top: -40px;
            left: 50%;
            transform: translateX(-50%);
            box-shadow: 0 0 20px rgba(255, 204, 0, 0.7);
        }
        
        .flame {
            position: absolute;
            width: 15px;
            height: 25px;
            background: linear-gradient(to bottom, #fff5b7 0%, #ffde59 50%, #ff9500 100%);
            border-radius: 50% 50% 20% 20%;
            top: -65px;
            left: 50%;
            transform: translateX(-50%);
            animation: flicker 0.8s infinite alternate;
        }
        
        @keyframes flicker {
            0% {
                opacity: 1;
                transform: translateX(-50%) scale(1);
                box-shadow: 0 0 15px 5px rgba(255, 204, 0, 0.5);
            }
            50% {
                opacity: 0.9;
                transform: translateX(-50%) scale(1.1, 1);
                box-shadow: 0 0 20px 8px rgba(255, 204, 0, 0.7);
            }
            100% {
                opacity: 0.8;
                transform: translateX(-50%) scale(1);
                box-shadow: 0 0 10px 3px rgba(255, 204, 0, 0.3);
            }
        }
        
        .button {
            background: linear-gradient(to right, #ff758c, #ff7eb3);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 30px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 117, 140, 0.4);
        }
        
        .button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 117, 140, 0.6);
        }
        
        .button:active {
            transform: translateY(0);
        }
        
        .hidden-message {
            display: none;
            margin-top: 30px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
        }
        
        .photo-collage {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin: 30px 0;
        }
        
        .photo-collage img {
            width: 100%;
            border-radius: 10px;
            transition: transform 0.3s ease;
            cursor: pointer;
        }
        
        .photo-collage img:hover {
            transform: scale(1.05);
        }
        
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background-color: #f00;
            animation: confetti-fall 5s linear;
            opacity: 0;
        }
        
        @keyframes confetti-fall {
            0% {
                transform: translateY(-100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(720deg);
                opacity: 0;
            }
        }
        
        .music-control {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 100;
        }
        
        .music-btn {
            background: #4690ff;
            color: white;
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }
    </style>
</head>
<body>
    <div id="app">
        <div class="birthday-card">
            <!-- Hearts floating around -->
            <div class="heart" style="top: 20%; left: 15%; animation-delay: 0.5s;"></div>
            <div class="heart" style="top: 80%; left: 85%; animation-delay: 1s;"></div>
            <div class="heart" style="top: 40%; left: 65%; animation-delay: 1.5s;"></div>
            <div class="heart" style="top: 60%; left: 25%; animation-delay: 2s;"></div>
            
            <h1 class="title">Happy Birthday My Love!</h1>
            <p class="subtitle">You My Favorite </p>
            
            <div class="cake-container">
                <div class="flame"></div>
                <div class="candle"></div>
                <img class="cake" src="c:\Users\user.DESKTOP-L3R9JOH.001\Documents\foto ultah\foto 7.jpg" alt="Beautiful birthday cake with pink frosting and fresh strawberries on top">
            </div>
            
            <div class="message">
                <p>My dearest,</p>
                <p>On your special day, I want you to know how much you mean to me. Every moment with you is a gift, and today we celebrate the wonderful person you are.</p>
                <p>May this year bring you endless joy, success in all your endeavors, and all the love you deserve (and that I'll be happy to give you every day).</p>
                <p>I love you more than words can express.</p>
            </div>
            
            <div class="photo-collage">
                <img src="image/foto 1.jpg" alt="img">
                <img src="image/foto 2.jpg" alt="Romantic dinner date with candlelight and wine">
                <img src="image/foto 3.jpg" alt="Funny selfie with silly faces and hats">
                <img src="image/foto 4.jpg" alt="Adventurous hiking trip with beautiful mountain view">
                <img src="c:\Users\user.DESKTOP-L3R9JOH.001\Documents\foto ultah\foto 5.jpg" alt="Cuddling on the couch watching movies">
                <img src="c:\Users\user.DESKTOP-L3R9JOH.001\Documents\foto ultah\foto 6.jpg" alt="Special moment kissing under mistletoe">
            </div>
            
            <button id="surpriseBtn" class="button">Click for a Surprise!</button>
            
            <div id="hiddenMessage" class="hidden-message">
                <h2 class="text-xl font-bold mb-3">To My Wonderful Partner</h2>
                <p>I've been thinking all day about how lucky I am to have you in my life. You make every day brighter just by being you.</p>
                <p>I promise to make this year your best one yet - filled with love, laughter, and unforgettable moments together.</p>
                <p>Happy birthday to the most amazing person I know!</p>
            </div>
            
            <div class="signature">Forever yours</div>
        </div>
    </div>
    
    <div class="music-control">
        <button id="musicBtn" class="music-btn">♫</button>
    </div>
    
    <audio id="birthdayMusic" loop>
        <source src="c:\Users\user.DESKTOP-L3R9JOH.001\Music\ytmp3free.cc_tulus-monokrom-lirik-lagu-lyrics-youtubemp3free.org.mp3" type="audio/mpeg">
    </audio>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Surprise button functionality
            const surpriseBtn = document.getElementById('surpriseBtn');
            const hiddenMessage = document.getElementById('hiddenMessage');
            
            surpriseBtn.addEventListener('click', function() {
                hiddenMessage.style.display = 'block';
                surpriseBtn.textContent = 'I Love You!';
                surpriseBtn.classList.add('bg-pink-500');
                
                // Create confetti effect
                createConfetti();
            });
            
            // Music control functionality
            const musicBtn = document.getElementById('musicBtn');
            const birthdayMusic = document.getElementById('birthdayMusic');
            
            musicBtn.addEventListener('click', function() {
                if (birthdayMusic.paused) {
                    birthdayMusic.play();
                    musicBtn.textContent = '♫';
                } else {
                    birthdayMusic.pause();
                    musicBtn.textContent = '♫';
                }
            });
            
            // Animate candles on hover
            const cake = document.querySelector('.cake');
            const candle = document.querySelector('.candle');
            const flame = document.querySelector('.flame');
            
            cake.addEventListener('mouseenter', function() {
                flame.style.animation = 'flicker 0.5s infinite alternate';
                candle.style.boxShadow = '0 0 25px rgba(255, 204, 0, 0.9)';
            });
            
            cake.addEventListener('mouseleave', function() {
                flame.style.animation = 'flicker 0.8s infinite alternate';
                candle.style.boxShadow = '0 0 20px rgba(255, 204, 0, 0.7)';
            });
            
            // Function to create confetti
            function createConfetti() {
                const colors = ['#ff4d6d', '#ff758c', '#ff8e9e', '#ffb3c1', '#ffd7e1'];
                
                for (let i = 0; i < 100; i++) {
                    const confetti = document.createElement('div');
                    confetti.className = 'confetti';
                    confetti.style.left = Math.random() * 100 + '%';
                    confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                    confetti.style.width = Math.random() * 10 + 5 + 'px';
                    confetti.style.height = Math.random() * 10 + 5 + 'px';
                    confetti.style.animationDuration = Math.random() * 3 + 2 + 's';
                    confetti.style.animationDelay = Math.random() * 2 + 's';
                    
                    document.body.appendChild(confetti);
                    
                    // Remove confetti after animation completes
                    setTimeout(() => {
                        confetti.remove();
                    }, 5000);
                }
            }
        });
    </script>
</body>
</html>

