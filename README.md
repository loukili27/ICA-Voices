# ICA Audio Source Separation

Projet pédagogique consacré à l'**Independent Component Analysis (ICA)** et à son application au problème de séparation aveugle de sources audio (*cocktail party problem*).

Le projet met notamment en évidence la différence entre :

- **PCA / ACP**, qui recherche des directions orthogonales maximisant la variance ;
- **ICA / ACI**, qui recherche des composantes aussi indépendantes et non gaussiennes que possible.

## Démonstration

Le notebook charge trois mélanges audio mono, applique `FastICA`, visualise les signaux, exporte les composantes estimées et calcule plusieurs contrôles numériques.

Résultats obtenus sur les fichiers fournis :

- 264 515 échantillons par mélange, à 44 100 Hz ;
- convergence de FastICA en 4 itérations avec la graine utilisée ;
- corrélations linéaires finales proches de zéro ;
- erreur relative de reconstruction d'environ `4.22e-16`.

Ces mesures ne remplacent pas une évaluation avec les sources originales. L'ordre, le signe et l'échelle des composantes ICA sont indéterminés.

## Structure

```text
.
|-- demo_ica_audio.ipynb
|-- requirements.txt
|-- data/
|   `-- mixtures/
|-- outputs/
|   `-- separated/
`-- report/
    |-- main.tex
    |-- ICA_report_draft.pdf
    `-- figures/
```

## Installation et exécution

```bash
python -m pip install -r requirements.txt
python -m jupyter lab
```

Ouvrir ensuite `demo_ica_audio.ipynb` et exécuter les cellules dans l'ordre depuis la racine du projet.

## Rapport

Le rapport LaTeX est en cours de révision. Sa version finale comparera explicitement PCA et ICA et présentera les résultats de la démonstration sans inclure le code complet en annexe.

## Attribution

Les mélanges audio ont été conservés depuis la version antérieure du projet publiée sous licence Apache 2.0. Voir `THIRD_PARTY_NOTICES.md` et `LICENSE-APACHE-2.0.txt`.
