<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gyane - Developer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
            overflow: hidden;
        }

        .bg-animation span {
            position: absolute;
            display: block;
            width: 20px;
            height: 20px;
            background: rgba(255, 255, 255, 0.1);
            animation: float 25s infinite;
            border-radius: 50%;
        }

        .bg-animation span:nth-child(1) { left: 10%; animation-delay: 0s; }
        .bg-animation span:nth-child(2) { left: 20%; animation-delay: 2s; animation-duration: 12s; }
        .bg-animation span:nth-child(3) { left: 30%; animation-delay: 4s; }
        .bg-animation span:nth-child(4) { left: 40%; animation-delay: 0s; animation-duration: 18s; }
        .bg-animation span:nth-child(5) { left: 50%; animation-delay: 1s; }
        .bg-animation span:nth-child(6) { left: 60%; animation-delay: 3s; }
        .bg-animation span:nth-child(7) { left: 70%; animation-delay: 7s; }
        .bg-animation span:nth-child(8) { left: 80%; animation-delay: 5s; animation-duration: 20s; }
        .bg-animation span:nth-child(9) { left: 90%; animation-delay: 2s; animation-duration: 15s; }
        .bg-animation span:nth-child(10) { left: 25%; animation-delay: 8s; }

        @keyframes float {
            0% {
                bottom: -100px;
                transform: translateX(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                bottom: 1080px;
                transform: translateX(100px) rotate(360deg);
                opacity: 0;
            }
        }

        /* Header Section */
        header {
            text-align: center;
            padding: 80px 20px 40px;
            animation: fadeInDown 1s ease;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            font-size: 4em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #fff, #a8edea);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 0 0 20px rgba(255, 255, 255, 0.5); }
            to { text-shadow: 0 0 30px rgba(255, 255, 255, 0.8), 0 0 40px rgba(168, 237, 234, 0.6); }
        }

        .typing-text {
            font-size: 1.5em;
            color: #a8edea;
            margin: 20px 0;
            min-height: 40px;
        }

        .typing-cursor {
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .profile-views {
            margin-top: 20px;
            font-size: 0.9em;
            opacity: 0.8;
        }

        /* Card Styles */
        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: fadeInUp 1s ease;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 48px rgba(0, 0, 0, 0.3);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h2 {
            font-size: 2em;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .about-list {
            list-style: none;
            line-height: 2;
        }

        .about-list li {
            padding: 10px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            animation: slideIn 0.5s ease forwards;
            opacity: 0;
        }

        .about-list li:nth-child(1) { animation-delay: 0.1s; }
        .about-list li:nth-child(2) { animation-delay: 0.2s; }
        .about-list li:nth-child(3) { animation-delay: 0.3s; }
        .about-list li:nth-child(4) { animation-delay: 0.4s; }
        .about-list li:nth-child(5) { animation-delay: 0.5s; }
        .about-list li:nth-child(6) { animation-delay: 0.6s; }
        .about-list li:nth-child(7) { animation-delay: 0.7s; }

        @keyframes slideIn {
            to {
                opacity: 1;
                transform: translateX(0);
            }
            from {
                transform: translateX(-20px);
            }
        }

        /* Skills Section */
        .skill-item {
            margin: 20px 0;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-weight: bold;
        }

        .progress-bar {
            background: rgba(255, 255, 255, 0.2);
            height: 25px;
            border-radius: 15px;
            overflow: hidden;
            position: relative;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #667eea, #a8edea);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: flex-end;
            padding-right: 10px;
            font-size: 0.85em;
            transition: width 2s ease;
            width: 0;
        }

        .progress-fill.animate {
            animation: fillBar 2s ease forwards;
        }

        /* Tech Icons */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .tech-item {
            text-align: center;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-item:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: scale(1.1) rotate(5deg);
        }

        .tech-item img {
            width: 50px;
            height: 50px;
            filter: brightness(0) invert(1);
            margin-bottom: 8px;
        }

        /* Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.15);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.05);
            background: rgba(255, 255, 255, 0.2);
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            color: #a8edea;
        }

        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.15);
            padding: 30px;
            border-radius: 15px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .project-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.2);
        }

        .project-badge {
            display: inline-block;
            padding: 10px 20px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 25px;
            margin: 10px 5px;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .project-badge:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        /* Connect Section */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .social-btn {
            padding: 15px 30px;
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 30px;
            text-decoration: none;
            color: #fff;
            font-weight: bold;
            transition: all 0.3s ease;
            display: inline-block;
        }

        .social-btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        footer {
            text-align: center;
            padding: 40px 20px;
            margin-top: 60px;
            opacity: 0.7;
        }

        /* Scroll Animation */
        .fade-in-section {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-in-section.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <div class="bg-animation">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>

    <div class="container">
        <header>
            <h1>Hi 👋, I'm Gyane</h1>
            <p style="font-size: 1.2em; opacity: 0.9;">A passionate developer from Nepal, building the future one line of code at a time</p>
            <div class="typing-text" id="typingText"></div>
            <div class="profile-views">👁️ Profile Views: <span id="viewCount">0</span></div>
        </header>

        <div class="card fade-in-section">
            <h2>🚀 About Me</h2>
            <ul class="about-list">
                <li>🔭 I'm currently working on <strong>Garg Dental eCom</strong></li>
                <li>🌱 I'm currently learning <strong>Flutter</strong> & <strong>Next.js</strong></li>
                <li>👯 I'm looking to collaborate on <strong>HRMS projects</strong></li>
                <li>🤝 I'm looking for help with <strong>Image Classification</strong></li>
                <li>💬 Ask me about <strong>Next.js, Python, Vercel</strong></li>
                <li>📫 How to reach me: <strong>gyanee750@gmail.com</strong></li>
                <li>🌐 Portfolio: <a href="https://gyanendrasah.com.np" style="color: #a8edea;">gyanendrasah.com.np</a></li>
            </ul>
        </div>

        <div class="card fade-in-section">
            <h2>💻 My Skills</h2>
            <div class="skill-item">
                <div class="skill-name">
                    <span>Flutter</span>
                    <span>90%</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" data-progress="90"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-name">
                    <span>Python</span>
                    <span>85%</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" data-progress="85"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-name">
                    <span>JavaScript</span>
                    <span>85%</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" data-progress="85"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-name">
                    <span>Next.js</span>
                    <span>80%</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" data-progress="80"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-name">
                    <span>Dart</span>
                    <span>80%</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" data-progress="80"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-name">
                    <span>PHP</span>
                    <span>75%</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" data-progress="75"></div>
                </div>
            </div>
        </div>

        <div class="card fade-in-section">
            <h2>🛠️ Tools & Technologies</h2>
            <div class="tech-grid">
                <div class="tech-item">
                    <div style="font-size: 2em;">☁️</div>
                    <div>AWS</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">🔷</div>
                    <div>Azure</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">🎨</div>
                    <div>Bootstrap</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">📱</div>
                    <div>Flutter</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">⚛️</div>
                    <div>React</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">📘</div>
                    <div>TypeScript</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">🟢</div>
                    <div>Node.js</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">🐍</div>
                    <div>Django</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">🔴</div>
                    <div>Laravel</div>
                </div>
                <div class="tech-item">
                    <div style="font-size: 2em;">🗄️</div>
                    <div>MySQL</div>
                </div>
            </div>
        </div>

        <div class="card fade-in-section">
            <h2>📊 GitHub Stats</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number" id="commits">0</div>
                    <div>Total Commits</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="repos">0</div>
                    <div>Public Repos</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="streak">0</div>
                    <div>Day Streak</div>
                </div>
            </div>
        </div>

        <div class="card fade-in-section">
            <h2>💼 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>🦷 Garg Dental eCom</h3>
                    <p>E-commerce platform for dental products with modern UI and seamless shopping experience.</p>
                    <div>
                        <span class="project-badge">Next.js</span>
                        <span class="project-badge">E-Commerce</span>
                    </div>
                </div>
                <div class="project-card">
                    <h3>🌐 Portfolio Website</h3>
                    <p>Personal portfolio showcasing projects, skills, and professional journey.</p>
                    <div>
                        <span class="project-badge">React</span>
                        <span class="project-badge">Portfolio</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="card fade-in-section">
            <h2>🤝 Connect with Me</h2>
            <div class="social-links">
                <a href="https://linkedin.com/in/gyane-git" class="social-btn">💼 LinkedIn</a>
                <a href="https://twitter.com/gyane-git" class="social-btn">🐦 Twitter</a>
                <a href="mailto:gyanee750@gmail.com" class="social-btn">📧 Email</a>
                <a href="https://www.buymeacoffee.com/gyane-git" class="social-btn">☕ Buy Me Coffee</a>
            </div>
        </div>

        <footer>
            <p>© 2024 Gyane. Made with ❤️ in Nepal</p>
        </footer>
    </div>

    <script>
        // Typing animation
        const texts = ['Flutter Developer', 'Next.js Enthusiast', 'AI Hacker', 'Full Stack Developer'];
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typingText');

        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1) + '|';
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1) + '|';
                charIndex++;
            }

            if (!isDeleting && charIndex === currentText.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
            }

            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }

        type();

        // Animate profile views counter
        let views = 0;
        const targetViews = 1247;
        const viewCounter = setInterval(() => {
            views += 23;
            if (views >= targetViews) {
                views = targetViews;
                clearInterval(viewCounter);
            }
            document.getElementById('viewCount').textContent = views;
        }, 30);

        // Animate stats
        function animateCounter(id, target) {
            let count = 0;
            const increment = target / 50;
            const counter = setInterval(() => {
                count += increment;
                if (count >= target) {
                    count = target;
                    clearInterval(counter);
                }
                document.getElementById(id).textContent = Math.floor(count) + '+';
            }, 40);
        }

        // Scroll animations
        const fadeElements = document.querySelectorAll('.fade-in-section');
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    
                    // Animate progress bars when visible
                    if (entry.target.querySelector('.progress-fill')) {
                        entry.target.querySelectorAll('.progress-fill').forEach(bar => {
                            const progress = bar.getAttribute('data-progress');
                            bar.style.width = progress + '%';
                        });
                    }
                    
                    // Animate stats when visible
                    if (entry.target.querySelector('#commits')) {
                        animateCounter('commits', 850);
                        animateCounter('repos', 42);
                        animateCounter('streak', 127);
                    }
                }
            });
        }, { threshold: 0.1 });

        fadeElements.forEach(el => observer.observe(el));
    </script>
</body>
</html>
