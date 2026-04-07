# CLAN-
Joyboy…le respect ne se demande pas
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>JOYZET - Espace verrouillé avec chat</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: auto;
            padding: 20px;
            background: #f0f2f5;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        input, button {
            padding: 10px;
            margin: 5px;
            border-radius: 10px;
            border: 1px solid #ccc;
        }
        button {
            background: #1e88e5;
            color: white;
            cursor: pointer;
        }
        #chatArea {
            margin-top: 20px;
            border-top: 2px solid #ccc;
            display: none;
        }
        #messages {
            height: 200px;
            overflow-y: auto;
            background: #f9f9f9;
            padding: 10px;
            border-radius: 10px;
        }
        .message {
            margin: 5px 0;
            padding: 5px;
            background: #e1f5fe;
            border-radius: 8px;
        }
        .error {
            color: red;
        }
    </style>
</head>
<body>
<div class="container">
    <h2>🔐 Accès sécurisé JOYZET</h2>
    <p>Entrez le code de déverrouillage :</p>
    <input type="text" id="codeInput" placeholder="Code">
    <button onclick="verifierCode()">Déverrouiller</button>
    <p id="messageErreur" class="error"></p>

    <!-- Vidéo YouTube (Short) -->
    <div id="videoArea" style="display:none; margin-top:20px;">
        <h3>🎬 Vidéo verrouillée</h3>
        <iframe width="100%" height="400" src="https://www.youtube.com/embed/Q1WMof5utos" frameborder="0" allowfullscreen></iframe>
    </div>

    <!-- Zone de chat -->
    <div id="chatArea">
        <h3>💬 Discussion entre utilisateurs</h3>
        <div id="messages"></div>
        <input type="text" id="pseudo" placeholder="Votre pseudo" style="width:30%;">
        <input type="text" id="messageInput" placeholder="Votre message" style="width:50%;">
        <button onclick="envoyerMessage()">Envoyer</button>
        <p><small>Messages stockés localement (partagés sur ce navigateur uniquement).</small></p>
    </div>
</div>

<script>
    const CODE_SECRET = "JOYZET";

    function verifierCode() {
        const codeSaisi = document.getElementById("codeInput").value.trim().toUpperCase();
        const erreurDiv = document.getElementById("messageErreur");
        const videoDiv = document.getElementById("videoArea");
        const chatDiv = document.getElementById("chatArea");

        if (codeSaisi === CODE_SECRET) {
            erreurDiv.innerText = "";
            videoDiv.style.display = "block";
            chatDiv.style.display = "block";
            chargerMessages();
        } else {
            erreurDiv.innerText = "❌ Code incorrect. Accès refusé.";
            videoDiv.style.display = "none";
            chatDiv.style.display = "none";
        }
    }

    function chargerMessages() {
        const messages = JSON.parse(localStorage.getItem("chatMessages")) || [];
        const container = document.getElementById("messages");
        container.innerHTML = "";
        messages.forEach(msg => {
            const div = document.createElement("div");
            div.className = "message";
            div.innerHTML = `<strong>${msg.pseudo}</strong> (${msg.heure}) : ${msg.texte}`;
            container.appendChild(div);
        });
        container.scrollTop = container.scrollHeight;
    }

    function envoyerMessage() {
        const pseudo = document.getElementById("pseudo").value.trim();
        const texte = document.getElementById("messageInput").value.trim();
        if (!pseudo || !texte) {
            alert("Entrez un pseudo et un message.");
            return;
        }
        const messages = JSON.parse(localStorage.getItem("chatMessages")) || [];
        const heure = new Date().toLocaleTimeString([], {hour:'2-digit', minute:'2-digit'});
        messages.push({ pseudo, texte, heure });
        localStorage.setItem("chatMessages", JSON.stringify(messages));
        document.getElementById("messageInput").value = "";
        chargerMessages();
    }

    // Initialisation : cacher vidéo et chat
    document.getElementById("chatArea").style.display = "none";
    document.getElementById("videoArea").style.display = "none";
</script>
</body>
</html>
