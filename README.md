<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MacroLoaderX - Automation Redefined</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
    
    <style>
        /* --- VARIABLES & RESET --- */
        :root {
            --bg: #030303;
            --surface: #0a0a0a;
            --surface-highlight: #121212;
            --border: #262626;
            --border-hover: #404040;
            --text-main: #ededed;
            --text-muted: #888;
            --primary: #ffffff;
            --font-sans: 'Inter', -apple-system, sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            background-color: var(--bg);
            color: var(--text-main);
            font-family: var(--font-sans);
            line-height: 1.6;
            overflow-x: hidden; /* Empêche le scroll horizontal */
            -webkit-font-smoothing: antialiased;
        }

        a { text-decoration: none; color: inherit; transition: 0.2s; }
        ul { list-style: none; }

        /* --- UTILS --- */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 24px;
        }

        .badge {
            display: inline-flex;
            align-items: center;
            padding: 4px 12px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid var(--border);
            border-radius: 99px;
            font-size: 12px;
            font-weight: 500;
            color: var(--text-muted);
            margin-bottom: 24px;
            backdrop-filter: blur(5px);
        }

        .gradient-text {
            background: linear-gradient(to bottom right, #fff 30%, #666 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* --- BACKGROUND FX --- */
        .glow-bg {
            position: fixed;
            top: -300px;
            left: 50%;
            transform: translateX(-50%);
            width: 100vw;
            height: 800px;
            background: radial-gradient(circle, rgba(255,255,255,0.06) 0%, rgba(0,0,0,0) 60%);
            z-index: -1;
            pointer-events: none;
        }

        /* --- NAV --- */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 16px 0;
            backdrop-filter: blur(12px);
            background: rgba(3,3,3,0.7);
            border-bottom: 1px solid rgba(255,255,255,0.05);
            z-index: 100;
        }

        .nav-content { display: flex; justify-content: space-between; align-items: center; }
        .logo { font-weight: 600; font-size: 16px; display: flex; align-items: center; gap: 10px; }
        .logo img { width: 24px; height: 24px; border-radius: 4px; }
        .nav-links { display: flex; gap: 28px; font-size: 13px; color: var(--text-muted); }
        .nav-links a:hover { color: var(--text-main); }
        .btn-sm { padding: 6px 14px; background: var(--primary); color: #000; border-radius: 6px; font-size: 12px; font-weight: 600; }

        /* --- HERO --- */
        header { padding: 160px 0 80px; text-align: center; }
        h1 { font-size: 56px; font-weight: 600; letter-spacing: -2px; line-height: 1.1; margin-bottom: 20px; }
        .subtitle { font-size: 17px; color: var(--text-muted); max-width: 550px; margin: 0 auto 40px; }

        .cta-group { display: flex; justify-content: center; gap: 12px; }
        .btn-primary { padding: 12px 28px; background: var(--primary); color: #000; border-radius: 8px; font-weight: 600; font-size: 14px; }
        .btn-primary:hover { opacity: 0.9; }
        .btn-secondary { padding: 12px 28px; background: rgba(255,255,255,0.03); color: #fff; border-radius: 8px; font-weight: 500; font-size: 14px; border: 1px solid var(--border); }
        .btn-secondary:hover { border-color: var(--border-hover); background: rgba(255,255,255,0.06); }

        /* --- MARQUEE (New Feature 1) --- */
        .marquee-container {
            width: 100%;
            overflow: hidden;
            padding: 40px 0;
            border-top: 1px solid var(--border);
            border-bottom: 1px solid var(--border);
            background: rgba(255,255,255,0.01);
            position: relative;
        }
        
        /* Fade effect on sides */
        .marquee-container::before, .marquee-container::after {
            content: "";
            position: absolute;
            top: 0; width: 150px; height: 100%;
            z-index: 2;
        }
        .marquee-container::before { left: 0; background: linear-gradient(to right, var(--bg), transparent); }
        .marquee-container::after { right: 0; background: linear-gradient(to left, var(--bg), transparent); }

        .marquee-track {
            display: flex;
            gap: 40px;
            width: max-content;
            animation: scroll 30s linear infinite;
        }

        .game-tag {
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--text-muted);
            font-size: 13px;
            font-weight: 500;
        }
        .game-dot { width: 6px; height: 6px; background: #333; border-radius: 50%; }

        @keyframes scroll {
            0% { transform: translateX(0); }
            100% { transform: translateX(calc(-50% - 20px)); }
        }

        /* --- FEATURES --- */
        .features { padding: 100px 0; }
        .section-header { margin-bottom: 60px; }
        .section-header h2 { font-size: 28px; font-weight: 600; letter-spacing: -0.5px; margin-bottom: 10px; }
        .section-header p { color: var(--text-muted); font-size: 15px; }

        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; }
        .card {
            background: var(--surface);
            border: 1px solid var(--border);
            padding: 28px;
            border-radius: 10px;
            transition: 0.3s;
        }
        .card:hover { border-color: var(--border-hover); box-shadow: 0 10px 30px -10px rgba(0,0,0,0.5); }
        .card-icon { width: 36px; height: 36px; background: #1a1a1a; border-radius: 6px; display: flex; align-items: center; justify-content: center; margin-bottom: 16px; font-size: 16px; border: 1px solid var(--border); }
        .card h3 { font-size: 16px; margin-bottom: 8px; font-weight: 500; color: #fff; }
        .card p { font-size: 13px; color: var(--text-muted); line-height: 1.6; }

        /* --- CODE PREVIEW --- */
        .preview-section { padding: 80px 0; border-top: 1px solid var(--border); background: linear-gradient(180deg, var(--bg), #050505); }
        .terminal-window {
            background: #090909; border: 1px solid var(--border); border-radius: 10px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.6); max-width: 700px; margin: 0 auto;
        }
        .terminal-header { padding: 10px 14px; border-bottom: 1px solid var(--border); display: flex; gap: 6px; }
        .dot { width: 10px; height: 10px; border-radius: 50%; background: #333; }
        .terminal-body { padding: 20px; font-family: var(--font-mono); font-size: 12px; color: #a0a0a0; line-height: 1.5; }
        .c-kw { color: #569cd6; } .c-fn { color: #dcdcaa; } .c-str { color: #ce9178; } .c-num { color: #b5cea8; }

        /* --- FAQ (New Feature 2) --- */
        .faq-section { padding: 100px 0; border-top: 1px solid var(--border); }
        .faq-grid { max-width: 700px; margin: 0 auto; display: flex; flex-direction: column; gap: 12px; }
        
        details {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 8px;
            overflow: hidden;
            transition: 0.3s;
        }
        details:hover { border-color: var(--border-hover); }
        details[open] { background: var(--surface-highlight); }
        
        summary {
            padding: 16px 20px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 500;
            list-style: none;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        summary::-webkit-details-marker { display: none; }
        summary::after { content: "+"; font-size: 16px; color: var(--text-muted); font-weight: 300; }
        details[open] summary::after { content: "-"; }
        
        .faq-content { padding: 0 20px 20px; font-size: 13px; color: var(--text-muted); line-height: 1.6; animation: slideDown 0.2s ease-out; }
        @keyframes slideDown { from { opacity: 0; transform: translateY(-5px); } to { opacity: 1; transform: translateY(0); } }

        /* --- DOWNLOAD --- */
        .download-box {
            text-align: center; margin: 80px auto 40px; padding: 40px;
            background: radial-gradient(circle at center, rgba(255,255,255,0.03), transparent 70%);
            border: 1px solid var(--border); border-radius: 12px; max-width: 500px;
        }

        /* --- FOOTER --- */
        footer { border-top: 1px solid var(--border); padding: 40px 0; font-size: 12px; color: #555; text-align: center; }
        .status-dot { display: inline-block; width: 6px; height: 6px; background: #0f0; border-radius: 50%; box-shadow: 0 0 8px #0f0; margin-right: 6px; }

        /* Animation class */
        .fade-in { opacity: 0; transform: translateY(15px); transition: 0.6s ease-out; }
        .visible { opacity: 1; transform: translateY(0); }

    </style>
</head>
<body>

    <div class="glow-bg"></div>

    <nav>
        <div class="container nav-content">
            <a href="#" class="logo">
                <img src="https://files.catbox.moe/qz6o4n.jpg" alt="MX">
                MacroLoaderX
            </a>
            <div class="nav-links">
                <a href="#features">Features</a>
                <a href="#faq">Questions</a>
                <a href="https://discord.gg/macroloaderx" target="_blank">Discord</a>
            </div>
            <a href="#download" class="btn-sm">Télécharger</a>
        </div>
    </nav>

    <header class="container fade-in">
        <div class="badge">Version 2.4.0 Live</div>
        <h1>L'automatisation Roblox <br><span class="gradient-text">simplifiée.</span></h1>
        <p class="subtitle">Automatisez vos actions répétitives sans injecteur. 100% externe, sûr, et conçu pour la performance.</p>
        <div class="cta-group">
            <a href="#download" class="btn-primary">Télécharger Gratuitement</a>
            <a href="https://github.com/n0lex9999/MacroLoaderX" target="_blank" class="btn-secondary">Voir sur GitHub</a>
        </div>
    </header>

    <div class="marquee-container fade-in">
        <div class="marquee-track">
            <div class="game-tag"><div class="game-dot"></div>Blox Fruits</div>
            <div class="game-tag"><div class="game-dot"></div>Pet Simulator 99</div>
            <div class="game-tag"><div class="game-dot"></div>Da Hood</div>
            <div class="game-tag"><div class="game-dot"></div>Adopt Me</div>
            <div class="game-tag"><div class="game-dot"></div>Anime Defenders</div>
            <div class="game-tag"><div class="game-dot"></div>Brookhaven</div>
            <div class="game-tag"><div class="game-dot"></div>BedWars</div>
            <div class="game-tag"><div class="game-dot"></div>Blade Ball</div>
            <div class="game-tag"><div class="game-dot"></div>Blox Fruits</div>
            <div class="game-tag"><div class="game-dot"></div>Pet Simulator 99</div>
            <div class="game-tag"><div class="game-dot"></div>Da Hood</div>
            <div class="game-tag"><div class="game-dot"></div>Adopt Me</div>
            <div class="game-tag"><div class="game-dot"></div>Anime Defenders</div>
            <div class="game-tag"><div class="game-dot"></div>Brookhaven</div>
            <div class="game-tag"><div class="game-dot"></div>BedWars</div>
            <div class="game-tag"><div class="game-dot"></div>Blade Ball</div>
        </div>
    </div>

    <section id="features" class="container features fade-in">
        <div class="section-header">
            <h2>L'avantage technologique</h2>
            <p>Pourquoi utiliser MacroLoaderX plutôt qu'un autoclicker basique.</p>
        </div>
        <div class="grid">
            <div class="card">
                <div class="card-icon">🔒</div>
                <h3>100% Externe</h3>
                <p>Contrairement aux executeurs, MacroLoaderX n'injecte rien dans Roblox. Il simule simplement votre clavier et souris.</p>
            </div>
            <div class="card">
                <div class="card-icon">⚡</div>
                <h3>Moteur Lua Léger</h3>
                <p>Pas de bloatware. Un moteur d'exécution optimisé qui utilise moins de 1% de votre CPU en arrière-plan.</p>
            </div>
            <div class="card">
                <div class="card-icon">📂</div>
                <h3>Bibliothèque Cloud</h3>
                <p>Téléchargez des macros créées par la communauté directement depuis l'interface. Plus de 300 scripts disponibles.</p>
            </div>
        </div>
    </section>

    <section class="preview-section fade-in">
        <div class="container">
            <div class="section-header" style="text-align: center;">
                <h2>Codez ou importez</h2>
                <p>Compatible avec la syntaxe Lua standard.</p>
            </div>
            <div class="terminal-window">
                <div class="terminal-header">
                    <div class="dot" style="background:#ff5f56"></div>
                    <div class="dot" style="background:#ffbd2e"></div>
                    <div class="dot" style="background:#27c93f"></div>
                </div>
                <div class="terminal-body">
                    <span class="c-kw">local</span> Player = game.Players.LocalPlayer<br>
                    <span class="c-kw">local</span> Toggle = <span class="c-kw">true</span><br><br>
                    <span class="c-kw">while</span> Toggle <span class="c-kw">do</span><br>
                    &nbsp;&nbsp;<span class="c-kw">if</span> Player.Character <span class="c-kw">then</span><br>
                    &nbsp;&nbsp;&nbsp;&nbsp;input.press(<span class="c-str">"Space"</span>)<br>
                    &nbsp;&nbsp;&nbsp;&nbsp;print(<span class="c-str">"Auto-Jump exécuté"</span>)<br>
                    &nbsp;&nbsp;<span class="c-kw">end</span><br>
                    &nbsp;&nbsp;wait(<span class="c-num">2.5</span>)<br>
                    <span class="c-kw">end</span>
                </div>
            </div>
        </div>
    </section>

    <section id="faq" class="container faq-section fade-in">
        <div class="section-header" style="text-align:center">
            <h2>Questions fréquentes</h2>
        </div>
        <div class="faq-grid">
            <details>
                <summary>Est-ce que je peux être banni ?</summary>
                <div class="faq-content">Le risque est minime car MacroLoaderX n'injecte aucun code dans le jeu (contrairement à Synapse ou Krnl). Il agit comme un clavier virtuel. Cependant, utilisez-le avec bon sens.</div>
            </details>
            <details>
                <summary>Comment charger un script ?</summary>
                <div class="faq-content">Ouvrez le logiciel, cliquez sur "Load File" et sélectionnez votre fichier .lua. Vous pouvez aussi coller le code directement dans l'éditeur.</div>
            </details>
            <details>
                <summary>Est-ce compatible Windows 11 ?</summary>
                <div class="faq-content">Oui, le logiciel est optimisé pour Windows 10 et Windows 11. Une version MacOS est prévue pour 2027.</div>
            </details>
        </div>
    </section>

    <section id="download" class="container fade-in">
        <div class="download-box">
            <h2>Commencer maintenant</h2>
            <p style="color: var(--text-muted); margin: 10px 0 25px; font-size:14px;">Rejoignez les utilisateurs intelligents.</p>
            <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/download/MacroLoaderX.zip" class="btn-primary">Télécharger v2.4.0</a>
        </div>
    </section>
    
    <section id="download" class="container fade-in">
        <div class="download-box">
            <h2>Commencer maintenant</h2>
            <p style="color: var(--text-muted); margin: 15px 0 45px; font-size:14px;">Rejoignez les utilisateurs intelligents.</p>
            <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/macroloader/MacroLoaderX.apk" class="btn-primary">Télécharger v2.4.0</a>
        </div>
    </section>

    <footer class="container">
        <p>&copy; 2026 MacroLoaderX. <span style="opacity:0.3">|</span> <span class="status-dot"></span>Tous les systèmes opérationnels</p>
    </footer>

    <script>
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
    </script>

</body>
</html>
