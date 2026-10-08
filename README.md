# 🎯 Human Activity Recognition basé sur Wi-Fi CSI
## avec mécanisme d'attention et techniques d'adaptation de domaine

![Python](https://img.shields.io/badge/Python-3.10.4-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)
![License](https://img.shields.io/badge/License-Academic-green.svg)
![Master](https://img.shields.io/badge/Master-WISD-orange.svg)

---

## 📋 Description

Ce projet est un mémoire de **Master WISD (Web Intelligence et Science des Données)** portant sur la **reconnaissance d'activités humaines (HAR)** à partir des données **CSI (Channel State Information)** du Wi-Fi, avec un mécanisme d'attention multi-dimensionnel et des techniques d'adaptation de domaine.

**Problématique centrale :** Les modèles de deep learning entraînés sur un ensemble d'utilisateurs peinent à généraliser à de nouveaux individus en raison des différences morphologiques, biomécaniques et environnementales.

**Contribution principale :** Une approche d'adaptation **cross-user** en deux étapes combinant :
1. Un extracteur **CNN 2D** avec attention multi-dimensionnelle **CTSC-AB** (*Channel–Time–Subcarrier Attention Block*)
2. Un **réseau prototypique** pour l'apprentissage few-shot
3. Un **aligneur léger** entraîné sur très peu d'exemples du nouvel utilisateur

---

## 🎯 Résultats clés

| Configuration | Accuracy | Gain vs baseline |
|---|---|---|
| Domaine source (U1+U2) | **99,41 %** | Référence |
| Cross-user sans adaptation (U3) | 31,01 % | — |
| Cross-user + fine-tuning standard | 72,75 % | +41,74 pts |
| **Cross-user + notre aligneur** | **84,11 %** | **+53,29 pts** |

### Points forts
- ✅ L'aligneur comble **~77 %** de l'écart initial entre domaines
- ✅ Surpasse l'état de l'art : DASAN-MMD (74,1 %) et GAN adversarial (76,0 %)
- ✅ Coût d'annotation minimal : **10 exemples par classe** (60 échantillons)
- ✅ Temps d'adaptation réduit : **30 époques** (< 5 min sur GPU)
- ✅ Moins de **0,5 %** des paramètres totaux pour l'aligneur

---

## 📊 Jeux de données

| Dataset | Matériel | Sous-porteuses | Classes | Usage |
|---|---|---|---|---|
| **NTU-FiHAR** | Atheros CSI Tool | 114 | 6 activités | Validation intra-domaine |
| **Widar3.0** | Intel 5300 NIC | 30 | 6 gestes | Évaluation cross-user |

### Détails

**NTU-FiHAR** — 6 activités : boxe, cercle de bras, nettoyage, chute, course, marche
- Format : `3 × 114 × 500` (antennes × sous-porteuses × temps)
- 936 échantillons train / 264 test

**Widar3.0** — 6 classes les plus représentées
- **Source :** U1 + U2 → 756 train / 162 val / 162 test
- **Cible :** U3 (support : 10 exemples/classe = 60 échantillons ; test : ~180 échantillons)

---

## 🛠️ Environnement technique

| Composant | Technologie |
|---|---|
| **Langage** | Python 3.10.4 |
| **IDE** | Visual Studio Code (+ Google Colab) |
| **Deep Learning** | PyTorch, Torchvision, Einops |
| **Traitement** | NumPy, Pandas, SciPy |
| **Visualisation** | Matplotlib, OpenCV, PIL |
| **ML classique** | Scikit-learn |

