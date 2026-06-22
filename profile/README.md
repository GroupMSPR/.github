# 🏥 HealthAI Coach - MSPR Project

![Repos](https://img.shields.io/badge/Repositories-7-blue)
![Stack](https://img.shields.io/badge/Stack-Laravel%20%7C%20React%20%7C%20FastAPI%20%7C%20TypeScript-brightgreen)
![Updated](https://img.shields.io/badge/Updated-2026--06--22-orange)

Bienvenue dans l'organisation **GroupMSPR** ! Ce projet est une plateforme complète de coaching santé alimentée par l'IA, composée d'une API backend robuste, d'un pipeline ETL de traitement de données, d'une interface web moderne, d'une API d'analyse IA, de dashboards de visualisation, et d'une application mobile dédiée.

---

## 📋 Table des matières

- [Vue d'ensemble](#vue-densemble)
- [Architecture du projet](#architecture-du-projet)
- [Statut des briques](#statut-des-briques)
- [Repositories](#repositories)
- [Guide de déploiement](#guide-de-déploiement)
- [Stack technologique](#stack-technologique)
- [Documentation](#documentation)
- [Contribuer](#contribuer)
- [Troubleshooting](#troubleshooting)
- [Checklist opérationnelle](#checklist-opérationnelle)

---

## Vue d'ensemble

**HealthAI Coach** est composé de **7 briques principales** :

1. **API Backend (Laravel + PostgreSQL)** - API REST pour gérer les utilisateurs, les données nutritionnelles et les métriques santé  
2. **ETL (Python)** - Pipeline d'ingestion et de transformation de données depuis Google Drive  
3. **Frontend (React + TypeScript)** - Interface utilisateur moderne et réactive  
4. **API IA (FastAPI + LLaVA/Ollama)** - Analyse d'images et extraction d'informations nutritionnelles via LLM  
5. **Grafana (Dashboards)** - Visualisation des données de santé  
6. **Mobile (TypeScript)** - Application mobile HealthAI Coach  
7. **Workspace (Orchestration)** - Point d'entrée et déploiement automatisé  

Le point d'entrée recommandé est le repository **Health-IA-Workspace**, qui automatise le déploiement de l'ensemble de la stack.

---

## Architecture du projet

```text
GroupMSPR
├── Health-IA-Workspace (Point d'entrée - Monorepo)
│   └── start.bat (Lance l'ensemble du projet)
│
├── Health-IA-Backend (API Laravel)
│   ├── API REST
│   ├── Admin Panel (Filament)
│   └── PostgreSQL
│
├── Health-IA-ETL (Pipeline Python)
│   ├── Ingestion Google Drive
│   ├── Traitement des données
│   └── Chargement PostgreSQL
│
├── Health-IA-Frontend (React)
│   ├── Interface utilisateur
│   ├── Tableau de bord
│   └── Gestion profil
│
├── Health-IA-FastAPI (Analyse IA)
│   ├── API FastAPI
│   ├── Intégration LLaVA
│   └── Analyse d'images
│
├── Health-IA-Grafana (Visualisation)
│   ├── Dashboards
│   ├── Data Sources
│   └── Visualisations
│
├── Health-IA-Mobile (Application mobile)
│   ├── Interface mobile
│   ├── Parcours utilisateur santé
│   └── Intégration API
│
└── .github (Documentation)
    └── README.md (Ce fichier)
```

---

## Statut des briques

| Brique | Repository | Environnement | Statut | Documentation |
|---|---|---|---|---|
| Workspace | [Health-IA-Workspace](https://github.com/GroupMSPR/Health-IA-Workspace) | Docker/Batch | 🟢 Actif | ✅ |
| Backend | [Health-IA-Backend](https://github.com/GroupMSPR/Health-IA-Backend) | Laravel/PostgreSQL | 🟢 Actif | ✅ |
| ETL | [Health-IA-ETL](https://github.com/GroupMSPR/Health-IA-ETL) | Python | 🟢 Actif | ✅ |
| Frontend | [Health-IA-Frontend](https://github.com/GroupMSPR/Health-IA-Frontend) | React/TypeScript | 🟢 Actif | ✅ |
| API IA | [Health-IA-FastAPI](https://github.com/GroupMSPR/Health-IA-FastAPI) | FastAPI/Ollama | 🟢 Actif | ✅ |
| Grafana | [Health-IA-Grafana](https://github.com/GroupMSPR/Health-IA-Grafana) | Dashboards | 🟢 Actif | ✅ |
| Mobile | [Health-IA-Mobile](https://github.com/GroupMSPR/Health-IA-Mobile) | TypeScript Mobile | 🟢 Actif | ✅ |

---

## Repositories

### 1. **Health-IA-Workspace** (Monorepo - Point d'entrée)
**Langue** : Batch Script  
**Repository** : [GroupMSPR/Health-IA-Workspace](https://github.com/GroupMSPR/Health-IA-Workspace)

Point d'entrée central qui orchestrate l'ensemble de la stack via Docker Compose. Contient le script `start.bat` pour un déploiement automatisé.

**Topics** : `automation`, `batch-script`, `deployment`, `devops`, `monorepo`, `workspace`

---

### 2. **Health-IA-Backend** (API Laravel)
**Langue** : PHP (Laravel)  
**Repository** : [GroupMSPR/Health-IA-Backend](https://github.com/GroupMSPR/Health-IA-Backend)

API REST complète construite avec Laravel et PostgreSQL. Gère les utilisateurs, les recettes, les exercices et les métriques santé. Inclut un panneau d'administration via Filament.

**Fonctionnalités** :
- API REST documentée (Swagger)
- Base de données PostgreSQL
- Admin Panel (Filament)
- Authentification JWT
- Migrations et seeders

**Topics** : `api-rest`, `backend`, `filament`, `laravel`, `pgsql`

---

### 3. **Health-IA-ETL** (Pipeline de données)
**Langue** : Python  
**Repository** : [GroupMSPR/Health-IA-ETL](https://github.com/GroupMSPR/Health-IA-ETL)

Pipeline Extract-Transform-Load qui récupère les données depuis Google Drive, les transforme et les charge dans PostgreSQL. Gère les erreurs et archivage automatique.

**Fonctionnalités** :
- Connexion Google Drive OAuth 2.0
- Transformation de données
- Gestion des erreurs
- Archivage automatique
- Logging détaillé

**Topics** : `clean`, `data-analysis`, `datasets`, `extract`, `load`, `python`, `transform`

---

### 4. **Health-IA-Frontend** (Interface utilisateur)
**Langue** : TypeScript (React)  
**Repository** : [GroupMSPR/Health-IA-Frontend](https://github.com/GroupMSPR/Health-IA-Frontend)

Interface moderne et réactive construite avec React, TypeScript et TailwindCSS. Consomme l'API Backend et affiche les données de santé.

**Fonctionnalités** :
- Interface responsive
- Thème moderne
- Intégration API
- Gestion d'état optimisée
- Performance optimisée

**Topics** : `frontend`, `react`, `tailwindcss`, `typescript`, `vite`

---

### 5. **Health-IA-FastAPI** (Analyse IA)
**Langue** : Python (FastAPI)  
**Repository** : [GroupMSPR/Health-IA-FastAPI](https://github.com/GroupMSPR/Health-IA-FastAPI)

API d'analyse d'images basée sur FastAPI et le modèle LLaVA via Ollama. Permet l'extraction d'informations nutritionnelles à partir d'images d'aliments.

**Fonctionnalités** :
- Analyse d'images via LLaVA
- Extraction de données nutritionnelles
- Endpoints REST documentés
- Intégration Ollama

**Topics** : `api-rest`, `fastapi`, `ia`, `llava`, `ollama`, `python`

---

### 6. **Health-IA-Grafana** (Visualisation)
**Langue** : JSON (Dashboards)  
**Repository** : [GroupMSPR/Health-IA-Grafana](https://github.com/GroupMSPR/Health-IA-Grafana)

Dashboards Grafana préconfigurés pour la visualisation des données de santé. Inclut 4 dashboards principaux : Utilisateurs, Aliments, Exercices et Métriques de santé.

**Dashboards disponibles** :
- Dashboard Users
- Dashboard Foods
- Dashboard Exercises
- Dashboard Health Metrics

**Topics** : `dashboard`, `data-visualization`, `grafana`, `graphics`

---

### 7. **Health-IA-Mobile** (Application mobile)
**Langue** : TypeScript  
**Repository** : [GroupMSPR/Health-IA-Mobile](https://github.com/GroupMSPR/Health-IA-Mobile)

Application mobile du projet HealthAI Coach, dédiée à l'expérience utilisateur sur smartphone et à l'accès mobile aux fonctionnalités de suivi santé.

**Fonctionnalités** :
- Interface mobile TypeScript
- Parcours utilisateur santé
- Intégration avec les APIs du projet

**Topics** : `mobile`, `typescript`, `healthai`

---

## Guide de déploiement

### Prérequis

- **Windows** (recommandé) ou Linux avec Docker
- **Docker Desktop** en cours d'exécution
- **Docker Compose v2** disponible
- **Ports disponibles** : 80, 55432, 3000, 4000

### Déploiement rapide (Recommandé)

```bash
# 1. Cloner le workspace
git clone https://github.com/GroupMSPR/Health-IA-Workspace.git
cd Health-IA-Workspace

# 2. Initialiser les fichiers .env
cp HealthAI-Coach/.env.example HealthAI-Coach/.env
cp ETL/.env.example ETL/.env

# 3. Lancer le déploiement
start.bat
```

### Options de déploiement

```bash
# Déploiement standard interactif
start.bat

# Mode CI/CD non-interactif
start.bat --auto

# Reset complet de la base de données
start.bat --fresh

# Reset BDD + Mode CI/CD
start.bat --auto --fresh
```

### Vérifications après déploiement

Une fois le déploiement terminé, vérifier :

✅ **API Backend** : http://localhost  
✅ **Admin Panel** : http://localhost/admin  
✅ **Swagger API** : http://localhost/api/documentation  
✅ **Grafana** : http://localhost:3000  
✅ **FastAPI** : http://localhost:4000/docs

**Identifiants Grafana** :
- Username : `admin`
- Password : `admin`

---

### Configuration PostgreSQL (DBeaver / PhpStorm)

```text
Host: localhost
Port: 55432
Database: laravel
Username: sail
Password: password
```

**Note** : Le port `55432` est volontaire pour éviter les conflits avec un PostgreSQL local.

---

### Configuration ETL

L'ETL nécessite une configuration supplémentaire :

#### 1. Structure Google Drive obligatoire

```text
ETL/
├── ToImport/          (Fichiers à traiter)
├── Archive/           (Fichiers traités)
├── Error/             (Fichiers en erreur)
└── Log/               (Journaux d'exécution)
```

#### 2. Variables d'environnement ETL

Fichier : `ETL/.env`

```env
DATABASE_URL=postgresql://sail:password@host.docker.internal:55432/laravel
GCS_BUCKET=your-bucket
TO_IMPORT_ID=<ID_ToImport>
ARCHIVE_ID=<ID_Archive>
ERROR_ID=<ID_Error>
LOG_ID=<ID_Log>
GOOGLE_TOKEN_PICKLE=<Base64_ou_path>
```

#### 3. Authentification Google Drive

1. Créer un OAuth 2.0 Client ID sur [Google Cloud Console](https://console.cloud.google.com/apis/credentials)
2. Télécharger le fichier JSON et le renommer en `credentials.json`
3. Placer le fichier dans le dossier `ETL/`
4. Initialiser le token OAuth en décommentant le code dans `ETL/utils/driveHelper.py`

---

### Configuration Grafana

#### 1. Ajouter la datasource PostgreSQL

Dans Grafana :

1. Aller dans **Connections** → **Add new connection**
2. Choisir **PostgreSQL**
3. Renseigner les paramètres :
   - **Host URL** : `host.docker.internal:55432`
   - **Database** : `laravel`
   - **User** : `sail`
   - **Password** : `password`
   - **Version** : `15`
4. Cliquer **Save and Test**

#### 2. Importer les dashboards

Chemins des fichiers JSON :

- `Grafana/usersGrafana.json`
- `Grafana/foodsGrafana.json`
- `Grafana/exercisesGrafana.json`
- `Grafana/healthMetricsGrafana.json`

Pour chaque dashboard :

1. **Create** → **Import dashboard**
2. **Upload dashboard JSON file**
3. Sélectionner le fichier JSON
4. Confirmer l'import

---

## Stack technologique

### Backend
- **Framework** : Laravel 12
- **Base de données** : PostgreSQL 15
- **API** : Lomkit REST avec Swagger
- **Admin** : Filament
- **Auth** : JWT Sanctum

### ETL
- **Langage** : Python 3.11+
- **ETL** : Custom pipeline
- **Sources** : Google Drive (OAuth 2.0)
- **Destination** : PostgreSQL

### Frontend
- **Framework** : React 18+
- **Langage** : TypeScript
- **Styling** : TailwindCSS
- **Build** : Vite
- **State Management** : React Hooks

### IA & Analyse
- **Framework** : FastAPI
- **Modèle** : LLaVA (via Ollama)
- **Analyse** : Vision par ordinateur

### Mobile
- **Langage** : TypeScript
- **Cible** : Application mobile HealthAI Coach

### Visualisation
- **Outil** : Grafana
- **Datasources** : PostgreSQL
- **Dashboards** : Personnalisés

### Infrastructure
- **Orchestration** : Docker Compose
- **Déploiement** : Scripts Batch (Windows)
- **CI/CD** : GitHub Actions

---

## Documentation

### Documentation complète

Chaque repository contient sa propre documentation :

- **[Health-IA-Workspace](https://github.com/GroupMSPR/Health-IA-Workspace)** - Guide de déploiement et architecture
- **[Health-IA-Backend](https://github.com/GroupMSPR/Health-IA-Backend)** - Documentation API et base de données
- **[Health-IA-ETL](https://github.com/GroupMSPR/Health-IA-ETL)** - Configuration ETL et sources de données
- **[Health-IA-Frontend](https://github.com/GroupMSPR/Health-IA-Frontend)** - Documentation React et composants
- **[Health-IA-FastAPI](https://github.com/GroupMSPR/Health-IA-FastAPI)** - Documentation API IA et intégration Ollama
- **[Health-IA-Grafana](https://github.com/GroupMSPR/Health-IA-Grafana)** - Dashboards et visualisations
- **[Health-IA-Mobile](https://github.com/GroupMSPR/Health-IA-Mobile)** - Application mobile et intégration API

### Ports utilisés

| Service | Port | URL |
|---|---:|---|
| API Backend | 80 | http://localhost |
| Admin Panel | 80 | http://localhost/admin |
| Swagger API | 80 | http://localhost/api/documentation |
| PostgreSQL (Windows) | 55432 | localhost:55432 |
| Grafana | 3000 | http://localhost:3000 |
| FastAPI | 4000 | http://localhost:4000/docs |

---

## Contribuer

Pour contribuer efficacement :

1. Ouvrir une **Issue** claire (bug, amélioration, tâche)
2. Créer une branche dédiée (`feature/...`, `fix/...`)
3. Ouvrir une **Pull Request** avec :
   - contexte
   - changements réalisés
   - captures (si UI)
   - checklist de tests
4. Demander une review à au moins 1 membre de l’équipe

---

## Troubleshooting

### Impossible de se connecter à localhost:55432

✓ Vérifier que vous utilisez `localhost:55432` (pas `5432`)  
✓ Vérifier que Docker Desktop est démarré  
✓ Vérifier la configuration dans DBeaver/PhpStorm

### Ancien cluster PostgreSQL incompatible

Le script `start.bat` tente une réparation automatique. En cas d'échec :

```bash
cd HealthAI-Coach
docker compose down -v
docker compose up -d --force-recreate
docker compose exec -T laravel.test php artisan migrate --seed
```

### L'ETL ne traite pas les fichiers

✓ Vérifier les IDs Google Drive dans `ETL/.env`  
✓ Vérifier la présence de `credentials.json` dans `ETL/`  
✓ Vérifier le token OAuth Google (fichier `token.pickle` ou variable `GOOGLE_TOKEN_PICKLE`)  
✓ Vérifier que les fichiers sont dans `ToImport/` (pas à la racine)

### Grafana affiche "connection refused"

Cause : Grafana tourne en conteneur, `localhost` pointe vers le conteneur lui-même.

Solution :

1. Ouvrir la datasource PostgreSQL dans Grafana
2. Remplacer **Host URL** par `host.docker.internal:55432`
3. Cliquer **Save and Test**

---

## Checklist opérationnelle

Avant de considérer la plateforme opérationnelle, vérifier :

- [ ] API disponible sur http://localhost
- [ ] Swagger disponible sur http://localhost/api/documentation
- [ ] Connexion PostgreSQL valide en localhost:55432
- [ ] Grafana accessible sur http://localhost:3000
- [ ] Swagger FastAPI disponible sur http://localhost:4000/docs
- [ ] `php artisan migrate:status` sans erreur
- [ ] ETL configuré avec IDs Drive + `credentials.json` + token OAuth
- [ ] Datasource PostgreSQL Grafana configurée en `host.docker.internal:55432`
- [ ] 4 dashboards importés (Users, Foods, Exercises, Health Metrics)

---

## 👥 Équipe

**Contributeurs MSPR** : Ilan, Anthony, Diana

---

## 📄 Licence

Tous les repositories de cette organisation sont publics et disponibles sur GitHub.

---

## 🔗 Liens rapides

| Repository | Description | Langue |
|---|---|---|
| [Health-IA-Workspace](https://github.com/GroupMSPR/Health-IA-Workspace) | Point d'entrée & orchestration | Batch |
| [Health-IA-Backend](https://github.com/GroupMSPR/Health-IA-Backend) | API REST & Base de données | PHP/Laravel |
| [Health-IA-ETL](https://github.com/GroupMSPR/Health-IA-ETL) | Pipeline de données | Python |
| [Health-IA-Frontend](https://github.com/GroupMSPR/Health-IA-Frontend) | Interface utilisateur | TypeScript/React |
| [Health-IA-FastAPI](https://github.com/GroupMSPR/Health-IA-FastAPI) | Analyse IA d'images | Python/FastAPI |
| [Health-IA-Grafana](https://github.com/GroupMSPR/Health-IA-Grafana) | Dashboards de visualisation | JSON/Grafana |
| [Health-IA-Mobile](https://github.com/GroupMSPR/Health-IA-Mobile) | Application mobile | TypeScript |

---

**Dernière mise à jour** : 22 juin 2026

Pour toute question ou problème, consultez la documentation spécifique de chaque repository ou ouvrez une issue dans le repository approprié.
