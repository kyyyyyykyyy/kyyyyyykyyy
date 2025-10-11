<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kyy - Digital Architect & Creative Technologist</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-primary: #050505;
            --bg-secondary: #0A0F1E;
            --neon-cyan: #00FFFF;
            --neon-magenta: #FF00FF;
            --neon-green: #7FFF00;
            --text-light: #B0B0B0;
            --text-white: #FFFFFF;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-primary);
            color: var(--text-light);
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            line-height: 1.6;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Orbitron', sans-serif;
            color: var(--text-white);
            margin-bottom: 1rem;
        }

        h1 {
            font-size: 4rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
        }

        h2 {
            font-size: 2.5rem;
            position: relative;
            display: inline-block;
            margin-bottom: 3rem;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--neon-cyan), var(--neon-magenta));
            box-shadow: 0 0 10px var(--neon-cyan);
        }

        /* Animasi Pembuka */
        #opening-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--bg-primary);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
        }

        .line {
            width: 0;
            height: 4px;
            background-color: var(--neon-cyan);
            position: absolute;
            box-shadow: 0 0 15px var(--neon-cyan);
            animation: blink 0.5s infinite alternate;
        }

        @keyframes blink {
            0% { opacity: 0.2; }
            100% { opacity: 1; }
        }

        .particle {
            position: absolute;
            width: 8px;
            height: 8px;
            background-color: var(--neon-cyan);
            border-radius: 50%;
            opacity: 0;
        }

        .name-letter {
            font-family: 'Orbitron', sans-serif;
            font-size: 8rem;
            color: var(--neon-cyan);
            position: absolute;
            opacity: 0;
            text-shadow: 0 0 20px var(--neon-cyan);
        }

        /* Kursor Kustom */
        .cursor {
            position: fixed;
            width: 20px;
            height: 20px;
            border: 2px solid var(--neon-cyan);
            border-radius: 50%;
            pointer-events: none;
            z-index: 999;
            transition: transform 0.1s;
            mix-blend-mode: difference;
        }

        .cursor-trail {
            position: fixed;
            width: 6px;
            height: 6px;
            background-color: var(--neon-magenta);
            border-radius: 50%;
            pointer-events: none;
            z-index: 998;
            opacity: 0.6;
            transition: transform 0.05s;
        }

        /* Background Partikel */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        /* Container Utama */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        section {
            padding: 8rem 0;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        /* Hero Section */
        #hero {
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(to bottom, rgba(5,5,5,0.9), rgba(10,15,30,0.8));
        }

        .hero-content {
            z-index: 2;
        }

        .tagline {
            font-size: 1.5rem;
            margin: 2rem 0;
            color: var(--text-white);
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: transparent;
            color: var(--neon-cyan);
            border: 2px solid var(--neon-cyan);
            border-radius: 0;
            font-family: 'Orbitron', sans-serif;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-top: 2rem;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 0 15px rgba(0, 255, 255, 0.3);
        }

        .cta-button:hover {
            background-color: var(--neon-cyan);
            color: var(--bg-primary);
            box-shadow: 0 0 25px var(--neon-cyan);
        }

        /* Glassmorphism Cards */
        .glass-card {
            background: rgba(10, 15, 30, 0.6);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .glass-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.5);
        }

        /* Profile Section */
        .profile-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }

        .profile-image {
            position: relative;
            width: 100%;
            max-width: 300px;
            margin: 0 auto;
        }

        .profile-img {
            width: 100%;
            border-radius: 10px;
            filter: grayscale(30%);
            transition: all 0.5s ease;
        }

        .profile-img:hover {
            filter: grayscale(0%);
        }

        .hud-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 2px solid var(--neon-green);
            border-radius: 10px;
            box-shadow: 0 0 15px var(--neon-green);
            opacity: 0;
            transition: opacity 0.5s ease;
            pointer-events: none;
        }

        .profile-image:hover .hud-overlay {
            opacity: 0.7;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 1.5rem;
        }

        .skill-item {
            text-align: center;
            padding: 1.5rem 1rem;
            border-radius: 8px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-item:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px var(--neon-magenta);
            background-color: rgba(255, 0, 255, 0.1);
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--neon-cyan);
        }

        /* Timeline */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 4px;
            background: linear-gradient(to bottom, var(--neon-cyan), var(--neon-magenta));
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
            box-shadow: 0 0 10px var(--neon-cyan);
        }

        .timeline-item {
            padding: 10px 40px;
            position: relative;
            width: 50%;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
        }

        .timeline-item:nth-child(odd) {
            left: 0;
        }

        .timeline-item:nth-child(even) {
            left: 50%;
        }

        .timeline-dot {
            position: absolute;
            width: 20px;
            height: 20px;
            right: -10px;
            background-color: var(--neon-green);
            border-radius: 50%;
            z-index: 1;
            box-shadow: 0 0 10px var(--neon-green);
            top: 15px;
            animation: pulse 2s infinite;
        }

        .timeline-item:nth-child(even) .timeline-dot {
            left: -10px;
        }

        @keyframes pulse {
            0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(127, 255, 0, 0.7); }
            70% { transform: scale(1); box-shadow: 0 0 0 10px rgba(127, 255, 0, 0); }
            100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(127, 255, 0, 0); }
        }

        /* Portfolio Grid */
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }

        .portfolio-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            height: 250px;
            cursor: pointer;
        }

        .portfolio-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .portfolio-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease;
            padding: 1rem;
            text-align: center;
        }

        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }

        .portfolio-item:hover .portfolio-img {
            transform: scale(1.1);
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            z-index: 1000;
            overflow-y: auto;
        }

        .modal-content {
            background-color: var(--bg-secondary);
            margin: 5% auto;
            padding: 2rem;
            border: 1px solid var(--neon-cyan);
            width: 80%;
            max-width: 800px;
            border-radius: 10px;
            position: relative;
            box-shadow: 0 0 30px var(--neon-cyan);
            animation: modalOpen 0.5s ease;
        }

        @keyframes modalOpen {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }

        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1.5rem;
            font-size: 2rem;
            color: var(--neon-cyan);
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close-modal:hover {
            color: var(--neon-magenta);
        }

        /* Contact Section */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }

        .social-links {
            display: flex;
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .social-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--neon-cyan);
            font-size: 1.5rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .social-icon:hover {
            transform: rotateY(180deg) scale(1.2);
            background-color: var(--neon-cyan);
            color: var(--bg-primary);
            box-shadow: 0 0 15px var(--neon-cyan);
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-input {
            padding: 1rem;
            background-color: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 5px;
            color: var(--text-white);
            font-family: 'Inter', sans-serif;
            transition: all 0.3s ease;
        }

        .form-input:focus {
            outline: none;
            border-color: var(--neon-cyan);
            box-shadow: 0 0 10px var(--neon-cyan);
        }

        .submit-btn {
            padding: 1rem 2rem;
            background: transparent;
            color: var(--neon-magenta);
            border: 2px solid var(--neon-magenta);
            border-radius: 0;
            font-family: 'Orbitron', sans-serif;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .submit-btn:hover {
            background-color: var(--neon-magenta);
            color: var(--bg-primary);
            box-shadow: 0 0 20px var(--neon-magenta);
        }

        /* Music Toggle */
        .music-toggle {
            position: fixed;
            top: 2rem;
            right: 2rem;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: rgba(10, 15, 30, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            z-index: 100;
            border: 1px solid var(--neon-cyan);
            color: var(--neon-cyan);
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }

        .music-toggle:hover {
            background-color: var(--neon-cyan);
            color: var(--bg-primary);
            box-shadow: 0 0 15px var(--neon-cyan);
        }

        /* Responsiveness */
        @media (max-width: 992px) {
            .profile-content, .contact-content {
                grid-template-columns: 1fr;
            }
            
            .timeline::after {
                left: 31px;
            }
            
            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            
            .timeline-item:nth-child(even) {
                left: 0;
            }
            
            .timeline-dot {
                left: 21px;
            }
            
            .timeline-item:nth-child(even) .timeline-dot {
                left: 21px;
            }
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 2rem;
            }
            
            section {
                padding: 5rem 0;
            }
            
            .portfolio-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Animasi Scroll */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .typewriter {
            overflow: hidden;
            border-right: 2px solid var(--neon-cyan);
            white-space: nowrap;
            margin: 0 auto;
            animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--neon-cyan) }
        }
    </style>
</head>
<body>
    <!-- Opening Animation -->
    <div id="opening-animation">
        <div class="line" id="line"></div>
    </div>

    <!-- Kursor Kustom -->
    <div class="cursor"></div>
    <div class="cursor-trail"></div>

    <!-- Background Partikel -->
    <div id="particles-js"></div>

    <!-- Music Toggle -->
    <div class="music-toggle" id="music-toggle">
        <i class="fas fa-music"></i>
    </div>

    <!-- Hero Section -->
    <section id="hero">
        <div class="container">
            <div class="hero-content">
                <h1 class="fade-in">KYY</h1>
                <p class="tagline fade-in">Digital Architect & Creative Technologist</p>
                <a href="#portfolio" class="cta-button fade-in">Lihat Proyek Saya</a>
            </div>
        </div>
    </section>

    <!-- Profile Section -->
    <section id="profile">
        <div class="container">
            <h2 class="fade-in">Tentang Saya</h2>
            <div class="profile-content">
                <div class="profile-image fade-in">
                    <div class="profile-img-placeholder" style="background: linear-gradient(45deg, #0A0F1E, #1a1f2e); height: 300px; border-radius: 10px;"></div>
                    <div class="hud-overlay"></div>
                </div>
                <div class="profile-text glass-card fade-in">
                    <p>Saya adalah seorang Digital Architect dengan passion mendalam dalam menciptakan pengalaman digital yang imersif dan berdampak. Dengan latar belakang di bidang teknologi kreatif, saya menggabungkan estetika visual yang kuat dengan fungsionalitas teknis yang solid.</p>
                    <p>Visi saya adalah membangun masa depan digital di mana teknologi dan seni bersatu untuk menciptakan pengalaman yang tak terlupakan. Saya percaya bahwa setiap proyek adalah cerita yang menunggu untuk diceritakan, dan saya berdedikasi untuk menghidupkan cerita tersebut melalui kode dan desain.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="container">
            <h2 class="fade-in">Keahlian</h2>
            <div class="skills-grid">
                <div class="skill-item glass-card fade-in">
                    <div class="skill-icon">JS</div>
                    <h3>JavaScript</h3>
                    <p>Expert</p>
                </div>
                <div class="skill-item glass-card fade-in">
                    <div class="skill-icon">RCT</div>
                    <h3>React</h3>
                    <p>Expert</p>
                </div>
                <div class="skill-item glass-card fade-in">
                    <div class="skill-icon">UI/UX</div>
                    <h3>UI/UX Design</h3>
                    <p>Advanced</p>
                </div>
                <div class="skill-item glass-card fade-in">
                    <div class="skill-icon">NODE</div>
                    <h3>Node.js</h3>
                    <p>Advanced</p>
                </div>
                <div class="skill-item glass-card fade-in">
                    <div class="skill-icon">PY</div>
                    <h3>Python</h3>
                    <p>Intermediate</p>
                </div>
                <div class="skill-item glass-card fade-in">
                    <div class="skill-icon">3D</div>
                    <h3>3D Modeling</h3>
                    <p>Intermediate</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience">
        <div class="container">
            <h2 class="fade-in">Pengalaman Kerja</h2>
            <div class="timeline">
                <div class="timeline-item glass-card fade-in">
                    <div class="timeline-dot"></div>
                    <h3>Lead Frontend Developer</h3>
                    <h4>NeoTech Solutions</h4>
                    <p>2022 - Sekarang</p>
                    <ul>
                        <li>Mengembangkan aplikasi web responsif dengan React dan Vue.js</li>
                        <li>Memimpin tim pengembang frontend dalam proyek enterprise</li>
                        <li>Mengimplementasikan sistem desain yang konsisten</li>
                    </ul>
                </div>
                <div class="timeline-item glass-card fade-in">
                    <div class="timeline-dot"></div>
                    <h3>UI/UX Designer</h3>
                    <h4>CyberDynamics Inc.</h4>
                    <p>2020 - 2022</p>
                    <ul>
                        <li>Mendesain antarmuka pengguna untuk aplikasi mobile dan web</li>
                        <li>Melakukan penelitian pengguna dan pengujian kegunaan</li>
                        <li>Berkolaborasi dengan tim pengembang untuk implementasi desain</li>
                    </ul>
                </div>
                <div class="timeline-item glass-card fade-in">
                    <div class="timeline-dot"></div>
                    <h3>Full Stack Developer</h3>
                    <h4>Digital Forge Studio</h4>
                    <p>2018 - 2020</p>
                    <ul>
                        <li>Mengembangkan aplikasi web full stack dengan MERN stack</li>
                        <li>Mengintegrasikan API pihak ketiga dan layanan cloud</li>
                        <li>Mengoptimalkan performa dan keamanan aplikasi</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education">
        <div class="container">
            <h2 class="fade-in">Pendidikan</h2>
            <div class="timeline">
                <div class="timeline-item glass-card fade-in">
                    <div class="timeline-dot"></div>
                    <h3>Master of Computer Science</h3>
                    <h4>Institute of Advanced Technology</h4>
                    <p>2016 - 2018</p>
                </div>
                <div class="timeline-item glass-card fade-in">
                    <div class="timeline-dot"></div>
                    <h3>Bachelor of Information Systems</h3>
                    <h4>Digital University</h4>
                    <p>2012 - 2016</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio">
        <div class="container">
            <h2 class="fade-in">Portofolio</h2>
            <div class="portfolio-grid">
                <div class="portfolio-item glass-card fade-in">
                    <div class="portfolio-img-placeholder" style="background: linear-gradient(45deg, #0A0F1E, #2a2f3e); height: 100%;"></div>
                    <div class="portfolio-overlay">
                        <h3>Neon Nexus</h3>
                        <p>Aplikasi e-commerce futuristik dengan AR integration</p>
                        <button class="cta-button project-detail" data-project="1">Detail</button>
                    </div>
                </div>
                <div class="portfolio-item glass-card fade-in">
                    <div class="portfolio-img-placeholder" style="background: linear-gradient(45deg, #1a1f2e, #3a3f4e); height: 100%;"></div>
                    <div class="portfolio-overlay">
                        <h3>Cyber Dashboard</h3>
                        <p>Dashboard analitik real-time dengan visualisasi data 3D</p>
                        <button class="cta-button project-detail" data-project="2">Detail</button>
                    </div>
                </div>
                <div class="portfolio-item glass-card fade-in">
                    <div class="portfolio-img-placeholder" style="background: linear-gradient(45deg, #2a2f3e, #4a4f5e); height: 100%;"></div>
                    <div class="portfolio-overlay">
                        <h3>Virtual Concert Platform</h3>
                        <p>Platform konser virtual dengan efek visual interaktif</p>
                        <button class="cta-button project-detail" data-project="3">Detail</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <h2 class="fade-in">Hubungi Saya</h2>
            <div class="contact-content">
                <div class="contact-info glass-card fade-in">
                    <h3>Mari Berkolaborasi</h3>
                    <p>Saya selalu terbuka untuk diskusi tentang proyek baru, peluang kolaborasi, atau sekadar berbagi ide tentang masa depan digital.</p>
                    <p>Email: <span style="color: var(--neon-cyan);">kyy@digitalarchitect.io</span></p>
                    <div class="social-links">
                        <div class="social-icon">in</div>
                        <div class="social-icon">gh</div>
                        <div class="social-icon">ig</div>
                        <div class="social-icon">db</div>
                    </div>
                </div>
                <div class="contact-form glass-card fade-in">
                    <div class="form-group">
                        <label for="name">Nama</label>
                        <input type="text" id="name" class="form-input" placeholder="Masukkan nama Anda">
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" class="form-input" placeholder="Masukkan email Anda">
                    </div>
                    <div class="form-group">
                        <label for="message">Pesan</label>
                        <textarea id="message" class="form-input" rows="5" placeholder="Tulis pesan Anda di sini..."></textarea>
                    </div>
                    <button class="submit-btn" id="submit-form">Kirim Pesan</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Project Modal -->
    <div id="project-modal" class="modal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <h2 id="modal-title">Judul Proyek</h2>
            <div id="modal-content">
                <!-- Konten modal akan diisi oleh JavaScript -->
            </div>
        </div>
    </div>

    <!-- Scripts -->
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        // Opening Animation
        document.addEventListener('DOMContentLoaded', function() {
            const openingAnimation = document.getElementById('opening-animation');
            const line = document.getElementById('line');
            
            // Animasi garis horizontal
            setTimeout(() => {
                line.style.width = '80%';
                line.style.transition = 'width 1s ease';
                
                // Suara statis (simulasi)
                setTimeout(() => {
                    // Animasi partikel meledak
                    createParticles();
                    
                    // Animasi nama muncul
                    setTimeout(() => {
                        createNameLetters();
                        
                        // Animasi montage dan transisi
                        setTimeout(() => {
                            openingAnimation.style.opacity = '0';
                            openingAnimation.style.transition = 'opacity 1s ease';
                            
                            setTimeout(() => {
                                openingAnimation.style.display = 'none';
                            }, 1000);
                        }, 2000);
                    }, 1000);
                }, 1000);
            }, 500);
            
            function createParticles() {
                for (let i = 0; i < 50; i++) {
                    const particle = document.createElement('div');
                    particle.classList.add('particle');
                    
                    const size = Math.random() * 10 + 5;
                    particle.style.width = ${size}px;
                    particle.style.height = ${size}px;
                    
                    const x = Math.random() * window.innerWidth;
                    const y = Math.random() * window.innerHeight;
                    
                    particle.style.left = ${x}px;
                    particle.style.top = ${y}px;
                    
                    const color = Math.random() > 0.5 ? 'var(--neon-cyan)' : 'var(--neon-magenta)';
                    particle.style.backgroundColor = color;
                    particle.style.boxShadow = 0 0 10px ${color};
                    
                    openingAnimation.appendChild(particle);
                    
                    // Animasi partikel
                    setTimeout(() => {
                        particle.style.opacity = '1';
                        particle.style.transition = 'opacity 0.5s ease';
                        
                        setTimeout(() => {
                            particle.style.transform = translate(${Math.random() * 200 - 100}px, ${Math.random() * 200 - 100}px) scale(0);
                            particle.style.opacity = '0';
                            particle.style.transition = 'all 0.8s ease';
                        }, 300);
                    }, i * 20);
                }
            }
            
            function createNameLetters() {
                const letters = ['K', 'Y', 'Y'];
                const centerX = window.innerWidth / 2;
                const centerY = window.innerHeight / 2;
                
                letters.forEach((letter, index) => {
                    const letterElement = document.createElement('div');
                    letterElement.classList.add('name-letter');
                    letterElement.textContent = letter;
                    
                    letterElement.style.left = ${centerX - 100 + (index * 80)}px;
                    letterElement.style.top = ${centerY - 60}px;
                    
                    openingAnimation.appendChild(letterElement);
                    
                    // Animasi glitch untuk setiap huruf
                    setTimeout(() => {
                        letterElement.style.opacity = '1';
                        letterElement.style.transition = 'opacity 0.3s ease';
                        
                        // Efek glitch
                        setTimeout(() => {
                            letterElement.style.transform = 'translateX(5px)';
                            setTimeout(() => {
                                letterElement.style.transform = 'translateX(-5px)';
                                setTimeout(() => {
                                    letterElement.style.transform = 'translateX(0)';
                                }, 50);
                            }, 50);
                        }, 300);
                    }, index * 200);
                });
            }
            
            // Kursor Kustom
            const cursor = document.querySelector('.cursor');
            const cursorTrail = document.querySelector('.cursor-trail');
            
            document.addEventListener('mousemove', (e) => {
                cursor.style.left = e.clientX + 'px';
                cursor.style.top = e.clientY + 'px';
                
                setTimeout(() => {
                    cursorTrail.style.left = e.clientX + 'px';
                    cursorTrail.style.top = e.clientY + 'px';
                }, 100);
            });
            
            // Efek hover pada elemen yang dapat diklik
            const clickableElements = document.querySelectorAll('a, button, .skill-item, .portfolio-item, .social-icon');
            
            clickableElements.forEach(element => {
                element.addEventListener('mouseenter', () => {
                    cursor.style.transform = 'scale(1.5)';
                    cursor.style.backgroundColor = 'var(--neon-cyan)';
                    cursor.style.mixBlendMode = 'normal';
                });
                
                element.addEventListener('mouseleave', () => {
                    cursor.style.transform = 'scale(1)';
                    cursor.style.backgroundColor = 'transparent';
                    cursor.style.mixBlendMode = 'difference';
                });
            });
            
            // Background Partikel
            particlesJS('particles-js', {
                particles: {
                    number: { value: 80, density: { enable: true, value_area: 800 } },
                    color: { value: ['#00FFFF', '#FF00FF', '#7FFF00'] },
                    shape: { type: 'circle' },
                    opacity: { value: 0.5, random: true },
                    size: { value: 3, random: true },
                    line_linked: {
                        enable: true,
                        distance: 150,
                        color: '#00FFFF',
                        opacity: 0.2,
                        width: 1
                    },
                    move: {
                        enable: true,
                        speed: 2,
                        direction: 'none',
                        random: true,
                        out_mode: 'out'
                    }
                },
                interactivity: {
                    detect_on: 'canvas',
                    events: {
                        onhover: { enable: true, mode: 'repulse' },
                        onclick: { enable: true, mode: 'push' }
                    }
                }
            });
            
            // Animasi Scroll
            const fadeElements = document.querySelectorAll('.fade-in');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        
                        // Efek typewriter untuk tagline
                        if (entry.target.classList.contains('tagline')) {
                            entry.target.classList.add('typewriter');
                        }
                    }
                });
            }, { threshold: 0.1 });
            
            fadeElements.forEach(element => {
                observer.observe(element);
            });
            
            // Timeline animation
            const timelineItems = document.querySelectorAll('.timeline-item');
            
            const timelineObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                        
                        // Animate timeline line
                        const timeline = document.querySelector('.timeline');
                        timeline.style.background = linear-gradient(to bottom, var(--neon-cyan) 0%, var(--neon-magenta) 100%);
                    }
                });
            }, { threshold: 0.3 });
            
            timelineItems.forEach(item => {
                timelineObserver.observe(item);
            });
            
            // Modal Project
            const modal = document.getElementById('project-modal');
            const projectButtons = document.querySelectorAll('.project-detail');
            const closeModal = document.querySelector('.close-modal');
            
            projectButtons.forEach(button => {
                button.addEventListener('click', () => {
                    const projectId = button.getAttribute('data-project');
                    showProjectModal(projectId);
                });
            });
            
            closeModal.addEventListener('click', () => {
                modal.style.display = 'none';
            });
            
            window.addEventListener('click', (e) => {
                if (e.target === modal) {
                    modal.style.display = 'none';
                }
            });
            
            function showProjectModal(projectId) {
                const modalTitle = document.getElementById('modal-title');
                const modalContent = document.getElementById('modal-content');
                
                let title = '';
                let content = '';
                
                switch(projectId) {
                    case '1':
                        title = 'Neon Nexus';
                        content = `
                            <p><strong>Deskripsi:</strong> Platform e-commerce futuristik dengan integrasi augmented reality untuk visualisasi produk.</p>
                            <p><strong>Teknologi:</strong> React, Three.js, Node.js, MongoDB, ARCore</p>
                            <p><strong>Tantangan:</strong> Mengoptimalkan performa rendering 3D di perangkat mobile dan mengintegrasikan AR dengan mulus ke dalam flow pembelian.</p>
                            <p><strong>Solusi:</strong> Mengimplementasikan lazy loading untuk model 3D dan mengembangkan custom shader untuk optimisasi visual.</p>
                            <div style="margin-top: 2rem;">
                                <a href="#" class="cta-button" style="margin-right: 1rem;">Live Demo</a>
                                <a href="#" class="cta-button">Source Code</a>
                            </div>
                        `;
                        break;
                    case '2':
                        title = 'Cyber Dashboard';
                        content = `
                            <p><strong>Deskripsi:</strong> Dashboard analitik real-time dengan visualisasi data 3D interaktif untuk monitoring bisnis.</p>
                            <p><strong>Teknologi:</strong> Vue.js, D3.js, WebGL, Socket.io, Python</p>
                            <p><strong>Tantangan:</strong> Menampilkan data kompleks dalam format yang mudah dipahami tanpa mengorbankan detail.</p>
                            <p><strong>Solusi:</strong> Mengembangkan sistem layer informasi yang memungkinkan pengguna menyesuaikan tingkat detail yang ditampilkan.</p>
                            <div style="margin-top: 2rem;">
                                <a href="#" class="cta-button" style="margin-right: 1rem;">Live Demo</a>
                                <a href="#" class="cta-button">Source Code</a>
                            </div>
                        `;
                        break;
                    case '3':
                        title = 'Virtual Concert Platform';
                        content = `
                            <p><strong>Deskripsi:</strong> Platform konser virtual dengan efek visual interaktif yang disinkronisasi dengan musik secara real-time.</p>
                            <p><strong>Teknologi:</strong> WebRTC, WebGL, Tone.js, Firebase, React</p>
                            <p><strong>Tantangan:</strong> Menyinkronisasi efek visual dengan audio secara real-time di berbagai kondisi jaringan.</p>
                            <p><strong>Solusi:</strong> Mengimplementasikan buffer adaptif dan fallback visual untuk menjaga pengalaman konsisten.</p>
                            <div style="margin-top: 2rem;">
                                <a href="#" class="cta-button" style="margin-right: 1rem;">Live Demo</a>
                                <a href="#" class="cta-button">Source Code</a>
                            </div>
                        `;
                        break;
                }
                
                modalTitle.textContent = title;
                modalContent.innerHTML = content;
                modal.style.display = 'block';
            }
            
            // Form Submission
            const contactForm = document.getElementById('submit-form');
            contactForm.addEventListener('click', (e) => {
                e.preventDefault();
                
                // Simulasi pengiriman form
                const name = document.getElementById('name').value;
                const email = document.getElementById('email').value;
                const message = document.getElementById('message').value;
                
                if (name && email && message) {
                    // Efek tombol diklik
                    contactForm.textContent = 'Mengirim...';
                    contactForm.style.background = 'var(--neon-magenta)';
                    contactForm.style.color = 'var(--bg-primary)';
                    
                    // Simulasi delay pengiriman
                    setTimeout(() => {
                        // Reset form
                        document.getElementById('name').value = '';
                        document.getElementById('email').value = '';
                        document.getElementById('message').value = '';
                        
                        // Reset tombol
                        contactForm.textContent = 'Pesan Terkirim!';
                        
                        setTimeout(() => {
                            contactForm.textContent = 'Kirim Pesan';
                            contactForm.style.background = 'transparent';
                            contactForm.style.color = 'var(--neon-magenta)';
                        }, 2000);
                    }, 1500);
                }
            });
            
            // Music Toggle
            const musicToggle = document.getElementById('music-toggle');
            let audio = null;
            
            musicToggle.addEventListener('click', () => {
                if (!audio) {
                    // In a real implementation, you would link to an actual audio file
                    // audio = new Audio('path-to-synthwave-track.mp3');
                    // audio.loop = true;
                    // audio.play();
                    
                    // For demo purposes, we'll just change the icon
                    musicToggle.innerHTML = '<i class="fas fa-volume-up"></i>';
                    musicToggle.style.boxShadow = '0 0 20px var(--neon-cyan)';
                } else {
                    // audio.pause();
                    musicToggle.innerHTML = '<i class="fas fa-music"></i>';
                    musicToggle.style.boxShadow = 'none';
                    audio = null;
                }
            });
        });
    </script>
</body>
</html>
