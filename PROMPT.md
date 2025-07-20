# webOS Prompt (VibeCoding)
Je souhaite créer un **Web OS nommé "MonumentalOS Web"**, accessible via navigateur, avec pour objectif de fournir à chaque utilisateur une **instance isolée de Linux** (VM ou conteneur), avec terminal interactif, persistance, et interface moderne.

🎯 Objectif principal :
Créer une **plateforme web** où chaque utilisateur peut se connecter et obtenir **sa propre session Linux** (Debian-based de préférence), utilisable dans le navigateur, comme un véritable OS en ligne.

🧱 Fonctionnalités et contraintes obligatoires :

1. 💻 **Virtualisation pour chaque utilisateur :**
   - Chaque utilisateur dispose de **sa propre machine virtuelle Linux ou conteneur Docker**.
   - Isolation stricte des sessions (pas une VM partagée).
   - Linux Debian, Ubuntu ou Alpine selon performance.
   - **Persistance des fichiers** par utilisateur (volumes, base de données ou disque dédié).
   - Possibilité de sauvegarder/restaurer une session.

2. 🖥️ **Affichage de la VM dans le navigateur :**
   - Utilisation de **noVNC** (ou autre solution VNC/WebGL) pour afficher une interface graphique Linux dans le navigateur.
   - OU **Web terminal type ttyd, Wetty ou Shellinabox** pour accès shell direct.

3. 🧑‍💻 **Gestion utilisateur complète :**
   - Système d’authentification sécurisé (JWT, Firebase Auth, etc.).
   - Base de données pour stocker les sessions, comptes, permissions.
   - Chaque session VM liée à un ID utilisateur.

4. 🖌️ **Interface Web OS stylisée :**
   - UI inspirée d’un OS de bureau (barre de tâches, fenêtres, notifications).
   - Responsive pour **desktop ET mobile**.
   - Codée en **React.js** (ou Vue.js, Svelte…).
   - Possibilité d’ajouter des applications natives comme :
     - Terminal
     - Explorateur de fichiers
     - Bloc-notes ou éditeur de code (ex: Monaco Editor)
     - Paramètres de la session

5. 🔐 **Sécurité :**
   - Chaque utilisateur est isolé (sandbox / user namespace / Docker avec limites).
   - Pas d’accès root par défaut.
   - Authentification obligatoire avant création de session.

6. 📦 **Stack suggérée (modifiable) :**
   - Frontend : React.js + TailwindCSS (ou autre)
   - Backend : Node.js ou Python (FastAPI, Flask…)
   - Auth : JWT ou Firebase
   - VM : Docker / QEMU / LXC
   - Affichage terminal : noVNC (GUI) ou ttyd/Wetty (CLI)
   - Base de données : MongoDB, PostgreSQL, ou SQLite (pour début)

🧪 Bonus :
- Si possible, intégrer une **IA embarquée** (genre assistant dans le terminal).
- Prévoir un système de gestion de ressources (RAM/CPU par utilisateur).
- Prévoir un mode invité temporaire, avec suppression automatique de la session.

🎯 Ce que je souhaite maintenant :
Génère-moi un **prototype fonctionnel minimal (MVP)** de cette plateforme :
- Auth utilisateur
- VM ou conteneur Linux dédié
- Affichage via noVNC ou ttyd dans le navigateur
- Interface simple mais extensible

Tu peux séparer le projet en frontend/backend et utiliser Docker pour orchestrer les services. Le but est d’avoir une base sur laquelle ajouter les fonctionnalités plus tard.
