# MelSam-SMP <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MelSamsMP - Lifesteal SMP</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            color: #ffffff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            padding: 40px 0;
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            margin-bottom: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
        }

        .server-name {
            font-size: 4rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #f9ca24);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.3);
            margin-bottom: 10px;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 20px #ff6b6b); }
            to { filter: drop-shadow(0 0 30px #4ecdc4); }
        }

        .server-tag {
            font-size: 1.5rem;
            color: #4ecdc4;
            margin-bottom: 20px;
        }

        .owner-info {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .owner-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: transform 0.3s ease;
        }

        .owner-card:hover {
            transform: translateY(-10px);
        }

        .owner-name {
            font-size: 1.3rem;
            color: #f9ca24;
        }

        main {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }

        .section {
            background: rgba(0, 0, 0, 0.4);
            padding: 40px;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease;
        }

        .section:hover {
            transform: translateY(-5px);
        }

        .section h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .features {
            grid-column: 1 / -1;
        }

        .feature-list {
            list-style: none;
            padding: 0;
        }

        .feature-list li {
            padding: 15px 0;
            font-size: 1.2rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .feature-list li::before {
            content: "⚡";
            font-size: 1.5rem;
        }

        .discord-btn {
            display: block;
            width: 100%;
            max-width: 300px;
            margin: 30px auto 0;
            padding: 20px;
            background: linear-gradient(45deg, #7289da, #99aab5);
            color: white;
            text-decoration: none;
            text-align: center;
            font-size: 1.5rem;
            font-weight: bold;
            border-radius: 50px;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(114, 137, 218, 0.4);
        }

        .discord-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 40px rgba(114, 137, 218, 0.6);
        }

        .server-ip {
            background: rgba(76, 175, 80, 0.2);
            padding: 30px;
            text-align: center;
            border-radius: 15px;
            margin: 20px 0;
            border: 2px solid #4caf50;
        }

        .ip-text {
            font-size: 2rem;
            font-weight: bold;
            color: #4caf50;
            margin-bottom: 10px;
        }

        footer {
            text-align: center;
            padding: 40px 0;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 20px;
            margin-top: 40px;
        }

        @media (max-width: 768px) {
            main {
                grid-template-columns: 1fr;
            }
            
            .server-name {
                font-size: 2.5rem;
            }
            
            .section {
                padding: 30px 20px;
            }
        }

        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #4ecdc4;
            border-radius: 50%;
            animation: float 6s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>
    
    <div class="container">
        <header>
            <h1 class="server-name">MelSamsMP</h1>
            <p class="server-tag">Lifesteal SMP</p>
            <div class="owner-info">
                <div class="owner-card">
                    <div class="owner-name">👑 Owner: itzsamog</div>
                </div>
                <div class="owner-card">
                    <div class="owner-name">👑 Owner: melxi</div>
                </div>
            </div>
        </header>

        <main>
            <div class="section">
                <h2>🚀 Server Info</h2>
                <div class="server-ip">
                    <div class="ip-text">melsamsmp.net</div>
                    <p style="color: #ccc;">Copy & Join Now!</p>
                </div>
                <p><strong>Version:</strong> 1.20.1+</p>
                <p><strong>Gamemode:</strong> Lifesteal SMP</p>
            </div>

            <div class="section">
                <h2>⚔️ Lifesteal Features</h2>
                <ul class="feature-list">
                    <li>Kill players to steal hearts!</li>
                    <li>Lose hearts when you die</li>
                    <li>0 hearts = permanent ban</li>
                    <li>Custom crafting recipes</li>
                    <li>Regular events & tournaments</li>
                    <li>Active staff team</li>
                </ul>
            </div>

            <div class="section features">
                <h2>🎮 Why Join MelSamsMP?</h2>
                <ul class="feature-list">
                    <li>💎 Custom plugins & features</li>
                    <li>🏆 Leaderboards & competitions</li>
                    <li>🛡️ Anti-cheat protection</li>
                    <li>🌍 Huge custom world</li>
                    <li>👥 Friendly community</li>
                    <li>📱 Mobile-friendly Discord</li>
                </ul>
                
                <a href="https://discord.gg/JfYedbuSU" target="_blank" class="discord-btn">
                    🎉 Join Discord Server
                </a>
            </div>
        </main>

        <footer>
            <h3>Ready to steal some hearts?</h3>
            <p>Join <strong>melsamsmp.aternos.me</strong> and start your lifesteal adventure!</p>
            <p>&copy; 2026 MelSamsMP. Made with ❤️ by itzsamog & melxi</p>
        </footer>
    </div>

    <script>
        // Floating particles effect
        function createParticle() {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDuration = (Math.random() * 3 + 4) + 's';
            particle.style.animationDelay = Math.random() * 2 + 's';
            document.getElementById('particles').appendChild(particle);

            setTimeout(() => {
                particle.remove();
            }, 7000);
        }

        // Create particles continuously
        setInterval(createParticle, 300);

        // Copy IP to clipboard
        document.querySelector('.ip-text').addEventListener('click', function() {
            navigator.clipboard.writeText('melsamsmp.aternos.me');
            const originalText = this.textContent;
            this.textContent = 'Copied!';
            this.style.color = '#ffeb3b';
            setTimeout(() => {
                this.textContent = originalText;
                this.style.color = '#4caf50';
            }, 2000);
        });
    </script>
</body>
</html>
