# Rapport d'exploration -- Lab 0

## Équipe : Les Sentinelles

---

### Architecture Backend (par DB -- Marième Sambe)

- **Nombre de modèles Mongoose** : 2 (Restaurant et Plat)

- **Champs du modèle Restaurant** (9 champs) : nom, cuisine, adresse, telephone, description, note, image, horaires (ouverture + fermeture), estOuvert + timestamps automatiques (createdAt, updatedAt)

- **Champs du modèle Plat** (7 champs) : nom, description, prix, categorie (enum : entrée/plat principal/dessert/boisson/accompagnement), image, disponible, restaurant (ObjectId référence vers Restaurant) + timestamps automatiques

- **Relation** : Plat → Restaurant via `ObjectId ref: 'Restaurant'` (One-to-Many)

- **Nombre de routes** : 11 endpoints au total

- **Endpoints existants** :
  - `GET /api/restaurants` — Liste tous les restaurants
  - `GET /api/restaurants/:id` — Détail d'un restaurant
  - `POST /api/restaurants` — Créer un restaurant
  - `PUT /api/restaurants/:id` — Modifier un restaurant
  - `DELETE /api/restaurants/:id` — Supprimer un restaurant
  - `GET /api/plats` — Liste tous les plats
  - `GET /api/plats/restaurant/:restaurantId` — Plats d'un restaurant donné
  - `GET /api/plats/:id` — Détail d'un plat
  - `POST /api/plats` — Créer un plat
  - `PUT /api/plats/:id` — Modifier un plat
  - `DELETE /api/plats/:id` — Supprimer un plat

- **Pattern utilisé** : MVC (Modèle — Vue — Contrôleur). Flux : Client → Route → Contrôleur → Modèle → MongoDB

- **Logique de la fonction `getAll` (restaurantController.js)** : fonction asynchrone qui appelle `Restaurant.find()` pour récupérer tous les documents de la collection MongoDB, les trie par note décroissante (`.sort({ note: -1 })`) pour afficher les meilleurs restaurants en premier, puis renvoie le résultat en JSON via `res.json(restaurants)`. Les erreurs sont déléguées au middleware global via `next(error)`.

---

### Architecture Frontend (par DF -- Dialika Ndong)

- Nombre de pages : 2
- URLs : `/` (accueil), `/restaurants/[id]` (détail restaurant)
- Composants réutilisables : Header, RestaurantCard, PlatCard
- Méthode d'appel API : fetch (http://localhost:3001/api/) dans lib/api.js

---

### Configuration (par DO -- Dieynaba Cire Daff)

- Variables d'environnement : ...
- Scripts npm : ...
- Fichiers ignorés par Git : ...

---

### Tests fonctionnels (par QA -- Mamadou Mathiam Thiam)

- Fonctionnalités testées : ...
- Bugs trouvés : ...

---

### Synthèse (par CP -- Thiané Boye)

- **Ce qui fonctionne bien** : l'application démarre correctement, l'API répond, le frontend affiche les restaurants et les détails, le workflow Git collaboratif a été appliqué avec branches, issues, PR et merges
- **Ce qui manque (le 30%)** : finaliser les livrables restants du projet, notamment les extensions prévues pour les prochains labs, la conteneurisation, le déploiement en production et la validation complète du workflow Git.
