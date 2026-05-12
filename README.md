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

        /* --- NAVIGATION --- */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 2rem 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            letter-spacing: -0.5px;
        }

        .nav-links a {
            margin-left: 2rem;
            font-weight: 500;
            color: var(--text-muted);
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        /* --- HERO SECTION --- */
        .hero {
            max-width: 1200px;
            margin: 6rem auto;
            padding: 0 5%;
            text-align: left;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 1.5rem;
        }

        .hero p {
            font-size: 1.25rem;
            color: var(--text-muted);
            max-width: 600px;
            margin-bottom: 2rem;
        }

        .btn {
            display: inline-block;
            background-color: var(--text-main);
            color: #fff;
            padding: 0.8rem 1.5rem;
            border-radius: 6px;
            font-weight: 600;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }

        .btn:hover {
            background-color: var(--accent-color);
            transform: translateY(-2px);
        }

        /* --- PROJECTS GALLERY --- */
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
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
        }

        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 24px rgba(0, 0, 0, 0.08);
        }

        /* Set a fixed aspect ratio for images/gifs */
        .card-img-wrapper {
            width: 100%;
            height: 220px;
            overflow: hidden;
            background-color: #f0f0f0; /* Placeholder color */
        }

        .card-img-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: cover; /* Ensures images/GIFs fill the space without stretching */
            transition: transform 0.5s ease;
        }

        .card:hover .card-img-wrapper img {
            transform: scale(1.05); /* Slight zoom effect on hover */
        }

        .card-content {
            padding: 1.5rem;
        }

        .card-title {
            font-size: 1.25rem;
            margin-bottom: 0.5rem;
        }

        .card-desc {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 1.5rem;
        }

        .card-tags {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
        }

        .tag {
            background-color: #f1f5f9;
            color: #475569;
            font-size: 0.75rem;
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-weight: 600;
        }

        .card-links a {
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--accent-color);
            margin-right: 1rem;
        }

        .card-links a:hover {
            text-decoration: underline;
        }

        /* --- FOOTER --- */
        footer {
            text-align: center;
            padding: 3rem 5%;
            border-top: 1px solid var(--border-color);
            color: var(--text-muted);
        }

        /* --- RESPONSIVE DESIGN --- */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .nav-links { display: none; } /* Simple mobile approach: hide links, keep logo */
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
        <a href="#projects" class="btn">View My Work</a>
    </header>

    <!-- Projects Section -->
    <section class="projects-section" id="projects">
        <h2 class="section-title">Selected Projects</h2>
        
        <div class="grid">
            
            <!-- Project Card 1 (Example with a GIF) -->
            <div class="card">
                <div class="card-img-wrapper">
                    <!-- Replace with your own GIF or Image path -->
                    <img src="https://via.placeholder.com/600x400.png?text=Your+Project+GIF+Here" alt="Project 1 Demo">
                </div>
                <div class="card-content">
                    <h3 class="card-title">E-Commerce Dashboard</h3>
                    <p class="card-desc">A full-stack analytics dashboard built for tracking online store metrics in real-time. Features interactive charts and a dark mode.</p>
                    <div class="card-tags">
                        <span class="tag">React</span>
                        <span class="tag">Node.js</span>
                        <span class="tag">Chart.js</span>
                    </div>
                    <div class="card-links">
                        <a href="#">Live Demo &rarr;</a>
                        <a href="#">GitHub Repo</a>
                    </div>
                </div>
            </div>

            <!-- Project Card 2 -->
            <div class="card">
                <div class="card-img-wrapper">
                    <img src="https://via.placeholder.com/600x400.png?text=Your+Image+Here" alt="Project 2 Preview">
                </div>
                <div class="card-content">
                    <h3 class="card-title">Weather Companion App</h3>
                    <p class="card-desc">A location-based weather application utilizing external REST APIs to provide accurate 7-day forecasting with animated UI elements.</p>
                    <div class="card-tags">
                        <span class="tag">JavaScript</span>
                        <span class="tag">CSS Animations</span>
                        <span class="tag">API</span>
                    </div>
                    <div class="card-links">
                        <a href="#">Live Demo &rarr;</a>
                        <a href="#">GitHub Repo</a>
                    </div>
                </div>
            </div>

            <!-- Project Card 3 -->
            <div class="card">
                <div class="card-img-wrapper">
                    <img src="https://via.placeholder.com/600x400.png?text=Your+GIF+Here" alt="Project 3 Preview">
                </div>
                <div class="card-content">
                    <h3 class="card-title">Portfolio Template</h3>
                    <p class="card-desc">A minimalist, highly customizable portfolio template designed specifically for GitHub Pages deployment without any build tools.</p>
                    <div class="card-tags">
                        <span class="tag">HTML5</span>
                        <span class="tag">CSS Grid</span>
                    </div>
                    <div class="card-links">
                        <a href="#">Live Demo &rarr;</a>
                        <a href="#">GitHub Repo</a>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <!-- Footer Section -->
    <footer id="contact">
        <p>&copy; 2026 Jane Doe. Built with HTML & CSS.</p>
        <p style="margin-top: 0.5rem;">
            <a href="#" style="color: var(--accent-color); margin: 0 0.5rem;">GitHub</a> | 
            <a href="#" style="color: var(--accent-color); margin: 0 0.5rem;">LinkedIn</a> | 
            <a href="#" style="color: var(--accent-color); margin: 0 0.5rem;">Email</a>
        </p>
    </footer>

</body>
</html>
