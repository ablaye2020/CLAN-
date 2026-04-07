# CLAN-
Joyboy ….le respect ne se demande pas 
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>ZETSU Clan | Purge Éternelle</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {<!-- VIDÉO LOCALE EN ARRIÈRE-PLAN -->
<video autoplay muted loop playsinline style="position: fixed; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: -1;">
    <source src="ta-video.mp4" type="video/mp4">
</video>
            min-height: 100vh;
            background: radial-gradient(circle at 20% 30%, #0b0e1a, #03050b);
            font-family: 'Segoe UI', 'Poppins', 'Orbitron', 'Montserrat', system-ui, sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1.5rem;
            position: relative;
        }

        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 245, 210, 0.03);
            pointer-events: none;
            z-index: 0;
        }

        .main-container {
            max-width: 1400px;
            width: 100%;
            background: rgba(12, 10, 22, 0.65);
            backdrop-filter: blur(14px);
            border-radius: 3rem;
            border: 1px solid rgba(210, 180, 140, 0.3);
            box-shadow: 0 25px 45px rgba(0, 0, 0, 0.5), 0 0 0 1px rgba(255, 215, 150, 0.1) inset;
            padding: 2rem;
            transition: all 0.3s;
            z-index: 2;
        }

        .lock-screen {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 1.8rem;
            padding: 2rem 1rem;
        }

        .lock-icon {
            font-size: 4rem;
            filter: drop-shadow(0 0 8px #ffbb77);
        }

        .lock-screen h2 {
            font-size: 2rem;
            letter-spacing: 4px;
            background: linear-gradient(135deg, #e6d5a8, #b97f44);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-transform: uppercase;
            font-weight: 700;
        }

        .code-input-group {
            display: flex;
            gap: 0.8rem;
            flex-wrap: wrap;
            justify-content: center;
        }

        #codeInput {
            background: rgba(0, 0, 0, 0.65);
            border: 2px solid #b87c4f;
            padding: 0.9rem 1.5rem;
            font-size: 1.2rem;
            border-radius: 60px;
            color: #ffeaC0;
            font-family: monospace;
            letter-spacing: 2px;
            text-align: center;
            width: 220px;
            backdrop-filter: blur(4px);
            outline: none;
        }

        #codeInput:focus {
            border-color: #e7b874;
            box-shadow: 0 0 12px rgba(231, 184, 116, 0.5);
        }

        .btn-code {
            background: linear-gradient(95deg, #2a2418, #1f1b12);
            border: 1px solid #dba459;
            padding: 0.9rem 1.8rem;
            border-radius: 60px;
            font-weight: bold;
            color: #ffdd99;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.2s;
            font-family: inherit;
        }

        .btn-code:hover {
            background: #3f3422;
            border-color: #f5bc70;
            color: #fff2df;
            transform: scale(0.97);
        }

        .error-msg {
            color: #ffa098;
            background: #2c1810aa;
            padding: 0.4rem 1rem;
            border-radius: 40px;
            font-size: 0.85rem;
        }

        .clan-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(12px);}
            to { opacity: 1; transform: translateY(0);}
        }

        .cheffe-header {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: baseline;
            border-bottom: 2px solid rgba(218, 165, 32, 0.5);
            padding-bottom: 1.2rem;
            margin-bottom: 2rem;
        }

        .clan-name {
            font-size: 2.8rem;
            font-weight: 800;
            background: linear-gradient(145deg, #fae67a, #c48a3c);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: 3px;
        }

        .chef-title {
            text-align: right;
        }

        .chef-label {
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            color: #cfb47c;
        }

        .chef-name {
            font-size: 1.8rem;
            font-weight: bold;
            background: linear-gradient(to right, #efcd93, #bd8a4a);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .roles-section {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            margin: 2rem 0 2rem 0;
        }

        .card {
            flex: 1;
            min-width: 280px;
            background: rgba(0, 0, 0, 0.55);
            backdrop-filter: blur(8px);
            border-radius: 2rem;
            padding: 1.6rem;
            border: 1px solid rgba(200, 160, 90, 0.5);
        }

        .card h3 {
            font-size: 1.5rem;
            font-weight: 600;
            border-left: 5px solid #e7b45a;
            padding-left: 1rem;
            margin-bottom: 1.2rem;
            color: #f7e3b2;
        }

        .member-list, .chef-list {
            list-style: none;
        }

        .member-list li, .chef-list li {
            background: rgba(30, 27, 40, 0.7);
            margin: 0.8rem 0;
            padding: 0.8rem 1.2rem;
            border-radius: 2rem;
            display: flex;
            align-items: center;
            gap: 12px;
            font-weight: 500;
            border: 1px solid #5f4a2e;
            color: #f0e2c5;
        }

        .member-list li::before, .chef-list li::before {
            content: "⚔️";
            font-size: 1.1rem;
        }

        .chef-list li::before {
            content: "👑";
        }

        .spectators-area {
            margin-top: 2rem;
            background: rgba(0, 0, 0, 0.45);
            border-radius: 1.8rem;
            padding: 1.6rem;
            border-top: 1px dashed #b88d54;
        }

        .spectator-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 1.2rem;
        }

        .spectator-header span {
            font-size: 1.5rem;
            font-weight: bold;
            background: linear-gradient(145deg, #ebc48e, #b47c3c);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .spectator-code-box {
            display: flex;
            gap: 10px;
            align-items: center;
            background: #020617aa;
            padding: 0.4rem 0.8rem 0.4rem 1.2rem;
            border-radius: 60px;
        }

        .spectator-code-box input {
            background: transparent;
            border: none;
            border-bottom: 2px solid #b98f54;
            padding: 8px 6px;
            width: 140px;
            color: #ffefcf;
            font-family: monospace;
            font-size: 1rem;
            outline: none;
        }

        .spectator-code-box button {
            background: #3f3320;
            border: none;
            padding: 6px 14px;
            border-radius: 40px;
            color: #ffddbb;
            cursor: pointer;
            font-weight: bold;
        }

        .spectator-code-box button:hover {
            background: #66512e;
        }

        .spectator-message {
            margin-top: 14px;
            font-size: 0.9rem;
            color: #ffe2b5;
            background: #1c170e80;
            padding: 8px 16px;
            border-radius: 30px;
            display: inline-block;
        }

        .spectator-view {
            margin-top: 1rem;
            font-style: italic;
            border-left: 3px solid #cb9e6b;
            padding-left: 1rem;
            color: #d4c09d;
        }

        .form-input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 30px;
            background: #1a1625;
            border: 1px solid #b87c4f;
            color: white;
            font-family: inherit;
        }

        textarea.form-input {
            resize: vertical;
            border-radius: 20px;
        }

        .btn-clan {
            background: #b87c4f;
            border: none;
            padding: 10px;
            border-radius: 30px;
            color: white;
            cursor: pointer;
            width: 100%;
            font-weight: bold;
            transition: 0.2s;
            margin-top: 5px;
        }

        .btn-clan:hover {
            background: #d4945e;
        }

        .btn-clan.secondary {
            background: #3f3320;
            color: #ffdd99;
        }

        .btn-clan.secondary:hover {
            background: #66512e;
        }

        .messages-container {
            max-height: 250px;
            overflow-y: auto;
            margin-top: 15px;
        }

        .message-item {
            background: #0f0d16;
            margin: 8px 0;
            padding: 10px;
            border-radius: 15px;
            border-left: 3px solid #e7b45a;
        }

        .message-author {
            color: #e7b45a;
            font-weight: bold;
        }

        .message-date {
            color: #7a6a4a;
            font-size: 0.7rem;
        }

        .message-text {
            color: #f0e2c5;
            margin-top: 5px;
            word-break: break-word;
        }

        .membres-list {
            margin-top: 15px;
            padding: 10px;
            background: #0a0814;
            border-radius: 20px;
            font-size: 0.85rem;
            color: #c4b28a;
        }

        hr {
            border-color: #5e4a2e;
            margin: 1rem 0;
        }

        footer {
            text-align: center;
            font-size: 0.7rem;
            margin-top: 2rem;
            color: #b6a077;
            opacity: 0.7;
        }

        @media (max-width: 900px) {
            .main-container {
                padding: 1.2rem;
            }
            .clan-name {
                font-size: 2rem;
            }
            .chef-name {
                font-size: 1.3rem;
            }
            .card h3 {
                font-size: 1.3rem;
            }
        }
    </style>
</head>
<body>
<div class="main-container">
    <!-- ÉCRAN DE VERROUILLAGE -->
    <div id="lockScreen" class="lock-screen">
        <div class="lock-icon">🔐⛩️</div>
        <h2>✦ ACCÈS CLAN ZETSU ✦</h2>
        <p style="color:#ddc9a0;">Entrez le code sacré de la purge</p>
        <div class="code-input-group">
            <input type="password" id="codeInput" placeholder="CODE D'ACCÈS" autocomplete="off">
            <button class="btn-code" id="unlockBtn">DÉVERROUILLER</button>
        </div>
        <div id="lockError" class="error-msg"></div>
    </div>

    <!-- CONTENU PRINCIPAL DU CLAN -->
    <div id="clanContent" class="clan-content">
        <!-- En-tête avec cheffe -->
        <div class="cheffe-header">
            <div class="clan-name">⚔️ 𝐙𝐄𝐓𝐒𝐔 ⚔️</div>
            <div class="chef-title">
                <div class="chef-label">⟡ CHEFFE SUPRÊME ⟡</div>
                <div class="chef-name">BLACK 𝐓𝐎𝐁𝐈 𝐙𝐄𝐓𝐒𝐔</div>
            </div>
        </div>

        <!-- Section Chef + Membres existants -->
        <div class="roles-section">
            <div class="card">
                <h3>👑 HAUT COMMANDEMENT</h3>
                <ul class="chef-list">
                    <li><strong>BLACK 𝐓𝐎𝐁𝐈 𝐙𝐄𝐓𝐒𝐔</strong> — Cheffe & Stratège</li>
                    <li><strong>AKUMA ZETSU</strong> — Bras droit / Exécuteur noir</li>
                    <li><strong>RAIJIN KAGE</strong> — Gardien de l'Ombre</li>
                </ul>
                <!-- Zone qui affichera les membres inscrits dynamiquement -->
                <div id="listeMembresInscrits" class="membres-list">
                    📜 Chargement des membres...
                </div>
            </div>

            <div class="card">
                <h3>⚔️ MEMBRES D'ÉLITE</h3>
                <ul class="member-list">
                    <li>SHINIGAMI ZETSU</li>
                    <li>KURO HAGANE</li>
                    <li>AKARI NO HIKARI</li>
                    <li>RYUJIN ZETSU</li>
                    <li>SAYAKA VORPAL</li>
                    <li>+ 17 Purgeurs silencieux</li>
                </ul>
            </div>
        </div>

        <!-- SECTION INSCRIPTION MEMBRES -->
        <div class="card" style="margin-bottom: 1.5rem;">
            <h3>📝 ENREGISTREMENT ZETSU</h3>
            <input type="text" id="pseudoInscription" class="form-input" placeholder="Ton pseudo de guerrier">
            <input type="password" id="mdpInscription" class="form-input" placeholder="Mot de passe du clan">
            <button id="btnInscription" class="btn-clan">⚔️ Devenir membre ZETSU</button>
            <div id="messageInscription" style="margin-top:10px; font-size:0.8rem; color:#ffcc88;"></div>
        </div>

        <!-- SECTION DICTÉE / MESSAGES DU CLAN -->
        <div class="card">
            <h3>🎙️ PAROLE DU CLAN (DICTÉE)</h3>
            <textarea id="messageTexte" class="form-input" rows="3" placeholder="Écris ton message ici..."></textarea>
            <button id="btnPoster" class="btn-clan secondary">📢 DICTER / PUBLIER</button>
            <div id="listeMessages" class="messages-container">
                <p style="color:#aa9f7f; font-style:italic;">Aucun message pour l'instant...</p>
            </div>
        </div>

        <!-- SECTION TÉLÉSPECTATEURS -->
        <div class="spectators-area">
            <div class="spectator-header">
                <span>🎭 SPECTATEURS & ALLIÉS 🎭</span>
                <div class="spectator-code-box">
                    <input type="text" id="spectatorCodeInput" placeholder="Code téléspectateur">
                    <button id="validateSpectatorBtn">ENTRER</button>
                </div>
            </div>
            <div id="spectatorFeedback" class="spectator-message">🔒 Entrez le code des témoins pour voir les transmissions.</div>
            <div id="spectatorSecretZone" class="spectator-view">
                ⚡ En attente du code des téléspectateurs...
            </div>
            <hr>
            <div style="font-size:0.7rem; text-align:right;">⚔️ La Purge est éternelle — Code & Honneur</div>
        </div>
        <footer>© CLAN ZETSU — Sous l'égide de BLACK TOBI ZETSU</footer>
    </div>
</div>

<script>
    // ==================== CODES D'ACCÈS ====================
    const MAIN_ACCESS_CODE = "PURGEZETSU2025";
    const SPECTATOR_CODE = "EYEOFZETSU";
    const MEMBER_PASSWORD = "ZETSU2025";  // mot de passe pour s'inscrire

    let isUnlocked = false;
    let spectatorValidated = false;

    // Données stockées localement
    let membresZetsu = JSON.parse(localStorage.getItem('membresZetsu')) || [];
    let messagesClan = JSON.parse(localStorage.getItem('messagesClan')) || [];

    // ==================== FONCTIONS D'AFFICHAGE ====================
    function afficherMessages() {
        const container = document.getElementById('listeMessages');
        if (!container) return;
        if (messagesClan.length === 0) {
            container.innerHTML = '<p style="color:#aa9f7f; font-style:italic;">Aucun message pour l\'instant... Sois le premier à dicter !</p>';
            return;
        }
        container.innerHTML = messagesClan.map(msg => `
            <div class="message-item">
                <span class="message-author">${escapeHtml(msg.auteur)}</span>
                <span class="message-date">(${msg.date})</span>
                <p class="message-text">${escapeHtml(msg.texte)}</p>
            </div>
        `).join('');
    }

    function mettreAJourListeMembres() {
        const zone = document.getElementById('listeMembresInscrits');
        if (!zone) return;
        if (membresZetsu.length === 0) {
            zone.innerHTML = '📜 Aucun membre inscrit pour l\'instant. Deviens le premier !';
        } else {
            zone.innerHTML = `<strong>👥 Membres enregistrés (${membresZetsu.length}) :</strong><br> ${membresZetsu.map(m => `⚔️ ${escapeHtml(m)}`).join(' • ')}`;
        }
    }

    // Fonction anti-XSS simple
    function escapeHtml(str) {
        if (!str) return '';
        return str.replace(/[&<>]/g, function(m) {
            if (m === '&') return '&amp;';
            if (m === '<') return '&lt;';
            if (m === '>') return '&gt;';
            return m;
        }).replace(/[\uD800-\uDBFF][\uDC00-\uDFFF]/g, function(c) {
            return c;
        });
    }

    // ==================== GESTION SPECTATEURS ====================
    function updateSpectatorUI() {
        if (!isUnlocked) return;
        const feedback = document.getElementById('spectatorFeedback');
        const secretZone = document.getElementById('spectatorSecretZone');
        if (spectatorValidated) {
            feedback.innerHTML = "✅ [CODE VALIDE] Bienvenue, témoin de la purge. Accès aux transmissions spéciales.";
            feedback.style.background = "#1f3a1faa";
            secretZone.innerHTML = `📡 TRANSMISSION SPECTATEUR :<br>▸ La grande purge approche... BLACK TOBI ZETSU lance un appel.<br>▸ Prochain rassemblement : Sanctuaire de la Lune Noire (24h).<br>▸ "Ceux qui regardent sans agir seront pourtant les témoins de l'éternité."<br>🎴 Message codé : restez vigilants.`;
        } else {
            feedback.innerHTML = "🔐 Code téléspectateur requis. Entrez le code pour recevoir les visions du clan.";
            feedback.style.background = "#1c170e80";
            secretZone.innerHTML = `🌙 [Accès restreint] Les murmures de la purge ne sont accessibles qu'aux téléspectateurs ayant le bon code. ⚡ Entrez le code des témoins.`;
        }
    }

    // ==================== DÉVERROUILLAGE DU SITE ====================
    function unlockSite() {
        const code = document.getElementById('codeInput').value.trim();
        if (code === MAIN_ACCESS_CODE) {
            isUnlocked = true;
            document.getElementById('lockScreen').style.display = 'none';
            document.getElementById('clanContent').style.display = 'block';
            spectatorValidated = false;
            updateSpectatorUI();
            afficherMessages();
            mettreAJourListeMembres();
            document.getElementById('lockError').innerText = "";
        } else {
            document.getElementById('lockError').innerText = "❌ Code invalide. L'accès au clan est refusé.";
            setTimeout(() => {
                const err = document.getElementById('lockError');
                if (err) err.innerText = "";
            }, 2000);
        }
    }

    // ==================== INSCRIPTION MEMBRE ====================
    function inscrireMembre() {
        if (!isUnlocked) {
            alert("Déverrouille d'abord l'accès au clan !");
            return;
        }
        const pseudo = document.getElementById('pseudoInscription').value.trim();
        const mdp = document.getElementById('mdpInscription').value;
        const msgDiv = document.getElementById('messageInscription');
        
        if (!pseudo || !mdp) {
            msgDiv.innerHTML = "❌ Remplis ton pseudo et ton mot de passe !";
            return;
        }
        if (mdp !== MEMBER_PASSWORD) {
            msgDiv.innerHTML = "❌ Mot de passe du clan incorrect ! (Le code est ZETSU2025)";
            return;
        }
        if (membresZetsu.includes(pseudo)) {
            msgDiv.innerHTML = "⚠️ Ce pseudo est déjà enregistré dans le clan !";
            return;
        }
        
        membresZetsu.push(pseudo);
        localStorage.setItem('membresZetsu', JSON.stringify(membresZetsu));
        msgDiv.innerHTML = "✅ Félicitations ! Tu es officiellement un membre ZETSU 🔥 La purge t'appelle.";
        document.getElementById('pseudoInscription').value = "";
        document.getElementById('mdpInscription').value = "";
        mettreAJourListeMembres();
        setTimeout(() => {
            if (msgDiv) msgDiv.innerHTML = "";
        }, 3000);
    }

    // ==================== DICTÉE / POSTER MESSAGE ====================
    function posterMessage() {
        if (!isUnlocked) {
            alert("Déverrouille l'accès au clan d'abord.");
            return;
        }
        const pseudoActif = prompt("🔐 Entre ton pseudo ZETSU (celui avec lequel tu t'es inscrit) pour dicter :");
        if (!pseudoActif) return;
        
        if (!membresZetsu.includes(pseudoActif)) {
            alert("❌ Tu n'es pas un membre enregistré du clan ! Inscris-toi d'abord avec le mot de passe.");
            return;
        }
        
        const texte = document.getElementById('messageTexte').value.trim();
        if (!texte) {
            alert("Écris un message avant de dicter !");
            return;
        }
        
        const nouveauMsg = {
            auteur: pseudoActif,
            texte: texte.substring(0, 500),
            date: new Date().toLocaleString()
        };
        messagesClan.unshift(nouveauMsg);
        if (messagesClan.length > 50) messagesClan.pop();
        localStorage.setItem('messagesClan', JSON.stringify(messagesClan));
        afficherMessages();
        document.getElementById('messageTexte').value = "";
        alert("📢 Message dicté avec succès ! Les membres du clan peuvent le voir.");
    }

    function validateSpectator() {
        if (!isUnlocked) {
            alert("Veuillez d'abord déverrouiller l'accès au clan avec le code principal.");
            return;
        }
        const specCode = document.getElementById('spectatorCodeInput').value.trim();
        if (specCode === SPECTATOR_CODE) {
            spectatorValidated = true;
            updateSpectatorUI();
            document.getElementById('spectatorCodeInput').value = "";
            const fb = document.getElementById('spectatorFeedback');
            fb.style.transition = "0.2s";
        } else {
            spectatorValidated = false;
            updateSpectatorUI();
            const fb = document.getElementById('spectatorFeedback');
            fb.innerHTML = "❌ Code téléspectateur incorrect. Accès refusé.";
            setTimeout(() => {
                if (!spectatorValidated && isUnlocked) updateSpectatorUI();
            }, 1800);
        }
    }

    // ==================== ATTACHEMENT DES ÉVÉNEMENTS ====================
    document.getElementById('unlockBtn').addEventListener('click', unlockSite);
    document.getElementById('codeInput').addEventListener('keypress', (e) => {
        if (e.key === 'Enter') unlockSite();
    });
    document.getElementById('btnInscription').addEventListener('click', inscrireMembre);
    document.getElementById('btnPoster').addEventListener('click', posterMessage);
    document.getElementById('validateSpectatorBtn').addEventListener('click', validateSpectator);
    document.getElementById('spectatorCodeInput').addEventListener('keypress', (e) => {
        if (e.key === 'Enter') validateSpectator();
    });

    // Initialisation silencieuse
    if (membresZetsu.length === 0) {
        console.log("Aucun membre enregistré pour le moment.");
    }
    if (messagesClan.length === 0) {
        console.log("Bienvenue dans le clan ZETSU !");
    }
</script>
</body>
</html>
