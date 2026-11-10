# Évaluation des métriques en Computer Vision

Projet réalisé dans le cadre du **Master Data & IA**. Ce dépôt contient un notebook Python destiné à expliquer et illustrer les métriques d'évaluation de trois tâches de vision par ordinateur : **Image Generation**, **Object Detection** et **Object Tracking**.

## Notebook

**Fichier :** [`Evaluation_Computer_Vision.ipynb`](./Evaluation_Computer_Vision.ipynb)

[Ouvrir le notebook dans Google Colab](https://colab.research.google.com/github/oussamaOugouzale/computer-vision-evaluation/blob/main/Evaluation_Computer_Vision.ipynb)

> Le lien Colab sera accessible après la publication du notebook sur GitHub.

## Métriques étudiées

| Tâche | Métriques | Objectif |
| --- | --- | --- |
| **Image Generation** | FID, KID, CLIPScore | Comparer les distributions des images et vérifier leur correspondance avec un texte. |
| **Object Detection** | IoU, précision, rappel, AP, mAP | Mesurer la localisation des objets et la qualité des détections. |
| **Object Tracking** | MOTA, IDF1, HOTA | Évaluer les détections et la conservation des identités dans le temps. |

## Exécution dans Google Colab

1. Cliquer sur **Ouvrir le notebook dans Google Colab** ci-dessus, ou importer manuellement le fichier `.ipynb` dans [Google Colab](https://colab.research.google.com/).
2. Choisir **Exécution → Tout exécuter**.
3. Consulter les graphiques, les valeurs calculées et les interprétations après chaque section.

La partie principale utilise **NumPy, SciPy, Matplotlib et Pillow**, disponibles dans l'environnement Colab habituel. **Aucun GPU n'est nécessaire** pour ces exemples.

## Organisation du notebook

- **01 — Image Generation :** visualisation de vecteurs de caractéristiques synthétiques, calculs pédagogiques de FID/KID, explication de CLIPScore.
- **02 — Object Detection :** calcul de l'IoU entre deux boîtes, distinction TP/FP/FN, précision et rappel, courbe précision–rappel et mAP simplifié.
- **03 — Object Tracking :** suivi de deux objets sur trois frames, illustration d'un *identity switch*, calcul de MOTA/IDF1 et illustration de HOTA.
- **04 — Synthèse :** tableau comparatif des métriques.
- **Annexe facultative :** exemples avec **TorchMetrics** (FID, KID, mAP) et un modèle **CLIP** pré-entraîné. Ces cellules sont désactivées par défaut et peuvent télécharger des dépendances ou des poids de modèles.

Le code est commenté et les résultats sont accompagnés de courtes explications en français.

## Important : portée des résultats

Les données de la démonstration sont **fictives ou synthétiques** : il ne s'agit pas d'un benchmark ni d'une mesure des performances d'un modèle entraîné.

- **FID et KID :** calculés sur des vecteurs 2D simulés, sans extraction de caractéristiques Inception dans la partie principale.
- **CLIPScore :** expliqué au moyen de vecteurs inventés ; le calcul avec un vrai modèle CLIP se trouve dans l'annexe facultative.
- **AP / mAP :** version pédagogique utilisant une image, une classe et une interpolation à 101 niveaux de rappel ; elle ne couvre pas toutes les règles d'une évaluation COCO complète.
- **HOTA :** illustration à seuil fixe ; une évaluation officielle utilise notamment plusieurs seuils et un outil dédié comme [TrackEval](https://github.com/JonathonLuiten/TrackEval).

## Références

- [TorchMetrics — FID](https://lightning.ai/docs/torchmetrics/stable/image/frechet_inception_distance.html)
- [TorchMetrics — KID](https://lightning.ai/docs/torchmetrics/stable/image/kernel_inception_distance.html)
- [TorchMetrics — mAP](https://lightning.ai/docs/torchmetrics/stable/detection/mean_average_precision.html)
- [COCO — Detection Evaluation](https://cocodataset.org/#detection-eval)
- [CLIPScore — article](https://aclanthology.org/2021.emnlp-main.595/)
- [HOTA — article](https://doi.org/10.1007/s11263-020-01375-2)

## Auteur

**Oussama Ougouzale** — Master Data & IA, 2026.
