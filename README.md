<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name | Portfolio</title>
    <style>
        /* --- CSS VARIABLES & RESET --- */
        :root {
            --bg-color: #fcfcfc;
            --text-main: #1a1a1a;
            --text-muted: #666666;
            --accent-color: #2563eb;
            --accent-hover: #1d4ed8;
            --card-bg: #ffffff;
            --border-color: #e5e5e5;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
        }

        a { text-decoration: none; color: inherit; }

        /* --- NAVIGATION & HERO --- */
        nav { display: flex; justify-content: space-between; align-items: center; padding: 2rem 5%; max-width: 1200px; margin: 0 auto; }
        .logo { font-size: 1.5rem; font-weight: 700; letter-spacing: -0.5px; }
        .nav-links a { margin-left: 2rem; font-weight: 500; color: var(--text-muted); transition: color 0.3s ease; }
        .nav-links a:hover { color: var(--accent-color); }
        
        .hero { max-width: 1200px; margin: 6rem auto; padding: 0 5%; text-align: left; }
        .hero h1 { font-size: 3.5rem; font-weight: 800; line-height: 1.1; margin-bottom: 1.5rem; }
        .hero p { font-size: 1.25rem; color: var(--text-muted); max-width: 600px; margin-bottom: 2rem; }

        /* --- PROJECTS GALLERY --- */
        .projects-section {
            max-width: 1200px;
            margin: 0 auto 6rem auto;
            padding: 0 5%;
        }

        .section-title { font-size: 2rem; margin-bottom: 3rem; border-bottom: 2px solid var(--border-color); padding-bottom: 1rem; }

        .grid {
            display: grid;
            /* Increased card size to accommodate the collage beautifully */
            grid-template-columns: repeat(auto-fit, minmax(420px, 1fr));
            gap: 3rem;
        }

        /* Card Container */
        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-6px);
            box-shadow: 0 16px 32px rgba(0, 0, 0, 0.08);
        }

        /* --- NEW: MEDIA COLLAGE & SINGLE LAYOUTS --- */
        
        /* Base media container */
        .card-media {
            display: grid;
            gap: 2px; /* Creates a clean 2px gap between collage images */
            background-color: #f0f0f0; /* Color of the gap lines */
        }

        .card-media img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        /* Slight zoom effect on hover for all images */
        .card:hover .card-media img {
            transform: scale(1.03);
        }

        /* 1. Collage Layout: 1 Top, 2 Bottom */
        .media-collage {
            grid-template-columns: 1fr 1fr; /* Two columns for the bottom row */
            grid-template-rows: 260px 160px; /* Top row height, Bottom row height */
        }

        /* The first image (GIF) spans all the way across */
        .media-collage img:first-child {
            grid-column: 1 / -1; 
        }

        /* 2. Single Image Layout */
        .media-single {
            grid-template-columns: 1fr;
            grid-template-rows: 320px; /* Generous height for a single banner image */
        }

        /* Prevent the hover scale from overflowing the grid cells */
        .img-wrapper {
            overflow: hidden;
            width: 100%;
            height: 100%;
        }
        .media-collage .img-wrapper:first-child { grid-column: 1 / -1; }

        /* --- CARD CONTENT & BUTTONS --- */
        .card-content { padding: 2rem; display: flex; flex-direction: column; flex-grow: 1; }
        .card-title { font-size: 1.4rem; margin-bottom: 0.5rem; font-weight: 700;}
        .card-desc { color: var(--text-muted); font-size: 1.05rem; margin-bottom: 1.5rem; }
        
        .card-tags { display: flex; gap: 0.5rem; margin-bottom: 2rem; flex-wrap: wrap; }
        .tag { background-color: #f1f5f9; color: #475569; font-size: 0.8rem; padding: 0.35rem 0.85rem; border-radius: 20px; font-weight: 600; }

        .card-actions { display: flex; gap: 1rem; margin-top: auto; flex-wrap: wrap; }
        
        .action-btn { display: inline-flex; align-items: center; justify-content: center; padding: 0.75rem 1.25rem; font-size: 0.95rem; font-weight: 600; border-radius: 8px; transition: all 0.2s ease; }
        .action-btn.primary { background-color: var(--accent-color); color: #ffffff; }
        .action-btn.primary:hover { background-color: var(--accent-hover); transform: translateY(-2px); box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25); }
        .action-btn.secondary { background-color: #f1f5f9; color: var(--text-main); border: 1px solid #e2e8f0; }
        .action-btn.secondary:hover { background-color: #e2e8f0; transform: translateY(-2px); }
        
        .action-btn svg { width: 18px; height: 18px; margin-left: 6px; transition: transform 0.2s ease; }
        .action-btn:hover svg { transform: translateX(4px); }

        /* --- FOOTER & RESPONSIVE --- */
        footer { text-align: center; padding: 3rem 5%; border-top: 1px solid var(--border-color); color: var(--text-muted); }
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .nav-links { display: none; }
            .grid { grid-template-columns: 1fr; } /* Stack cards on mobile */
            .media-collage { grid-template-rows: 200px 120px; } /* Slightly smaller collage on mobile */
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav>
        <div class="logo">Jane Doe.</div>
        <div class="nav-links">
            <a href="#about">About</a>
            <a href="#projects">Work</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="hero" id="about">
        <h1>Hi, I'm Jane. <br>I build digital experiences.</h1>
        <p>I am a software developer and designer specializing in creating clean, user-friendly, and performant applications. Here is a showcase of my recent work.</p>
    </header>

    <!-- Projects Section -->
    <section class="projects-section" id="projects">
        <h2 class="section-title">Selected Projects</h2>
        
        <div class="grid">
            
            <!-- PROJECT 1: COLLAGE LAYOUT (3 Images) -->
            <div class="card">
                <!-- Notice the 'media-collage' class -->
                <div class="card-media media-collage">
                    <!-- Top Image / GIF (Spans full width) -->
                    <div class="img-wrapper">
                        <img src="assets/Images/quadruped_walk.gif" alt="Main GIF">
                    </div>
                    <!-- Bottom Left Image -->
                    <div class="img-wrapper">
                        <img src="assets/Images/quadruped_walk_trot.gif" alt="Detail 1">
                    </div>
                    <!-- Bottom Right Image -->
                    <div class="img-wrapper">
                        <img src="assets/Images/quadruped_running.gif" alt="Detail 2">
                    </div>
                </div>
                
                <div class="card-content">
                    <h3 class="card-title">E-Commerce Dashboard</h3>
                    <p class="card-desc">A full-stack analytics dashboard built for tracking online store metrics in real-time. Features interactive charts and a dynamic dark mode interface.</p>
                    <div class="card-tags">
                        <span class="tag">React</span>
                        <span class="tag">Node.js</span>
                    </div>
                    <div class="card-actions">
                        <a href="#" class="action-btn primary">
                            Live Demo 
                            <svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
                        </a>
                        <a href="#" class="action-btn secondary">GitHub</a>
                    </div>
                </div>
            </div>

            <!-- PROJECT 2: SINGLE IMAGE LAYOUT (1 Image) -->
            <div class="card">
                <!-- Notice the 'media-single' class -->
                <div class="card-media media-single">
                    <div class="img-wrapper">
                        <img src="https://via.placeholder.com/800x500.png?text=Single+Project+Banner" alt="Project Banner">
                    </div>
                </div>
                
                <div class="card-content">
                    <h3 class="card-title">Weather Companion App</h3>
                    <p class="card-desc">A location-based weather application utilizing external REST APIs to provide accurate 7-day forecasting with beautifully animated UI elements.</p>
                    <div class="card-tags">
                        <span class="tag">JavaScript</span>
                        <span class="tag">API</span>
                    </div>
                    <div class="card-actions">
                        <a href="#" class="action-btn primary">
                            View Project
                            <svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
                        </a>
                        <a href="#" class="action-btn secondary">Source Code</a>
                    </div>
                </div>
            </div>

            <!-- PROJECT 3: COLLAGE LAYOUT AGAIN -->
            <div class="card">
                <div class="card-media media-collage">
                    <div class="img-wrapper">
                        <img src="https://via.placeholder.com/800x400.png?text=App+Demo+GIF" alt="App GIF">
                    </div>
                    <div class="img-wrapper">
                        <img src="https://via.placeholder.com/400x300.png?text=Mobile+View" alt="Mobile">
                    </div>
                    <div class="img-wrapper">
                        <img src="https://via.placeholder.com/400x300.png?text=Tablet+View" alt="Tablet">
                    </div>
                </div>
                
                <div class="card-content">
                    <h3 class="card-title">Task Management Tool</h3>
                    <p class="card-desc">A Kanban-style project management tool with drag-and-drop functionality, real-time sync, and team collaboration features.</p>
                    <div class="card-tags">
                        <span class="tag">Vue.js</span>
                        <span class="tag">Firebase</span>
                    </div>
                    <div class="card-actions">
                        <a href="#" class="action-btn secondary">Read Case Study</a>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <!-- Footer Section -->
    <footer id="contact">
        <p>&copy; 2026 Jane Doe. Built with HTML & CSS.</p>
    </footer>

</body>
</html>
