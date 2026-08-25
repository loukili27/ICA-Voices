# ICA Audio Source Separation

Projet pédagogique consacré à l'**Independent Component Analysis (ICA)** : modèle mathématique, hypothèses d'identifiabilité, critères d'estimation, algorithme FastICA, domaines d'application et séparation aveugle de sources audio (*cocktail party problem*).

La PCA / ACP n'est abordée qu'en complément, afin d'expliquer son rôle éventuel dans le blanchiment et de préciser quand choisir une réduction de dimension plutôt qu'une séparation de sources.

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
|-- report/
|   |-- main.tex
|   `-- figures/
`-- output/
    `-- pdf/
        `-- ICA_report.pdf
```

## Installation et exécution

```bash
python -m pip install -r requirements.txt
python -m jupyter lab
```

Ouvrir ensuite `demo_ica_audio.ipynb` et exécuter les cellules dans l'ordre depuis la racine du projet.

## Rapport

Le rapport final, disponible dans `output/pdf/ICA_report.pdf`, est centré sur l'ICA. Il développe le modèle de mélange, l'indépendance statistique, la non-gaussianité, les ambiguïtés intrinsèques, le blanchiment, la kurtosis, la négentropie, l'information mutuelle, le maximum de vraisemblance, FastICA et les principaux domaines d'utilisation. Il documente ensuite la démonstration audio et ses limites. Une courte mise en perspective avec la PCA apparaît seulement à la fin. Le code reste dans le notebook versionné et n'est pas reproduit en annexe.

## Attribution

Les mélanges audio ont été conservés depuis la version antérieure du projet publiée sous licence Apache 2.0. Voir `THIRD_PARTY_NOTICES.md` et `LICENSE-APACHE-2.0.txt`.
