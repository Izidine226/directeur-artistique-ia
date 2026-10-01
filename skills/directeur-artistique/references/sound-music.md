# Son, dialogues et musique

Seedance 2.5 génère le son avec l'image : musique, bruitages, ambiance, dialogues. C'est un atout, mais le son se contrôle mal sans consignes précises. Ce fichier explique comment.

## Sommaire
1. La syntaxe des crochets
2. L'ordre et la place du son dans le prompt
3. Contrôler la musique
4. Le budget de mots des dialogues
5. La synchronisation labiale
6. Les dialogues en français
7. La voix de chaque personnage
8. La voix off
9. Les bruitages et l'ambiance
10. Le rôle d'un fichier audio en référence
11. La synchronisation musicale
12. Ce qui se fait au montage

---

## 1. La syntaxe des crochets

Le guide de Seedance 2.5 sépare les canaux sonores avec des crochets. Le langage naturel fonctionne aussi, mais les crochets évitent les confusions :

| Crochets | Usage | Exemple |
|---|---|---|
| `( )` | Musique | `(slow solo piano, 70 bpm, melancholic, enters at 00:05)` |
| `< >` | Bruitages | `<a bell rings once, distant>` |
| `{ }` | Dialogue | `{Tu le savais depuis quand ?}` |
| `【 】` | Sous-titres | à éviter : ajoute-les au montage |

## 2. L'ordre et la place du son dans le prompt

- **La parole uniquement dans la partie son.** Tout texte lisible dans la description de l'action devient une demande de voix : `a look that says "you too?"` peut être prononcé, un panneau peut être lu à voix haute. Écrire ensuite `no dialogue` ne l'annule pas.
- **Ordre des couches** : dialogue → bruitages → ambiance → musique.
- **Le son placé tôt dans le prompt pèse plus.** Les règles sonores essentielles se mettent dans le bloc global **et** se répètent à la fin.

## 3. Contrôler la musique

- **La norme en production** : seulement les sons du monde filmé (pas, voix, ambiance), et la musique au montage. C'est la méthode la plus sûre.
- **Pour éviter la musique** : écris d'abord la liste des sons voulus, puis l'interdiction en texte simple, hors des parenthèses :
  > `Room tone, footsteps on parquet, slow breathing. NO BGM.`
- **Si une musique apparaît quand même**, la documentation officielle recommande de citer tous les mots qui la désignent et de répéter la règle **au début et à la fin** du prompt :
  > `No music, no BGM, no score, no instrumental, no melody, no synth, no ambient pad. Only ambient and action sounds.`
  Sinon, retire la piste au montage.
- **N'écris jamais `(no music)`** : dans les parenthèses de la musique, c'est lu comme une consigne de musique.
- **Si tu veux une musique générée**, décris l'instrumentation, le tempo, l'ambiance et le moment d'entrée. **Jamais un titre de chanson ni un nom d'artiste.**
- **Pour une musique précise** (ton morceau, un morceau sous licence), charge-la en référence audio (section 10) ou ajoute-la au montage.
- **Les sous-titres** : le modèle en ajoute parfois par défaut. Écris `No subtitles.` dans le bloc global et à la fin.

## 4. Le budget de mots des dialogues

- **Rythme fiable : environ 1 à 1,3 mot par seconde de plan.** Une réplique de 5 à 10 mots, pour un plan de 4 à 8 secondes.
- **Trop de mots** : la bouche décroche. Au-delà de 8 mots en 3 secondes, la synchronisation se perd, et la parole continue devient approximative après environ 8 secondes.
- **Trop peu de mots pour la durée du plan** : le modèle comble avec des marmonnements inventés (mesuré sur Seedance 2.0 avec des répliques de 6 mots ou moins dans un plan de 4 s). Solutions : allonger la réplique, raccourcir le plan, ou écrire le silence (`one door latch at 3.4s, then silence`).
- **Un seul personnage parle par plan.** La synchronisation de plusieurs personnages dans un même plan n'est fiable nulle part : utilise le champ-contrechamp.

## 5. La synchronisation labiale

- **Cadrage** : plans de 3 à 8 secondes, plan rapproché ou plus serré, **un seul visage qui parle**, caméra fixe ou travelling avant lent.
- **Retire les mots de mouvement de tête** (`nodding`, `turning`, `looking around`) d'un plan de dialogue.
- **Cite la réplique exacte** entre `{ }`.
- **Empêche les paroles inventées** : `Her line, and nothing else. Nobody else speaks.` Les autres visages : `eyes on the speaker, mouth still`.
- **Voix hors champ** : `(an off-screen voice only; she never enters the shot)`.
- **Les noms rares s'écrivent phonétiquement** pour être bien prononcés.
- **Langues** : le mandarin se synchronise le mieux, l'anglais est fiable ; les autres langues sont moins régulières.

## 6. Les dialogues en français

**Le français ne figure pas dans les langues officielles de Seedance 2.5** (`dreamina-seedance.md`, §6). Des dialogues français peuvent fonctionner, sans garantie. Choisis la méthode selon l'enjeu :

**Méthode rapide (à tester sur un plan court d'abord).** L'ordre qui fonctionne : **langue + accent + ton + personnage + réplique**.
```
Dialogue language: French from France. Mara says quietly, without looking up:
{Tu le savais depuis quand ?}
```
Pour plusieurs répliques d'émotions différentes, le format officiel est : `Mara's line (cold, controlled): {…}`.

**Méthode fiable.** Génère la vidéo sans dialogue, enregistre ou synthétise la voix française à part, puis fais parler le personnage avec l'outil **Synchronisation labiale** de Dreamina (audio de 30 s et 10 Mo maximum, pas plus long que la vidéo).

**Règles communes :**
- **Ne mélange jamais deux langues dans une scène** (sauf noms propres) : l'accent dérive.
- **Ne répète pas les mots d'un dialogue ailleurs dans le prompt**, et n'attache pas d'indication de jeu à un mot isolé : ça déclenche l'apparition de sous-titres.
- **Une voix donnée par une référence audio se décrit aussi en mots** : `the low, warm, slightly husky voice of @Audio 1`.

## 7. La voix de chaque personnage

Rédige **une ligne de voix par personnage** dans la bible (registre, débit, accent, manière), et recopie-la **mot pour mot** à chaque génération. Un synonyme suffit à changer la voix.

```
Mara's voice: low register, slow delivery, slightly husky, French from France, never raises her voice.
```

**Raccord de voix** : ouvre la génération suivante avec la dernière réplique de la précédente, puis coupe au montage.

## 8. La voix off

- **Le plus fiable** : l'enregistrer ou la synthétiser à part et l'ajouter au montage.
- Si elle est générée par Seedance, tiens une **liste maîtresse** : identifiant, texte, début, fin. Dans le déroulé, ne cite que l'identifiant. Une même phrase collée dans deux moments est prononcée deux fois.
- Un silence de plus de 2,5 s dans une voix off demande un événement visuel qui prend le relais.
- **Minutage** d'une voix off posée au montage : environ 2,5 mots par seconde en français (`script-writing-fr.md`). Les dialogues générés dans l'image suivent le budget, bien plus serré, de la section 4.

## 9. Les bruitages et l'ambiance

- **Un bruitage = un événement + une matière + une extinction**, calé sur une action visible :
  > `<the glass hits the tile: a sharp crack, then a settling tinkle>`
- **Un ou deux bruitages par plan** quand il y a du dialogue.
- **L'ambiance** : 2 ou 3 éléments, plus l'acoustique du lieu (`small tiled room, short echo`).
- Exemples de matières : `footsteps on wet cobblestones`, `heels on a marble floor`, `fabric rustling`, `a zipper`, `breath`, `room tone of an empty bar`, `fridge hum`, `a match striking`.
- **Un son hors champ raconte ce qu'on ne montre pas** : une sirène qui s'éloigne, une porte qui claque à l'étage.
- **Évite les mots d'eau, de vagues et d'écho** dans la description sonore : ils créent des artefacts (bouillonnements, réverbération parasite). Si une scène au bord de l'eau en a besoin, garde des sons secs et ajoute l'eau au montage.

## 10. Le rôle d'un fichier audio en référence

Un fichier audio sans rôle précis transmet tout (voix, musique, ambiance). Dis toujours lequel de ces trois rôles il joue :

1. **Tel quel** : `@Audio 1 plays exactly as uploaded, from start to end. Do not modify it.` Supprime alors toute autre consigne sonore.
2. **Moteur du rythme** : `@Audio 1 drives the edit: cuts land on the downbeats, movement peaks on the drop.`
3. **Interprétation** : ce qui est repris (la mélodie), ce qui ne l'est pas (la voix de l'interprète), et ce qui la remplace (`his own speaking voice`).

Découpe toi-même l'extrait utile : certains modèles n'utilisent que le début d'un long fichier.

## 11. La synchronisation musicale

- **Densité des coupes selon la musique** :
  - charleston rapide : un changement par demi-temps ;
  - refrain : une coupe par grosse caisse ;
  - couplet : une coupe toutes les 4 à 8 temps ;
  - travelling avant lent : sur 8 mesures.
- **Le drop est le plus grand moment visuel**, et il n'y en a qu'un. Ne synchronise pas chaque temps : c'est épuisant à regarder.
- **Un point de synchro = deux ancres** : un temps et un événement sonore.
  > `At about 2.2 seconds, on the line {Maintenant.}, the camera snaps into a crash zoom.`
- **Chant en playback** : tranches d'environ 12 s qui gardent des phrases entières ; `lips visibly mouthing the lyrics with exaggerated clarity` ; lèvres fermées pendant les passages instrumentaux ; un seul chanteur à la fois.
- Calcul des temps et des mesures à partir du BPM : `formats/music-video.md`.

## 12. Ce qui se fait au montage

- Une seule piste musicale maîtresse pour tout le montage.
- Les coupes calées sur la ponctuation musicale.
- La voix off et les sous-titres.
- Le nettoyage des sons générés (un marmonnement, un bruit parasite).
- Le redoublage d'un plan dont la voix dérive (avec l'accord de la personne si c'est une vraie voix).
- Une musique de fond générée après coup avec l'outil **Générer la bande son** de Dreamina, en choisissant l'ambiance, le genre ou les instruments.
- Le rééchantillonnage de l'audio à 48 kHz si ton logiciel de montage l'exige : des testeurs ont mesuré un son généré en 32 kHz.
