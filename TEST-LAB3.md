# Rapport de tests -- Lab 3: DevOps

## Équipe : Les Sentinelles
## Testeur : Dialika NDONG (QA)


## 9.1. Tests des images Docker
| # |  Test                          | OK ? | Notes           |
|---|--------------------------------|------|-----------------|
| 1 | docker build API réussit       | ok   |                 |
| 2 | docker build Frontend réussit  | ok   |                 |
| 3 | Image API < 250 Mo             | ok   | Taille : 180 Mo |
| 4 | Image Frontend < 500 Mo        | ok   | Taille : 420 Mo |

## 9.2. Tests Docker Compose
| # |       Test                        | OK ? | Notes             |
|---|-----------------------------------|------|-------------------|
| 5 | docker compose up --build réussit | ok   |                   |
| 6 | 3 conteneurs en état "Up"         | ok   |                   |
| 7 | Seed fonctionne dans le conteneur | ok   | 5 rest. + 26 plats|
| 8 | API répond sur localhost:3001     | ok   |                   |
| 9 | Frontend répond sur localhost:3000| ok   |                   |

## 9.3. Tests fonctionnels
| # |       Test                          | OK ? | Notes |
|---|-------------------------------------|------|-------|
|10 | Restaurants affichés                | ok   |       |
|11 | Commande créée via formulaire       | ok   |       |
|12 | Commande visible dans mes-commandes | ok   |       |
|13 | Données persistent après restart    | ok   |       |
|14 | docker compose down fonctionne      | ok   |       |
|15 | docker compose down -v vide la DB   | ok   |       |


### Test des endpoints API
```bash
curl http://localhost:3001/api/restaurants
curl http://localhost:3001/api/plats
curl http://localhost:3001/api/commandes
```
## 5. Résultats des endpoints API

| Endpoint           | Méthode | Statut HTTP | Résultat                   |
|--------------------|---------|-------------|----------------------------|
| /api/restaurants   | GET     | 200         | 5 restaurants retournés    |
| /api/plats         | GET     | 200         | 26 plats retournés         |
| /api/commandes     | GET     | 200         | Liste des commandes        |
| /api/commandes     | POST    | 201         | Commande créée avec succès |

---
