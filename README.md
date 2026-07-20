# 🍔 Snack Menu Manager

Une application **Full Stack** permettant de gérer le menu d'un snack grâce à une API REST et une application mobile Expo.
L'application fonctionne même sans connexion Internet grâce à une synchronisation en arrière-plan et un cache local.

---

# 📌 Présentation

Ce projet a été réalisé dans le cadre d'un projet pédagogique.

L'objectif est de développer une application complète permettant à un propriétaire de snack de gérer facilement son menu.

L'application est composée de deux parties :

* **Backend** : API REST développée avec Express et PostgreSQL
* **Mobile** : Application Expo utilisant TanStack Query avec synchronisation en arrière-plan

Le projet met principalement l'accent sur :

* Architecture propre
* Documentation API
* Gestion du cache
* Fonctionnement hors-ligne
* Synchronisation automatique

---

# ✨ Fonctionnalités

## Backend

* CRUD complet des plats
* Validation des données
* Gestion des erreurs
* Documentation OpenAPI
* Interface Scalar UI
* Base PostgreSQL avec Sequelize

## Mobile

* Liste des plats
* Ajouter un plat
* Modifier un plat
* Supprimer un plat
* Changer la disponibilité
* Synchronisation manuelle
* Synchronisation automatique en arrière-plan
* Cache local AsyncStorage
* Mode hors-ligne
* Affichage de la dernière synchronisation

---

# 🛠 Stack Technique

## Backend

* Node.js
* Express.js
* PostgreSQL
* Sequelize ORM
* OpenAPI 3
* Scalar API Reference

## Mobile

* React Native
* Expo
* Expo Router
* Axios
* TanStack Query
* Expo Task Manager
* Expo Background Task
* AsyncStorage

---

# 📂 Structure du projet

```text
snack-menu-manager/
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── docs/
│   │   ├── app.js
│   │   └── server.js
│   │
│   ├── package.json
│   └── README.md
│
├── mobile/
│   ├── app/
│   ├── components/
│   ├── hooks/
│   ├── services/
│   ├── storage/
│   ├── tasks/
│   ├── constants/
│   ├── package.json
│   └── README.md
│
└── README.md
```

---

# 🗄 Base de données

Table **plats**

| Champ      | Type               |
| ---------- | ------------------ |
| id         | SERIAL PRIMARY KEY |
| nom        | VARCHAR(100)       |
| prix       | NUMERIC(6,2)       |
| categorie  | VARCHAR(50)        |
| disponible | BOOLEAN            |
| created_at | TIMESTAMP          |

---

# 🚀 API REST

| Méthode | Endpoint       | Description              |
| ------- | -------------- | ------------------------ |
| GET     | /api/plats     | Récupérer tous les plats |
| GET     | /api/plats/:id | Récupérer un plat        |
| POST    | /api/plats     | Ajouter un plat          |
| PUT     | /api/plats/:id | Modifier un plat         |
| DELETE  | /api/plats/:id | Supprimer un plat        |

---

# 📚 Documentation API

Une documentation interactive est disponible grâce à **Scalar UI**.

```text
http://localhost:3000/docs
```

Elle contient :

* Description des endpoints
* Paramètres
* Corps des requêtes
* Réponses
* Codes HTTP
* Exemples

---

# 🔄 Synchronisation en arrière-plan

La fonctionnalité principale du projet repose sur une tâche exécutée en arrière-plan.

Fonctionnement :

1. Expo Task Manager enregistre une tâche.
2. Expo Background Task exécute la tâche selon les contraintes du système.
3. L'application récupère le menu via l'API.
4. Les données sont sauvegardées dans AsyncStorage.
5. La date de synchronisation est enregistrée.
6. En cas d'absence de réseau, les données du cache sont utilisées.
7. L'utilisateur peut également lancer une synchronisation manuelle.

---

# 📱 Fonctionnement hors-ligne

Lorsque le serveur ou Internet est indisponible :

* Les données sont chargées depuis AsyncStorage.
* Un bandeau informe l'utilisateur que l'application fonctionne en mode hors-ligne.
* La dernière synchronisation reste affichée.

---

# ⚙ Installation

## 1. Cloner le dépôt

```bash
git clone https://github.com/USERNAME/snack-menu-manager.git
```

---

## 2. Backend

```bash
cd backend

npm install

cp .env.example .env

npm run dev
```

---

## 3. Mobile

```bash
cd mobile

npm install

npx expo start
```

---

# 📌 Variables d'environnement

Backend

```env
PORT=3000

DB_HOST=localhost
DB_PORT=5432
DB_NAME=snack_db
DB_USER=postgres
DB_PASSWORD=password
```

---

# 📸 Captures d'écran

Ajouter ici :

* Liste des plats
* Formulaire
* Mode hors-ligne
* Documentation Scalar
* Dernière synchronisation

---

# 🧪 Tests

Le backend peut être testé avec :

* Postman
* Thunder Client
* Scalar UI

---

# 💡 Bonus réalisés

* Notification locale après synchronisation
* Pull To Refresh
* Optimistic Update
* Filtre par catégorie
* Recherche
* Détection réseau
* Pagination

---

# 👨‍💻 Auteur

**Marouane Ouhfid**

Full Stack Developer

GitHub : https://github.com/Ouhfi

LinkedIn : https://www.linkedin.com/in/marouan-ouhfid-a6b132237/

---

# 📄 Licence

Projet réalisé dans un objectif pédagogique.

Libre d'utilisation pour l'apprentissage.

