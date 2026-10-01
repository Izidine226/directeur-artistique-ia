# Mouvement, physique et effets visuels

Les déformations, les mains en trop, les marches qui glissent et les effets qui ont l'air collés sont les défauts les plus visibles de la vidéo IA. Ce fichier explique comment les éviter en écrivant la physique au lieu d'espérer que le modèle la devine.

## Sommaire
1. Nommer le mouvement, pas la biomécanique
2. La densité d'action
3. Remplir le plan, le finir proprement
4. La vitesse par des repères
5. Les quatre couches de mouvement
6. Les points faibles : marche, mains, objets, poids
7. Les effets visuels : les images d'abord
8. Choisir la bonne voie pour un effet
9. Le prompt de transformation
10. Les effets dans le temps
11. Créatures et échelle
12. Ancrer l'image dans le réel

---

## 1. Nommer le mouvement, pas la biomécanique

- `spinning back kick connects` fonctionne ; `left forearm rotates 45 degrees` échoue.
- Écris **la force et la direction** : `driven into the car door, metal buckling`.
- Ajoute **un adverbe de degré** (`violently`, `gently`, `explosively`) et **une conséquence physique** (`dust erupts`, `sparks fly`).
- « Rends ça plus naturel » ne fait rien. Écris la physique : `a wave rolls through the body, chest to belly to hips, on every step`.

## 2. La densité d'action

- **1 à 2 temps d'action pour 5 secondes.** La surcharge se voit tout de suite : flou, saccades, morphings.
- **Un seul régime physique par plan** : pas d'apesanteur suivie d'une chute au sol.
- Les plafonds pour 15 secondes sont dans `prompt-craft.md`, §7.

## 3. Remplir le plan, le finir proprement

- **Enchaîne 2 ou 3 actions dans la même direction** : `walks to the window, pulls the curtain aside, leans into the glass`. Sinon le temps restant est souvent rempli par l'action rejouée à l'envers.
- **Un aller-retour, ce sont deux plans.**
- **Pour une action réversible** (tendre la main puis la retirer, armer un coup), commence dans l'état : `he is already mid-swing`.
- **Termine sur un résultat stable et visible** : `the lid seats flush and stays there`.
- **Verrouille la direction** : `travels from screen-left to screen-right, locked`.

## 4. La vitesse par des repères

- **Des analogies** : `like dust suspended in honey`, `like a slammed door rebounding`.
- **Des cadences** : `one full revolution across the 10-second clip`, `tracks alongside at a steady 5 km/h, 2 m away`.
- **`fast` est le mot qui dégrade le plus l'image.** Confie la vitesse à un seul élément du plan.
- **Combat** : écris `real-time speed` et exclus le ralenti nommément.

## 5. Les quatre couches de mouvement

Décris-les séparément :
1. **le sujet** : l'action principale ;
2. **le mouvement interne** : respiration, cheveux, tissu, yeux ;
3. **la caméra** ;
4. **l'environnement** : feuilles, fumée, foule, eau.

Relie le mouvement secondaire à l'action : `the wind catches her dress on each spin`. Ne rien dire d'un élément qui doit bouger, c'est le laisser immobile : l'absence n'est pas une consigne.

## 6. Les points faibles : marche, mains, objets, poids

- **La marche** : `heel lands first, strict left-right alternation, one foot always on the ground`. Sans ça, le personnage glisse.
- **Les mains** : `only two hands in frame, both his; the left enters from the left sleeve`. Compte les mains et donne à chacune un propriétaire.
- **Les objets** : écris la chaîne causale : ce qui le tient → où la force s'applique → comment la matière réagit → l'état final. Un objet ne bouge que sous l'effet d'une cause visible.
- **Le poids** : en unités réelles : `a 75 kg man; the drop lands hard`.
- **Une ligne de physique globale** dans le préfixe : `Gravity and inertia respected; mass has real weight; correct contact shadows.`
- **Stroboscope** : `every body is in continuous motion; only the light freezes them`.
- **Pas de reflets** quand c'est évitable : miroirs et vitres sont des pièges pour le modèle.

## 7. Les effets visuels : les images d'abord

« Une mauvaise image fixe ne se rattrape pas avec le prompt vidéo. »
- **Fiches de référence** sur fond gris. Une créature : en pied, gueule fermée, gueule ouverte, sinon le crâne se déforme.
- **Décors** : choisis-les d'abord pour leur lumière.
- **Corrige les petits défauts par une retouche localisée**, jamais par une nouvelle génération complète.

## 8. Choisir la bonne voie pour un effet

| Besoin | Voie |
|---|---|
| Un changement limité dans un plan dont le déroulé doit être conservé | **Édition** de la vidéo |
| Remplacer un sujet ou ajouter un élément qui hérite du jeu du plan d'origine | **Référence multimodale**, avec le plan en vidéo de référence. Durée = celle de la source (au moins 4 s) |
| Refaire le plan autrement | **Référence multimodale**, avec le plan comme référence de mouvement uniquement |

**La loi de l'ancrage** : une transformation vidéo vers vidéo ne rend que des actions que le plan d'origine contient. Si la source ne montre pas de saut, un saut demandé sort raté à chaque fois. Dans ce cas : prends une capture du plan comme première image, écris l'action de zéro, et prévois une pause d'environ 1,5 s comme point de raccord.

**Un même défaut sur plusieurs lots** : le prompt ou la source sont en cause. Arrête-toi à la première répétition.

## 9. Le prompt de transformation

- **Préserve tout, puis change une seule chose.** Verrouille l'identité, le visage, la tenue, le jeu, le cadrage, l'optique et la caméra. Répète le verrou le plus fragile en dernier : `face and identity unchanged`.
- **L'héritage du jeu** : même posture, même angle de tête, même ouverture de bouche, même rythme de clignement, mêmes sorties de champ. `Silhouette scale and screen position match at every frame.`
- **La clause d'intégration** : grain, flou de mouvement, chute de netteté, compression et couleur identiques à la source, `indistinguishable from originally shot footage`. Ajoute la physique de la lumière :
  - la direction de la lumière principale ;
  - le rebond de l'environnement (ciel froid, sol chaud) ;
  - le voile atmosphérique sur le sujet ;
  - des ombres de contact douces ;
  - aucun halo.

  Accorder seulement la couleur donne un élément qui « a l'air collé ».

## 10. Les effets dans le temps

- Dis **où l'effet commence, comment il se propage, comment il bouge, et quelle lumière il projette** sur la peau, les surfaces et le sol.
- **Une transformation progresse** (`seams split one at a time`) ; le feu **s'allume puis grandit**.
- **Les morphings à l'écran sont fragiles.** Écris une étape intermédiaire (début → déclencheur → fissures de lumière → fin), ou cache le changement hors champ ou en silhouette.
- **Un seul effet par plan, écrit en dernier, lié à un temps d'action.**

## 11. Créatures et échelle

- **Créatures** : des mots d'imperfection (`wrinkled`, `cracked`, `asymmetric`, `mud-caked`, `matte`), jamais `smooth` ni `glossy`. Accorde la direction du soleil du décor et ajoute des ombres de contact. Garde des designs originaux, jamais une créature de franchise.
- **Échelle** : un vrai repère corporel : `the railing is 110 cm; on this 185 cm man the top rail sits just above his belt`. Un faux repère est obéi : c'est l'objet qui change de taille.
- **Géants** : `reaches just above his ankle; at least five times his height`, avec une image de référence de taille. Vends la taille avec des obstacles au premier plan et la compression d'une longue focale.
- **Verrou d'asymétrie** : `render the rider SMALLER, never larger`.

## 12. Ancrer l'image dans le réel

- **Les écrans** : l'ordre de ce qui s'affiche, plus le reflet du verre, la trame des pixels, le moiré.
- **Les défauts deviennent du contenu** quand on les rattache à un élément : `heat haze over the road, building from 20% to 70%`. Une formule générique de « réalisme » ajoutée en fin de prompt dégrade l'image.
- **Difficulté croissante** : caméra fixe < caméra embarquée sur un véhicule < caméra à l'épaule. Un éclairage de jour protège mieux l'identité qu'une nuit ou des néons.
