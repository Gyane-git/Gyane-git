<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile Preview</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 40px 20px;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 50px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            animation: fadeInUp 0.8s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .header h1 {
            font-size: 3.5em;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            animation: slideIn 1s ease-out;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .wave {
            display: inline-block;
            animation: wave 2s ease-in-out infinite;
            transform-origin: 70% 70%;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            10%, 30% { transform: rotate(14deg); }
            20% { transform: rotate(-8deg); }
            40% { transform: rotate(-4deg); }
            50% { transform: rotate(10deg); }
        }

        .subtitle {
            font-size: 1.3em;
            color: #555;
            margin-bottom: 20px;
            animation: fadeIn 1.5s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .typing-animation {
            height: 40px;
            margin: 20px 0;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .typing-text {
            font-size: 1.2em;
            color: #667eea;
            font-weight: 600;
            border-right: 3px solid #667eea;
            padding-right: 5px;
            animation: blink 0.7s step-end infinite;
        }

        @keyframes blink {
            50% { border-color: transparent; }
        }

        .badge {
            display: inline-block;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 8px 20px;
            border-radius: 25px;
            font-size: 0.9em;
            margin: 5px;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .section {
            margin: 40px 0;
            opacity: 0;
            animation: fadeInSection 0.8s ease-out forwards;
        }

        .section:nth-child(1) { animation-delay: 0.2s; }
        .section:nth-child(2) { animation-delay: 0.4s; }
        .section:nth-child(3) { animation-delay: 0.6s; }
        .section:nth-child(4) { animation-delay: 0.8s; }

        @keyframes fadeInSection {
            to {
                opacity: 1;
            }
        }

        .section h2 {
            font-size: 2em;
            color: #333;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .section h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 3px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            animation: expandWidth 1s ease-out;
        }

        @keyframes expandWidth {
            from { width: 0; }
            to { width: 60px; }
        }

        .about-list {
            list-style: none;
            padding: 0;
        }

        .about-list li {
            padding: 12px 0;
            color: #555;
            font-size: 1.1em;
            border-left: 3px solid transparent;
            padding-left: 20px;
            margin: 8px 0;
            transition: all 0.3s ease;
        }

        .about-list li:hover {
            border-left-color: #667eea;
            padding-left: 30px;
            background: rgba(102, 126, 234, 0.05);
        }

        .skill-bar {
            margin: 20px 0;
        }

        .skill-name {
            font-weight: 600;
            color: #333;
            margin-bottom: 8px;
            font-size: 1.1em;
        }

        .progress-bar {
            width: 100%;
            height: 30px;
            background: #e0e0e0;
            border-radius: 15px;
            overflow: hidden;
            position: relative;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: flex-end;
            padding-right: 15px;
            color: white;
            font-weight: 600;
            animation: fillBar 2s ease-out;
            position: relative;
            overflow: hidden;
        }

        .progress-fill::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            100% { left: 100%; }
        }

        @keyframes fillBar {
            from { width: 0; }
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .tech-item {
            text-align: center;
            padding: 20px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-item:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }

        .tech-icon {
            font-size: 3em;
            margin-bottom: 10px;
        }

        .project-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            margin: 20px 0;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            transform: scale(0);
            transition: transform 0.6s ease;
        }

        .project-card:hover::before {
            transform: scale(1);
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        .project-card h3 {
            font-size: 1.8em;
            margin-bottom: 10px;
        }

        .connect-buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
            margin-top: 30px;
        }

        .connect-btn {
            padding: 15px 30px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .connect-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .connect-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .connect-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-card {
            background: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.2);
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: 700;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            color: #666;
            margin-top: 10px;
            font-size: 1.1em;
        }

        @media (max-width: 768px) {
            .container {
                padding: 30px 20px;
            }

            .header h1 {
                font-size: 2.5em;
            }

            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(60px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Hi <span class="wave">👋</span>, I'm Gyane</h1>
            <p class="subtitle">A passionate developer from Nepal, building the future one line of code at a time</p>
            <div class="typing-animation">
                <span class="typing-text" id="typingText"></span>
            </div>
            <div>
                <span class="badge">🚀 Flutter Developer</span>
                <span class="badge">⚡ Next.js Enthusiast</span>
                <span class="badge">🤖 AI Hacker</span>
            </div>
        </div>

        <div class="section">
            <h2>🚀 About Me</h2>
            <ul class="about-list">
                <li>🔭 Currently working on <strong>Garg Dental eCom</strong></li>
                <li>🌱 Learning <strong>Flutter & Next.js</strong></li>
                <li>👯 Looking to collaborate on <strong>HRMS projects</strong></li>
                <li>🤝 Seeking help with <strong>Image Classification</strong></li>
                <li>💬 Ask me about <strong>Next.js, Python, Vercel</strong></li>
                <li>📫 Reach me at <strong>gyanee750@gmail.com</strong></li>
                <li>🌐 Portfolio: <strong>gyanendrasah.com.np</strong></li>
            </ul>
        </div>

        <div class="section">
            <h2>💻 Technical Skills</h2>
            <div class="skill-bar">
                <div class="skill-name">Flutter</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 90%;">90%</div>
                </div>
            </div>
            <div class="skill-bar">
                <div class="skill-name">Python</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 85%;">85%</div>
                </div>
            </div>
            <div class="skill-bar">
                <div class="skill-name">JavaScript</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 85%;">85%</div>
                </div>
            </div>
            <div class="skill-bar">
                <div class="skill-name">Next.js</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 80%;">80%</div>
                </div>
            </div>
            <div class="skill-bar">
                <div class="skill-name">Dart</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 80%;">80%</div>
                </div>
            </div>
            <div class="skill-bar">
                <div class="skill-name">PHP</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 75%;">75%</div>
                </div>
            </div>
        </div>

        <div class="section">
            <h2>🛠️ Tech Stack</h2>
            <div class="tech-grid">
                <div class="tech-item">
                    <div class="tech-icon">📱</div>
                    <div>Flutter</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">⚛️</div>
                    <div>React</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🔷</div>
                    <div>Next.js</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🐍</div>
                    <div>Python</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🟢</div>
                    <div>Node.js</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">☁️</div>
                    <div>AWS</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🔵</div>
                    <div>Azure</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🗄️</div>
                    <div>MySQL</div>
                </div>
            </div>
        </div>

        <div class="section">
            <h2>💼 Featured Projects</h2>
            <div class="project-card">
                <h3>🦷 Garg Dental eCom</h3>
                <p>A comprehensive e-commerce platform for dental products with modern UI/UX and seamless shopping experience.</p>
            </div>
            <div class="project-card">
                <h3>🌐 Portfolio Website</h3>
                <p>Personal portfolio showcasing projects, skills, and professional journey with interactive design.</p>
            </div>
        </div>

        <div class="section">
            <h2>📊 GitHub Statistics</h2>
            <div class="stats-container">
                <div class="stat-card">
                    <div class="stat-number">500+</div>
                    <div class="stat-label">Contributions</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">50+</div>
                    <div class="stat-label">Repositories</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">15+</div>
                    <div class="stat-label">Projects</div>
                </div>
            </div>
        </div>

        <div class="section">
            <h2>🤝 Connect With Me</h2>
            <div class="connect-buttons">
                <a href="https://linkedin.com/in/gyane-git" class="connect-btn">LinkedIn</a>
                <a href="https://twitter.com/gyane-git" class="connect-btn">Twitter</a>
                <a href="https://github.com/gyane-git" class="connect-btn">GitHub</a>
                <a href="mailto:gyanee750@gmail.com" class="connect-btn">Email</a>
                <a href="https://www.buymeacoffee.com/gyane-git" class="connect-btn">Buy Me a Coffee</a>
            </div>
        </div>
    </div>

    <script>
        // Typing animation
        const phrases = [
            'Flutter Developer',
            'Next.js Enthusiast',
            'AI Hacker',
            'Full Stack Developer',
            'Problem Solver'
        ];
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingText = document.getElementById('typingText');

        function type() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                typingText.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingText.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentPhrase.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
            }

            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }

        type();

        // Intersection Observer for scroll animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.section').forEach(section => {
            section.style.opacity = '0';
            section.style.transform = 'translateY(20px)';
            section.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(section);
        });
    </script>
</body>
</html>
