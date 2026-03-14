# Prédiction des Futures Ventes — Machine Learning & Data Engineering
> Projet personnel — Pipeline complet de prédiction de ventes mensuelles, du feature engineering au déploiement Kubernetes.

Prédiction des ventes mensuelles de produits en magasin à partir d'un dataset Kaggle de ~3 millions de lignes. Le projet couvre l'ensemble du cycle data : préparation des données, modélisation ML, exposition via API, orchestration et déploiement.

## Chiffres clés
| Métrique | Valeur |
|---|---|
| Taille du dataset | **2 935 849 lignes** |
| Features après engineering | **6 → 11** |
| Modèle | **XGBoost** |
| MAE (Mean Absolute Error) | **1.39** |
| RMSE | **5.58** |
| Déploiement | **FastAPI + Docker + Kubernetes** |
| CI/CD | **GitLab** |

## Architecture du pipeline
```
Dataset Kaggle (~3M lignes)
        │
        ▼
  Feature Engineering (Pandas)
  6 colonnes → 11 features
        │
        ▼
  Modélisation XGBoost (Scikit-learn)
  MAE : 1.39 | RMSE : 5.58
        │
        ▼
  API FastAPI (prédiction à la demande)
        │
        ▼
  Docker → Kubernetes (déploiement)
        │
        ▼
  Airflow (orchestration) + GitLab CI/CD
```

## Stack technique
| Composant | Technologie |
|---|---|
| Analyse & Préparation | Python, Pandas, Jupyter Notebook |
| Machine Learning | XGBoost, Scikit-learn |
| API | FastAPI |
| Stockage | PostgreSQL |
| Orchestration | Apache Airflow |
| Conteneurisation | Docker |
| Déploiement | Kubernetes |
| CI/CD | GitLab CI/CD |


## Structure du projet
```
.
├── Data/                   # Dataset et scripts de préparation
├── ML/                     # Notebooks : EDA, feature engineering, modélisation
├── FastAPI/                # API de prédiction
├── PostgreSQL/             # Schéma et scripts d'ingestion
├── Airflow/                # DAGs d'orchestration
├── Kubernetes/             # Manifestes de déploiement K8s
├── GitLab/                 # Configuration pipeline CI/CD
└── README.md
```

## Fonctionnalités
**Feature Engineering** — Transformation du dataset brut de 6 colonnes vers 11 features exploitables, incluant des variables temporelles et des agrégations.

**Modélisation** — Entraînement d'un modèle XGBoost optimisé pour la prédiction mensuelle des ventes. Le modèle atteint une MAE de 1.39, ce qui signifie une erreur moyenne d'environ 1 unité par prédiction sur l'ensemble de test.

**API de prédiction** — Exposition du modèle via FastAPI, permettant des prédictions à la demande avec validation des entrées.

**Orchestration** — Apache Airflow pour l'automatisation et le séquencement des étapes du pipeline (ingestion, transformation, entraînement, déploiement).

**Déploiement** — Conteneurisation Docker avec déploiement sur Kubernetes et pipeline CI/CD GitLab pour l'intégration continue.

## Lancement
```bash
# Cloner le repo
git clone https://github.com/sdlm01/Predire_les_futures_ventes.git
cd Predire_les_futures_ventes

# Lancer l'API localement
cd FastAPI
docker build -t ventes-api .
docker run -p 8000:8000 ventes-api

# Accéder à la documentation
# http://localhost:8000/docs
```

## Dataset
Source : [Kaggle](https://www.kaggle.com/) — Dataset de ventes en magasin (~3M de lignes, 6 colonnes initiales).

## Auteur
Samuel Wankebosua — Projet personnel réalisé dans le cadre d'une montée en compétences Data Engineering (2024).

## Auteur

**Samuel Wankebosua** — Projet personnel réalisé dans le cadre d'une montée en compétences Data Engineering (2024).
