<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Landing Page Template</title>
    
    <!-- Google Fonts Preconnect & 25 Preset Import -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Anton&family=Bebas+Neue&family=Comfortaa:wght@400;700&family=Cormorant+Garamond:ital,wght@0,400;0,700;1,400&family=Fira+Code:wght@400;600&family=Fredoka:wght@400;600&family=Inter:wght@400;600;800&family=JetBrains+Mono:wght@400;700&family=Lora:ital,wght@0,400;0,600;1,400&family=Merriweather:ital,wght@0,400;0,700;1,400&family=Montserrat:wght@400;600;800&family=Nunito:wght@400;600;800&family=Open+Sans:wght@400;600;700&family=Oswald:wght@500;700&family=Outfit:wght@400;600;800&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Poppins:wght@400;600;800&family=Quicksand:wght@400;600;700&family=Righteous&family=Roboto:wght@400;500;700&family=Source+Code+Pro:wght@400;700&family=Space+Mono:wght@400;700&family=Syne:wght@600;800&display=swap" rel="stylesheet">

    <style>
        :root {
            --primary-color: #4A90E2;
            --bg-color: #ffffff;
            --text-color: #333333;
            --card-bg: #f8f9fa;
            --border-radius: 8px;
            --font-family: 'Inter', sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: var(--font-family);
            transition: background-color 0.3s, color 0.3s;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 8%;
            border-bottom: 1px solid rgba(0,0,0,0.08);
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-text {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--primary-color);
        }

        .signature-img {
            max-height: 40px;
            display: none;
        }

        nav a {
            margin-left: 2rem;
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
        }

        .hero {
            padding: 5rem 8%;
            text-align: center;
            max-width: 900px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.25rem;
            margin-bottom: 2rem;
            opacity: 0.85;
        }

        .btn {
            display: inline-block;
            background-color: var(--primary-color);
            color: #ffffff;
            padding: 0.9rem 2.2rem;
            border-radius: var(--border-radius);
            text-decoration: none;
            font-weight: 600;
        }

        .features {
            padding: 4rem 8%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .card {
            background-color: var(--card-bg);
            padding: 2.5rem;
            border-radius: var(--border-radius);
            border: 1px solid rgba(0,0,0,0.05);
        }

        .card h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
        }

        footer {
            text-align: center;
            padding: 2rem;
            border-top: 1px solid rgba(0,0,0,0.08);
            margin-top: 4rem;
            font-size: 0.95rem;
        }

        /* Customizer Panel Styling */
        #customizer-panel {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #ffffff;
            color: #222;
            padding: 1.2rem;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.25);
            z-index: 1000;
            width: 320px;
            max-height: 85vh;
            overflow-y: auto;
            font-family: Arial, sans-serif;
            font-size: 13px;
        }

        #customizer-panel h3 {
            margin-bottom: 0.8rem;
            font-size: 1rem;
            color: #111;
        }

        .control-group {
            margin-bottom: 0.8rem;
        }

        .control-group label {
            display: block;
            margin-bottom: 0.2rem;
            font-weight: bold;
        }

        .control-group input, .control-group select {
            width: 100%;
            padding: 0.4rem;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        canvas#sigCanvas {
            border: 1px dashed #aaa;
            background: #fff;
            border-radius: 5px;
            cursor: crosshair;
        }

        .btn-sm {
            padding: 0.3rem 0.6rem;
            font-size: 11px;
            cursor: pointer;
            border: none;
            border-radius: 4px;
            background: #4A90E2;
            color: white;
            margin-top: 4px;
        }

        .btn-clear {
            background: #e74c3c;
        }
    </style>
</head>
<body>

    <header>
        <div class="logo-container">
            <span class="logo-text" id="headerLogoText">BrandName</span>
            <img id="headerSigImg" class="signature-img" alt="Signature Logo">
        </div>
        <nav>
            <a href="#services">Services</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <section class="hero">
        <h1 id="heroTitle">Transform Your Online Presence</h1>
        <p>A modern, high-converting one-page website tailored to your brand identity.</p>
        <a href="#contact" class="btn">Get Started Today</a>
        <div style="margin-top: 1.5rem;">
            <img id="heroSigImg" class="signature-img" style="max-height: 60px;" alt="Signature Emblem">
        </div>
    </section>

    <section id="services" class="features">
        <div class="card">
            <h3>Modern Design</h3>
            <p>Clean layout tailored for high engagement and readability.</p>
        </div>
        <div class="card">
            <h3>Fully Responsive</h3>
            <p>Adapts seamlessly across mobile, tablet, and desktop screens.</p>
        </div>
        <div class="card">
            <h3>Live Editor</h3>
            <p>Modify fonts, colors, signatures, and footer copyright details in real time.</p>
        </div>
    </section>

    <footer>
        <p id="footerDisplay"><span id="footSym">©</span> <span id="footYear">2026</span> <span id="footOwner">BrandName</span>. <span id="footRights">All rights reserved.</span></p>
    </footer>

    <!-- Theme Customizer Drawer -->
    <div id="customizer-panel">
        <h3>🎨 Theme & Design Editor</h3>

        <!-- Font Selector -->
        <div class="control-group">
            <label for="fontSelect">Select Font Preset</label>
            <select id="fontSelect" onchange="updateFont(this.value)">
                <optgroup label="Modern Sans-Serif">
                    <option value="'Inter', sans-serif">Inter</option>
                    <option value="'Roboto', sans-serif">Roboto</option>
                    <option value="'Open Sans', sans-serif">Open Sans</option>
                    <option value="'Montserrat', sans-serif">Montserrat</option>
                    <option value="'Poppins', sans-serif">Poppins</option>
                </optgroup>
                <optgroup label="Elegant Serif">
                    <option value="'Playfair Display', serif">Playfair Display</option>
                    <option value="'Merriweather', serif">Merriweather</option>
                    <option value="'Lora', serif">Lora</option>
                    <option value="'Cinzel', serif">Cinzel</option>
                    <option value="'Cormorant Garamond', serif">Cormorant Garamond</option>
                </optgroup>
                <optgroup label="Friendly & Soft">
                    <option value="'Nunito', sans-serif">Nunito</option>
                    <option value="'Quicksand', sans-serif">Quicksand</option>
                    <option value="'Outfit', sans-serif">Outfit</option>
                    <option value="'Fredoka', sans-serif">Fredoka</option>
                    <option value="'Comfortaa', cursive">Comfortaa</option>
                </optgroup>
                <optgroup label="Tech & Monospace">
                    <option value="'Fira Code', monospace">Fira Code</option>
                    <option value="'JetBrains Mono', monospace">JetBrains Mono</option>
                    <option value="'Space Mono', monospace">Space Mono</option>
                    <option value="'Source Code Pro', monospace">Source Code Pro</option>
                </optgroup>
                <optgroup label="Bold Display">
                    <option value="'Bebas Neue', sans-serif">Bebas Neue</option>
                    <option value="'Oswald', sans-serif">Oswald</option>
                    <option value="'Syne', sans-serif">Syne</option>
                    <option value="'Anton', sans-serif">Anton</option>
                    <option value="'Righteous', cursive">Righteous</option>
                </optgroup>
            </select>
        </div>

        <div class="control-group">
            <label for="customFontInput">Or Type Any Google Font Name</label>
            <input type="text" id="customFontInput" placeholder="e.g. Lobster" onchange="loadCustomGoogleFont(this.value)">
        </div>

        <!-- Color Controls -->
        <div class="control-group">
            <label>Primary Color</label>
            <input type="color" value="#4A90E2" oninput="updateColor('--primary-color', this.value)">
        </div>
        <div class="control-group">
            <label>Background Color</label>
            <input type="color" value="#ffffff" oninput="updateColor('--bg-color', this.value)">
        </div>
        <div class="control-group">
            <label>Text Color</label>
            <input type="color" value="#333333" oninput="updateColor('--text-color', this.value)">
        </div>

        <hr style="margin: 1rem 0; opacity: 0.3;">

        <!-- Signature Drawing Pad -->
        <h3>✍️ Signature / Logo Pad</h3>
        <canvas id="sigCanvas" width="280" height="100"></canvas>
        <div>
            <input type="color" id="penColor" value="#4A90E2" style="width: 40px; height: 25px; padding: 0;">
            <button class="btn-sm btn-clear" onclick="clearSignature()">Clear</button>
            <button class="btn-sm" onclick="applySignature()">Apply Signature</button>
        </div>

        <hr style="margin: 1rem 0; opacity: 0.3;">

        <!-- Footer & Copyright Editor -->
        <h3>📜 Footer & Copyright</h3>
        <div class="control-group">
            <label>Symbol</label>
            <select id="symbolSelect" onchange="document.getElementById('footSym').innerText = this.value">
                <option value="©">© (Copyright)</option>
                <option value="®">® (Registered)</option>
                <option value="™">™ (Trademark)</option>
                <option value="CC">CC (Creative Commons)</option>
            </select>
        </div>
        <div class="control-group">
            <label>Owner / Company Name</label>
            <input type="text" value="BrandName" oninput="document.getElementById('footOwner').innerText = this.value">
        </div>
        <div class="control-group">
            <label>Year</label>
            <input type="text" value="2026" oninput="document.getElementById('footYear').innerText = this.value">
        </div>
        <div class="control-group">
            <label>Rights / Disclaimer Line</label>
            <input type="text" value="All rights reserved." oninput="document.getElementById('footRights').innerText = this.value">
        </div>
    </div>

    <script>
        // Customizer color & font script
        function updateFont(val) { document.documentElement.style.setProperty('--font-family', val); }
        function updateColor(varName, val) { document.documentElement.style.setProperty(varName, val); }
        function loadCustomGoogleFont(fontName) {
            if (!fontName.trim()) return;
            const link = document.createElement('link');
            link.href = `https://fonts.googleapis.com/css2?family=${fontName.trim().replace(/\s+/g, '+')}:wght@400;600;700&display=swap`;
            link.rel = 'stylesheet';
            document.head.appendChild(link);
            document.documentElement.style.setProperty('--font-family', `'${fontName.trim()}', sans-serif`);
        }

        // Signature Canvas Functionality
        const canvas = document.getElementById('sigCanvas');
        const ctx = canvas.getContext('2d');
        let isDrawing = false;

        function getPos(e) {
            const rect = canvas.getBoundingClientRect();
            const clientX = e.touches ? e.touches[0].clientX : e.clientX;
            const clientY = e.touches ? e.touches[0].clientY : e.clientY;
            return { x: clientX - rect.left, y: clientY - rect.top };
        }

        function startDrawing(e) {
            isDrawing = true;
            const pos = getPos(e);
            ctx.beginPath();
            ctx.moveTo(pos.x, pos.y);
            ctx.strokeStyle = document.getElementById('penColor').value;
            ctx.lineWidth = 2;
            ctx.lineCap = 'round';
        }

        function draw(e) {
            if (!isDrawing) return;
            const pos = getPos(e);
            ctx.lineTo(pos.x, pos.y);
            ctx.stroke();
        }

        function stopDrawing() { isDrawing = false; }

        canvas.addEventListener('mousedown', startDrawing);
        canvas.addEventListener('mousemove', draw);
        canvas.addEventListener('mouseup', stopDrawing);
        canvas.addEventListener('touchstart', (e) => { startDrawing(e); e.preventDefault(); });
        canvas.addEventListener('touchmove', (e) => { draw(e); e.preventDefault(); });
        canvas.addEventListener('touchend', stopDrawing);

        function clearSignature() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
        }

        function applySignature() {
            const dataURL = canvas.toDataURL();
            const headImg = document.getElementById('headerSigImg');
            const heroImg = document.getElementById('heroSigImg');
            
            headImg.src = dataURL;
            heroImg.src = dataURL;
            headImg.style.display = 'inline-block';
            heroImg.style.display = 'inline-block';
        }
    </script>
</body>
</html>
