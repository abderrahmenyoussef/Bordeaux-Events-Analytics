# Bordeaux Events Analytics 🎭

Une solution complète d'analyse des événements culturels, sportifs et économiques de la métropole bordelaise.

## 📖 Description du Projet

Ce projet collecte, analyse et visualise les données d'événements se déroulant à Bordeaux et dans sa métropole. Il utilise des techniques de web scraping pour récupérer des informations depuis diverses sources (sites officiels, plateformes culturelles, venues sportives) et fournit des analyses détaillées sur la programmation événementielle.

### 🎯 Objectifs
- **Collecte automatisée** : Scraping de 12+ sources événementielles bordelaises
- **Traitement intelligent** : Normalisation des dates, catégorisation automatique, extraction de lieux
- **Analyse approfondie** : Visualisations et insights sur les tendances événementielles
- **Focus septembre 2025** : Analyse spécifique des événements du mois cible

## 🏗️ Structure du Projet

```
Bordeaux-Events-Analytics/
├── data/                              # Données du projet
│   ├── raw/                          # Données brutes collectées
│   │   ├── bordeaux_events_all_raw_*.json
│   │   ├── bordeaux_events_business_*.json
│   │   ├── bordeaux_events_cultural_*.json
│   │   ├── bordeaux_events_official_*.json
│   │   ├── bordeaux_events_platforms_*.json
│   │   ├── bordeaux_events_sports_*.json
│   │   └── metadata_collection_*.json
│   └── processed/                    # Données traitées et enrichies
│       ├── bordeaux_events_processed_*.json
│       ├── bordeaux_events_september2025_*.csv
│       ├── bordeaux_events_september2025_*.json
│       ├── september2025_*_*.json    # Par catégorie
│       ├── analysis_results_bordeaux_events.json
│       ├── insights_september_2025.json
│       └── processing_report_*.json
├── notebooks/                        # Notebooks Jupyter
│   ├── bordeaux_events_scraping.ipynb      # Phase 1: Collecte
│   ├── data_processing_pipeline.ipynb      # Phase 2: Traitement
│   └── bordeaux_events_analysis.ipynb      # Phase 3: Analyse
├── requirements.txt                   # Dépendances Python
├── README.md                         # Ce fichier
└── AMELIORATIONS.md                  # Roadmap des améliorations
```

## 🔧 Installation et Configuration

### Prérequis
- Python 3.8+
- Jupyter Notebook
- Chrome/Chromium pour Selenium

### Installation

1. **Cloner le repository**
```bash
git clone https://github.com/abderrahmenyoussef/Bordeaux-Events-Analytics.git
cd Bordeaux-Events-Analytics
```

2. **Créer un environnement virtuel**
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate     # Windows
```

3. **Installer les dépendances**
```bash
pip install -r requirements.txt
```

4. **Installer ChromeDriver pour Selenium**
```bash
# Ubuntu/Debian
sudo apt-get install chromium-chromedriver

# macOS
brew install chromedriver

# Windows
# Télécharger depuis https://chromedriver.chromium.org/
```

5. **Lancer Jupyter**
```bash
jupyter notebook
```

## 🚀 Utilisation

### Phase 1 : Collecte des Données
Ouvrir `notebooks/bordeaux_events_scraping.ipynb`

- **Sources configurées** : 12 sources réparties en 5 catégories
  - 🏛️ Sources officielles : Bordeaux Métropole, Ville de Bordeaux
  - 🎭 Sources culturelles : Opéra, Cap Sciences, Bassins des Lumières, Musée d'Aquitaine
  - ⚽ Sources sportives : UBB Rugby, Stade Matmut Atlantique
  - 💼 Sources économiques : Événements business métropolitains
  - 🌐 Plateformes : Université de Bordeaux, agendas spécialisés

- **Fonctionnalités** :
  - Web scraping respectueux avec délais aléatoires
  - Support Selenium pour sites dynamiques
  - Sauvegarde par catégorie au format JSON
  - Métadonnées de collecte détaillées

### Phase 2 : Traitement et Structuration
Ouvrir `notebooks/data_processing_pipeline.ipynb`

- **Parsing intelligent des dates** :
  - Gestion des intervalles français (ex: "16 juin - 21 septembre")
  - Détection automatique septembre 2025
  - Support des formats multiples

- **Extraction de lieux** :
  - Identification des venues spécifiques (musées, théâtres)
  - Classification par type (commune, quartier, lieu précis)
  - Géolocalisation métropolitaine

- **Catégorisation enrichie** :
  - 13 catégories automatiques (Concerts, Expositions, Sport, etc.)
  - Scoring pondéré titre/description
  - Validation manuelle possible

### Phase 3 : Analyse et Visualisation
Ouvrir `notebooks/bordeaux_events_analysis.ipynb`

- **Analyses temporelles** :
  - Distribution par mois/jour/semaine
  - Calendrier de septembre 2025
  - Pics d'activité événementielle

- **Analyses géographiques** :
  - Répartition par commune
  - Venues les plus actifs
  - Concentration géographique

- **Analyses catégorielles** :
  - Top catégories par popularité
  - Attractivité par type d'événement
  - Accessibilité (événements gratuits/payants)

- **Indicateurs de qualité** :
  - Score de données manquantes
  - Métriques de couverture
  - Diversité des sources

## 📊 Résultats et Outputs

Le projet génère plusieurs types d'outputs :

### Données Structurées
- **JSON processé** : Événements enrichis avec métadonnées
- **CSV septembre 2025** : Export Excel-compatible
- **JSON par catégorie** : Concerts, expositions, sport, etc.

### Visualisations
- **Graphiques temporels** : Calendriers, distributions
- **Charts géographiques** : Répartition par ville/lieu
- **Analyses catégorielles** : Popularité, accessibilité

### Rapports
- **Insights automatiques** : Tendances identifiées
- **Métriques de qualité** : Couverture et fiabilité des données
- **Recommandations** : Actions suggérées

## 📈 Métriques Typiques

D'après les analyses actuelles :
- **~150+ événements** collectés toutes catégories
- **56 événements** identifiés pour septembre 2025
- **5 catégories principales** : Culturel (27%), Sport (25%), Économique, Général
- **Coverage géographique** : Bordeaux centre + métropole (Pessac, Talence, Mérignac...)

## 🛠️ Technologies Utilisées

- **Web Scraping** : requests, BeautifulSoup, Selenium
- **Data Processing** : pandas, numpy, dateparser
- **Visualisation** : matplotlib, seaborn, plotly
- **Environment** : Jupyter, Python 3.8+

## 📝 Limitations Actuelles

- **Dépendance aux structures HTML** : Les sélecteurs CSS peuvent changer
- **Pas de scraping en temps réel** : Exécution manuelle requise
- **Qualité variable des données** : Selon la source et la structuration
- **Pas d'interface utilisateur** : Utilisation via notebooks uniquement

## 🔮 Améliorations Futures

Voir `AMELIORATIONS.md` pour la roadmap complète des améliorations envisagées.

## 👤 Auteur

**Abderrahmen Youssef**
- GitHub: [@abderrahmenyoussef](https://github.com/abderrahmenyoussef)

---

*Bordeaux Events Analytics - Analyser l'écosystème événementiel bordelais avec la data science* 🎯
