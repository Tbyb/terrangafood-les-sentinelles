# Rapport d'exploration -- Lab 0

## Équipe : Les Sentinelles

### Configuration (par DO -- Dieynaba cire Daff)
**Variables d'environnement (`.env.example`) :**

| Variable              | Rôle                        | Exemple                                                    |
|-----------------------|-----------------------------|------------------------------------------------------------|
| `MONGODB_URI`         | Connexion à MongoDB         | `mongodb+srv://user:pass@cluster.mongodb.net/terrangafood` |
| `PORT`                | Port de l'API Express       | `3001`                                                     |
| `NEXT_PUBLIC_API_URL` | URL appelée par le frontend | `http://localhost:3001/api`                                |

> Le fichier `.env.example` sert de modèle. Chaque développeur le copie en `.env` et y met ses propres valeurs (identifiants, mots de passe). Le `.env` n'est jamais commité pour des raisons de sécurité.

---

**Scripts npm définis :**

**API (backend) :**
| Script  | Commande                | Description                               |
|---------|-------------------------|-------------------------------------------|
| `dev`   | `nodemon src/app.js`    | Lance l'API avec rechargement automatique |
| `start` | `node src/app.js`       | Lance l'API en mode production            |
| `seed`  | `node src/seed/seed.js` | Remplit la base avec des données initiales|

**Web (frontend Next.js) :**
| Script      | Commande     | Description                                   |
|-------------|--------------|-----------------------------------------------|
| `dev`       | `next dev`   | Lance le serveur de développement (port 3000) |
| `build`     | `next build` | Construit l'application pour la production    |
| `start`     | `next start` | Lance l'application en production             |
| `lint`      | `next lint`  | Vérifie la qualité du code                    |

---
**Fichiers ignorés par Git (`.gitignore`) :**

| Fichier/Dossier          | Raison de l'ignorance                                  |
|--------------------------|--------------------------------------------------------|
| `node_modules/`          | Trop volumineux, se réinstalle avec `npm install`      |
| `.env`                   | Contient des secrets (mots de passe, clés API)         |
| `.next/`, `dist/`        | Fichiers générés par le build, propres à chaque machine|
| `*.log`                  | Fichiers journaux, inutiles pour les autres développeurs|
| `.DS_Store`, `Thumbs.db` | Fichiers spécifiques au système d'exploitation          |
| `.vscode/`, `.idea/`     | Configurations personnelles d'IDE                       |

> Règle d'or : on ne commit que le code source, jamais les fichiers générés, les dépendances ou les secrets.

---

**Remarques complémentaires :**
- L'API tourne sur le port **3001**, le frontend sur le port **3000**
- Les deux serveurs doivent tourner simultanément pour que l'application fonctionne
- La connexion à MongoDB Atlas a nécessité l'ajout de l'IP `0.0.0.0/0` dans Network Access

---