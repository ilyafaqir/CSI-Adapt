# Projet d'analyse d'activit�s humaines (HAR)

Ce d�p�t contient un projet de reconnaissance d'activit�s humaines bas� sur des donn�es de mouvement et des r�seaux de neurones.

## Structure du d�p�t

- `src.py` : script principal ou point d'entr�e pour le traitement et les exp�riences.
- `requirements.txt` : d�pendances Python n�cessaires pour ex�cuter le projet.

- `figure/` : visualisations ou figures g�n�r�es par le projet.
- `modele/` : mod�le entra�n� et r�sultats.
  - `best_li_har_model.pth` : mod�le PyTorch sauvegard�.
  - `results.json` : m�triques ou r�sultats d'�valuation enregistr�s.

- `Notbook/` : notebooks Jupyter d'analyse et de traitement.
  - `augmentation.ipynb` : exploration de l'augmentation de donn�es.
  - `modele.ipynb` : d�veloppement et analyse du mod�le.
  - `preprocessing.ipynb` : �tapes de pr�traitement des donn�es.
  - `visualisation.ipynb` : visualisation des donn�es et des r�sultats.

- `NTU-Fi_HAR/` : jeu de donn�es de test et d'entra�nement organis� par type d'activit�.
  - `test_amp/` : donn�es de test amplifi�es.
    - `box/`, `circle/`, `clean/`, `fall/`, `run/`, `walk/` : classes d'activit� pour le test.
  - `train_amp/` : donn�es d'entra�nement amplifi�es.
    - m�mes sous-dossiers de classes que pour `test_amp/`.

- `processed_data/` : donn�es pr�trait�es pr�tes � l'utilisation.
  - `preprocessed_test.pt`
  - `preprocessed_train_val.pt`
  - `test.pt`
  - `train_val_aug.pt`

## Objectif

Le projet vise � traiter des donn�es d'activit�s humaines, � entra�ner un mod�le de classification et � �valuer les performances sur des donn�es de test.

## Utilisation

1. Installer les d�pendances :
   ```powershell
   pip install -r requirements.txt
   ```

2. Explorer les notebooks pour comprendre les �tapes de traitement, d'augmentation, de mod�lisation et de visualisation.

3. Ex�cuter `src.py` ou les notebooks pour reproduire l'entra�nement et l'�valuation.

## Remarques

- Les donn�es brutes sont stock�es dans `NTU-Fi_HAR/`.
- Les fichiers dans `processed_data/` contiennent des versions pr�tes � l'entra�nement.
- Le mod�le entra�n� se trouve dans `modele/best_li_har_model.pth`.
- Les notebooks sont utiles pour la recherche et l'exp�rimentation.

# CSI-Adapt