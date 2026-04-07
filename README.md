# CLAN-
Joyboy…le respect ne se demande pas
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZETSU CLAN - Espace Officiel</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', 'Arial', sans-serif;
            min-height: 100vh;
            color: white;
        }

        /* Vidéo de fond */
        #bgVideo {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: -2;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: -1;
        }

        /* Conteneur principal */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Header du clan */
        .clan-header {
            text-align: center;
            padding: 30px;
            background: rgba(0, 0, 0, 0.6);
            border-radius: 20px;
            margin-bottom: 30px;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 215, 0, 0.3);
        }

        .clan-header h1 {
            font-size: 3em;
            letter-spacing: 5px;
            text-shadow: 0 0 20px gold;
            color: #ffd700;
        }

        .leaders {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 20px;
            font-size: 1.2em;
        }

        .leaders span {
            background: rgba(0,0,0,0.5);
            padding: 8px 15px;
            border-radius: 50px;
            border-left: 3px solid gold;
        }

        /* Vidéo principale */
        .video-section {
            background: rgba(0, 0, 0, 0.6);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 30px;
            backdrop-filter: blur(5px);
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            overflow: hidden;
            border-radius: 15px;
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        /* Formulaires */
        .auth-section, .post-section {
            background: rgba(0, 0, 0, 0.6);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 30px;
            backdrop-filter: blur(5px);
        }

        .auth-buttons {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        input, textarea, select {
            padding: 10px;
            margin: 5px;
            border-radius: 10px;
            border: none;
            background: rgba(255,255,255,0.9);
            width: 200px;
        }

        button {
            padding: 10px 20px;
            margin: 5px;
            border-radius: 10px;
            border: none;
            background: #ffd700;
            color: black;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
        }

        button:hover {
            background: #ffed4a;
            transform: scale(1.02);
        }

        .logout-btn {
            background: #dc3545;
            color: white;
        }

        /* Feed des posts */
        .feed {
            background: rgba(0, 0, 0, 0.6);
            border-radius: 20px;
            padding: 20px;
            backdrop-filter: blur(5px);
        }

        .post {
            background: rgba(255,255,255,0.1);
            border-radius: 15px;
            padding: 15px;
            margin-bottom: 20px;
            border-left: 4px solid #ffd700;
        }

        .post-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            flex-wrap: wrap;
        }

        .post-author {
            font-weight: bold;
            color: #ffd700;
        }

        .post-date {
            font-size: 0.8em;
            opacity: 0.7;
        }

        .post-content {
            margin: 10px 0;
            word-break: break-word;
        }

        .post-actions {
            display: flex;
            gap: 15px;
            margin-top: 10px;
        }

        .like-btn, .comment-btn {
            background: transparent;
            color: white;
            border: 1px solid #ffd700;
            padding: 5px 15px;
            font-size: 0.9em;
        }

        .like-btn.liked {
            background: #ffd700;
            color: black;
        }

        .comments-section {
            margin-top: 15px;
            padding-left: 20px;
            border-left: 2px solid rgba(255,215,0,0.3);
            display: none;
        }

        .comment {
            background: rgba(0,0,0,0.5);
            padding: 8px;
            margin: 5px 0;
            border-radius: 10px;
            font-size: 0.9em;
        }

        .comment-input {
            width: calc(100% - 80px);
            margin-top: 10px;
        }

        .user-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        @media (max-width: 768px) {
            .container { padding: 10px; }
            .clan-header h1 { font-size: 2em; }
            input, textarea { width: 100%; }
        }
    </style>
</head>
<body>
    <video autoplay loop muted id="bgVideo">
        <source src="https://ia800504.us.archive.org/10/items/youtube-embed-Q1WMof5utos/Q1WMof5utos.mp4" type="video/mp4">
    </video>
    <div class="overlay"></div>

    <div class="container">
        <div class="clan-header">
            <h1>⚔️ 𝐙𝐄𝐓𝐒𝐔 𝐂𝐋𝐀𝐍 ⚔️</h1>
            <div class="leaders">
                <span>👑 Chef: 𝐁𝐋𝐀𝐂𝐊 𝐓𝐎𝐁𝐈 𝐙𝐄𝐓𝐒𝐔</span>
                <span>🌸 Sous-chef: Hinata 𝐙𝐄𝐓𝐒𝐔</span>
                <span>👸 Reine: 𝙌𝙐𝙀𝙀𝙉 𝐙𝐄𝐓𝐒𝐔</span>
            </div>
        </div>

        <!-- Section Authentification -->
        <div id="authSection" class="auth-section">
            <h3>🔐 Espace 𝐙𝐄𝐓𝐒𝐔</h3>
            <div id="authForms">
                <input type="text" id="regPseudo" placeholder="Pseudo ZETSU">
                <input type="password" id="regMdp" placeholder="Mot de passe">
                <button onclick="register()">📝 S'inscrire</button>
                <hr style="margin: 15px 0;">
                <input type="text" id="loginPseudo" placeholder="Pseudo">
                <input type="password" id="loginMdp" placeholder="Mot de passe">
                <button onclick="login()">🔓 Se connecter</button>
            </div>
            <div id="userInfo" style="display:none;">
                <div class="user-info">
                    <span>👤 Connecté en tant que: <strong id="currentUser"></strong></span>
                    <button class="logout-btn" onclick="logout()">🚪 Déconnexion</button>
                </div>
            </div>
        </div>

        <!-- Vidéo du clan -->
        <div class="video-section">
            <h3>📺 Vidéo Officielle 𝐙𝐄𝐓𝐒𝐔</h3>
            <div class="video-wrapper">
                <iframe src="https://www.youtube.com/embed/Q1WMof5utos?autoplay=1&mute=0&loop=1&playlist=Q1WMof5utos" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </div>

        <!-- Zone de publication (visible seulement connecté) -->
        <div id="postSection" class="post-section" style="display:none;">
            <h3>📝 Partager avec le clan</h3>
            <textarea id="newPostContent" rows="3" placeholder="Exprime-toi, 𝐙𝐄𝐓𝐒𝐔 !" style="width:100%;"></textarea>
            <button onclick="createPost()">➕ Publier</button>
        </div>

        <!-- Feed des posts -->
        <div class="feed">
            <h3>💬 Mur du clan 𝐙𝐄𝐓𝐒𝐔</h3>
            <div id="feedContainer"></div>
        </div>
    </div>

    <script>
        // Structure des données
        let users = JSON.parse(localStorage.getItem('zetsu_users')) || [];
        let posts = JSON.parse(localStorage.getItem('zetsu_posts')) || [];
        let currentUser = localStorage.getItem('zetsu_currentUser') || null;

        // Sauvegarde automatique
        function saveData() {
            localStorage.setItem('zetsu_users', JSON.stringify(users));
            localStorage.setItem('zetsu_posts', JSON.stringify(posts));
        }

        // Inscription
        function register() {
            const pseudo = document.getElementById('regPseudo').value.trim();
            const mdp = document.getElementById('regMdp').value.trim();
            if (!pseudo || !mdp) {
                alert("Veuillez remplir tous les champs");
                return;
            }
            if (users.find(u => u.pseudo === pseudo)) {
                alert("Ce pseudo existe déjà !");
                return;
            }
            users.push({ pseudo, mdp, date: new Date().toISOString() });
            saveData();
            alert("Inscription réussie ! Connecte-toi.");
            document.getElementById('regPseudo').value = '';
            document.getElementById('regMdp').value = '';
        }

        // Connexion
        function login() {
            const pseudo = document.getElementById('loginPseudo').value.trim();
            const mdp = document.getElementById('loginMdp').value.trim();
            const user = users.find(u => u.pseudo === pseudo && u.mdp === mdp);
            if (user) {
                currentUser = pseudo;
                localStorage.setItem('zetsu_currentUser', currentUser);
                updateUI();
                loadFeed();
                alert("Bienvenue dans le clan " + pseudo + " !");
            } else {
                alert("Pseudo ou mot de passe incorrect");
            }
        }

        // Déconnexion
        function logout() {
            currentUser = null;
            localStorage.removeItem('zetsu_currentUser');
            updateUI();
            loadFeed();
        }

        // Mise à jour de l'interface selon connexion
        function updateUI() {
            const authForms = document.getElementById('authForms');
            const userInfoDiv = document.getElementById('userInfo');
            const postSection = document.getElementById('postSection');
            const currentUserSpan = document.getElementById('currentUser');

            if (currentUser) {
                authForms.style.display = 'none';
                userInfoDiv.style.display = 'block';
                postSection.style.display = 'block';
                currentUserSpan.innerText = currentUser;
            } else {
                authForms.style.display = 'block';
                userInfoDiv.style.display = 'none';
                postSection.style.display = 'none';
            }
        }

        // Créer un post
        function createPost() {
            if (!currentUser) {
                alert("Connecte-toi pour publier !");
                return;
            }
            const content = document.getElementById('newPostContent').value.trim();
            if (!content) {
                alert("Écris quelque chose !");
                return;
            }
            const newPost = {
                id: Date.now(),
                author: currentUser,
                content: content,
                date: new Date().toLocaleString(),
                likes: [],
                comments: []
            };
            posts.unshift(newPost);
            saveData();
            document.getElementById('newPostContent').value = '';
            loadFeed();
        }

        // Liker un post
        function likePost(postId) {
            if (!currentUser) {
                alert("Connecte-toi pour liker !");
                return;
            }
            const post = posts.find(p => p.id === postId);
            if (post) {
                const index = post.likes.indexOf(currentUser);
                if (index === -1) {
                    post.likes.push(currentUser);
                } else {
                    post.likes.splice(index, 1);
                }
                saveData();
                loadFeed();
            }
        }

        // Ajouter un commentaire
        function addComment(postId) {
            if (!currentUser) {
                alert("Connecte-toi pour commenter !");
                return;
            }
            const inputId = `commentInput_${postId}`;
            const commentText = document.getElementById(inputId).value.trim();
            if (!commentText) return;
            
            const post = posts.find(p => p.id === postId);
            if (post) {
                post.comments.push({
                    author: currentUser,
                    text: commentText,
                    date: new Date().toLocaleString()
                });
                saveData();
                document.getElementById(inputId).value = '';
                loadFeed();
            }
        }

        // Afficher/masquer les commentaires
        function toggleComments(postId) {
            const commentsDiv = document.getElementById(`comments_${postId}`);
            if (commentsDiv.style.display === 'none' || commentsDiv.style.display === '') {
                commentsDiv.style.display = 'block';
            } else {
                commentsDiv.style.display = 'none';
            }
        }

        // Charger le feed
        function loadFeed() {
            const container = document.getElementById('feedContainer');
            if (!container) return;
            
            if (posts.length === 0) {
                container.innerHTML = '<p style="text-align:center; padding:20px;">Aucun post pour le moment. Sois le premier 𝐙𝐄𝐓𝐒𝐔 à publier ! 🔥</p>';
                return;
            }
            
            container.innerHTML = '';
            posts.forEach(post => {
                const postDiv = document.createElement('div');
                postDiv.className = 'post';
                const isLiked = currentUser && post.likes.includes(currentUser);
                
                postDiv.innerHTML = `
                    <div class="post-header">
                        <span class="post-author">⚔️ ${post.author}</span>
                        <span class="post-date">📅 ${post.date}</span>
                    </div>
                    <div class="post-content">${post.content.replace(/</g, '&lt;').replace(/>/g, '&gt;')}</div>
                    <div class="post-actions">
                        <button class="like-btn ${isLiked ? 'liked' : ''}" onclick="likePost(${post.id})">❤️ ${post.likes.length}</button>
                        <button class="comment-btn" onclick="toggleComments(${post.id})">💬 ${post.comments.length} commentaires</button>
                    </div>
                    <div class="comments-section" id="comments_${post.id}" style="display:none;">
                        <div id="commentsList_${post.id}">
                            ${post.comments.map(c => `<div class="comment"><strong>${c.author}</strong> (${c.date}) : ${c.text.replace(/</g, '&lt;')}</div>`).join('')}
                        </div>
                        <div style="display:flex; gap:5px; margin-top:10px;">
                            <input type="text" id="commentInput_${post.id}" placeholder="Ton commentaire..." class="comment-input">
                            <button onclick="addComment(${post.id})">Envoyer</button>
                        </div>
                    </div>
                `;
                container.appendChild(postDiv);
            });
        }

        // Initialisation avec des posts d'exemple
        function initDemoPosts() {
            if (posts.length === 0) {
                posts = [
                    {
                        id: 1,
                        author: "𝐁𝐋𝐀𝐂𝐊 𝐓𝐎𝐁𝐈 𝐙𝐄𝐓𝐒𝐔",
                        content: "Bienvenue à tous les 𝐙𝐄𝐓𝐒𝐔 ! Ici c'est notre maison. Respect et honneur 🔥",
                        date: new Date().toLocaleString(),
                        likes: [],
                        comments: []
                    },
                    {
                        id: 2,
                        author: "𝙌𝙐𝙀𝙀𝙉 𝐙𝐄𝐓𝐒𝐔",
                        content: "Que la puissance des 𝐙𝐄𝐓𝐙𝐔 nous guide ✨ Postez vos exploits !",
                        date: new Date().toLocaleString(),
                        likes: [],
                        comments: []
                    }
                ];
                saveData();
            }
        }

        // Lancer l'app
        initDemoPosts();
        updateUI();
        loadFeed();
    </script>
</body>
</html>
