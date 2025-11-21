<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>StealthMetrics | Defense Analytics & Program Tracking</title>

    <meta name="description" content="StealthMetrics provides high-quality defense visualizations, program timelines, cost analytics, and OSINT-driven aerospace insights.">
    
    <meta property="og:title" content="StealthMetrics | Defense Analytics">
    <meta property="og:description" content="Defense Analytics • Program Tracking • OSINT. Visualizing the F-35 program, LCS deployments, and cost per flight hour data.">
    <meta property="og:type" content="website">
    <meta property="og:image" content="https://vlo225.github.io/VLO-Defense-archives/f35-timeline.png">

    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="StealthMetrics">
    <meta name="twitter:description" content="High-fidelity defense program tracking and cost analytics.">
    <meta name="twitter:image" content="https://vlo225.github.io/VLO-Defense-archives/f35-timeline.png">

    <style>
        :root {
            --bg-color: #f4f1ea;
            --card-bg: #ffffff;
            --text-primary: #2c2926;
            --text-secondary: #595550;
            --accent: #8c3b2b;
            --border: #dcd6cc;
        }

        body {
            font-family: Georgia, "Times New Roman", serif;
            background-color: var(--bg-color);
            color: var(--text-primary);
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        header {
            text-align: center;
            padding-bottom: 40px;
            border-bottom: 2px solid var(--accent);
            margin-bottom: 50px;
        }

        .logo svg {
            height: 60px;
            width: auto;
            margin-bottom: 15px;
            display: block;
            margin-left: auto;
            margin-right: auto;
        }

        h1 {
            margin: 0;
            font-size: 3rem;
            letter-spacing: -1px;
            color: #1a1a1a;
            font-weight: 700;
        }

        .subtitle {
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
            color: var(--text-secondary);
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.85rem;
            margin-top: 10px;
            font-weight: 600;
        }

        .social-link {
            display: inline-block;
            margin-top: 25px;
            color: var(--text-primary);
            text-decoration: none;
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
            font-size: 0.75rem;
            border: 1px solid #b0aaa0;
            padding: 8px 18px;
            border-radius: 4px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            transition: all 0.2s ease;
        }

        .social-link:hover {
            background-color: #e6e2d8;
            border-color: var(--text-primary);
        }

        .chart-card {
            background-color: var(--card-bg);
            border: 1px solid var(--border);
            margin-bottom: 60px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        .chart-info {
            padding: 30px 30px 20px 30px;
            border-bottom: 1px solid var(--bg-color);
        }

        .chart-title {
            font-size: 1.5rem;
            margin: 0 0 10px 0;
            font-weight: 700;
        }

        .chart-desc {
            color: var(--text-secondary);
            font-size: 1rem;
            margin: 0;
            font-style: italic;
        }

        .chart-display {
            padding: 20px;
            background-color: #faf9f7;
            text-align: center;
            cursor: pointer;
        }

        .chart-display img {
            max-width: 100%;
            max-height: 350px;
            width: auto;
            display: inline-block;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: transform 0.2s ease;
        }

        .chart-display:hover img {
            transform: scale(1.02);
        }

        .click-hint {
            font-family: "Helvetica Neue", sans-serif;
            font-size: 0.7rem;
            color: #999;
            margin-top: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        #lightbox {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(20, 20, 20, 0.95);
            align-items: center;
            justify-content: center;
            cursor: zoom-out;
        }

        #lightbox img {
            max-width: 95%;
            max-height: 95%;
            box-shadow: 0 0 20px rgba(0,0,0,0.5);
        }

        footer {
            text-align: center;
            color: var(--text-secondary);
            padding: 50px 0;
            font-size: 0.85rem;
            border-top: 1px solid var(--border);
            margin-top: 60px;
            font-family: "Helvetica Neue", sans-serif;
        }
    </style>
</head>
<body>

    <div id="lightbox" onclick="closeLightbox()">
        <img id="lightbox-img" src="" alt="Full Screen View">
    </div>

    <div class="container">
        <header>
            <div class="logo">
                <svg viewBox="0 0 200 60" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="#2c2926" stroke-width="2">
                    <path d="M10 30 L60 15 L120 15 L170 30 L120 45 L60 45 Z" />
                    <path d="M60 15 L90 5 L120 15" />
                </svg>
            </div>
            <h1>StealthMetrics</h1>
            <div class="subtitle">Visual Intelligence for Aerospace & Defense</div>
            <a href="https://x.com/VLO225" class="social-link">Connect on X</a>
        </header>

        <article class="chart-card">
            <div class="chart-info">
                <h2 class="chart-title">F-35 Program Timeline & Delivery Schedule</h2>
                <p class="chart-desc">Comprehensive breakdown of Software Blocks, Hardware Generations (TR-1/2/3), and Production Lots.</p>
            </div>
            <div class="chart-display" onclick="openLightbox('f35-timeline.png')">
                <img src="f35-timeline.png" alt="F-35 Timeline Chart">
                <div class="click-hint">Click to Expand</div>
            </div>
        </article>

        <article class="chart-card">
            <div class="chart-info">
                <h2 class="chart-title">Aircraft Cost Per Flight Hour (2024 vs 2025)</h2>
                <p class="chart-desc">DoD Component User Rates analysis comparing YoY changes.</p>
            </div>
            <div class="chart-display" onclick="openLightbox('rcpfh-2025.png')">
                <img src="rcpfh-2025.png" alt="RCPFH Cost Analysis">
                <div class="click-hint">Click to Expand</div>
            </div>
        </article>

        <article class="chart-card">
            <div class="chart-info">
                <h2 class="chart-title">U.S. Navy LCS Deployments (2022-2025)</h2>
                <p class="chart-desc">Sustained deployment tracking for Independence and Freedom class variants.</p>
            </div>
            <div class="chart-display" onclick="openLightbox('lcs-deployments.jpeg')">
                <img src="lcs-deployments.jpeg" alt="LCS Deployment Timeline">
                <div class="click-hint">Click to Expand</div>
            </div>
        </article>

        <footer>
            &copy; 2025 StealthMetrics. All rights reserved.<br>
            Data sourced from official DoD reports and open-source analysis.
        </footer>
    </div>

    <script>
        function openLightbox(imageSrc) {
            const lightbox = document.getElementById('lightbox');
            const lightboxImg = document.getElementById('lightbox-img');
            lightboxImg.src = imageSrc;
            lightbox.style.display = 'flex';
        }
        function closeLightbox() {
            document.getElementById('lightbox').style.display = 'none';
        }
    </script>
</body>
</html>
