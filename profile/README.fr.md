# UltiMed

[English version](https://github.com/UltiMed-Org)

> [!WARNING]
> **Publication en cours.** UltiMed v2 est en train d'être publié. Tant que cet avertissement est présent, les dépôts, les liens et les chiffres sont encore en cours de modification, et certains liens v2 ci-dessous peuvent ne pas encore fonctionner.

> [!IMPORTANT]
> **Envie d'améliorations plus rapides ?** Ce projet est entièrement autofinancé sur mon salaire au SMIC, et chaque entraînement se dispute un seul GPU grand public. Si vous ou votre organisation pouvez donner une **RTX 5090**, ou l'argent pour en acheter une d'occasion, cela accélérerait directement les prochaines versions du jeu de données et des modèles. Contactez-moi via [olicorne.org](https://olicorne.org) ou ouvrez une issue sur l'un des dépôts.

UltiMed est un projet d'[Olivier Cornelis](https://olicorne.org) pour rendre la dictée médicale vocale omniprésente et gratuite. Il produit un jeu de données synthétique de dictée médicale en français (noms de médicaments et posologies, termes du dictionnaire médical, notes cliniques, comptes rendus de radiologie, acronymes), affine parakeet-ultra (un `parakeet-tdt-0.6b-v3` de NVIDIA post-entraîné) dessus, exporte le résultat en ONNX pour qu'il tourne en local (y compris dans le navigateur), et fournit des règles regex qui corrigent les erreurs que le modèle fait encore. Tout est publié : données, code, poids et règles.

> [!WARNING]
> **La v3 est déjà prévue, et elle sera multilingue.** Les v1 et v2 sont uniquement en français.

## Version actuelle : v2

| Quoi | Où |
|---|---|
| Jeu de données | [Olicorne/UltiMed-ASR-FR-v2](https://huggingface.co/datasets/Olicorne/UltiMed-ASR-FR-v2) sur Hugging Face |
| Modèle | [Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v2-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v2-onnx) sur Hugging Face (ONNX, fp32 / fp16 / int8 / w4a8) |
| Scripts du jeu de données | [UltiMed-ASR-FR-v2-scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-scripts) : génération du texte, synthèse vocale, contrôle qualité, publication |
| Scripts d'entraînement | [UltiMed-ASR-FR-v2-NeMo_training_scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-NeMo_training_scripts) : le fork de NeMo utilisé pour affiner le modèle |
| Corrections d'erreurs | [UltiMed-ASR-FR-v2-regex-fixes](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-regex-fixes) : règles regex et tables de correspondance qui corrigent les erreurs restantes du modèle |

## L'utiliser

| Où | Application |
|---|---|
| Dans le navigateur | [parakeet_web](https://github.com/thiswillbeyourgithub/parakeet_web) : transcription locale dans une page web, avec un mode médical qui utilise le modèle et les règles UltiMed |
| Sur ordinateur | [Plumed](https://github.com/PlumedOrg/Plumed) : une application de dictée, fork de [Murmure](https://github.com/Kieirra/murmure), qui utilise le modèle et les règles UltiMed |

## Modèles associés

| Modèle | Ce que c'est |
|---|---|
| [Olicorne/parakeet-tdt-0.6b-v3-ultra-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-onnx) | Parakeet Ultra en ONNX : le `parakeet-tdt-0.6b-v3` post-entraîné par moondream, généraliste, à partir duquel le modèle UltiMed est affiné |
| [Olicorne/parakeet-tdt-0.6b-v3-redux-UltiMed-experimental-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-redux-UltiMed-experimental-onnx) | un mélange expérimental des poids du modèle parakeet redux et d'UltiMed v1, pas un vrai affinage |

## Version précédente : v1 (obsolète)

Conservée pour référence et reproductibilité. Utilisez la v2.

| Quoi | Où |
|---|---|
| Jeu de données | [Olicorne/UltiMed-ASR-FR-v1](https://huggingface.co/datasets/Olicorne/UltiMed-ASR-FR-v1) |
| Modèle | [Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v1-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v1-onnx) |
| Scripts du jeu de données | [UltiMed-ASR-FR-v1-scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-scripts) |
| Scripts d'entraînement | [UltiMed-ASR-FR-v1-NeMo_training_scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-NeMo_training_scripts) |
| Configuration de synthèse vocale | [UltiMed-ASR-FR-v1-Voxtral](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-Voxtral) : configuration Docker du TTS Voxtral utilisé pour la voix de la v1 |
