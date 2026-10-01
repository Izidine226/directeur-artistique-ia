# Résultats des tests — version 1.0

**Date** : 1er octobre 2026.
**Méthode** : chaque cas de [`evals.json`](evals.json) a été produit deux fois, par deux agents indépendants : l'un avec la skill `directeur-artistique`, l'autre sans. Les deux recevaient le même contexte (l'utilisateur produit avec Seedance 2.5 sur Dreamina) et les mêmes conditions (pas de recherche web, pas de question possible à l'utilisateur). Un troisième agent a noté les six dossiers avec la même rigueur, critère par critère, en citant ses preuves.

## Scores

| Cas | Avec la skill | Sans la skill | Critères échoués sans la skill |
|---|---|---|---|
| Clip electro de 30 s à 124 BPM, vertical | **14/14** | 11/14 | Aucun découpage temporel dans les prompts ; mots inutiles (« Epic scale ») ; mouvements de caméra sans vitesse ni point d'arrivée |
| Vidéo lifestyle de 20 s, « morning routine » | **14/14** | 12/14 | Un âge chiffré dans un prompt ; quatre plans sur neuf entièrement fixes |
| Mini-série thriller, 4 × 1 min | **15/16** | 11/16 | Un âge dans les 16 prompts ; plans sans mouvement ; pas d'accroche par épisode ; pas de script complet de l'épisode 1 ; deux personnages qui parlent dans le même plan |
| **Total** | **43/44 (98 %)** | **34/44 (77 %)** | |

Le seul échec avec la skill est discutable : dans la mini-série, deux plans sont volontairement fixes, avec une justification de mise en scène (la caméra ne bouge que vers celui qui ment).

## Exactitude sur Seedance

Seuls les dossiers produits **sans** la skill contenaient des affirmations fausses :
- une limite de 15 s par génération supposée pour Seedance 2.5, alors qu'elle monte à 30 s ;
- des dialogues en français présentés comme une fonction normale, alors que le français n'est pas une langue officielle de Seedance ;
- un découpage à la demi-seconde que la version 2.5 ne suit pas.

## Ce que les critères ne mesurent pas

- **La longueur** : les dossiers avec la skill font 8 000 à 8 600 mots, contre 4 100 à 6 700 sans. C'est trop pour une vidéo de 20 à 30 secondes.
- **Le temps de production** : environ trois fois plus long avec la skill, qui lit ses fichiers de référence avant d'écrire.
- **Le budget** : les dossiers avec la skill estiment 5 100 à 5 900 crédits pour le clip et 6 700 à 7 700 pour un épisode d'une minute, sans proposer de version économe.

Ces trois points sont les priorités de la version suivante.

## Limites de ce test

- Un seul passage par configuration : la variance n'est pas mesurée.
- Plusieurs critères vérifient la présence d'un élément plutôt que sa qualité ; ils passent dans les deux configurations.
- Les dossiers n'ont pas été générés réellement dans Dreamina : les tests portent sur la qualité des instructions, pas sur les vidéos obtenues.
