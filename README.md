<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sagar Ghimire | Full-Stack Developer & Cybersecurity Enthusiast</title>
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
    
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        :root {
            --bg-dark: #0d1117;
            --bg-card: #161b22;
            --text-main: #c9d1d9;
            --text-muted: #8b949e;
            --accent-primary: #3b82f6; /* Blue */
            --accent-secondary: #8b5cf6; /* Purple */
            --accent-success: #238636;
            --border-color: #30363d;
            --glow: 0 0 20px rgba(59, 130, 246, 0.15);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: 0.3s ease;
        }

        ul {
            list-style: none;
        }

        /* Container */
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* Header */
        header {
            text-align: center;
            margin-bottom: 60px;
            animation: fadeIn Down 0.8s ease-out;
        }

        .profile-img-container {
            width: 180px;
            height: 180px;
            margin: 0 auto 20px;
            position: relative;
        }

        .profile-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid var(--accent-primary);
            box-shadow: 0 0 30px rgba(59, 130, 246, 0.3);
            transition: transform 0.3s ease;
        }

        .profile-img:hover {
            transform: scale(1.05);
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #fff, var(--accent-primary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .subtitle {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 20px;
            font-weight: 300;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 20px;
        }

        .social-btn {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 10px 20px;
            border-radius: 8px;
            font-weight: 600;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .social-btn.github {
            background-color: #181717;
            border: 1px solid #30363d;
            color: #fff;
        }
        .social-btn.github:hover { background-color: #30363d; }

        .social-btn.linkedin {
            background-color: #0A66C2;
            color: white;
        }
        .social-btn.linkedin:hover { background-color: #004182; }

        .social-btn.portfolio {
            background-color: var(--accent-primary);
            color: white;
        }
        .social-btn.portfolio:hover { background-color: #2563eb; box-shadow: var(--glow); }

        .location-info {
            font-size: 0.95rem;
            color: var(--text-muted);
        }

        /* Sections */
        section {
            margin-bottom: 60px;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeUp 0.6s forwards;
        }

        section:nth-child(2) { animation-delay: 0.1s; }
        section:nth-child(3) { animation-delay: 0.2s; }
        section:nth-child(4) { animation-delay: 0.3s; }
        section:nth-child(5) { animation-delay: 0.4s; }
        section:nth-child(6) { animation-delay: 0.5s; }

        .section-title {
            font-size: 1.8rem;
            margin-bottom: 25px;
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 10px;
            display: inline-block;
        }

        /* Code Block */
        .code-block {
            background-color: #000;
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 20px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.9rem;
            color: #e6edf3;
            overflow-x: auto;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .code-key { color: #79c0ff; }
        .code-str { color: #a5d6ff; }
        .code-prop { color: #d2a8ff; }
        .code-comment { color: #8b949e; font-style: italic; }

        /* Tech Stack Grid */
        .tech-category {
            margin-bottom: 30px;
        }

        .tech-category h3 {
            font-size: 1.2rem;
            color: var(--text-main);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tech-category h3 i {
            color: var(--accent-secondary);
        }

        .badges-container {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .tech-badge {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 8px 16px;
            border-radius: 6px;
            font-size: 0.85rem;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: transform 0.2s, border-color 0.2s;
        }

        .tech-badge:hover {
            transform: translateY(-2px);
            border-color: var(--accent-primary);
        }

        .tech-badge i { font-size: 1.1rem; }

        /* Services Table */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .service-card {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 25px;
            border-radius: 12px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 4px; height: 100%;
            background: var(--accent-primary);
            opacity: 0;
            transition: opacity 0.3s;
        }

        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            border-color: var(--border-color);
        }

        .service-card:hover::before { opacity: 1; }

        .service-card h3 {
            margin-bottom: 10px;
            color: var(--accent-primary);
        }

        /* Stats */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }

        .stat-card {
            background-color: var(--bg-card);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            display: flex;
            flex-direction: column;
        }

        .stat-img {
            width: 100%;
            height: auto;
            display: block;
        }

        .streak-card {
            background-color: var(--bg-card);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
        }

        /* Terminal Window for Competencies */
        .terminal {
            background-color: #0d1117;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            overflow: hidden;
            font-family: 'JetBrains Mono', monospace;
        }

        .terminal-header {
            background-color: #161b22;
            padding: 10px 15px;
            display: flex;
            gap: 8px;
            border-bottom: 1px solid var(--border-color);
        }

        .dot { width: 12px; height: 12px; border-radius: 50%; }
        .red { background-color: #ff5f56; }
        .yellow { background-color: #ffbd2e; }
        .green { background-color: #27c93f; }

        .terminal-body {
            padding: 20px;
            color: #3fb950;
        }

        .terminal-body li {
            margin-bottom: 8px;
        }

        .terminal-body li::before {
            content: "✓";
            margin-right: 10px;
            color: var(--accent-primary);
        }

        /* Footer */
        footer {
            text-align: center;
            margin-top: 80px;
            padding-top: 40px;
            border-top: 1px solid var(--border-color);
        }

        .quote {
            font-style: italic;
            color: var(--text-muted);
            margin-bottom: 20px;
            font-size: 1.1rem;
        }

        .quote span {
            color: var(--accent-secondary);
            font-weight: 600;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }

        .profile-views {
            display: inline-block;
            background: rgba(59, 130, 246, 0.1);
            color: var(--accent-primary);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            border: 1px solid rgba(59, 130, 246, 0.2);
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            h1 { font-size: 2rem; }
            .social-links { flex-direction: column; align-items: center; }
            .social-btn { width: 100%; justify-content: center; }
            .stats-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>

    <div class="container">
        
        <!-- Header Section -->
        <header>
            <div class="profile-img-container">
                <!-- Using a seed based on username for a consistent placeholder, but ready for real image -->
                <img src="./552707294_819338267298222_8646963405884587945_n.jpg" 
                     onerror="this.src='https://picsum.photos/seed/E-4-0-4/200/200'" 
                     alt="Sagar Ghimire" 
                     class="profile-img">
            </div>
            
            <h1>👋 Hi, I'm Sagar Ghimire</h1>
            <p class="subtitle">Full-Stack Developer | Cybersecurity Enthusiast</p>
            
            <div class="social-links">
                <a href="https://github.com/E-4-0-4" target="_blank" class="social-btn github">
                    <i class="fab fa-github"></i> GitHub
                </a>
                <a href="https://www.linkedin.com/in/sagar-ghimire-191a28345/" target="_blank" class="social-btn linkedin">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://sghimrie.com.np" target="_blank" class="social-btn portfolio">
                    <i class="fas fa-globe"></i> Portfolio
                </a>
            </div>

            <p class="location-info">
                📍 Kathmandu, Nepal | 🎓 IT Student (Expected 2026)
            </p>
        </header>

        <!-- About Me -->
        <section>
            <h2 class="section-title">🚀 About Me</h2>
            <p style="margin-bottom: 20px; color: var(--text-main);">
                I'm a passionate <strong>Full-Stack Developer</strong> and <strong>Cybersecurity Enthusiast</strong> dedicated to building secure, scalable web applications while exploring the depths of ethical hacking. I combine my development skills with security expertise to create robust, production-ready solutions.
            </p>

            <div class="code-block">
                <pre><code><span class="code-key">const</span> sagar = {
    <span class="code-prop">location</span>: <span class="code-str">"Kathmandu, Nepal"</span>,
    <span class="code-prop">education</span>: <span class="code-str">"Bachelor's in Information Technology (Expected 2026)"</span>,
    <span class="code-prop">focus</span>: [<span class="code-str">"Full-Stack Development"</span>, <span class="code-str">"Cybersecurity"</span>, <span class="code-str">"Ethical Hacking"</span>],
    <span class="code-prop">currentlyLearning</span>: [<span class="code-str">"Advanced Penetration Testing"</span>, <span class="code-str">"Cloud Security"</span>, <span class="code-str">"DevSecOps"</span>],
    <span class="code-prop">askMeAbout</span>: [<span class="code-str">"MERN Stack"</span>, <span class="code-str">"Web Security"</span>, <span class="code-str">"API Development"</span>, <span class="code-str">"Network Security"</span>],
    <span class="code-prop">funFact</span>: <span class="code-str">"I secure what I build and build what I secure 🔐"</span>
};</code></pre>
            </div>
        </section>

        <!-- Technical Arsenal -->
        <section>
            <h2 class="section-title">💻 Technical Arsenal</h2>
            
            <div class="tech-category">
                <h3><i class="fas fa-code"></i> Core Programming</h3>
                <div class="badges-container">
                    <div class="tech-badge" style="color: #00599C"><i class="fa-solid fa-c"></i> C</div>
                    <div class="tech-badge" style="color: #00599C"><i class="fa-solid fa-c"></i> C++</div>
                    <div class="tech-badge" style="color: #f89820"><i class="fa-brands fa-java"></i> Java</div>
                    <div class="tech-badge" style="color: #f7df1e"><i class="fa-brands fa-js"></i> JavaScript</div>
                </div>
            </div>

            <div class="tech-category">
                <h3><i class="fas fa-globe"></i> Web Development</h3>
                <div class="badges-container">
                    <div class="tech-badge" style="color: #47A248"><i class="fa-solid fa-leaf"></i> MongoDB</div>
                    <div class="tech-badge" style="color: #fff"><i class="fa-solid fa-server"></i> Express.js</div>
                    <div class="tech-badge" style="color: #61DAFB"><i class="fa-brands fa-react"></i> React</div>
                    <div class="tech-badge" style="color: #339933"><i class="fa-brands fa-node"></i> Node.js</div>
                    <div class="tech-badge" style="color: #777BB4"><i class="fa-brands fa-php"></i> PHP</div>
                    <div class="tech-badge" style="color: #FF6C37"><i class="fa-solid fa-bolt"></i> REST API</div>
                </div>
            </div>

            <div class="tech-category">
                <h3><i class="fas fa-user-secret"></i> Cybersecurity & Ethical Hacking</h3>
                <div class="badges-container">
                    <div class="tech-badge" style="color: #557C94"><i class="fa-brands fa-linux"></i> Kali Linux</div>
                    <div class="tech-badge" style="color: #2596CD"><i class="fa-solid fa-bug"></i> Metasploit</div>
                    <div class="tech-badge" style="color: #FF6633"><i class="fa-solid fa-shield-halved"></i> Burp Suite</div>
                    <div class="tech-badge" style="color: #1679A7"><i class="fa-solid fa-network-wired"></i> Wireshark</div>
                    <div class="tech-badge" style="color: #0E83CD"><i class="fa-solid fa-radar"></i> Nmap</div>
                </div>
                <div style="margin-top: 15px; font-size: 0.9rem; color: var(--text-muted);">
                    <strong>Security Expertise:</strong> 🔍 Penetration Testing | 🛡️ Network Security | 🔐 Web App Security (OWASP) | 🦠 Malware Analysis | 🔓 Vulnerability Assessment
                </div>
            </div>

            <div class="tech-category">
                <h3><i class="fas fa-database"></i> Databases & DevOps</h3>
                <div class="badges-container">
                    <div class="tech-badge" style="color: #4479A1"><i class="fa-solid fa-database"></i> MySQL</div>
                    <div class="tech-badge" style="color: #2496ED"><i class="fa-brands fa-docker"></i> Docker</div>
                    <div class="tech-badge" style="color: #F05032"><i class="fa-brands fa-git-alt"></i> Git</div>
                    <div class="tech-badge" style="color: #fff"><i class="fa-brands fa-github"></i> GitHub</div>
                    <div class="tech-badge" style="color: #fff"><i class="fa-solid fa-triangle-exclamation"></i> Vercel</div>
                </div>
            </div>
        </section>

        <!-- What I Do -->
        <section>
            <h2 class="section-title">🎯 What I Do</h2>
            <div class="services-grid">
                <div class="service-card">
                    <h3>🌐 Full-Stack Development</h3>
                    <p>Building scalable, responsive web applications using the MERN stack with focus on clean architecture and best practices.</p>
                </div>
                <div class="service-card">
                    <h3>🔒 Security Implementation</h3>
                    <p>Implementing robust security measures including DDoS protection, SQL injection prevention, CSRF & XSS protection, and secure authentication.</p>
                </div>
                <div class="service-card">
                    <h3>🎯 Ethical Hacking</h3>
                    <p>Conducting penetration testing, vulnerability assessments, and security audits to identify and fix security flaws.</p>
                </div>
            </div>
        </section>

        <!-- GitHub Stats -->
        <section>
            <h2 class="section-title">📊 GitHub Stats</h2>
            <div class="stats-grid">
                <!-- GitHub Stats Card -->
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=E-4-0-4&show_icons=true&theme=tokyonight&hide_border=true&bg_color=161b22&title_color=3b82f6&icon_color=8b5cf6&text_color=c9d1d9" alt="GitHub Stats" class="stat-img">
                </div>
                <!-- Top Languages Card -->
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=E-4-0-4&layout=compact&theme=tokyonight&hide_border=true&bg_color=161b22&title_color=3b82f6&text_color=c9d1d9" alt="Top Languages" class="stat-img">
                </div>
            </div>
            <!-- Streak Card -->
            <div class="streak-card">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=E-4-0-4&theme=tokyonight&hide_border=true&background=161b22&ring=3b82f6&fire=8b5cf6&currStreakLabel=c9d1d9" alt="GitHub Streak" style="width: 100%; display: block;">
            </div>
        </section>

        <!-- Certifications -->
        <section>
            <h2 class="section-title">🏆 Certifications</h2>
            <ul style="display: flex; flex-wrap: wrap; gap: 15px;">
                <li style="background: rgba(35, 134, 54, 0.1); color: #3fb950; padding: 10px 15px; border-radius: 6px; border: 1px solid rgba(35, 134, 54, 0.2);">
                    <i class="fas fa-check-circle"></i> MERN Stack Development
                </li>
                <li style="background: rgba(35, 134, 54, 0.1); color: #3fb950; padding: 10px 15px; border-radius: 6px; border: 1px solid rgba(35, 134, 54, 0.2);">
                    <i class="fas fa-check-circle"></i> Cybersecurity & Ethical Hacking
                </li>
                <li style="background: rgba(35, 134, 54, 0.1); color: #3fb950; padding: 10px 15px; border-radius: 6px; border: 1px solid rgba(35, 134, 54, 0.2);">
                    <i class="fas fa-check-circle"></i> PHP Web Development
                </li>
            </ul>
        </section>

        <!-- Core Competencies -->
        <section>
            <h2 class="section-title">💡 Core Competencies</h2>
            <div class="terminal">
                <div class="terminal-header">
                    <div class="dot red"></div>
                    <div class="dot yellow"></div>
                    <div class="dot green"></div>
                </div>
                <div class="terminal-body">
                    <ul>
                        <li>Secure Web Application Development</li>
                        <li>RESTful API Design & Implementation</li>
                        <li>Database Design & Optimization (SQL & NoSQL)</li>
                        <li>Authentication & Authorization (JWT, OAuth)</li>
                        <li>Security Best Practices (OWASP Top 10)</li>
                        <li>Penetration Testing & Vulnerability Assessment</li>
                        <li>Network Security & Traffic Analysis</li>
                        <li>Malware Analysis & Reverse Engineering</li>
                        <li>Docker Containerization & Deployment</li>
                        <li>Version Control & Collaborative Development</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Currently Exploring -->
        <section>
            <h2 class="section-title">🌱 Currently Exploring</h2>
            <div style="background: var(--bg-card); padding: 20px; border-radius: 8px; border-left: 4px solid var(--accent-secondary);">
                <ul style="list-style-type: disc; padding-left: 20px; color: var(--text-muted);">
                    <li style="margin-bottom: 10px;">🔐 Advanced penetration testing techniques</li>
                    <li style="margin-bottom: 10px;">☁️ Cloud security and DevSecOps practices</li>
                    <li style="margin-bottom: 10px;">🤖 AI/ML integration in cybersecurity</li>
                    <li style="margin-bottom: 10px;">🚀 Microservices architecture and scalability</li>
                    <li>🔍 Advanced malware analysis and forensics</li>
                </ul>
            </div>
        </section>

        <!-- Footer / Connect -->
        <footer>
            <h2 class="section-title" style="border: none;">📫 Let's Connect!</h2>
            <p style="margin-bottom: 30px; color: var(--text-muted);">
                I'm always interested in collaborating on innovative projects, discussing cybersecurity, or exploring new technologies. Feel free to reach out!
            </p>
            
            <div class="footer-links">
                <a href="https://github.com/E-4-0-4" target="_blank" style="color: var(--text-main); font-size: 2rem;"><i class="fab fa-github"></i></a>
                <a href="https://www.linkedin.com/in/sagar-ghimire-191a28345/" target="_blank" style="color: var(--text-main); font-size: 2rem;"><i class="fab fa-linkedin"></i></a>
                <a href="https://sghimrie.com.np" target="_blank" style="color: var(--text-main); font-size: 2rem;"><i class="fas fa-globe"></i></a>
            </div>

            <img src="https://komarev.com/ghpvc/?username=E-4-0-4&color=3b82f6&style=for-the-badge&label=Profile+Views" alt="Profile Views" class="profile-views">
            
            <br><br>
            <p class="quote">
                💭 <span>"Code with passion, secure with precision"</span>
            </p>
            
            <p style="margin-top: 20px; font-size: 0.85rem; color: var(--text-muted);">
                ⭐ If you find my work interesting, consider giving a star to my repositories!
            </p>
        </footer>

    </div>

</body>
</html>
