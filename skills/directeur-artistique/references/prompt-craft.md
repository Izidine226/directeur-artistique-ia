# Construire un prompt Seedance 2.5

Ce fichier explique comment écrire un prompt que Seedance exécute fidèlement. À lire à chaque production, avec `dreamina-seedance.md` pour les limites de la plateforme.

## Sommaire
1. Choisir le mode avant d'écrire
2. Les principes
3. Les réglages vont dans l'interface
4. L'ordre d'écriture et la longueur
5. La structure d'une génération longue
6. Le déroulé temporel
7. La densité : actions et plans
8. La caméra comme une spécification
9. Les mots de vitesse
10. Les coupes et les transitions
11. Les négations
12. Les mots inutiles
13. La langue du prompt
14. Modèles prêts à l'emploi
15. La vérification avant envoi
16. Itérer

---

## 1. Choisir le mode avant d'écrire

Seedance 2.5 n'attend pas le même type de prompt selon le mode. Choisis-le d'abord (noms exacts dans `dreamina-seedance.md`) :

| Besoin | Mode | Le prompt est… |
|---|---|---|
| Une vidéo à partir de mots | Texte vers vidéo | une description de scène |
| Une vidéo à partir de tes fichiers : personnages, décors, première ou dernière image, mouvement à copier, musique | Référence multimodale | une **carte des rôles** + la scène |
| Changer un seul élément d'une vidéo existante | Édition | **maître unique + périmètre + liste de ce qui ne change pas** |
| Ajouter des images avant ou après une vidéo | Extension | un **contrat de raccord** + le nouveau contenu |

La première et la dernière image imposées, les images clés et les storyboards relèvent tous de la référence multimodale.

## 2. Les principes

- **Seulement ce qu'une caméra ou un micro peut capter.** « Une ambiance mystérieuse » ne se filme pas ; « une seule lampe qui grésille au fond du couloir », oui.
- **Le comportement plutôt que l'apparence.** Décrire longuement un visage et oublier ce que fait le personnage est l'erreur la plus courante.
- **Écris le mouvement, pas le résultat.** `walks to the far door` plutôt que `recedes`. Des verbes concrets : `slams`, `pivots`, `lunges`, `exhales`, `grips`.
- **Des termes mesurables** : secondes, mètres, km/h, pourcentage du cadre. Une bonne question : une caméra pourrait-elle mesurer ça ?
- **Des repères visibles, jamais un âge.** `a lean courier in a soaked parka`, pas `a 22-year-old courier`. Les mots d'âge déclenchent des filtres et n'aident pas l'image.
- **Le bloc identité ne bouge pas, le bloc action varie.** Visage, carrure, signes distinctifs et tenue se recopient mot pour mot d'un prompt à l'autre ; l'action, la caméra et le décor changent. Mélanger les deux déforme les visages.
- **Chaque prompt se suffit à lui-même.** Le modèle ne se souvient de rien entre deux générations : pas de « comme au plan 3 », pas de « idem ». Répète ce qui doit rester fixe.
- **À partir d'une image de départ, décris seulement ce qui change.** `Starting from the provided image as the first frame,` puis l'action et un mouvement de caméra. Redécrire l'image donne un plan presque figé.
- **Couleur + matière + lumière** plutôt que des adjectifs : `marble counter, brass machine, warm tungsten pendant`.

## 3. Les réglages vont dans l'interface

La durée, le format (9:16, 16:9…), la résolution et le modèle se règlent dans Dreamina. Dans le dossier de réalisation, indique-les à part sous **Réglages**.

Le guide de Dreamina ouvre parfois ses exemples par une ligne de structure (`30 seconds, 16:9, four connected shots.`). Tu peux le faire pour annoncer le nombre de plans, à condition que la durée et le format soient **identiques** aux réglages : une contradiction entre le texte et l'interface fait échouer les générations à plusieurs plans.

## 4. L'ordre d'écriture et la longueur

**L'attention du modèle va de gauche à droite.** L'ordre fiable :

**sujet → action → caméra → style → contraintes**

- Le sujet et l'action dans les **20 à 30 premiers mots**.
- La caméra en troisième position : placée en tête, elle concurrence l'identité ; placée à la fin, elle est négligée.
- La formule de base du guide officiel de Seedance 2.5 suit la même colonne vertébrale : *`<sujet> performs <action principale> in <lieu>. The visuals feature <style>. Use <valeur de plan, angle, mouvement, coupes>. Audio includes <dialogue, ambiance, bruitages, musique>.`* Supprime les cases inutiles.

**Deux régimes de longueur, à ne pas mélanger :**
- **Plan unique** : 30 à 100 mots, idéalement 50 à 80. Jamais plus de 200.
- **Génération longue (au-delà d'environ 10 s ou plusieurs plans)** : la structure en blocs remplace la limite de mots (section 5). Reste concentré : chaque phrase doit porter une consigne.

Le modèle respecte surtout les deux ou trois premières consignes et décroche au-delà d'environ huit exigences : le critique d'abord, et répété une fois à la fin.

## 5. La structure d'une génération longue

Garde cet ordre et saute les blocs vides :

```
[En-tête]     nombre de personnages s'il y en a plusieurs :
              EXACTLY 2 CHARACTERS — NO DUPLICATES
[Références]  une ligne de rôle + exclusion par fichier (continuity.md)
[Lieu]        le bloc géographie du décor (continuity.md)
[Global]      look (lumière + palette + texture), optique, caméra de base,
              blocs identité des personnages, jeu clé, politique sonore
[Étapes]      Stage 1 [00:00-00:06] : état de départ → UN événement principal
              → état final visible
              Stage 2 [00:06-00:14] : Continue from the previous stage: …
[Son]         dialogues, bruitages, ambiance, musique (sound-music.md)
[Verrous]     les contraintes essentielles, reformulées positivement, en dernier
```

Chaque étape peut porter une courte **ligne d'émotion** : `emotion: dread turning into resolve`.

## 6. Le déroulé temporel

- **Seedance 2.5 comprend les repères à la seconde** : plages (`0-3 seconds`, `[1s-4s]`), instants (`At the 5-second mark`), durées relatives (`After 3 seconds`). **Seedance 2.0 les ignore** : utilise `Shot 1:`, `Shot 2:` dans l'ordre de l'histoire.
- Des plages **contiguës qui couvrent toute la durée**, à la seconde : `[00:00-00:04]`, `[00:04-00:09]`, `[00:09-00:15]`. Pas de trous.
- Trop d'actions dans une plage provoque des coupes en trop ou des actions sautées ; trop peu laisse le modèle improviser.
- Ne chronomètre pas une action très rapide et répétée (« secoue la tête trois fois par seconde ») : le modèle ne suit pas.
- Une plage dure **au moins 2 à 3 secondes**. Trois étapes ne tiennent pas en 5 secondes.
- Les plages sont un **budget de temps**, pas des coupes exactes. La précision se gagne au montage.
- **La durée doit être identique partout** : réglage, en-tête, et somme des plages. Une incohérence est la cause la plus fréquente d'une génération multi-plans rendue en un seul plan.
- Les **conditions** fonctionnent : `the ink effect only appears after 25s, when she clicks`.
- **Termine sur un état tenu** (`Hold.`), sinon le modèle invente un événement pour remplir le temps.

## 7. La densité : actions et plans

- **1 à 2 actions pour 5 secondes.** Au-delà : flou, saccades, morphings.
- **Repères de durée** : 4 à 8 s pour une action forte ; 8 à 12 s pour une action et une révélation ; 12 à 15 s pour 2 ou 3 actions simples.
- **Budget pour 15 secondes** : 2 actions fortes, 2 mouvements de caméra, 3 personnages importants, 1 effet visuel complexe, 1 changement de lieu. Au-delà d'un seul de ces plafonds, découpe en plusieurs générations.
- **Enchaîne 2 ou 3 actions dans la même direction** : `walks to the window, pulls the curtain aside, leans into the glass`. Sinon, le temps restant est souvent rempli par l'action jouée **à l'envers**. Un aller-retour, c'est deux plans.
- **Une action qui va et revient** (tendre le bras puis le retirer, armer un geste) : commence dans l'état (`he is already mid-swing`).
- **Physique et jeu d'acteur en gros plan ne vont pas ensemble** : la bagarre s'adoucit et les visages s'aplatissent. Génère-les séparément, puis monte.
- **Rythme de montage** : environ 4 à 6 s par plan en narratif, avec un plan héroïque tenu de 6 à 8 s. Pour un clip ou une pub, jusqu'à une douzaine de coupes en 30 s, à condition de lister chaque plan.
- Le détail du mouvement et de la physique est dans `motion-vfx.md`.

## 8. La caméra comme une spécification

Écris la caméra comme une fiche technique : **valeur de plan + mouvement + direction + cible + début + fin + durée**.

> `Slow dolly push from a medium shot to a tight close-up on her eyes over 8 seconds.`

- **Un mouvement principal par plan**, avec au plus un modificateur (`slow dolly-in, slightly handheld`). Jamais deux mouvements opposés. Empiler les mouvements (avancer en panoramiquant en basculant) est la première cause de saccades.
- **Plusieurs mouvements ?** Des phases chronométrées (`rises 0-3s, holds, then pushes in 4-8s`) ou des coupes.
- **Nomme la fin du mouvement.** Un mouvement sans point d'arrivée revient en arrière ; un mouvement trop petit pour atteindre le cadre final est improvisé.
- **`zoom` donne un zoom optique.** Pour un déplacement de la caméra, écris `push in`, `dolly in`, `pull back`.
- **Avec plusieurs sujets, dis lequel la caméra suit**, et où le mouvement commence et finit.
- **La caméra bouge avec l'acteur**, pas selon sa propre horloge : `the camera moves with her`.
- **Termes techniques** : garde le terme, puis traduis-le en résultat visible : `rack focus: focus shifts from the leaves in the foreground to the face behind; the leaves blur as the face sharpens.`
- **Mise au point** : `focus locked on her eyes from first frame to last`.
- **Optique** : en millimètres avec l'ouverture (`85mm f/1.4`), ou en champ de vision, que certains guides trouvent plus fiable : 84° large, 63° observation, 47° neutre, 29° buste en dialogue, 12° insert. À tester.
- Le lexique complet est dans `camera-language.md`.

## 9. Les mots de vitesse

Du plus lent au plus brutal :

`slightly` · `subtly` · `slowly` · `extremely slowly` · `gradually` · `smoothly` · `steadily` · `at a constant speed` · `continuously` · `quickly` · `rapidly` · `at extreme speed` · `suddenly` · `instantly` · `violently`

- `Freeze.` arrête un mouvement.
- **`fast` est le mot qui dégrade le plus l'image.** Donne la vitesse par un repère : un rythme (`one full revolution across the 10-second clip`, `tracks alongside at a steady 5 km/h, 2 m away`) ou une analogie (`like dust suspended in honey`).
- Pour un combat, écris `real-time speed` et exclus le ralenti.

## 10. Les coupes et les transitions

- **Nomme les coupes** : `Exactly one HARD CUT, at 0:07; otherwise the camera holds.` Ajoute `cuts only at the specified points`.
- **Chaque coupe change à la fois la valeur de plan et le mode de caméra** (épaule, fixe, travelling, grue, aérien). Jamais trois coupes de suite avec la même valeur et le même mouvement.
- **Transition** : le type, une échéance et deux contraintes : `the whip pan starts at 9.0s; the new room is readable by 9.5s; no rigid cut, nothing appears out of thin air.` Un panoramique filé a besoin d'au moins 0,8 s de flou, sinon il devient une coupe.
- Évite les verbes ouverts (`drift`, `gradually become`) : sans échéance, une transition peut s'étaler sur dix secondes.

## 11. Les négations

Seedance n'a pas de champ de négation : une liste `negative:` ou une pile de « no X » est lue comme du contenu. Écrire `no gun` fait apparaître un pistolet. D'après la documentation officielle, les négations ne sont fiables que pour **les sous-titres et le son** (`No subtitles.`, `No BGM; only ambient and action sounds.`, `No audio.`). Regroupe-les, courtes, à la fin.

- **Formule l'état voulu** : `holster clipped, hands empty` ; `Face stable. Limbs anatomically natural.` ; `sharp, in focus`.
- **Exclusions limitées à une référence** : `Do not use the people in @Image 2.`
- **Interdictions isolées seulement là où le modèle échoue par défaut** : les doublons (`exactly ONE lamp`), la musique (`NO BGM`), les sous-titres (`No subtitles.`), le ralenti dans un combat, la copie de la voix d'une référence.
- **Ne nomme jamais un style dont tu ne veux pas**, même pour l'exclure. Préfère affirmer le registre et son contraire : `photoreal live-action, not a 3D render`.

## 12. Les mots inutiles

`8K`, `masterpiece`, `stunning`, `breathtaking`, `epic`, `mesmerizing`, `hyperrealistic`, `high quality`, `ultra detailed`, `seamlessly` n'apportent aucune information. Remplace `cinematic` par un mécanisme précis (une optique, une lumière, un mouvement).

Certains mots ont un effet indésirable :
- `blush` donne un filtre rose ; `dreamy`, `soft focus`, `blurry background` adoucissent toute l'image ;
- les **mots d'émotion intense** (`fanatical`, `possessed`, `rage`) font briller les yeux : préfère des signes physiques neutres (`acting-direction.md`) ;
- les mots d'**eau, de vagues ou d'écho** créent des artefacts sonores (bouillonnements, réverbération) : si l'eau n'est pas nécessaire au son, décris-la sans ces mots ou coupe le son de cette partie ;
- les **expressions imagées** (« il a les yeux qui lancent des éclairs ») : écris une phrase descriptive ;
- les **verbes à double lecture visuelle** : `tearing` (déchirer ou pleurer), `shoot`, `duck`, `bolt`, `draw`, `charge`, `snap`.

Ne colle jamais un script complet comme prompt : traduis-le en plans. Et un prompt écrit pour Seedance 2.0 peut mal passer en 2.5 : ralentis le rythme et rends les actions plus posées.

## 13. La langue du prompt

- **Anglais par défaut** : la langue la plus testée par les guides internationaux, et l'utilisateur peut relire ses prompts.
- **Chinois en option** : les exemples officiels de ByteDance sont souvent en chinois. Pour un plan important décevant, une version chinoise vaut le test. Les termes de caméra anglais fonctionnent aussi dans un prompt chinois.
- **Les dialogues restent dans leur langue**, annoncés par une ligne de langue (`sound-music.md`).
- Sous chaque prompt, **une ligne en français** résume ce qu'il fait.

## 14. Modèles prêts à l'emploi

### Plan unique, texte seul
```
A courier in a yellow rain jacket sprints through a narrow night-market alley,
shoulder-checking paper lanterns. Low tracking shot at hip height behind her,
matching her running pace; stalls pass in the foreground, lights streaking into
motion blur. She vaults a crate, lands, keeps running. Wet asphalt reflects red
and amber neon. Audio includes ragged breath, splashing sneakers, vendors shouting.
NO BGM. No subtitles.
```

### Personnage et décor en référence
```
@Image 1 defines the dancer's face, hair and red tracksuit only; do not use its background.
@Image 2 defines the rooftop location as a style reference only; she moves through real space.
At dusk, the dancer — red tracksuit, high ponytail — spins on the rooftop, then freezes mid-spin.
Low orbit around her, rapidly at first, then extremely slowly as she freezes; the orbit ends
facing her. Golden backlight, soft rim on her hair, city haze behind.
Exactly one dancer. Face stable throughout.
```

### Séquence avec étapes
```
@Image 1 defines the lighthouse keeper's face, grey beard and grey wool coat.
A lighthouse at dawn, one continuous take, handheld with a slight breathing motion.
Global: salt haze between the camera, the keeper and the sea; cold blue light warming to gold.
Stage 1 [00:00-00:08]: the keeper — grey beard, grey coat — climbs the spiral iron stairs,
one hand on the rail; the camera follows behind. End: he reaches the lamp room.
Stage 2 [00:08-00:18]: continue from the previous stage. Slow push-in as he trims the wick;
focus locked on his hands, then his face. Emotion: quiet care.
Stage 3 [00:18-00:30]: on the gallery, wind lifts his collar; he looks out at the sea.
Hold on his silhouette as the lamp dims behind him.
Audio includes wind, distant gulls, boots on iron steps. NO BGM. No subtitles.
Same face and coat throughout.
```

### Première et dernière image imposées
À utiliser dans le mode « Première et dernière image », le seul qui verrouille exactement ces images.
```
@Image 1 is the first frame. It defines the opening composition, her position and the café.
@Image 2 is the last frame. It defines the closing composition.
In one continuous action that begins naturally from the first frame, she stands, crosses
to the window and opens it, reaching the composition of the last frame.
Slow lateral tracking shot at waist height.
```

### Extension (ajout à la suite)
```
The first frame of the extended segment directly continues from the last frame of @Video 1.
Same stride, facing direction, camera speed and ambience; @Video 1 stays unchanged.
Then, he stops at the gate and looks back once; the porch light goes out. Hold.
Smooth action connection, nothing appearing from thin air.
```
Pour un ajout **avant**, la nouvelle partie doit se terminer en se raccordant naturellement à la première image de la vidéo. N'écris jamais `then connect to the source video` : des éléments de la suite fuient dans l'ajout.

### Édition locale
```
Edit @Video 1, which is the sole editing master.
Only from 4 to 7 seconds, replace the paper cup in her hand with the mug from @Image 1.
The mug inherits every motion, occlusion and exit of the cup. Exactly one mug.
Keep her face, clothing, camera move, lighting and audio unchanged.
```

### Montage calé sur une musique
```
@Audio 1 drives the edit: cuts land on the downbeats, movement peaks on the drop.
@Image 1 to @Image 6 are used in upload order, each alive with small motion and a slow push-in.
Verse: cut every four beats. Chorus: cut every two beats.
One beat of stillness before the drop, then a white flash and a fast aerial pull-back
from the last image. No subtitles.
```

### Pub avec accroche immédiate
```
Stage 1 [00:00-00:03]: frame one is already mid-action: hands tear a loaf of bread open,
steam bursting in backlight. No static hold.
Stage 2 [00:03-00:07]: the baker slides the tray onto the wooden counter.
Stage 3 [00:07-00:11]: macro, the crust cracks under a bread knife.
Stage 4 [00:11-00:15]: the loaf alone on the board, stable, softly front-lit.
Audio includes crust crackle, knife on wood. NO BGM. No text in frame.
```
Le logo, le texte et le prix s'ajoutent au montage.

## 15. La vérification avant envoi

- [ ] Le mode est choisi, les réglages sont notés à part.
- [ ] Chaque référence a sa ligne de rôle et son exclusion.
- [ ] Le sujet et l'action sont dans les 20-30 premiers mots.
- [ ] Un mouvement de caméra principal par moment, avec un début et une fin.
- [ ] Les plages sont contiguës et leur somme égale la durée réglée.
- [ ] Chaque étape contient un seul changement et un état final visible.
- [ ] Ni âge, ni nom de célébrité, de marque ou d'œuvre protégée, ni liste `negative:`.
- [ ] Les dialogues sont uniquement entre `{ }` ; la musique et les sous-titres sont exclus s'ils ne sont pas voulus.
- [ ] Le texte, les logos et les prix sont prévus au montage.
- [ ] Les blocs identité et look sont recopiés mot pour mot.

## 16. Itérer

- **Sois réaliste sur le nombre de prises.** Sur un long-métrage IA professionnel, environ 1,5 % des vidéos générées ont été gardées. Prévois plusieurs prises par plan important, et le budget de crédits qui va avec.
- **Défaut systématique ou aléatoire ?** Décide-le avant de toucher au prompt.
  - **Le même défaut à chaque prise** : le prompt est en cause. Change une seule chose, en cherchant dans cet ordre : sujet, action, caméra, style, son. La plupart des problèmes sont dans les deux premiers.
  - **Des défauts différents, certaines prises presque bonnes** : c'est de la variance. Garde le prompt et génère plusieurs prises, triées selon des critères fixés à l'avance.
- **Cinq verdicts par prise** : garder · corriger au montage · modifier une seule couche · relancer à l'identique · réécrire.
- **Règles d'arrêt** :
  - deux fois le même défaut → réécris le prompt ;
  - dix à quinze retouches d'une ligne sans progrès → **simplifie le plan**, pas les mots (découpe, retire une action, change d'angle).
- **Remplace le texte en place** au lieu d'ajouter des phrases : les ajouts créent des contradictions. Garde les 80 % qui marchaient et donne le prompt **complet** corrigé.
- **Les brouillons basse résolution valident la structure** (plans, placement, identité), pas le jeu ni les détails.
- **Récupère les bons fragments** : un film IA se monte avec les meilleures secondes de nombreuses prises.
- Le diagnostic des problèmes courants est dans `troubleshooting.md`.
