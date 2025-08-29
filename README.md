# Bordeaux Events Analytics

## Projet d'Analyse des Événements à Bordeaux

### Contexte
La ville de Bordeaux organise de nombreux événements (culturels, sportifs, économiques, etc.) chaque mois. L'objectif est de collecter, traiter et analyser les données non structurées issues du web.

### Objectifs
1. **Collecte des données** : Identifier et scraper les événements prévus à Bordeaux pour le mois à venir (septembre 2025)
2. **Traitement des données** : Nettoyer et structurer les données collectées
3. **Analyse** : Analyser les tendances et patterns des événements bordelais

### Structure du Projet
```
Bordeaux-Events-Analytics/
├── notebooks/          # Jupyter notebooks pour l'analyse et le scraping
├── data/
│   ├── raw/            # Données brutes collectées
│   └── processed/      # Données nettoyées et structurées
├── scripts/            # Scripts Python utilitaires
└── README.md           # Documentation du projet
```

### Sources de Données Identifiées
- Sites officiels de la ville de Bordeaux
- Agendas culturels locaux
- Plateformes spécialisées en événements
- Réseaux sociaux et sites d'actualités

### Installation et Utilisation
1. Installer les dépendances : `pip install -r requirements.txt`
2. Lancer Jupyter : `jupyter lab`
3. Exécuter le notebook de scraping : `notebooks/bordeaux_events_scraping.ipynb`

### Technologies Utilisées
- Python 3.x
- Jupyter Notebook
- BeautifulSoup4 / Scrapy pour le web scraping
- Pandas pour la manipulation des données
- Requests pour les requêtes HTTP
