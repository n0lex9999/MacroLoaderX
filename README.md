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
            --surface-highlight: #141414;
            --border: #222;
            --border-hover: #444;
            --text-main: #ededed;
            --text-muted: #888;
            --primary: #ffffff;
            --accent-glow: rgba(255, 255, 255, 0.15);
            --font-sans: 'Inter', -apple-system, sans-serif;
            --font-mono: 'JetBrains Mono', monospace;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            background-color: var(--bg);
            color: var(--text-main);
            font-family: var(--font-sans);
            line-height: 1.6;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }

        a { text-decoration: none; color: inherit; transition: 0.2s; }
        ul { list-style: none; }

        /* --- UTILS --- */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        .badge {
            display: inline-flex;
            align-items: center;
            padding: 4px 12px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--border);
            border-radius: 99px;
            font-size: 12px;
            font-weight: 500;
            color: var(--text-muted);
            margin-bottom: 24px;
        }

        .gradient-text {
            background: linear-gradient(to right, #fff, #888);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* --- BACKGROUND FX --- */
        .glow-bg {
            position: fixed;
            top: -20%;
            left: 50%;
            transform: translateX(-50%);
            width: 1000px;
            height: 600px;
            background: radial-gradient(circle, rgba(255,255,255,0.08) 0%, rgba(0,0,0,0) 70%);
            z-index: -1;
            pointer-events: none;
        }

        /* --- NAV --- */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 0;
            backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(255,255,255,0.03);
            z-index: 100;
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo { font-weight: 600; font-size: 18px; letter-spacing: -0.5px; display: flex; align-items: center; gap: 10px; }
        .logo img { width: 24px; height: 24px; border-radius: 6px; }

        .nav-links { display: flex; gap: 32px; font-size: 14px; color: var(--text-muted); }
        .nav-links a:hover { color: var(--text-main); }

        .btn-sm {
            padding: 8px 16px;
            background: var(--primary);
            color: #000;
            border-radius: 6px;
            font-size: 13px;
            font-weight: 600;
        }
        .btn-sm:hover { opacity: 0.9; }

        /* --- HERO --- */
        header {
            padding: 180px 0 100px;
            text-align: center;
            position: relative;
        }

        h1 {
            font-size: 64px;
            font-weight: 600;
            letter-spacing: -2px;
            line-height: 1.1;
            margin-bottom: 24px;
        }

        .subtitle {
            font-size: 18px;
            color: var(--text-muted);
            max-width: 600px;
            margin: 0 auto 48px;
            font-weight: 400;
        }

        .cta-group {
            display: flex;
            justify-content: center;
            gap: 16px;
        }

        .btn-primary {
            padding: 14px 32px;
            background: var(--primary);
            color: #000;
            border-radius: 8px;
            font-weight: 600;
            font-size: 15px;
            border: 1px solid var(--primary);
        }

        .btn-secondary {
            padding: 14px 32px;
            background: rgba(255,255,255,0.05);
            color: #fff;
            border-radius: 8px;
            font-weight: 500;
            font-size: 15px;
            border: 1px solid var(--border);
        }
        .btn-secondary:hover { background: rgba(255,255,255,0.1); border-color: var(--border-hover); }

        /* --- STATS / SOCIAL --- */
        .stats-bar {
            display: flex;
            justify-content: center;
            gap: 24px;
            margin-top: 60px;
            opacity: 0.6;
            filter: grayscale(1);
            transition: 0.3s;
        }
        .stats-bar:hover { filter: grayscale(0); opacity: 1; }

        /* --- FEATURES GRID --- */
        .features { padding: 100px 0; border-top: 1px solid var(--border); }
        .section-header { margin-bottom: 60px; }
        .section-header h2 { font-size: 32px; font-weight: 600; letter-spacing: -1px; margin-bottom: 12px; }
        .section-header p { color: var(--text-muted); }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 24px;
        }

        .card {
            background: var(--surface);
            border: 1px solid var(--border);
            padding: 32px;
            border-radius: 12px;
            transition: transform 0.3s, border-color 0.3s;
        }

        .card:hover {
            border-color: var(--border-hover);
            transform: translateY(-2px);
        }

        .card-icon {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.05);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            font-size: 18px;
        }

        .card h3 { font-size: 18px; margin-bottom: 10px; font-weight: 500; }
        .card p { font-size: 14px; color: var(--text-muted); line-height: 1.6; }

        /* --- CODE PREVIEW (TERMINAL) --- */
        .preview-section {
            padding: 80px 0;
            background: linear-gradient(180deg, var(--bg) 0%, #080808 100%);
            border-top: 1px solid var(--border);
        }

        .terminal-window {
            background: #0d0d0d;
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 40px 80px rgba(0,0,0,0.5);
            max-width: 800px;
            margin: 0 auto;
        }

        .terminal-header {
            background: rgba(255,255,255,0.03);
            padding: 12px 16px;
            display: flex;
            gap: 8px;
            border-bottom: 1px solid var(--border);
        }

        .dot { width: 10px; height: 10px; border-radius: 50%; }
        .red { background: #ff5f56; }
        .yellow { background: #ffbd2e; }
        .green { background: #27c93f; }

        .terminal-body {
            padding: 24px;
            font-family: var(--font-mono);
            font-size: 13px;
            color: #a9b7c6;
            overflow-x: auto;
        }

        .code-keyword { color: #cc7832; }
        .code-func { color: #ffc66d; }
        .code-str { color: #6a8759; }
        .code-bool { color: #9876aa; }

        /* --- DOWNLOAD --- */
        .download-box {
            background: rgba(255,255,255,0.02);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 48px;
            text-align: center;
            margin: 100px auto;
            max-width: 600px;
        }

        .meta-info {
            display: flex;
            justify-content: center;
            gap: 24px;
            margin-top: 24px;
            font-size: 12px;
            color: var(--text-muted);
            font-family: var(--font-mono);
        }

        .virus-check { color: #27c93f; display: flex; align-items: center; gap: 6px; }

        /* --- FOOTER --- */
        footer {
            border-top: 1px solid var(--border);
            padding: 60px 0;
            text-align: center;
            color: var(--text-muted);
            font-size: 13px;
        }
        
        /* --- ANIMATIONS --- */
        .fade-in { opacity: 0; transform: translateY(20px); transition: 0.8s ease-out; }
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
                <a href="#features">Fonctionnalités</a>
                <a href="#how-to">Guide</a>
                <a href="https://discord.gg/macroloaderx" target="_blank">Discord</a>
            </div>
            <a href="#download" class="btn-sm">Télécharger v2.4</a>
        </div>
    </nav>

    <header class="container fade-in">
        <div class="badge">Safe & External Automation</div>
        <h1>
            L'automatisation Roblox,<br>
            <span class="gradient-text">enfin moderne.</span>
        </h1>
        <p class="subtitle">
            Automatisez vos actions répétitives sans risque. MacroLoaderX simule les périphériques externes, ne touche pas à la mémoire du jeu et reste indétectable.
        </p>
        
        <div class="cta-group">
            <a href="#download" class="btn-primary">Télécharger Gratuitement</a>
            <a href="https://github.com/n0lex9999/MacroLoaderX" target="_blank" class="btn-secondary">GitHub</a>
        </div>

        <div class="stats-bar">
            <img src="https://img.shields.io/github/stars/MacroLoaderX/MacroLoaderX?style=social&color=000" alt="Stars">
            <img src="https://img.shields.io/github/v/release/MacroLoaderX/MacroLoaderX?color=333&label=Release&style=flat-square" alt="Version">
            <img src="https://img.shields.io/discord/123456789012345678?label=Discord&color=333&style=flat-square" alt="Discord">
        </div>
    </header>

    <section id="features" class="container features fade-in">
        <div class="section-header">
            <h2>Conçu pour la performance</h2>
            <p>Une suite d'outils complète dans une interface minimaliste.</p>
        </div>
        <div class="grid">
            <div class="card">
                <div class="card-icon">⚡</div>
                <h3>100% Externe</h3>
                <p>Contrairement aux executors, MacroLoaderX n'injecte rien dans Roblox. Il simule simplement votre clavier et souris.</p>
            </div>
            <div class="card">
                <div class="card-icon">📝</div>
                <h3>Scripting Lua</h3>
                <p>Écrivez vos propres macros en Lua ou importez des scripts existants. Flexibilité totale pour vos routines.</p>
            </div>
            <div class="card">
                <div class="card-icon">🌐</div>
                <h3>Communauté</h3>
                <p>Accédez à une bibliothèque de +300 macros vérifiées (farming, mouvements, anti-afk) prêtes à l'emploi.</p>
            </div>
            <div class="card">
                <div class="card-icon">👁️</div>
                <h3>Overlay Moderne</h3>
                <p>Une interface graphique claire qui fonctionne par-dessus vos jeux, même en mode plein écran fenêtré.</p>
            </div>
        </div>
    </section>

    <section class="preview-section fade-in">
        <div class="container">
            <div class="section-header" style="text-align: center;">
                <h2>Simplicité du code</h2>
                <p>Un moteur Lua puissant pour des tâches complexes.</p>
            </div>
            
            <div class="terminal-window">
                <div class="terminal-header">
                    <div class="dot red"></div>
                    <div class="dot yellow"></div>
                    <div class="dot green"></div>
                </div>
                <div class="terminal-body">
                    <span class="code-keyword">while</span> <span class="code-bool">true</span> <span class="code-keyword">do</span><br>
                    &nbsp;&nbsp;<span class="code-muted">-- Anti-AFK simple example</span><br>
                    &nbsp;&nbsp;<span class="code-keyword">local</span> player = game.Players.LocalPlayer<br>
                    &nbsp;&nbsp;player.Character.Humanoid.Jump = <span class="code-bool">true</span><br>
                    <br>
                    &nbsp;&nbsp;<span class="code-func">print</span>(<span class="code-str">"Saut effectué - "</span> .. os.time())<br>
                    &nbsp;&nbsp;<span class="code-func">wait</span>(2)<br>
                    <span class="code-keyword">end</span>
                </div>
            </div>
        </div>
    </section>

    <section id="download" class="container fade-in">
        <div class="download-box">
            <h2>Prêt à automatiser ?</h2>
            <p style="color: var(--text-muted); margin: 16px 0 32px;">Rejoignez des milliers de joueurs qui optimisent leur temps.</p>
            
            <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/untagged-e76d7861168038356685/MacroLoaderX.zip" class="btn-primary">
                Télécharger pour Windows
            </a>

            <div class="meta-info">
                <span>v2.4.0</span>
                <span>•</span>
                <span>Win 10/11</span>
                <span>•</span>
                <span class="virus-check">🛡️ 0/72 VirusTotal</span>
            </div>
        </div>
    </section>

    <footer class="container">
        <p>&copy; 2026 MacroLoaderX. Non affilié à Roblox Corporation.</p>
        <p style="margin-top: 8px; opacity: 0.5;">Fait avec soin pour la communauté.</p>
    </footer>

    <script>
        // Simple scroll reveal effect
        const observerOptions = {
            threshold: 0.1
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });
    </script>

</body>
</html>
