<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MacroLoaderX - L'outil macro ultime pour Roblox</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .navbar {
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 2px solid rgba(255, 255, 255, 0.1);
        }

        .nav-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 40px;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            background: linear-gradient(45deg, #fff, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            padding: 8px 16px;
            border-radius: 20px;
        }

        .nav-links a:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
        }

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 120px 40px 60px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            border-radius: 50%;
            top: -200px;
            right: -200px;
            animation: float 6s ease-in-out infinite;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(255,255,255,0.08) 0%, transparent 70%);
            border-radius: 50%;
            bottom: -150px;
            left: -150px;
            animation: float 8s ease-in-out infinite reverse;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-30px); }
        }

        .hero-content {
            max-width: 900px;
            z-index: 1;
        }

        .hero-logo {
            width: 180px;
            height: 180px;
            margin: 0 auto 30px;
            border-radius: 30px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            animation: pulse 3s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        h1 {
            font-size: 56px;
            margin-bottom: 20px;
            text-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
            line-height: 1.2;
        }

        .subtitle {
            font-size: 24px;
            margin-bottom: 40px;
            opacity: 0.9;
            font-weight: 300;
        }

        .badges {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 40px;
        }

        .badge {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            padding: 10px 20px;
            border-radius: 25px;
            font-size: 14px;
            font-weight: 600;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 18px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 18px;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background: linear-gradient(45deg, #ffd700, #ff6b6b);
            color: #000;
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.6);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.2);
            color: #fff;
            border: 2px solid rgba(255, 255, 255, 0.5);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);
        }

        .section {
            padding: 100px 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 42px;
            text-align: center;
            margin-bottom: 60px;
            position: relative;
            padding-bottom: 20px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #ffd700, #ff6b6b);
            border-radius: 2px;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .feature-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 40px;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.15);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
        }

        .feature-icon {
            font-size: 48px;
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 24px;
            margin-bottom: 15px;
        }

        .feature-card p {
            opacity: 0.9;
            line-height: 1.6;
        }

        .screenshots {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .screenshot-card {
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
            transition: all 0.3s;
        }

        .screenshot-card:hover {
            transform: scale(1.05);
        }

        .screenshot-card img {
            width: 100%;
            height: auto;
            display: block;
        }

        .screenshot-caption {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            text-align: center;
            font-weight: 600;
        }

        .download-section {
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            padding: 80px 40px;
            text-align: center;
            border-radius: 30px;
            margin: 60px 40px;
        }

        .version-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            max-width: 800px;
            margin: 40px auto;
        }

        .info-box {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .info-box strong {
            display: block;
            margin-bottom: 8px;
            color: #ffd700;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .stat-card {
            text-align: center;
            padding: 30px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .stat-number {
            font-size: 48px;
            font-weight: bold;
            background: linear-gradient(45deg, #ffd700, #ff6b6b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }

        .stat-label {
            opacity: 0.9;
            font-size: 18px;
        }

        .footer {
            background: rgba(0, 0, 0, 0.3);
            padding: 40px;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .social-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-bottom: 20px;
        }

        .social-links a {
            width: 50px;
            height: 50px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            font-size: 24px;
            transition: all 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .social-links a:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
        }

        @media (max-width: 768px) {
            h1 { font-size: 36px; }
            .subtitle { font-size: 18px; }
            .section-title { font-size: 32px; }
            .features, .screenshots { grid-template-columns: 1fr; }
            .nav-links { display: none; }
        }

        .code-example {
            background: rgba(0, 0, 0, 0.4);
            padding: 25px;
            border-radius: 15px;
            margin: 20px 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
            text-align: left;
            font-family: 'Courier New', monospace;
            overflow-x: auto;
        }

        .code-example pre {
            margin: 0;
            color: #7dd3fc;
            line-height: 1.6;
        }

        .warning {
            background: rgba(255, 165, 0, 0.2);
            border-left: 4px solid #ffa500;
            padding: 20px;
            border-radius: 10px;
            margin: 40px 0;
        }

        .warning-title {
            font-weight: bold;
            margin-bottom: 10px;
            color: #ffd700;
        }

        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
            40% { transform: translateX(-50%) translateY(-20px); }
            60% { transform: translateX(-50%) translateY(-10px); }
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="nav-content">
            <div class="logo">
                🎮 MacroLoaderX
            </div>
            <ul class="nav-links">
                <li><a href="#features">Fonctionnalités</a></li>
                <li><a href="#screenshots">Aperçu</a></li>
                <li><a href="#download">Télécharger</a></li>
                <li><a href="#support">Support</a></li>
            </ul>
        </div>
    </nav>

    <section class="hero">
        <div class="hero-content">
            <img src="https://files.catbox.moe/qz6o4n.jpg" alt="MacroLoaderX Logo" class="hero-logo">
            <h1>MacroLoaderX</h1>
            <p class="subtitle">L'outil macro le plus complet et facile à utiliser pour Roblox en 2026</p>
            
            <div class="badges">
                <span class="badge">✨ Interface Moderne</span>
                <span class="badge">🚀 Ultra Performant</span>
                <span class="badge">🔥 +300 Macros</span>
                <span class="badge">🛡️ 100% Sécurisé</span>
            </div>

            <div class="cta-buttons">
                <a href="#download" class="btn btn-primary">
                    ⬇️ Télécharger v2.4.0
                </a>
                <a href="#features" class="btn btn-secondary">
                    📖 En savoir plus
                </a>
            </div>
        </div>
        <div class="scroll-indicator">
            <span style="font-size: 32px;">⬇️</span>
        </div>
    </section>

    <section class="section" id="stats">
        <h2 class="section-title">Pourquoi MacroLoaderX ?</h2>
        <div class="stats">
            <div class="stat-card">
                <div class="stat-number">50K+</div>
                <div class="stat-label">Utilisateurs actifs</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">300+</div>
                <div class="stat-label">Macros disponibles</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">4.9/5</div>
                <div class="stat-label">Note moyenne</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">24/7</div>
                <div class="stat-label">Support actif</div>
            </div>
        </div>
    </section>

    <section class="section" id="features">
        <h2 class="section-title">🎯 Fonctionnalités Principales</h2>
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">🔥</div>
                <h3>Exécution Lua Puissante</h3>
                <p>Moteur Lua optimisé supportant tous les scripts personnalisés avec une performance maximale et zéro impact sur vos FPS.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🎨</div>
                <h3>Interface Intuitive</h3>
                <p>Design moderne avec thème sombre/clair, navigation simplifiée et accès rapide à toutes les fonctionnalités en un clic.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">✍️</div>
                <h3>Éditeur Intégré</h3>
                <p>Créez et modifiez vos macros directement avec coloration syntaxique, auto-complétion et détection d'erreurs en temps réel.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">📚</div>
                <h3>Bibliothèque Massive</h3>
                <p>Plus de 300 macros testées et approuvées par la communauté : farming, combat, danse, et bien plus encore !</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🖥️</div>
                <h3>Mode Multi-Fenêtres</h3>
                <p>Compatible avec le mode fenêtré et plein écran, fonctionne en arrière-plan sans interruption de votre expérience de jeu.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🛡️</div>
                <h3>Protection Avancée</h3>
                <p>Système anti-détection intégré pour une utilisation sécurisée. Aucun virus détecté (0/72 sur VirusTotal).</p>
            </div>
        </div>
    </section>

    <section class="section" id="screenshots">
        <h2 class="section-title">📸 Aperçu de l'Interface</h2>
        <div class="screenshots">
            <div class="screenshot-card">
                <img src="https://files.catbox.moe/n4ezs7.jpg" alt="Interface principale">
                <div class="screenshot-caption">🎛️ Interface Principale</div>
            </div>
            <div class="screenshot-card">
                <img src="https://files.catbox.moe/in961k.jpg" alt="Macro en action">
                <div class="screenshot-caption">🎮 Macro en Action</div>
            </div>
        </div>
    </section>

    <section class="section">
        <h2 class="section-title">💻 Exemple de Macro</h2>
        <div class="code-example">
            <pre>-- 🚀 Macro d'auto-farming intelligente
local player = game.Players.LocalPlayer
local targetName = "Coin"

while true do
    for _, obj in pairs(workspace:GetDescendants()) do
        if obj.Name == targetName and obj:IsA("BasePart") then
            local distance = (player.Character.HumanoidRootPart.Position - obj.Position).Magnitude
            if distance < 100 then
                player.Character.HumanoidRootPart.CFrame = obj.CFrame
                wait(0.5)
            end
        end
    end
    wait(1)
end</pre>
        </div>
    </section>

    <div class="download-section" id="download">
        <h2 class="section-title">📥 Téléchargement</h2>
        <p style="font-size: 24px; margin-bottom: 30px;">Version actuelle : <strong>v2.4.0</strong> (01/01/2026)</p>
        
        <div class="version-info">
            <div class="info-box">
                <strong>📦 Taille</strong>
                1.38 MB
            </div>
            <div class="info-box">
                <strong>🖥️ Compatibilité</strong>
                Windows 10/11
            </div>
            <div class="info-box">
                <strong>🛡️ Sécurité</strong>
                VirusTotal 0/72 ✅
            </div>
            <div class="info-box">
                <strong>⚡ Exigences</strong>
                .NET 4.8+
            </div>
        </div>

        <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/untagged-e76d7861168038356685/MacroLoaderX.zip" class="btn btn-primary" style="margin-top: 30px; font-size: 20px;">
            ⬇️ Télécharger MacroLoaderX.exe
        </a>

        <p style="margin-top: 20px; opacity: 0.8;">💡 Conseil : Exécutez en administrateur pour une compatibilité optimale</p>
    </div>

    <section class="section">
        <h2 class="section-title">🚀 Guide de Démarrage Rapide</h2>
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">1️⃣</div>
                <h3>Téléchargez</h3>
                <p>Téléchargez le fichier ZIP et extrayez-le dans un dossier de votre choix.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">2️⃣</div>
                <h3>Installez</h3>
                <p>Clic droit sur MacroLoaderX.exe → Exécuter en tant qu'administrateur.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">3️⃣</div>
                <h3>Utilisez</h3>
                <p>Lancez Roblox, chargez votre macro et appuyez sur F6 pour démarrer !</p>
            </div>
        </div>
    </section>

    <div class="warning section">
        <div class="warning-title">⚠️ Avertissement Important</div>
        <p><strong>MacroLoaderX est fourni "tel quel" à des fins éducatives.</strong> L'utilisation de macros peut violer les conditions d'utilisation de certains jeux. Utilisez cet outil à vos propres risques. Les développeurs ne sont pas responsables des sanctions éventuelles. Respectez toujours les règles des jeux et la communauté.</p>
    </div>

    <section class="section" id="support">
        <h2 class="section-title">💬 Support & Communauté</h2>
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">💬</div>
                <h3>Discord</h3>
                <p>Rejoignez notre serveur Discord pour obtenir de l'aide, partager vos macros et discuter avec la communauté.</p>
                <a href="https://discord.gg/macroloaderx" class="btn btn-primary" style="margin-top: 15px; font-size: 14px; padding: 12px 24px;">Rejoindre</a>
            </div>
            <div class="feature-card">
                <div class="feature-icon">📧</div>
                <h3>Email</h3>
                <p>Besoin d'aide ? Envoyez-nous un email et notre équipe vous répondra dans les 2-4 heures.</p>
                <a href="mailto:support@macroloaderx.com" class="btn btn-primary" style="margin-top: 15px; font-size: 14px; padding: 12px 24px;">Contacter</a>
            </div>
            <div class="feature-card">
                <div class="feature-icon">📖</div>
                <h3>Documentation</h3>
                <p>Consultez notre documentation complète avec tutoriels, guides et FAQ pour tout savoir sur MacroLoaderX.</p>
                <a href="https://github.com/MacroLoaderX/MacroLoaderX/wiki" class="btn btn-primary" style="margin-top: 15px; font-size: 14px; padding: 12px 24px;">Lire</a>
            </div>
        </div>
    </section>

    <footer class="footer">
        <div class="social-links">
            <a href="https://github.com/MacroLoaderX/MacroLoaderX" title="GitHub">⭐</a>
            <a href="https://discord.gg/macroloaderx" title="Discord">💬</a>
            <a href="https://youtube.com/macroloaderx" title="YouTube">🎥</a>
            <a href="mailto:support@macroloaderx.com" title="Email">📧</a>
        </div>
        <p style="opacity: 0.8;">© 2026 MacroLoaderX - Fait avec ❤️ par la communauté</p>
        <p style="opacity: 0.6; margin-top: 10px; font-size: 14px;">Licence MIT - Projet open source</p>
    </footer>

    <script>
        // Smooth scroll pour les liens de navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Animation au scroll
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        });

        document.querySelectorAll('.feature-card, .stat-card, .screenshot-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'all 0.6s ease-out';
            observer.observe(el);
        });
    </script>
</body>
</html>
