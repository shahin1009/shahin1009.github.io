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

        a {
            text-decoration: none;
            color: inherit;
        }

        /* --- NAVIGATION & HERO (Unchanged for layout consistency) --- */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 2rem 5%;
            max-width: 1200px;
            margin: 0 auto;
        }
        .logo { font-size: 1.5rem; font-weight: 700; letter-spacing: -0.5px; }
        .nav-links a { margin-left: 2rem; font-weight: 500; color: var(--text-muted); transition: color 0.3s ease; }
        .nav-links a:hover { color: var(--accent-color); }
        
        .hero { max-width: 1200px; margin: 6rem auto; padding: 0 5%; text-align: left; }
        .hero h1 { font-size: 3.5rem; font-weight: 800; line-height: 1.1; margin-bottom: 1.5rem; }
        .hero p { font-size: 1.25rem; color: var(--text-muted); max-width: 600px; margin-bottom: 2rem; }

        /* --- UPGRADED PROJECTS GALLERY --- */
        .projects-section {
            max-width: 1200px;
            margin: 0 auto 6rem auto;
            padding: 0 5%;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 3rem;
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 1rem;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
            gap: 2.5rem;
        }

        /* Card Container */
        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 16px; /* Slightly softer corners */
            overflow: hidden;
            display: flex;
            flex-direction: column; /* Allows content to stretch */
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-6px);
            box-shadow: 0 16px 32px rgba(0, 0, 0, 0.08);
        }

        /* NEW: Swipeable Image Gallery */
        .card-gallery {
            display: flex;
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            scroll-behavior: smooth;
            -webkit-overflow-scrolling: touch; /* Smooth scrolling on iOS */
            width: 100%;
            height: 240px;
            background-color: #f8f9fa;
        }

        /* Elegant custom scrollbar for the gallery to hint at more images */
        .card-gallery::-webkit-scrollbar {
            height: 6px;
        }
        .card-gallery::-webkit-scrollbar-track {
            background: transparent;
        }
        .card-gallery::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 10px;
        }
        .card-gallery:hover::-webkit-scrollbar-thumb {
            background: #94a3b8; /* Darkens slightly on hover */
        }

        .card-gallery img {
            flex: 0 0 100%; /* Forces each image to take up exactly 100% of the card width */
            height: 100%;
            object-fit: cover;
            scroll-snap-align: start; /* Snaps perfectly to the next image */
        }

        /* Card Content Area */
        .card-content {
            padding: 1.5rem;
            display: flex;
            flex-direction: column;
            flex-grow: 1; /* Pushes the buttons to the bottom */
        }

        .card-title { font-size: 1.35rem; margin-bottom: 0.5rem; font-weight: 700;}
        .card-desc { color: var(--text-muted); font-size: 1rem; margin-bottom: 1.5rem; }
        
        .card-tags {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }
        .tag {
            background-color: #f1f5f9;
            color: #475569;
            font-size: 0.8rem;
            padding: 0.35rem 0.85rem;
            border-radius: 20px;
            font-weight: 600;
        }

        /* NEW: Better Clickables (Action Buttons) */
        .card-actions {
            display: flex;
            gap: 1rem;
            margin-top: auto; /* Aligns buttons to the bottom of the card */
            flex-wrap: wrap;
        }

        .action-btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 0.7rem 1.25rem;
            font-size: 0.95rem;
            font-weight: 600;
            border-radius: 8px;
            transition: all 0.2s ease;
        }

        /* Primary Button (e.g., Live Demo) */
        .action-btn.primary {
            background-color: var(--accent-color);
            color: #ffffff;
        }
        .action-btn.primary:hover {
            background-color: var(--accent-hover);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25);
        }

        /* Secondary Button (e.g., GitHub Repo) */
        .action-btn.secondary {
            background-color: #f1f5f9;
            color: var(--text-main);
            border: 1px solid #e2e8f0;
        }
        .action-btn.secondary:hover {
            background-color: #e2e8f0;
            transform: translateY(-2px);
        }

        /* SVG Arrow Animation inside buttons */
        .action-btn svg {
            width: 18px;
            height: 18px;
            margin-left: 6px;
            transition: transform 0.2s ease;
        }
        .action-btn:hover svg {
            transform: translateX(4px); /* Pushes the arrow to the right on hover */
        }

        /* --- FOOTER & RESPONSIVE --- */
        footer { text-align: center; padding: 3rem 5%; border-top: 1px solid var(--border-color); color: var(--text-muted); }
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .nav-links { display: none; }
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
            
            <!-- Project Card 1 (Showcasing 3 Images/GIFs) -->
            <div class="card">
                <div class="card-gallery">
                    <!-- Image 1 -->
                    <img src="https://via.placeholder.com/800x600.png?text=Preview+1" alt="Preview 1">
                    <!-- Image 2 -->
                    <img src="https://via.placeholder.com/800x600.png?text=Preview+2" alt="Preview 2">
                    <!-- Image 3 -->
                    <img src="https://via.placeholder.com/800x600.png?text=GIF+Demo" alt="GIF Demo">
                </div>
                <div class="card-content">
                    <h3 class="card-title">E-Commerce Dashboard</h3>
                    <p class="card-desc">A full-stack analytics dashboard built for tracking online store metrics in real-time. Try swiping the images above!</p>
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

            <!-- Project Card 2 (Showcasing 2 Images) -->
            <div class="card">
                <div class="card-gallery">
                    <img src="https://via.placeholder.com/800x600.png?text=App+Screenshot+1" alt="App Preview 1">
                    <img src="https://via.placeholder.com/800x600.png?text=App+Screenshot+2" alt="App Preview 2">
                </div>
                <div class="card-content">
                    <h3 class="card-title">Weather Companion App</h3>
                    <p class="card-desc">A location-based weather application utilizing external REST APIs to provide accurate 7-day forecasting with animated UI elements.</p>
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

            <!-- Project Card 3 (Showcasing 1 Image) -->
            <div class="card">
                <div class="card-gallery">
                    <img src="https://via.placeholder.com/800x600.png?text=Single+Showcase+Image" alt="Template Preview">
                </div>
                <div class="card-content">
                    <h3 class="card-title">Portfolio Template</h3>
                    <p class="card-desc">A minimalist, highly customizable portfolio template designed specifically for GitHub Pages deployment. Features pure CSS image sliders.</p>
                    <div class="card-tags">
                        <span class="tag">HTML5</span>
                        <span class="tag">CSS3</span>
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
