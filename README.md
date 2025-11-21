<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio GWHJGTY</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #FF6B6B;
            --secondary: #4ECDC4;
            --dark: #1A535C;
            --light: #F7FFF7;
            --accent: #FFE66D;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1A535C 0%, #4ECDC4 100%);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header dengan gaya Jepang */
        .header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: "🌸";
            position: absolute;
            top: 20px;
            left: 10%;
            font-size: 2rem;
            opacity: 0.7;
            animation: float 6s ease-in-out infinite;
        }

        .header::after {
            content: "🎋";
            position: absolute;
            top: 40px;
            right: 10%;
            font-size: 2rem;
            opacity: 0.7;
            animation: float 8s ease-in-out infinite 1s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
        }

        .profile-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .profile-pic {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 5px solid var(--accent);
            object-fit: cover;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: all 0.3s ease;
        }

        .profile-pic:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 40px rgba(255,230,109,0.4);
        }

        .name {
            font-size: 3rem;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            background: linear-gradient(45deg, var(--accent), #FF9F1C);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }

        .role {
            font-size: 1.5rem;
            color: var(--accent);
            margin-bottom: 15px;
        }

        .description {
            max-width: 600px;
            text-align: center;
            line-height: 1.6;
            font-size: 1.1rem;
            opacity: 0.9;
        }

        /* Section styling */
        .section {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            border: 1px solid rgba(255,255,255,0.2);
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: var(--accent);
            position: relative;
        }

        .section-title::after {
            content: "";
            display: block;
            width: 100px;
            height: 4px;
            background: var(--primary);
            margin: 10px auto;
            border-radius: 2px;
        }

        /* Skills section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .skill-item {
            background: rgba(255,255,255,0.1);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .skill-item:hover {
            transform: translateY(-10px);
            background: rgba(255,255,255,0.2);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            color: var(--accent);
        }

        .skill-name {
            font-weight: bold;
            font-size: 1.1rem;
        }

        /* Projects section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .project-card {
            background: rgba(255,255,255,0.1);
            border-radius: 15px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
        }

        .project-img {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .project-content {
            padding: 20px;
        }

        .project-title {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--accent);
        }

        .project-desc {
            color: rgba(255,255,255,0.8);
            margin-bottom: 15px;
            line-height: 1.5;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tag {
            background: rgba(255,255,255,0.2);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
        }

        /* Contact section */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .contact-item {
            font-size: 90%;
            background: rgba(255,255,255,0.1);
            padding: 35px;
            border-radius: 25px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid rgba(255,255,255,0.2);
        }

        .contact-item:hover {
            transform: scale(1.05);
            background: rgba(255,255,255,0.2);
        }

        .contact-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            color: var(--accent);
        }

        .contact-label {
            font-weight: bold;
            margin-bottom: 10px;
            color: var(--accent);
        }

        .contact-value {
            color: rgba(255,255,255,0.9);
            word-break: break-all;
        }

        /* Interactive elements */
        .floating {
            animation: float 6s ease-in-out infinite;
        }

        .pulse {
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Responsive design */
        @media (max-width: 768px) {
            .name {
                font-size: 2rem;
            }
            
            .role {
                font-size: 1.2rem;
            }
            
            .section {
                padding: 25px 20px;
            }
            
            .skills-grid,
            .projects-grid,
            .contact-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Cherry blossom background elements */
        .cherry-blossom {
            position: fixed;
            font-size: 2rem;
            opacity: 0.7;
            z-index: -1;
            pointer-events: none;
        }

        .blossom-1 { top: 10%; left: 5%; animation: fall 15s linear infinite; }
        .blossom-2 { top: 20%; right: 7%; animation: fall 18s linear infinite 2s; }
        .blossom-3 { top: 35%; left: 15%; animation: fall 12s linear infinite 4s; }
        .blossom-4 { top: 50%; right: 12%; animation: fall 20s linear infinite 1s; }
        .blossom-5 { top: 65%; left: 8%; animation: fall 16s linear infinite 3s; }

        @keyframes fall {
            0% { transform: translateY(-100px) rotate(0deg); opacity: 0; }
            10% { opacity: 0.7; }
            90% { opacity: 0.7; }
            100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }

        /* Modal for project details */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: var(--dark);
            padding: 30px;
            border-radius: 15px;
            max-width: 600px;
            width: 90%;
            text-align: center;
            transform: scale(0);
            transition: transform 0.3s ease;
        }

        .modal.show .modal-content {
            transform: scale(1);
        }

        .close-btn {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 2rem;
            cursor: pointer;
            color: var(--accent);
        }
    </style>
</head>
<body>
    <!-- Cherry blossom decorations -->
    <div class="cherry-blossom blossom-1">🌸</div>
    <div class="cherry-blossom blossom-2">🌸</div>
    <div class="cherry-blossom blossom-3">🌸</div>
    <div class="cherry-blossom blossom-4">🌸</div>
    <div class="cherry-blossom blossom-5">🌸</div>

    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-container">
                <img src="aset/ai_repair_20251111172630858.jpg" alt="Profile" class="profile-pic pulse">
                <h1 class="name">Satrya Khanza Al-faruq Kurniawan</h1>
                <p class="role">frontend Developer & UI/UX Designer</p>
                <p class="description">
                    Seorang frontend developer yang mencintai teknologi dan desain. 
                    membangun keindahan visual yang nyaman di mata semua orang. 
                    Terinspirasi oleh keindahan negara Jepang dan prinsip "less is more".
                </p>
            </div>
        </header>

        <!-- Skills Section -->
        <section class="section">
            <h2 class="section-title">Keahlian Saya</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-html5"></i>
                    </div>
                    <div class="skill-name">HTML5</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-css3-alt"></i>
                    </div>
                    <div class="skill-name">CSS3</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-js"></i>
                    </div>
                    <div class="skill-name">JavaScript</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-java"></i>
                    </div>
                    <div class="skill-name">Java</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fas fa-paint-brush"></i>
                    </div>
                    <div class="skill-name">UI/UX Design</div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section class="section">
            <h2 class="section-title">Proyek Terbaru</h2>
            <div class="projects-grid">
                <div class="project-card" onclick="showProject('E-commerce Platform', 'Platform e-commerce modern dengan fitur keranjang belanja dan sistem pembayaran.')">
                    <div class="project-img">
                        <i class="fas fa-shopping-cart"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">E-commerce Platform</h3>
                        <p class="project-desc">Platform e-commerce modern.</p>
                        <div class="project-tags">
                            <span class="tag">Html</span>
                            <span class="tag">Css</span>
                        </div>
                    </div>
                </div>
                <div class="project-card" onclick="showProject('Dashboard Analytics', 'Dashboard analitik real-time dengan visualisasi data yang interaktif.')">
                    <div class="project-img">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Portfolio</h3>
                        <p class="project-desc">Portfolio simple dengan isi yang efektif.</p>
                        <div class="project-tags">
                            <span class="tag">JavaScript</span>
                            <span class="tag">css</span>
                            <span class="tag">Html</span>
                        </div>
                    </div>
                </div>
                <div class="project-card" onclick="showProject('Travel App', 'Aplikasi perjalanan dengan fitur booking dan rekomendasi destinasi.')">
                    <div class="project-img">
                        <i class="fas fa-whiteboard fa-display"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Streaming App</h3>
                        <p class="project-desc">Aplikasi Streamin.</p>
                        <div class="project-tags">
                            <span class="tag">React Native</span>
                            <span class="tag">Firebase</span>
                            <span class="tag">  API</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="section">
            <h2 class="section-title">Kontak Saya</h2>
            <div class="contact-grid">
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fab fa-github"></i>
                    </div>
                    <div class="contact-label">GitHub</div>
                    <div class="contact-value"><a href="https://github.com/musyaf1r" style="text-decoration:none; color: aliceblue;">github.com/musyaf1r</a></div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-envelope"></i>
                    </div>
                    <div class="contact-label">Email</div>
                    <div class="contact-value"><a href="https://mail.google.com/mail/u/0/#inbox?compose=CrpPbDzHzfPmTVQDJVtcgDMvBzmzTpWLfjnltQfcWtZlMxBnpCVpLNRSDwmCGNwlFcCmBTtkMxpQGDVVHXpg" style="text-decoration: none;color: aliceblue;">musyafir84009@email.com</a></div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fab fa-whatsapp"></i>
                    </div>
                    <div class="contact-label">WhatsApp</div>
                    <div class="contact-value"><a href="https://wa.me/6283130098468" style="text-decoration: none;color: aliceblue;">+62 831-3009-8468</a></div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fab fa-instagram"></i>
                    </div>
                    <div class="contact-label">Instagram</div>
                    <div class="contact-value"><a href="https://www.instagram.com/htcntk_14/" style="text-decoration :none ; color: aliceblue;">@htcntk_14</a></div>
                </div>
            </div>
        </section>
    </div>
    <section class="section">
        <h2 class="section-title">Support me</h2>
        <div class="contact-grid">
            <div class="contact-item">
                <div class="contact-icon">
                </div>
                <div class="contact-value"><a href="https://saweria.co/musyafir" style="text-decoration:none; color: aliceblue; font-size: 30px;">Suport me with saweria</a></div>
            </div>
        </section>
    </div>

    <!-- Project Modal -->
    <div class="modal" id="projectModal">
        <div class="modal-content">
            <span class="close-btn" onclick="closeModal()">&times;</span>
            <h3 id="modalTitle" class="project-title">Project Title</h3>
            <p id="modalDesc" class="project-desc">Project description will appear here...</p>
            <button class="contact-item" style="margin-top: 20px; width: auto; display: inline-block;">
                <i class="fas fa-external-link-alt"></i> Lihat Proyek
            </button>
        </div>
    </div>

    <script>
        function showProject(title, description) {
            document.getElementById('modalTitle').textContent = title;
            document.getElementById('modalDesc').textContent = description;
            document.getElementById('projectModal').style.display = 'flex';
        }

        function closeModal() {
            document.getElementById('projectModal').style.display = 'none';
        }

        // Close modal when clicking outside
        window.onclick = function(event) {
            const modal = document.getElementById('projectModal');
            if (event.target === modal) {
                modal.style.display = 'none';
            }
        }

        // Add hover effects to contact items
        const contactItems = document.querySelectorAll('.contact-item');
        contactItems.forEach(item => {
            item.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.05)';
            });
            item.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1)';
            });
        });

        // Create dynamic cherry blossoms
        function createBlossoms() {
            const container = document.querySelector('.container');
            for (let i = 0; i < 20; i++) {
                const blossom = document.createElement('div');
                blossom.className = 'cherry-blossom';
                blossom.innerHTML = '🌸';
                blossom.style.left = Math.random() * 100 + 'vw';
                blossom.style.animationDelay = Math.random() * 5 + 's';
                blossom.style.fontSize = (Math.random() * 20 + 10) + 'px';
                document.body.appendChild(blossom);
            }
        }

        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            createBlossoms();
            
            // Add click effects to project cards
            const projectCards = document.querySelectorAll('.project-card');
            projectCards.forEach(card => {
                card.addEventListener('click', function() {
                    this.style.transform = 'translateY(-15px)';
                    setTimeout(() => {
                        this.style.transform = 'translateY(-10px)';
                    }, 200);
                });
            });
        });
    </script>
</body>
</html>
