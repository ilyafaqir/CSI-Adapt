# Projet d'analyse d'activités humaines (HAR)

Ce dépôt contient un projet de reconnaissance d'activités humaines basé sur des données de mouvement et des réseaux de neurones.

## Structure du dépôt

- `src.py` : script principal ou point d'entrée pour le traitement et les expériences.
- `requirements.txt` : dépendances Python nécessaires pour exécuter le projet.

- `figure/` : visualisations ou figures générées par le projet.
- `modele/` : modèle entraîné et résultats.
  - `best_li_har_model.pth` : modèle PyTorch sauvegardé.
  - `results.json` : métriques ou résultats d'évaluation enregistrés.

- `Notbook/` : notebooks Jupyter d'analyse et de traitement.
  - `augmentation.ipynb` : exploration de l'augmentation de données.
  - `modele.ipynb` : développement et analyse du modèle.
  - `preprocessing.ipynb` : étapes de prétraitement des données.
  - `visualisation.ipynb` : visualisation des données et des résultats.

- `NTU-Fi_HAR/` : jeu de données de test et d'entraînement organisé par type d'activité.
  - `test_amp/` : données de test amplifiées.
    - `box/`, `circle/`, `clean/`, `fall/`, `run/`, `walk/` : classes d'activité pour le test.
  - `train_amp/` : données d'entraînement amplifiées.
    - mêmes sous-dossiers de classes que pour `test_amp/`.

- `processed_data/` : données prétraitées prêtes à l'utilisation.
  - `preprocessed_test.pt`
  - `preprocessed_train_val.pt`
  - `test.pt`
  - `train_val_aug.pt`

## Objectif

Le projet vise à traiter des données d'activités humaines, à entraîner un modèle de classification et à évaluer les performances sur des données de test.

## Utilisation

1. Installer les dépendances :
   ```powershell
   pip install -r requirements.txt
   ```

2. Explorer les notebooks pour comprendre les étapes de traitement, d'augmentation, de modélisation et de visualisation.

3. Exécuter `src.py` ou les notebooks pour reproduire l'entraînement et l'évaluation.

## Remarques

- Les données brutes sont stockées dans `NTU-Fi_HAR/`.
- Les fichiers dans `processed_data/` contiennent des versions prêtes à l'entraînement.
- Le modèle entraîné se trouve dans `modele/best_li_har_model.pth`.
- Les notebooks sont utiles pour la recherche et l'expérimentation.
