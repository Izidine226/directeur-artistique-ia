# Cohérence des personnages, des lieux et du rendu

La cohérence est la plus grande difficulté de la vidéo IA. Un personnage dont le visage, la coiffure ou la tenue change d'un plan à l'autre suffit à détruire un clip ou une série. Ce fichier donne la méthode pour la tenir.

## Sommaire
1. Pourquoi ça dérive
2. La fiche personnage
3. Les images de référence
4. La ligne de rôle
5. Les verrous
6. Nommer et décrire
7. Plusieurs personnages dans le cadre
8. Le décor : le bloc géographie
9. Le rendu constant
10. Raccorder deux générations
11. La bible de série
12. Contrôle qualité

---

## 1. Pourquoi ça dérive

- Le modèle reconstruit le personnage à chaque génération à partir de ce qu'on lui donne. Moins il a d'informations précises, plus il improvise.
- Redécrire la tenue à chaque moment du déroulé, avec des mots légèrement différents, crée des variations.
- Une image de référence ambiguë (plusieurs personnes, un fond chargé, une seule vue de profil) produit des résultats ambigus.
- Changer de modèle en cours de projet change le rendu des visages.

## 2. La fiche personnage

Avant de générer quoi que ce soit, rédige une fiche par personnage récurrent. Plus elle est détaillée, plus le personnage est stable : le détail, c'est la matière de la cohérence.

```
NOM : Mara
ÂGE ET CARRURE : fin vingtaine, mince, 1,70 m
PEAU : teint mat, grain de peau visible, pores fins, taches de rousseur sur le nez
VISAGE : mâchoire carrée, sourcils épais et droits, petite cicatrice sur le menton
YEUX : marron foncé, en amande, regard direct
CHEVEUX : noirs, coupe au carré à hauteur de mâchoire, frange droite, mèches qui bougent
TENUE : veste en jean délavée, t-shirt blanc côtelé, pantalon noir large,
        baskets blanches usées, une seule bague en argent à la main droite
ALLURE : posture droite, gestes économes, calme même sous tension
VOIX : grave, posée, légère éraillure, débit lent
```

Les sept dimensions qui comptent : rôle et carrure, peau, trois ou quatre traits du visage, yeux, cheveux (en mouvement), matières des vêtements, allure.

**L'âge sert à l'écriture, pas au prompt.** Dans le prompt, traduis-le en signes visibles (`fine lines at the corners of the eyes`, `silver streak at the temple`). Les mots d'âge déclenchent des filtres et n'aident pas l'image. Ne représente jamais de mineurs.

## 3. Les images de référence

Génère les images de référence avec le modèle d'image de Dreamina, à partir de la fiche.

**Les règles :**
- **Une vue par image.** Avec Seedance 2.5, des vues séparées déclarées comme « une seule personne » fonctionnent mieux qu'une planche à plusieurs panneaux. Une seule vue de profil donne des plans tous de profil.
- **Les vues utiles** : buste de face, en pied de face, en pied de dos, et éventuellement trois quarts.
- **Fond gris moyen ou gris froid uni**, lumière douce et égale. Un fond blanc ou noir crée des halos autour du personnage.
- **Pas d'étalonnage, pas de grain** sur les références : le look se donne dans le prompt de la vidéo.
- **Une nouvelle tenue demande de nouvelles références.** Un état différent aussi : un personnage trempé ou blessé a ses propres images.
- **Pour un personnage qui parle**, ajoute une vue avec une expression franche, bouche ouverte, dents visibles. Sinon le modèle invente la bouche pendant les dialogues.
- **Pour retirer un accessoire, décris l'état voulu** (`bare head`) plutôt que de nier l'objet.

**Prompt d'image de référence (à adapter) :**
```
Character reference, single person, chest-up, facing the camera, neutral expression.
[fiche personnage en anglais]
Seamless mid-grey background, even soft studio light, no film grade, sharp focus.
```

**Visages réels** : Dreamina refuse les photos de vraies personnes en référence et interdit de reproduire une personne sans son autorisation. Travaille avec des personnages originaux.

**Enregistre chaque personnage récurrent comme Élément dans Dreamina** (« Éléments » dans l'interface française) : ses images de référence et sa voix, sous un nom que tu cites avec `@` dans tous les prompts. C'est la façon la plus simple de garder le même personnage d'une génération à l'autre (`dreamina-seedance.md`, §8).

**Si le visage dérive malgré tout** : ajoute un portrait serré et neutre à part, attribue le visage à une image et la tenue à une autre, et place ces images en tête du chargement.

## 4. La ligne de rôle

Chaque fichier chargé reçoit **sa propre ligne**, qui dit exactement ce qu'il apporte, et ce qu'il ne doit pas apporter.

```
@Image 1, @Image 2 and @Image 3 show one person, Mara: they define her face,
hair and clothing. Output exactly one Mara. Do not use the grey background.
@Image 4 defines the bar interior only, as a style reference; the characters
move through real space.
@Video 1 defines the camera movement only, seconds 0 to 6; do not use its
people, location or audio.
```

- Les numéros suivent **l'ordre de chargement par type** : la première image chargée est `@Image 1`, la première vidéo `@Video 1`. **Charge les personnages dans l'ordre de leur première apparition**, et garde la même numérotation entre l'image et l'audio d'un même personnage (Image 1 ↔ Audio 1).
- **Insère les balises avec le sélecteur `@`**, ne les tape pas. En interface française, elles s'appellent `@Vidéo 1` et `@Contenu audio 1` (`dreamina-seedance.md`, §5).
- **Ne compte pas sur un nom écrit dans une image** : lie chaque fichier à son rôle dans le texte.
- **Une ligne par sujet.** Plusieurs vues d'une même personne peuvent partager une ligne (« ces images montrent une seule personne »). Mais jamais une plage pour plusieurs personnages : « @Image 1 à @Image 4 définissent quatre personnages » est l'erreur classique qui mélange les visages.
- **Regroupe les références par catégorie** : `[Characters]`, `[Props]`, `[Scenes]`, `[Motion and Audio]`, et ajoute un verrou : `characters never swap appearances`. Un accessoire appartient à un seul personnage : `the silver lighter belongs only to the stranger`.
- **Dans une génération qui n'utilise pas toutes les références du projet, ne cite que celles dont elle a besoin.**
- Une image ne fournit que ce qu'elle montre : une image d'une seule personne ne définit jamais deux personnages.
- Une vidéo de mouvement ne transmet ni l'identité, ni le son, ni le style, sauf si tu le demandes. Un trait par vidéo de référence.
- Tu peux limiter une référence dans le temps : `only seconds 8 to 12 of @Video 1, for the gait`.
- Une image d'environnement doit être déclarée comme **référence de style**, sinon le modèle peut la figer comme une image fixe.

## 5. Les verrous

- **Première image** : pour la **verrouiller exactement**, utilise le mode « Première et dernière image » de Dreamina. Dans le mode « Références de tout type », la phrase `@Image 1 is the first frame.` (seule, suivie de la description de cette composition) guide le modèle mais ne garantit pas l'image exacte. La première et la dernière image doivent avoir le même format ; c'est la première qui le fixe.
- **Phrase de verrouillage** : `Strictly keep her face, hairstyle and outfit consistent with @Image 1 throughout.`
- **Nombre de personnages** : `exactly two characters, no duplicates`.
- **Vues multiples** : `these images show one subject; output exactly one`.
- **Chaque personnage récurrent garde sa propre référence**, même s'il apparaît aussi dans l'image du décor.

## 6. Nommer et décrire

- **Toujours le même nom.** Alterner « il », « l'homme », « le détective » fait dériver le personnage. Écris `Mara` à chaque fois.
- Avec plusieurs personnages, désigne-les par un nom ou une lettre (`Mara`, `woman A`), pas par un numéro qui pourrait se confondre avec celui d'une image.
- **Lie le nom à sa référence une seule fois**, dans le bloc des références : `Mara corresponds to @Image 1. Use only her face, hairstyle and jacket.`
- **Dans les actions, écris le nom suivi d'un repère visible, pas la balise** : `Mara — black bob, faded denim jacket — turns toward the door`. Sur Seedance 2.5, utiliser `@Image 1` comme sujet d'une phrase peut dédoubler le personnage. Sur Seedance 2.0, la convention était l'inverse : si tu travailles sur la 2.0, rappelle la balise.
- **Donne deux ou trois repères d'identité une seule fois**, dans le bloc global. Ne redécris pas la tenue à chaque moment : c'est la première cause de dérive.
- **Ne redécris jamais le décor** dans le déroulé s'il est fourni en référence.

## 7. Plusieurs personnages dans le cadre

- **Deux personnages maximum par plan.** Au-delà, les visages et les rôles se mélangent.
- **La carte du cadre d'abord, l'identité ensuite** : place chaque personnage avant de le décrire. C'est ce qui stabilise le mieux une scène à plusieurs.
  > `Mara (@Image 1) sits in the left third, foreground, facing right. The stranger (@Image 2) sits in the right third, midground, a wooden bar counter between them.`
- **Verrouille la posture** : orientation, pose, regard, et **points de contact** (pieds sur quel sol, main sur quel objet).
- **Règles de cadre** : `Neither crosses the centre of the frame. Their positions and eyelines stay the same.`
- **Différencie les personnages** sur au moins trois signes visibles : coiffure, couleur de tenue, silhouette, accessoire.
- **Donne les tailles en centimètres** (`Mara, 170 cm; the stranger, 190 cm`), sinon le modèle a tendance à les égaliser.
- **Après chaque coupe, replace tout le monde** : qui est où, tourné vers quoi. Garde la direction de l'écran, ou annonce explicitement un changement.
- **Ouvre une scène sur environ une seconde de plan large habité**, vivant mais sans action importante. Une scène d'action, elle, s'ouvre au milieu de l'action.
- **Un insert dure 0,3 à 0,5 s et a un propriétaire** : `HIS hand gripping the glass`, pas `a hand gripping a glass`.

## 8. Le décor : le bloc géographie

Pour chaque décor récurrent, écris un **bloc géographie** sans personnage, et colle-le dans chaque prompt qui s'y déroule :

```
LOCATION — the bar: a long dark wood counter runs along the left wall;
shelves of bottles glow behind it; a red neon sign on the back wall;
the entrance door is on the right, two meters from the counter;
three round tables between the counter and the window.
```

Place les personnages par rapport aux objets fixes (« au bout du comptoir, dos à la porte »), pas par rapport à l'écran (« à gauche »).

## 9. Le rendu constant

Rédige un **préfixe de style** d'environ 150 mots, une ligne par aspect, et recopie-le **à l'identique** dans chaque prompt du projet :
- le registre (`photoreal live-action`, `cel-shaded 2D animation`…) ;
- la lumière et sa logique (voir `light-color-look.md`) ;
- la palette ;
- l'optique et la vitesse d'obturation ;
- le rendu de la peau ;
- le registre de jeu (`eyes always working on someone or something`) ;
- la physique (`gravity and inertia respected, real weight, correct contact shadows`) ;
- la politique sonore (`diegetic sound only, NO BGM`).

Pas de format ni de résolution dedans : ce sont des réglages. Un synonyme suffit à décaler le rendu ; si une scène demande une exception, ajoute une ligne de surcharge plutôt que de modifier le préfixe.

## 10. Raccorder deux générations

- **Le modèle ne se souvient de rien entre deux générations.** La continuité vient de ce que tu répètes, jamais d'un renvoi (« comme au plan 9 » ne veut rien dire pour lui).
- **Dernière image → première image** : extrais la dernière image d'une génération et charge-la comme première image de la suivante. Mieux encore, quand c'est possible, donne les 3 ou 4 dernières secondes plutôt qu'une image fixe.
- **Une image fixe ne transmet ni le mouvement, ni la phase du mouvement de caméra, ni le son** : décris-les dans le texte.
- **Le fichier joint porte l'état, le prompt porte seulement le changement.** Marque ce qui est déjà fait (`the door already stands open`) et ne décris pas les actions futures.
- **Ordre d'un prompt de continuation** : une phrase qui ancre la dernière image ; le bloc identité, mot pour mot ; une phrase de liaison (`following her glance back`) ; la nouvelle action, avec `no repeated action`.
- **L'état de fin = l'état de départ** : note la pose, les accessoires, la direction du mouvement et la vitesse de la caméra en fin de génération, et reprends-les en début de la suivante.
- **Deux ou trois maillons au maximum.** Au-delà, la qualité se dégrade : repars des références d'origine. Termine une extension sur un changement d'angle, ce qui facilite le raccord suivant.
- **Dialogue** : ouvre la génération suivante avec la dernière réplique de la précédente, puis coupe au montage. La voix et le ton raccordent mieux.
- **Vidéo longue** : tiens une **chaîne d'états** d'une partie à l'autre : lieu, tenue, accessoires, heure et météo, objectif du personnage. Chaque partie hérite des dernières secondes de la précédente ; une partie faible contamine la suite.

## 11. La bible de série

Pour une mini-série ou tout projet de plus de trois plans avec un personnage récurrent :

```
# Bible — [titre]
## Ton et rendu
Logline · genre · bloc look (à recopier tel quel) · optiques · grain
## Personnages
Pour chacun : fiche complète · prompts des images de référence ·
ligne de rôle type · description de voix (à recopier telle quelle) · tenue par arc
## Décors
Pour chacun : bloc géographie · image de référence · heure et lumière
## Règles de cohérence
Modèle utilisé (ne pas en changer) · ordre de chargement des références ·
interdits (personnages en trop, changements de tenue non prévus)
## Registre de production
Pour chaque génération : prompt · références · prise gardée · pourquoi
```

## 12. Contrôle qualité

- **Les cheveux sont la dérive la plus fréquente**, puis les accessoires, puis la tenue.
- Avant de monter, **compare des images extraites** de chaque plan avec les références : visage, coiffure, tenue, accessoires.
- Une dérive qui revient à chaque prise vient du prompt ou de la référence, pas du hasard : corrige la source.
- **Ne change jamais de modèle en cours de projet.**
