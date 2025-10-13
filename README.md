<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aaditya Rawat - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #e0e0e0;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated Background */
        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(0, 255, 136, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(0, 150, 255, 0.1) 0%, transparent 50%);
            animation: gradientShift 15s ease infinite;
            z-index: -1;
            pointer-events: none;
        }

        @keyframes gradientShift {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(30px, -30px); }
        }

        /* Floating particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(0, 255, 136, 0.5);
            border-radius: 50%;
            animation: float linear infinite;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) translateX(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) translateX(100px) rotate(360deg);
                opacity: 0;
            }
        }

        /* Main container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 1;
        }

        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 80px;
            animation: slideDownFade 0.8s ease-out;
        }

        @keyframes slideDownFade {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header h1 {
            font-size: 4em;
            background: linear-gradient(135deg, #00ff88, #00d4ff, #ff006e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            animation: glow 3s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { filter: drop-shadow(0 0 10px rgba(0, 255, 136, 0.3)); }
            50% { filter: drop-shadow(0 0 25px rgba(0, 212, 255, 0.6)); }
        }

        .subtitle {
            font-size: 1.3em;
            color: #00ff88;
            margin-bottom: 20px;
            letter-spacing: 1px;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .tagline {
            font-size: 1em;
            color: #b0b0b0;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out 0.5s both;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 60px;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease-out 0.7s both;
        }

        .social-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(0, 255, 136, 0.1);
            border: 2px solid #00ff88;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5em;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .social-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(0, 255, 136, 0.3);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .social-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .social-btn:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.4);
            color: #00ff88;
        }

        /* Sections */
        .section {
            background: rgba(48, 43, 99, 0.3);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 255, 136, 0.2);
            border-radius: 15px;
            padding: 40px;
            margin-bottom: 40px;
            animation: slideInFade 0.8s ease-out;
            transition: all 0.3s ease;
        }

        @keyframes slideInFade {
            from {
                opacity: 0;
                transform: translateX(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .section:hover {
            border-color: rgba(0, 255, 136, 0.5);
            box-shadow: 0 10px 40px rgba(0, 255, 136, 0.1);
            transform: translateY(-5px);
        }

        .section h2 {
            font-size: 2em;
            color: #00ff88;
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            gap: 10px;
            position: relative;
            padding-bottom: 15px;
        }

        .section h2::after {
            content: '';
            flex-grow: 1;
            height: 2px;
            background: linear-gradient(90deg, #00ff88, transparent);
        }

        /* Tech Stack Grid */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .tech-item {
            background: rgba(0, 255, 136, 0.05);
            border: 2px solid rgba(0, 255, 136, 0.3);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(135deg, transparent, rgba(0, 255, 136, 0.2), transparent);
            animation: shine 3s infinite;
            transform: rotate(45deg);
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        .tech-item:hover {
            border-color: #00ff88;
            background: rgba(0, 255, 136, 0.1);
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 15px 40px rgba(0, 255, 136, 0.2);
        }

        .tech-item span {
            position: relative;
            z-index: 1;
            font-weight: 600;
            color: #00ff88;
        }

        /* Stats Section */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1), rgba(0, 150, 255, 0.1));
            border: 2px solid rgba(0, 255, 136, 0.3);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 136, 0.2), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .stat-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 50px rgba(0, 255, 136, 0.2);
            border-color: #00ff88;
        }

        .stat-number {
            font-size: 2.5em;
            color: #00ff88;
            font-weight: bold;
            margin-bottom: 10px;
            position: relative;
            z-index: 1;
        }

        .stat-label {
            color: #b0b0b0;
            font-size: 1em;
            position: relative;
            z-index: 1;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .about-text h3 {
            color: #00ff88;
            margin: 20px 0 10px 0;
            font-size: 1.3em;
        }

        .about-text p {
            color: #c0c0c0;
            margin-bottom: 15px;
            line-height: 1.8;
        }

        .about-list {
            list-style: none;
            margin-top: 20px;
        }

        .about-list li {
            color: #b0b0b0;
            margin: 12px 0;
            padding-left: 30px;
            position: relative;
            transition: all 0.3s ease;
        }

        .about-list li::before {
            content: '▸';
            color: #00ff88;
            position: absolute;
            left: 0;
            font-weight: bold;
        }

        .about-list li:hover {
            color: #00ff88;
            padding-left: 40px;
        }

        .about-image {
            text-align: center;
        }

        .about-image img {
            max-width: 100%;
            border-radius: 15px;
            border: 3px solid #00ff88;
            box-shadow: 0 0 30px rgba(0, 255, 136, 0.3);
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 40px;
            border-top: 2px solid rgba(0, 255, 136, 0.2);
            margin-top: 60px;
            animation: fadeInUp 1s ease-out 1s both;
        }

        .footer p {
            color: #b0b0b0;
            margin: 10px 0;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(135deg, #00ff88, #00d4ff);
            color: #0f0c29;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            margin-top: 20px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 255, 136, 0.5);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header h1 { font-size: 2.5em; }
            .about-content { grid-template-columns: 1fr; }
            .tech-grid { grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); }
            .section { padding: 25px; }
        }
    </style>
</head>
<body>
    <div class="animated-bg"></div>
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>👋 Aaditya Rawat</h1>
            <p class="subtitle">🚀 Blockchain Developer | Cybersecurity Enthusiast | Full-Stack Developer</p>
            <p class="tagline">Crafting innovative solutions with cutting-edge technology | From India 🇮🇳</p>
            
            <div class="social-links">
                <a href="https://github.com/Aaditya1273" class="social-btn" title="GitHub">🐙</a>
                <a href="https://www.linkedin.com/in/aditya-rawat-84970b301" class="social-btn" title="LinkedIn">💼</a>
                <a href="https://x.com/iocryposto1273" class="social-btn" title="Twitter">𝕏</a>
                <a href="https://www.youtube.com/@Aaditya1515" class="social-btn" title="YouTube">📺</a>
                <a href="https://t.me/aaditya092" class="social-btn" title="Telegram">✈️</a>
                <a href="https://discord.com/users/aadi02364" class="social-btn" title="Discord">🎮</a>
                <a href="mailto:aadityaofficial1515@gmail.com" class="social-btn" title="Email">📧</a>
            </div>
        </div>

        <!-- About Section -->
        <div class="section">
            <h2>💫 About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>I'm a passionate developer dedicated to creating engaging and dynamic applications. With expertise across blockchain, cybersecurity, and full-stack development, I'm constantly exploring emerging technologies and pushing the boundaries of what's possible.</p>
                    <h3>🎯 What I Excel At:</h3>
                    <ul class="about-list">
                        <li>Building secure, scalable blockchain applications</li>
                        <li>Identifying and mitigating cybersecurity vulnerabilities</li>
                        <li>Developing dynamic full-stack solutions</li>
                        <li>Mastering cutting-edge frameworks and tools</li>
                        <li>Contributing to open-source communities</li>
                        <li>Mentoring and sharing knowledge</li>
                    </ul>
                </div>
                <div class="about-image">
                    <img src="https://github.com/user-attachments/assets/9e7a96dc-a15e-402b-8bed-5984a84f61c5" alt="Aaditya">
                </div>
            </div>
        </div>

        <!-- Tech Stack -->
        <div class="section">
            <h2>💻 Tech Arsenal</h2>
            <div class="tech-grid">
                <div class="tech-item"><span>JavaScript</span></div>
                <div class="tech-item"><span>TypeScript</span></div>
                <div class="tech-item"><span>Python</span></div>
                <div class="tech-item"><span>React</span></div>
                <div class="tech-item"><span>Django</span></div>
                <div class="tech-item"><span>Node.js</span></div>
                <div class="tech-item"><span>MongoDB</span></div>
                <div class="tech-item"><span>PostgreSQL</span></div>
                <div class="tech-item"><span>AWS</span></div>
                <div class="tech-item"><span>Docker</span></div>
                <div class="tech-item"><span>Solidity</span></div>
                <div class="tech-item"><span>Web3</span></div>
                <div class="tech-item"><span>C++</span></div>
                <div class="tech-item"><span>Redux</span></div>
                <div class="tech-item"><span>Git</span></div>
                <div class="tech-item"><span>Figma</span></div>
            </div>
        </div>

        <!-- Stats -->
        <div class="section">
            <h2>📊 GitHub Analytics</h2>
            <div class="stats-container">
                <div class="stat-card">
                    <div class="stat-number">50+</div>
                    <div class="stat-label">Public Repositories</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">1000+</div>
                    <div class="stat-label">GitHub Contributions</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">10+</div>
                    <div class="stat-label">Years Experience</div>
                </div>
            </div>
            <div style="text-align: center; margin-top: 40px;">
                <img src="https://github-readme-stats.vercel.app/api?username=Aaditya1273&show_icons=true&theme=radical&hide_border=true&bg_color=0d1117&title_color=00ff88&icon_color=00ff88&text_color=c0c0c0" alt="GitHub Stats" style="border-radius: 10px; max-width: 100%; margin-bottom: 20px;">
                <img src="https://github-readme-stats.vercel.app/api/top-langs?username=Aaditya1273&layout=compact&theme=radical&hide_border=true&bg_color=0d1117&title_color=00ff88&text_color=c0c0c0" alt="Top Languages" style="border-radius: 10px; max-width: 100%;">
            </div>
        </div>

        <!-- Call to Action -->
        <div class="section" style="text-align: center;">
            <h2>🌟 Let's Build Something Amazing!</h2>
            <p style="color: #c0c0c0; font-size: 1.1em; margin: 20px 0;">I'm always open to exciting collaborations and innovative projects. Let's connect and create something extraordinary together!</p>
            <button class="cta-button">Get In Touch 🚀</button>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>💡 "Code is poetry written in logic"</p>
            <p style="margin-top: 20px; font-size: 0.9em; color: #808080;">© 2024 Aaditya Rawat. All rights reserved. | Crafted with ❤️ and ☕</p>
        </div>
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            for (let i = 0; i < 30; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDuration = (Math.random() * 20 + 10) + 's';
                particle.style.animationDelay = Math.random() * 5 + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Initialize
        createParticles();

        // Add click animation to buttons
        document.querySelectorAll('.cta-button, .social-btn').forEach(btn => {
            btn.addEventListener('click', function(e) {
                const ripple = document.createElement('span');
                ripple.style.position = 'absolute';
                ripple.style.borderRadius = '50%';
                ripple.style.background = 'rgba(255, 255, 255, 0.5)';
                ripple.style.pointerEvents = 'none';
                this.appendChild(ripple);
            });
        });

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) target.scrollIntoView({ behavior: 'smooth' });
            });
        });
    </script>
</body>
</html>
