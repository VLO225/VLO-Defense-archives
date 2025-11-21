<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VLO225 | Defense Data Intelligence</title>
    <style>
        /* Global Styles - Warm & Formal Theme */
        :root {
            --bg-color: #f4f1ea; /* Warm "Paper" Beige */
            --card-bg: #ffffff;
            --text-primary: #2c2926; /* Warm Charcoal */
            --text-secondary: #595550;
            --accent: #8c3b2b; /* Muted Military Red */
            --border: #dcd6cc;
        }

        body {
            /* Georgia/Serif fonts are the standard for "Formal" analysis */
            font-family: Georgia, "Times New Roman", serif;
            background-color: var(--bg-color);
            color: var(--text-primary);
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        /* Layout Container */
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* Header Section */
        header {
            text-align: center;
            padding-bottom: 40px;
            border-bottom: 2px solid var(--accent);
            margin-bottom: 50px;
        }

        h1 {
            margin: 0;
            font-size: 2.8rem;
            letter-spacing: -0.5px;
            color: #1a1a1a;
        }

        .subtitle {
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif; /* Sans-serif contrast for subtitle */
            color: var(--text-secondary);
            text-transform: uppercase;
            letter-spacing: 1.5px;
            font-size: 0.85rem;
            margin-top: 15px;
            font-weight: 600;
        }

        /* Social Link - Button Style */
        .social-link {
            display: inline-block;
            margin-top: 20px;
            color: var(--text-primary);
            text-decoration: none;
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
            font-size: 0.8rem;
            border: 1px solid #b0aaa0;
            padding: 8px 16px;
            border-radius: 4px;
            transition: all 0.2s ease;
        }

        .social-link:hover {
            background-color: #e6e2d8;
            border-color: var(--text-primary);
        }

        /* Chart Cards */
        .chart-card {
            background-color: var(--card-bg);
            border: 1px solid var(--border);
            margin-bottom: 60px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05); /* Very subtle shadow */
        }

        .chart-info {
            padding: 30px 30px 20px 30px;
            border-bottom: 1px solid var(--bg-color);
        }

        .chart-title {
            font-size: 1.4rem;
            margin: 0 0 10px 0;
        }

        .chart-desc {
            color: var(--text-secondary);
            font-size: 1rem;
            margin: 0;
            font-style: italic;
        }

        /* Image Handling - Thumbnail Style */
        .chart-display {
            padding: 20px;
            background-color: #faf9f7;
            text-align: center;
            cursor: pointer; /* Shows hand icon on hover */
        }

        .chart-display img {
            max-width: 100%;
            max-height: 350px; /* Keeps charts relatively small */
            width: auto;
            display: inline-block;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: transform 0.2s ease;
        }

        .chart-display:hover img {
            transform: scale(1.02); /* Subtle zoom on hover */
        }
        
        .click-hint {
            font-family: "Helvetica Neue", sans-serif;
            font-size: 0.7rem;
            color: #999;
            margin-top: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Lightbox (The Full Screen Viewer) */
        #lightbox {
            display: none; /* Hidden by default */
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(20, 20, 20, 0.95); /* Dark background when open */
            align-items: center;
            justify-content: center;
            cursor: zoom-out;
        }

        #lightbox img {
            max-width: 95%;
            max-height: 95%;
            box-shadow: 0 0 20px rgba(0,0,0,0.5);
        }

        /* Footer */
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
            <h1>VLO225 ARCHIVES</h1>
            <div class="subtitle">Defense Analysis • Program Tracking • OSINT</div>
            <a href="https://x.com/VLO225" class="social-link">Connect on X</a>
        </header>

        <article class="chart-card">
            <div class="chart-info">
                <h2 class="chart-title">F-35 Program Timeline & Delivery Schedule</h2>
                <p class="chart-desc">Comprehensive breakdown of Software Blocks, Hardware Generations (TR-1/2/3), and Production Lots.</p>
            </div>
            <div class="chart-display" onclick="openLightbox('f35.png')">
                <img src="f35.png" alt="F-35 Timeline Chart">
                <div class="click-hint">Click to Expand</div>
            </div>
        </article>

        <article class="chart-card">
            <div class="chart-info">
                <h2 class="chart-title">Aircraft Cost Per Flight Hour (2024 vs 2025)</h2>
                <p class="chart-desc">DoD Component User Rates analysis. Highlights include F-35C and F-15EX cost deltas.</p>
            </div>
            <div class="chart-display" onclick="openLightbox('rcpfh.png')">
                <img src="rcpfh.png" alt="RCPFH Cost Analysis">
                <div class="click-hint">Click to Expand</div>
            </div>
        </article>

        <article class="chart-card">
            <div class="chart-info">
                <h2 class="chart-title">U.S. Navy LCS Deployments (2022-2025)</h2>
                <p class="chart-desc">Sustained deployment tracking for Independence and Freedom class variants.</p>
            </div>
            <div class="chart-display" onclick="openLightbox('lcs.jpeg')">
                 <img src="lcs.jpeg" alt="LCS Deployment Timeline">
                <div class="click-hint">Click to Expand</div>
            </div>
        </article>

        <footer>
            &copy; 2025 VLO225. All rights reserved.<br>
            Data sourced from official DoD reports and open source analysis.
        </footer>
    </div>

    <script>
        // Simple Javascript to handle the click-to-expand feature
        function openLightbox(imageSrc) {
            const lightbox = document.getElementById('lightbox');
            const lightboxImg = document.getElementById('lightbox-img');
            
            lightboxImg.src = imageSrc; // Set the image
            lightbox.style.display = 'flex'; // Show the overlay
        }

        function closeLightbox() {
            document.getElementById('lightbox').style.display = 'none';
        }
    </script>

</body>
</html>
