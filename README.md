<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MacroLoaderX - Système d'Automatisation d'Entrée Externe</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;500;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
</head>
<body>

    <header class="hero-section">
        <div class="container">
            <div class="hero-content">
                <img src="https://files.catbox.moe/qz6o4n.jpg" alt="MacroLoaderX Logo" class="logo-large">
                <h1 class="main-title">MACROLOADERX</h1>
                
                <p class="tagline-primary">Le système d'automatisation d'entrée le plus fiable et discret pour la plateforme Roblox.</p>
                <p class="tagline-secondary"><i class="fas fa-lock"></i> **ARCHITECTURE EXTREMEMENT EXTERNE** : Simulation matérielle pure des touches et de la souris. Aucune injection.</p>
                
                <div class="metadata-badges">
                    <a href="https://github.com/MacroLoaderX/MacroLoaderX/stargazers" target="_blank"><img src="https://img.shields.io/github/stars/MacroLoaderX/MacroLoaderX?style=social" alt="GitHub stars"></a>
                    <a href="https://github.com/MacroLoaderX/MacroLoaderX/forks" target="_blank"><img src="https://img.shields.io/github/forks/MacroLoaderX/MacroLoaderX?style=social" alt="GitHub forks"></a>
                    <a href="https://github.com/MacroLoaderX/MacroLoaderX/releases/latest" target="_blank"><img src="https://img.shields.io/github/v/release/MacroLoaderX/MacroLoaderX?color=00ff7f&label=Dernière%20Version" alt="Latest Release"></a>
                    <a href="https://discord.gg/macroloaderx" target="_blank"><img src="https://img.shields.io/discord/123456789012345678?label=Discord&logo=discord&logoColor=white&color=5865F2" alt="Discord"></a>
                </div>

                <div class="cta-bar">
                    <div class="cta-item"><i class="fas fa-tools"></i> Configuration Simple</div>
                    <div class="cta-item"><i class="fas fa-file-code"></i> Scripts Lua Avancés</div>
                    <div class="cta-item"><i class="fas fa-network-wired"></i> Communauté de Développeurs</div>
                </div>
            </div>
        </div>
    </header>

    <main class="container">

        <section id="presentation" class="content-section">
            <h2 class="section-title"><i class="fas fa-microchip icon-left"></i> Architecture et Intégration</h2>
            <p class="lead-text">MacroLoaderX redéfinit l'automatisation en proposant une solution de simulation d'entrée **totalement découplée** de l'environnement d'exécution de Roblox. Notre approche garantit la performance tout en maintenant la plus haute discrétion.</p>
            
            <div class="key-principles">
                <div class="principle-card">
                    <i class="fas fa-terminal icon-principle"></i>
                    <h3>Simulation Matérielle</h3>
                    <p>Réplication précise des entrées clavier et souris au niveau du système d'exploitation.</p>
                </div>
                <div class="principle-card">
                    <i class="fas fa-lock icon-principle"></i>
                    <h3>Intégrité du Client</h3>
                    <p>Aucune lecture, écriture, ou modification de la mémoire du processus Roblox.</p>
                </div>
                <div class="principle-card">
                    <i class="fab fa-lua icon-principle"></i>
                    <h3>API Lua Dévouée</h3>
                    <p>Développement de macros complexes via un environnement de scripting Lua optimisé pour l'entrée.</p>
                </div>
            </div>
        </section>

        <section id="features" class="content-section">
            <h2 class="section-title"><i class="fas fa-cogs icon-left"></i> Spécifications Techniques</h2>
            <div class="specs-grid">
                <div class="spec-item">
                    <i class="fas fa-feather-alt spec-icon"></i>
                    <h4>EXÉCUTION À FAIBLE LATENCE</h4>
                    <p>Cycle d'exécution des scripts optimisé pour des actions rapides et répétitives, sans délai perceptible.</p>
                </div>
                <div class="spec-item highlighted">
                    <i class="fas fa-pen-nib spec-icon"></i>
                    <h4>ÉDITEUR DE MACROS INTÉGRÉ</h4>
                    <p>Environnement de développement (IDE) complet pour le codage et le débogage de vos scripts Lua en temps réel.</p>
                </div>
                <div class="spec-item">
                    <i class="fas fa-sync-alt spec-icon"></i>
                    <h4>MÉCANISME DE MISE À JOUR CONTINU</h4>
                    <p>Nouvelles versions automatiques pour garantir la performance et la compatibilité avec les systèmes d'exploitation récents.</p>
                </div>
                <div class="spec-item">
                    <i class="fas fa-layer-group spec-icon"></i>
                    <h4>COMPATIBILITÉ MULTI-CONTEXTE</h4>
                    <p>Fonctionnement garanti en mode plein écran, fenêtré ou en arrière-plan, sans perte de focus.</p>
                </div>
            </div>
        </section>

        <section id="documentation" class="content-section narrow-section">
            <h2 class="section-title"><i class="fas fa-code icon-left"></i> Documentation & Aperçu Lua</h2>
            <p>L'API MacroLoaderX utilise une syntaxe claire pour la gestion des événements système (clavier/souris).</p>
            
            <div class="code-container">
                <div class="code-header-bar">
                    <span class="code-title">Macro d'Échantillon : Routine de Saut Active</span>
                    <button class="copy-button" onclick="copyCode()"><i class="fas fa-copy"></i> Copier</button>
                </div>
                <pre><code id="sample-code">
-- Déclaration d'une routine Lua simple
while true do
    -- Simulation de l'appui sur la barre d'espace.
    -- Utilise les fonctions système de l'API MLX.
    Input.KeyPress("space") 
    
    -- Pause pour économiser les ressources et simuler un délai humain.
    System.Wait(2.0) 
end
                </code></pre>
            </div>
        </section>

        <section id="download" class="cta-section">
            <h2 class="section-title"><i class="fas fa-cloud-download-alt icon-left"></i> Télécharger MacroLoaderX</h2>
            <p class="version-info">VERSION ACTUELLE : **v2.4.0** | Date de publication : 01/01/2026</p>

            <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/untagged-e76d7861168038356685/MacroLoaderX.zip" class="download-btn">
                <i class="fas fa-angle-double-down"></i> TÉLÉCHARGEMENT SECURISE (.zip)
            </a>

            <div class="download-metadata">
                <span><i class="fas fa-weight-hanging"></i> Taille du fichier : 1.38 MB</span>
                <span><i class="fab fa-windows"></i> OS Compatible : Windows 10/11 (64bit)</span>
                <span class="security-check"><i class="fas fa-shield-alt"></i> Sécurité VirusTotal : 0/72 (Vérifié)</span>
            </div>
            
            <p class="note-admin"><i class="fas fa-info-circle"></i> **NOTE OPÉRATIONNELLE :** L'exécution en mode administrateur est recommandée pour garantir la priorité d'entrée système.</p>
        </section>

    </main>

    <footer>
        <div class="container footer-content">
            <div class="footer-links">
                <a href="https://github.com/MacroLoaderX/MacroLoaderX/issues" target="_blank"><i class="fas fa-bug"></i> Rapport de Bug</a>
                <a href="https://github.com/MacroLoaderX/MacroLoaderX/pulls" target="_blank"><i class="fas fa-code-branch"></i> Contribution Code</a>
                <a href="https://discord.gg/macroloaderx" target="_blank"><i class="fab fa-discord"></i> Support Technique</a>
            </div>
            <p class="copyright-info">
                © 2026 MacroLoaderX. Tous droits réservés. Développé par **@n0lex9999** · Sous licence MIT.
            </p>
        </div>
    </footer>

<script>
    // Fonction simple pour copier le code (JS)
    function copyCode() {
        const codeBlock = document.getElementById('sample-code');
        const code = codeBlock.innerText.trim();
        navigator.clipboard.writeText(code).then(() => {
            alert("Code Lua copié dans le presse-papiers.");
        }).catch(err => {
            console.error('Erreur lors de la copie: ', err);
        });
    }
</script>
</body>
</html>
