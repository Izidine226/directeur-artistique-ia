# Langage caméra — lexique de réalisation

Ce fichier sert à choisir le bon plan pour la bonne émotion, puis à l'écrire dans un prompt avec les termes anglais auxquels Seedance réagit. Les termes de prompt sont en `code` ; l'explication est en français.

## Sommaire
1. Méthode : partir de l'intention, pas de la technique
2. Valeurs de plan
3. Angles
4. Mouvements de caméra
5. Optiques, focus et profondeur de champ
6. Vitesse et temps
7. Composition (dont le vertical 9:16)
8. Transitions dans la caméra
9. Table intention → plan
10. Règles propres à la vidéo IA

---

## 1. Méthode : partir de l'intention, pas de la technique

Un mouvement de caméra n'est jamais décoratif : il dit au spectateur quoi ressentir. Avant d'écrire un mouvement, réponds à trois questions :

- **Qu'est-ce que le spectateur doit ressentir ?** (tension, émerveillement, intimité, énergie, malaise…)
- **Qu'est-ce qu'il doit regarder ?** (un visage, un objet, l'espace, la foule)
- **Qu'est-ce qui change pendant le plan ?** (une révélation, un rapprochement, une montée)

Puis choisis la valeur de plan, l'angle et le mouvement qui servent ces réponses. La section 9 donne des combinaisons éprouvées.

## 2. Valeurs de plan

| Prompt | Français | Ce qu'il montre | Usage |
|---|---|---|---|
| `extreme wide shot`, `establishing shot` | Plan de grand ensemble | Le lieu domine, le personnage est minuscule | Ouvrir, situer, solitude, échelle |
| `wide shot` | Plan d'ensemble | Le personnage en entier dans son décor | Action, déplacement, relation au lieu |
| `full shot` | Plan en pied | Le corps entier, cadré serré | Danse, tenue, gestuelle complète |
| `cowboy shot`, `medium-wide shot` | Plan américain | Mi-cuisses vers le haut | Attitude, confrontation, groupe |
| `medium shot` | Plan taille | Taille vers le haut | Dialogue, interaction, neutre |
| `medium close-up` | Plan poitrine | Poitrine vers le haut | Dialogue chargé, réaction |
| `close-up` | Gros plan | Le visage | Émotion, décision, intimité |
| `extreme close-up` | Très gros plan | Un œil, une bouche, un détail | Tension maximale, sensualité, révélation |
| `insert shot`, `macro detail shot` | Insert | Un objet, une texture | Indice, produit, rythme du montage |

En vertical 9:16, les plans serrés fonctionnent mieux : un visage remplit l'écran du téléphone. Les plans larges perdent leur force sur un petit écran, sauf si un seul élément fort ressort de l'image.

## 3. Angles

| Prompt | Français | Effet |
|---|---|---|
| `eye-level shot` | Hauteur d'yeux | Neutre, égalité, naturel |
| `low-angle shot` | Contre-plongée | Puissance, menace, héroïsme |
| `high-angle shot` | Plongée | Vulnérabilité, écrasement, solitude |
| `overhead shot`, `top-down shot`, `bird's-eye view` | Plongée totale (zénithale) | Graphique, chorégraphie, table, motifs |
| `worm's-eye view` | Contre-plongée extrême au sol | Démesure, monumentalité |
| `dutch angle`, `canted angle` | Plan débullé | Malaise, déséquilibre, folie |
| `over-the-shoulder shot` | Amorce épaule (champ-contrechamp) | Dialogue, point de vue, relation |
| `POV shot`, `first-person view` | Caméra subjective | Immersion, « tu es là » |
| `two-shot` | Plan à deux | Relation, tension ou complicité |
| `profile shot` | Plan de profil | Distance, réflexion, silhouette |

## 4. Mouvements de caméra

### Mouvements fondamentaux

| Prompt | Français | Effet / usage |
|---|---|---|
| `static shot`, `locked-off camera` | Plan fixe | Calme, observation, laisse le sujet bouger |
| `slow pan left/right` | Panoramique horizontal | Découvrir un espace, suivre un regard |
| `tilt up / tilt down` | Panoramique vertical | Révéler une hauteur, de la tête aux pieds |
| `slow push-in`, `dolly in` | Travelling avant | Tension qui monte, prise de conscience, intimité |
| `pull-out`, `dolly out` | Travelling arrière | Révélation du contexte, solitude, fin |
| `tracking shot`, `truck left/right` | Travelling latéral | Accompagner une marche, longer un décor |
| `following shot`, `camera follows behind` | Travelling d'accompagnement | Suivre un personnage, immersion |
| `leading shot`, `camera moves backward in front of the subject` | Travelling arrière devant le sujet | Le personnage avance vers nous, détermination |
| `crane up`, `jib up` | Grue montante | Envol, fin, grandeur, émotion qui s'élève |
| `crane down` | Grue descendante | Entrée dans la scène, atterrir sur un détail |
| `orbit shot`, `arc shot`, `360-degree orbit around the subject` | Travelling circulaire | Héroïsation, moment suspendu, romance, révélation |
| `pedestal up/down` | Montée/descente verticale sans basculer | Dévoiler un élément au-dessus ou en dessous |

### Mouvements à texture

| Prompt | Français | Effet / usage |
|---|---|---|
| `handheld camera`, `shaky handheld` | Caméra à l'épaule | Urgence, documentaire, chaos, réalisme |
| `smooth gimbal shot`, `steadicam` | Caméra stabilisée | Fluidité, plan-séquence, glisse |
| `slow zoom in` | Zoom lent | Inquiétude, style années 70, observation |
| `crash zoom`, `snap zoom` | Zoom brutal | Comédie, choc, énergie clip |
| `whip pan` | Panoramique filé | Transition énergique, surprise, comédie |
| `rack focus from X to Y` | Bascule de point | Déplacer l'attention, révéler un second plan |
| `dolly zoom`, `vertigo effect` | Effet Vertigo (travelling compensé) | Vertige, choc émotionnel, réalisation brutale |
| `snorricam`, `body-mounted camera` | Caméra fixée au corps | Ivresse, panique, perte de contrôle |

### Mouvements spectaculaires (très efficaces en IA)

| Prompt | Français | Effet / usage |
|---|---|---|
| `aerial drone shot`, `drone flyover` | Plan aérien | Échelle, ouverture, paysage |
| `FPV drone shot diving through…` | Drone FPV | Énergie folle, traversée de lieux, intro de clip |
| `fly-through shot through the window/keyhole` | Traversée d'objet | Transition magique, entrée dans un monde |
| `one continuous take`, `single long take` | Plan-séquence | Immersion totale, virtuosité |
| `bullet time`, `frozen moment, camera orbits` | Temps figé, caméra qui tourne | Moment iconique, action, danse |
| `low tracking shot at ground level` | Travelling ras du sol | Vitesse, pas qui frappent le sol |
| `top-down tracking shot` | Travelling zénithal | Graphique, foule, chorégraphie |
| `reveal shot, camera rises from behind the bar` | Révélation par un obstacle | Découverte, suspense, entrée de lieu |

## 5. Optiques, focus et profondeur de champ

| Prompt | Français | Rendu |
|---|---|---|
| `14mm ultra-wide lens`, `fisheye lens` | Très grand angle, fish-eye | Déformation, énergie, skate, clip hip-hop |
| `24mm wide-angle lens` | Grand angle | Espace, immersion, proximité dynamique |
| `35mm lens` | 35 mm | Naturel, documentaire, regard humain |
| `50mm lens` | 50 mm | Neutre, proche de l'œil |
| `85mm portrait lens` | 85 mm | Visage flatteur, fond flou, intimité |
| `135mm telephoto lens`, `long lens compression` | Longue focale | Arrière-plan écrasé, voyeurisme, foule compressée |
| `macro lens` | Macro | Texture, gouttes, produit, matière |
| `anamorphic lens, oval bokeh, horizontal lens flares` | Anamorphique | Cinéma, flares bleus horizontaux, bokeh ovale |
| `shallow depth of field`, `creamy bokeh` | Faible profondeur de champ | Isole le sujet, rend le fond doux |
| `deep focus` | Grande profondeur de champ | Tout est net, composition en couches |
| `tilt-shift lens, miniature effect` | Bascule-décentrement | Monde miniature, ville jouet |

Pour un personnage, une focale longue avec un fond flou dit « regarde cette personne ». Un grand angle proche du visage dit « tu es avec elle, dans son espace ».

## 6. Vitesse et temps

| Prompt | Français | Usage |
|---|---|---|
| `slow motion`, `120fps slow motion` | Ralenti | Moment suspendu, danse, liquides, cheveux, impact |
| `speed ramp from real-time to slow motion` | Rampe de vitesse | Clip, sport, transition énergique |
| `timelapse` | Accéléré fixe | Passage du temps, ciel, foule, montage de lieu |
| `hyperlapse` | Accéléré en mouvement | Traversée de ville, voyage |
| `freeze frame` | Arrêt sur image | Ponctuation comique, présentation de personnage |
| `reverse motion` | Image inversée | Surréalisme, effet de rembobinage |

## 7. Composition (dont le vertical 9:16)

- `rule of thirds composition` : le sujet sur une ligne des tiers, naturel et dynamique.
- `centered symmetrical composition` : symétrie frontale, style très graphique, solennel ou décalé.
- `leading lines` : les lignes du décor mènent l'œil vers le sujet.
- `negative space` : beaucoup de vide autour du sujet, solitude, élégance.
- `frame within a frame` : cadrer à travers une porte, une fenêtre, un miroir.
- `foreground elements`, `layered depth` : un premier plan flou, puis le sujet, puis le fond ; ça donne de la profondeur et un vrai rendu cinéma.

**Spécificités du vertical 9:16** :
- Garde le sujet dans la bande verticale centrale. Le haut et le bas de l'écran sont couverts par l'interface (pseudo, légende, boutons), donc rien d'important dans les ~15 % du haut et les ~25 % du bas.
- Privilégie le mouvement vertical : `tilt`, `crane`, chute, montée. Il exploite la hauteur de l'écran.
- Un visage en gros plan remplit l'écran : c'est la valeur la plus forte en vertical.
- Précise toujours le format dans le prompt ou les réglages : `vertical 9:16 composition`.

## 8. Transitions dans la caméra

Quand plusieurs plans sont générés séparément puis montés, ou quand une seule génération enchaîne plusieurs plans :

| Prompt | Français | Usage |
|---|---|---|
| `match cut on the shape of…` | Raccord par la forme | Relier deux lieux ou époques par une forme commune |
| `whip pan transition` | Transition filée | Changement de lieu énergique |
| `seamless morph transition from X into Y` | Morphing | Transformation, effet IA signature |
| `object wipe, a passing object fills the frame` | Volet par un objet | Raccord invisible entre deux plans |
| `camera flies through X into a new scene` | Traversée | Entrée dans un autre monde |
| `flash to white transition` | Flash blanc | Ellipse, souvenir, choc |
| `match on action` | Raccord dans le mouvement | Fluidité, le geste continue d'un plan à l'autre |

Pour un montage final propre, termine chaque génération sur une image facile à raccorder : un mouvement qui continue, un objet qui remplit le cadre, ou un plan fixe stable.

## 9. Table intention → plan

| Intention | Valeur | Angle | Mouvement | Optique |
|---|---|---|---|---|
| Tension qui monte | Gros plan → très gros plan | Hauteur d'yeux | `slow push-in` | 85 mm, faible profondeur |
| Puissance, héros | Plan américain ou pied | Contre-plongée | `slow orbit` ou `crane up` | 24-35 mm |
| Vulnérabilité, solitude | Plan d'ensemble | Plongée | `slow pull-out` | Grand angle, espace négatif |
| Émerveillement | Grand ensemble | Montée | `crane up`, `drone reveal` | Grand angle |
| Intimité, romance | Gros plan, plan à deux | Hauteur d'yeux | `slow orbit`, quasi fixe | 85 mm, bokeh crémeux |
| Énergie, fête, clip | Variable | Bas, ras du sol | `FPV`, `whip pan`, `speed ramp` | Grand angle, fish-eye |
| Chaos, urgence | Plan taille serré | Variable | `handheld`, `crash zoom` | 24-35 mm |
| Malaise, folie | Gros plan | `dutch angle` | `dolly zoom`, `snorricam` | Grand angle déformant |
| Mystère, révélation | Insert → plan large | Variable | `rack focus`, `reveal shot` | Longue focale |
| Nostalgie, souvenir | Plan moyen | Hauteur d'yeux | Lent, flottant | 50 mm, grain, halation |
| Comédie | Plan fixe frontal | Frontal | `crash zoom`, `freeze frame` | Symétrie |

## 10. Règles propres à la vidéo IA

- **Un mouvement principal par plan**, avec au plus un modificateur (`slow dolly-in, slightly handheld`), jamais deux mouvements opposés. Empiler les mouvements est la première cause de saccades et de caméra qui tourne. Pour une évolution, des phases chronométrées : `rises 0-3s, holds, then pushes in 4-8s`.
- **Précise la vitesse** (`prompt-craft.md`, §9). Sans indication, le modèle choisit un mouvement moyen et mou.
- **Décris le début et la fin du cadre, la distance et la durée.** `slow dolly push from a medium shot to a tight close-up over 8 seconds`. Un mouvement sans point d'arrivée revient en arrière.
- **`zoom` donne un zoom optique.** Pour déplacer la caméra : `push in`, `dolly in`, `pull back`.
- **Un panoramique filé a besoin d'au moins 0,8 s de flou**, sinon il devient une simple coupe.
- **Chaque coupe change à la fois la valeur de plan et le mode de caméra** (épaule, fixe, travelling, grue, aérien). Jamais trois coupes de suite identiques.
- **La caméra bouge avec l'acteur**, pas selon sa propre horloge. Avec plusieurs sujets, dis lequel elle suit.
- **Optique en champ de vision** : certains guides trouvent les degrés plus fiables que les millimètres (84° large, 63° observation, 47° neutre, 29° buste en dialogue, 12° insert). À tester ; avec des millimètres, ajoute l'ouverture (`85mm f/1.4`).
- **Ancre le mouvement dans l'espace.** `camera moves between the tables toward the stage` vaut mieux que `camera moves forward`.
- **Le sujet bouge OU la caméra bouge fort, rarement les deux au maximum.** Une danse frénétique filmée en FPV rapide multiplie les déformations.
- **Copie un mouvement par référence.** Quand Dreamina permet de fournir une vidéo de référence, c'est la façon la plus fiable d'obtenir un mouvement précis (voir `dreamina-seedance.md`).
