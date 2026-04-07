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
            user-select: none; /* pour un style "clan", évite la sélection gênante */
        }

        body {
            min-height: 100vh;
            background: radial-gradient(circle at 20% 30%, #0b0e1a, #03050b);
            font-family: 'Segoe UI', 'Poppins', 'Orbitron', 'Montserrat', system-ui, -apple-system, 'Inter', sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1.5rem;
            position: relative;
            transition: background 0.3s ease;
        }

        /* Overlay jour / lumière tamisée (jour mais sombre chic) */
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

        /* Conteneur principal glassmorphisme sombre mais avec reflets jour */
        .main-container {
            max-width: 1300px;
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

        /* zone de verrouillage (code) */
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
            transition: 0.2s;
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
            box-shadow: 0 4px 12px rgba(0,0,0,0.3);
        }

        .error-msg {
            color: #ffa098;
            background: #2c1810aa;
            padding: 0.4rem 1rem;
            border-radius: 40px;
            font-size: 0.85rem;
            backdrop-filter: blur(4px);
        }

        /* Contenu principal (après déverrouillage) */
        .clan-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(12px);}
            to { opacity: 1; transform: translateY(0);}
        }

        /* en-tête avec nom du chef */
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
            text-shadow: 0 2px 5px rgba(0,0,0,0.3);
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
            text-shadow: 0 0 6px rgba(0,0,0,0.5);
        }

        /* grille 2 parties : chef & membres */
        .roles-section {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            margin: 2rem 0 2.5rem 0;
        }

        .card {
            flex: 1;
            min-width: 250px;
            background: rgba(0, 0, 0, 0.55);
            backdrop-filter: blur(8px);
            border-radius: 2rem;
            padding: 1.6rem;
            border: 1px solid rgba(200, 160, 90, 0.5);
            transition: 0.2s;
        }

        .card h3 {
            font-size: 1.8rem;
            font-weight: 600;
            border-left: 5px solid #e7b45a;
            padding-left: 1rem;
            margin-bottom: 1.4rem;
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
            transition: 0.1s;
            color: #f0e2c5;
        }

        .member-list li::before, .chef-list li::before {
            content: "⚔️";
            font-size: 1.1rem;
        }

        .chef-list li::before {
            content: "👑";
        }

        /* zone téléspectateurs + code spécial */
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
            transition: 0.2s;
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

        hr {
            border-color: #5e4a2e;
            margin: 1rem 0;
        }

        /* responsive */
        @media (max-width: 780px) {
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
                font-size: 1.4rem;
            }
        }
        footer {
            text-align: center;
            font-size: 0.7rem;
            margin-top: 2rem;
            color: #b6a077;
            opacity: 0.7;
        }
        button {
            cursor: pointer;
        }
    </style>
</head>
<body>
<div class="main-container" id="appContainer">
    <!-- ÉCRAN DE VERROUILLAGE (code d'accès général) -->
    <div id="lockScreen" class="lock-screen">
        <div class="lock-icon">🔐⛩️</div>
        <h2>✦ ACCÈS CLAN ZETSU ✦</h2>
        <p style="color:#ddc9a0;">Entrez le code sacré de la purge</p>
        <div class="code-input-group">
            <input type="password" id="codeInput" placeholder="CODE D'ACCÈS" autocomplete="off">
            <button class="btn-code" id="unlockBtn">DÉVERROUILLER</button>
        </div>
        <div id="lockError" class="error-msg"></div>
        <div style="font-size:0.75rem; color:#9e8a64;">※ Code réservé aux guerriers ZETSU</div>
    </div>

    <!-- CONTENU PRINCIPAL DU CLAN (après code) -->
    <div id="clanContent" class="clan-content">
        <!-- Header avec nom de la cheffe : BLACK 𝐓𝐎𝐁𝐈 𝐙𝐄𝐓𝐒𝐔 -->
        <div class="cheffe-header">
            <div class="clan-name">⚔️ 𝐙𝐄𝐓𝐒𝐔 ⚔️</div>
            <div class="chef-title">
                <div class="chef-label">⟡ CHEFFE SUPRÊME ⟡</div>
                <div class="chef-name">BLACK 𝐓𝐎𝐁𝐈 𝐙𝐄𝐓𝐒𝐔</div>
            </div>
        </div>

        <!-- PARTIE CHEF et MEMBRES -->
        <div class="roles-section">
            <!-- Carte CHEF (détail) -->
            <div class="card">
                <h3>👑 HAUT COMMANDEMENT</h3>
                <ul class="chef-list">
                    <li><strong>BLACK 𝐓𝐎𝐁𝐈 𝐙𝐄𝐓𝐒𝐔</strong> — Cheffe & Stratège de la Purge</li>
                    <li><strong>AKUMA ZETSU</strong> — Bras droit / Exécuteur noir</li>
                    <li><strong>RAIJIN KAGE</strong> — Gardien de l'Ombre</li>
                </ul>
                <div style="margin-top: 12px; font-size:0.85rem; color:#dbbf88;">〄 La volonté de ZETSU ne faiblit jamais</div>
            </div>

            <!-- Carte MEMBRES élites -->
            <div class="card">
                <h3>⚔️ MEMBRES D’ÉLITE</h3>
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

        <!-- SECTION TÉLÉSPECTATEURS + CODE SPÉCIAL -->
        <div class="spectators-area">
            <div class="spectator-header">
                <span>🎭 SPECTATEURS & ALLIÉS 🎭</span>
                <div class="spectator-code-box">
                    <input type="text" id="spectatorCodeInput" placeholder="Code téléspectateur" maxlength="20">
                    <button id="validateSpectatorBtn">ENTRER</button>
                </div>
            </div>
            <div id="spectatorFeedback" class="spectator-message">🔒 Entrez le code des témoins pour voir les transmissions.</div>
            <div id="spectatorSecretZone" class="spectator-view">
                ⚡ En attente du code des téléspectateurs...
            </div>
            <hr>
            <div style="font-size:0.7rem; text-align:right; opacity:0.7;">⚔️ La Purge est éternelle — Les yeux ouverts, l'âme prête.</div>
        </div>
        <footer>© CLAN ZETSU — Sous l’égide de BLACK TOBI ZETSU — Code & Honneur</footer>
    </div>
</div>

<script>
    // ==================== CONFIGURATION DES CODES ====================
    // Code principal pour accéder au site (pour les membres et chef)
    const MAIN_ACCESS_CODE = "PURGEZETSU2025";   // code pour entrer dans le clan
    
    // Code spécial pour les téléspectateurs (observateurs externes)
    const SPECTATOR_CODE = "EYEOFZETSU";         // les témoins utilisent ce code pour accéder au message spécial
    
    // État : site déverrouillé ou non
    let isUnlocked = false;
    
    // État : code téléspectateur validé (pour afficher le contenu secret)
    let spectatorValidated = false;
    
    // Éléments DOM
    const lockScreenDiv = document.getElementById('lockScreen');
    const clanContentDiv = document.getElementById('clanContent');
    const unlockBtn = document.getElementById('unlockBtn');
    const codeInputField = document.getElementById('codeInput');
    const lockErrorSpan = document.getElementById('lockError');
    
    // éléments téléspectateurs
    const spectatorCodeInput = document.getElementById('spectatorCodeInput');
    const validateSpectatorBtn = document.getElementById('validateSpectatorBtn');
    const spectatorFeedbackDiv = document.getElementById('spectatorFeedback');
    const spectatorSecretZone = document.getElementById('spectatorSecretZone');
    
    // Fonction pour afficher le contenu principal si code correct
    function unlockSite(enteredCode) {
        if (enteredCode === MAIN_ACCESS_CODE) {
            isUnlocked = true;
            lockScreenDiv.style.display = 'none';
            clanContentDiv.style.display = 'block';
            // réinitialiser le statut spectateur quand on entre dans le site (mais on garde la zone neutre)
            spectatorValidated = false;
            updateSpectatorUI();
            return true;
        } else {
            lockErrorSpan.innerText = "❌ Code invalide. L'accès au clan est refusé.";
            setTimeout(() => {
                if(lockErrorSpan) lockErrorSpan.innerText = "";
            }, 2000);
            return false;
        }
    }
    
    // Gestion du clic déverrouillage
    unlockBtn.addEventListener('click', () => {
        const code = codeInputField.value.trim();
        if (code === "") {
            lockErrorSpan.innerText = "❌ Entrez le code sacré du clan.";
            return;
        }
        unlockSite(code);
    });
    
    // Optionnel: touche entrée sur le champ code
    codeInputField.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') {
            e.preventDefault();
            unlockBtn.click();
        }
    });
    
    // Mettre à jour l'interface des téléspectateurs selon validation
    function updateSpectatorUI() {
        if (!isUnlocked) return; // ne s'applique que si le site est débloqué
        if (spectatorValidated) {
            spectatorFeedbackDiv.innerHTML = "✅ [CODE VALIDE] Bienvenue, témoin de la purge. Vous avez accès aux transmissions spéciales.";
            spectatorFeedbackDiv.style.background = "#1f3a1faa";
            spectatorFeedbackDiv.style.color = "#d4ffc4";
            // contenu secret réservé aux spectateurs avec le code
            spectatorSecretZone.innerHTML = `
                <span style="font-weight:bold;">📡 TRANSMISSION SPECTATEUR ZETSU :</span><br>
                ▸ La grande purge approche... BLACK TOBI ZETSU lance un appel aux ombres.<br>
                ▸ Prochain rassemblement : Sanctuaire de la Lune Noire (24h).<br>
                ▸ "Ceux qui regardent sans agir seront pourtant les témoins de l'éternité."<br>
                🎴 <em>Message codé des spectateurs : code partagé — restez vigilants.</em>
            `;
        } else {
            spectatorFeedbackDiv.innerHTML = "🔐 Code téléspectateur requis. Entrez le code pour recevoir les visions du clan.";
            spectatorFeedbackDiv.style.background = "#1c170e80";
            spectatorFeedbackDiv.style.color = "#ffe2b5";
            spectatorSecretZone.innerHTML = `🌙 [Accès restreint] Les murmures de la purge ne sont accessibles qu'aux téléspectateurs ayant le bon code. 
            <br>⚡ Invocation: entrez le code des témoins.`;
        }
    }
    
    // Valider le code spectateur
    function validateSpectatorCode() {
        if (!isUnlocked) {
            // Si le site n'est pas encore débloqué, on ne peut pas activer cette partie
            alert("Veuillez d'abord déverrouiller l'accès au clan avec le code principal.");
            return;
        }
        const enteredSpecCode = spectatorCodeInput.value.trim();
        if (enteredSpecCode === SPECTATOR_CODE) {
            spectatorValidated = true;
            updateSpectatorUI();
            spectatorCodeInput.value = "";
            // petit effet visuel sympa
            spectatorFeedbackDiv.style.transition = "0.2s";
        } else {
            spectatorValidated = false;
            updateSpectatorUI();
            spectatorFeedbackDiv.innerHTML = "❌ Code téléspectateur incorrect. Aucun accès aux transmissions.";
            spectatorFeedbackDiv.style.background = "#2f1e18aa";
            setTimeout(() => {
                if (!spectatorValidated) {
                    // remettre le message par défaut si toujours invalide après 2 sec
                    if(!spectatorValidated && isUnlocked) updateSpectatorUI();
                }
            }, 1800);
        }
    }
    
    validateSpectatorBtn.addEventListener('click', validateSpectatorCode);
    spectatorCodeInput.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') validateSpectatorCode();
    });
    
    // Petite subtilité: si jamais le site est déjà débloqué via un code correct, on initialise l'interface téléspectateur.
    // Pour gérer le cas où on voudrait préremplir après déblocage (mais le code est validé par le bouton)
    // On initialise le statut spectatorValidated à false par défaut et on appel updateSpectatorUI quand le contenu devient visible.
    
    // Observer l'affichage du contenu principal via MutationObserver ou simple vérification lors du déblocage.
    // Dans unlockSite, après l'affichage, on met à jour l'UI des spectateurs.
    // On a déjà appelé updateSpectatorUI dans unlockSite.
    // Mais pour être sur, on surcharge unlockSite original pour qu'il déclenche l'update.
    // On va conserver la logique mais on avait déjà fait updateSpectatorUI à la fin de unlockSite.
    // Cependant notre fonction unlockSite originale ne contient pas encore updateSpectatorUI. On va la réécrire proprement.
    // Re-définissons unlockSite pour intégrer l'appel UI.
    // On va remplacer la fonction pour qu'elle contienne tout.
    // ATTENTION: on ne peut pas redéfinir simplement car le code a déjà défini addEventListener. On va plutôt remplacer la logique.
    // En fait, on override la fonction unlockSite originale en la déclarant de nouveau plus tard.
    // Mais pour éviter les conflits, je vais redéfinir proprement.
    // Je supprime l'ancien addEventListener et je recrée une version améliorée.
    // Cependant on ne peut pas supprimer l'écouteur facilement. On va simplement ajouter un call dans le click existant. 
    // On va modifier la fonction unlockSite initiale.
    // Solution: remplacer le comportement du bouton avec une nouvelle fonction mais attention aux doublons.
    // On va supprimer l'ancien écouteur en clonant? Non plus simple: on va commenter l'ancien écouteur théorique mais comme c'est déjà écrit, le code est exécuté séquentiellement.
    // Pour être propre, je vais redéfinir complètement l'écouteur après avoir retiré l'ancien ?
    // Le script est linéaire : l'ancien écouteur est déjà attaché. Mais on peut le remplacer en enlevant d'abord via removeEventListener? Pas simple sans ref.
    // Alternative: Je vais ajouter un drapeau pour éviter double update, mais je préfère réécrire la fonction unlockSite ET remplacer l'écouteur.
    // Je vais réaffecter l'écouteur après avoir retiré l'ancien avec une copie de la fonction.
    // On va stocker les références.
    
    // Rafraichissement complet de la gestion du déverrouillage pour intégrer UI spectateur :
    const newUnlockHandler = function() {
        const code = codeInputField.value.trim();
        if (code === "") {
            lockErrorSpan.innerText = "❌ Entrez le code sacré du clan.";
            return;
        }
        if (code === MAIN_ACCESS_CODE) {
            isUnlocked = true;
            lockScreenDiv.style.display = 'none';
            clanContentDiv.style.display = 'block';
            spectatorValidated = false;
            updateSpectatorUI();
            lockErrorSpan.innerText = "";
        } else {
            lockErrorSpan.innerText = "❌ Code invalide. L'accès au clan est refusé.";
            setTimeout(() => {
                if(lockErrorSpan) lockErrorSpan.innerText = "";
            }, 2000);
        }
    };
    
    // Remplacer l'événement click
    unlockBtn.removeEventListener('click', unlockSite); // la fonction originale n'est pas nommée, mais on va remplacer
    // On va plutôt remplacer le bouton en lui attribuant un nouvel écouteur, mais l'ancien existe toujours ? On clone ?
    // Technique: On va remplacer l'élément bouton par un clone pour supprimer tous les écouteurs.
    const newUnlockBtn = unlockBtn.cloneNode(true);
    unlockBtn.parentNode.replaceChild(newUnlockBtn, unlockBtn);
    // Maintenant on travaille avec newUnlockBtn
    const finalUnlockBtn = document.getElementById('unlockBtn'); // récupérer le nouvel id
    const finalCodeInput = document.getElementById('codeInput');
    const finalLockError = document.getElementById('lockError');
    
    finalUnlockBtn.addEventListener('click', () => {
        const code = finalCodeInput.value.trim();
        if (code === "") {
            if(finalLockError) finalLockError.innerText = "❌ Entrez le code sacré du clan.";
            return;
        }
        if (code === MAIN_ACCESS_CODE) {
            isUnlocked = true;
            lockScreenDiv.style.display = 'none';
            clanContentDiv.style.display = 'block';
            spectatorValidated = false;
            updateSpectatorUI();
            if(finalLockError) finalLockError.innerText = "";
        } else {
            if(finalLockError) finalLockError.innerText = "❌ Code invalide. L'accès au clan est refusé.";
            setTimeout(() => {
                if(finalLockError) finalLockError.innerText = "";
            }, 2000);
        }
    });
    
    finalCodeInput.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') finalUnlockBtn.click();
    });
    
    // réaffecter les références pour les autres fonctions
    window.updateSpectatorUI = updateSpectatorUI;
    // Mise à jour initiale : si par hasard quelqu'un avait déjà débloqué (impossible car on vient de démarrer)
    // Par défaut lockScreen visible, clanContent caché.
    // Assurons que le contenu soit masqué et lock screen visible.
    lockScreenDiv.style.display = 'flex';
    clanContentDiv.style.display = 'none';
    isUnlocked = false;
    spectatorValidated = false;
    
    // Rafraichir les messages spectateur après tout
    // On s'assure que updateSpectatorUI fonctionne même avant déverrouillage ? pas nécessaire.
    // Réassigner les écouteurs spectateur en cas de remplacement
    const newSpectatorBtn = document.getElementById('validateSpectatorBtn');
    const newSpectatorInput = document.getElementById('spectatorCodeInput');
    if(newSpectatorBtn && newSpectatorInput) {
        // Enlever les anciens écouteurs potentiels (clonage)
        const freshBtn = newSpectatorBtn.cloneNode(true);
        newSpectatorBtn.parentNode.replaceChild(freshBtn, newSpectatorBtn);
        const finalSpecBtn = document.getElementById('validateSpectatorBtn');
        const finalSpecInput = document.getElementById('spectatorCodeInput');
        finalSpecBtn.addEventListener('click', () => {
            if (!isUnlocked) {
                alert("Veuillez d'abord déverrouiller l'accès au clan.");
                return;
            }
            const codeSpec = finalSpecInput.value.trim();
            if (codeSpec === SPECTATOR_CODE) {
                spectatorValidated = true;
                updateSpectatorUI();
                finalSpecInput.value = "";
            } else {
                spectatorValidated = false;
                updateSpectatorUI();
                const fb = document.getElementById('spectatorFeedback');
                if(fb) {
                    fb.innerHTML = "❌ Code téléspectateur incorrect. Aucun accès.";
                    setTimeout(() => { if(!spectatorValidated && isUnlocked) updateSpectatorUI(); }, 1500);
                }
            }
        });
        finalSpecInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') finalSpecBtn.click();
        });
    }
    
    // initialiser l'affichage du contenu spectateur (par défaut)
    if(clanContentDiv.style.display !== 'block') {
        // rien pour le moment
    }
    // on force l'état UI pour l'écran spectateur quand le site est lock (juste pour cohérence)
    // au cas où l'utilisateur valide spectateur avant déblocage (on gère via alert)
    console.log("ZETSU CLAN | Prêt. Code principal: PURGEZETSU2025 | Code spectateur: EYEOFZETSU");
</script>
</body>
</html>
