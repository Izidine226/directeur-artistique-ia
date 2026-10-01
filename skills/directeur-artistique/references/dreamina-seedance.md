# Dreamina et Seedance : la fiche technique

> **Dernière vérification : 1er octobre 2026.** Sources : dreamina.capcut.com (pages officielles et interface en direct), docs.byteplus.com (documentation ModelArk), seed.bytedance.com.
> Les chiffres de ce fichier bougent souvent. Si cette date a plus de 60 jours, signale-le une fois et propose la mise à jour (`self-update.md`).
> **[estimation]** = calcul ou déduction non confirmé par une source officielle.

## Sommaire
1. Les modèles disponibles
2. Les modes de génération
3. Les limites de Seedance 2.5
4. Les limites de la famille Seedance 2.0
5. Citer les références
6. Les langues
7. Les outils après génération
8. Les Éléments, l'avatar IA et les assistants intégrés
9. Les restrictions de contenu
10. Les crédits et les formules
11. Produire de façon économique
12. Ce qui reste à vérifier

---

## 1. Les modèles disponibles

| Modèle dans Dreamina | Usage |
|---|---|
| **Seedance 2.5 (for preview)** | Brouillons en 480p, moins chers, pour tester une idée. L'aperçu reste valable 7 jours, puis on le génère en pleine qualité (1080p). |
| **Seedance 2.5** | Le modèle principal : plus réaliste, jusqu'à 30 s, jusqu'à 50 références, édition et extension. Sorti le 31 juillet 2026. |
| **Seedance 2.0** | Ancienne génération polyvalente, 15 s maximum. Pas de vrais visages. |
| **Seedance 2.0 Fast** | Plus rapide et moins cher que la 2.0. Pas de vrais visages. |
| **Seedance 2.0 Mini** | Le moins cher et le plus rapide. Pas de vrais visages. |
| Seedance 1.5 Pro, 1.0, 1.0 Fast | Anciens modèles. |
| MiniMax H3 | Modèle d'un autre éditeur, présent dans Dreamina. |

**Ce qui distingue la 2.5 de la 2.0** : des générations de 30 s au lieu de 15 ; 50 références au lieu de 12 ; la compréhension des repères temporels à la seconde ; les références uniquement audio ; plusieurs vues d'un même sujet ; l'édition, l'extension et la vidéo longue. ByteDance précise que ce n'est pas un saut de génération : les gains portent surtout sur l'usage en production.

**Ne mélange pas 2.5 et 2.0 dans un même montage** : leurs rendus sont nettement différents.

**Coûts relatifs** (tarifs de l'API, utiles pour comparer, pas des crédits Dreamina) : la 2.5 coûte environ 1,5 fois la 2.0 ; la 2.0 Fast environ 0,8 fois la 2.0 et la Mini environ 0,5 fois ; en 2.5, le 480p coûte environ 0,45 fois le 720p et le 1080p environ 2,5 fois.

## 2. Les modes de génération

Si l'interface de Dreamina est en français, les noms changent :

| Interface anglaise | Interface française | Rôle |
|---|---|---|
| Omni reference | Références de tout type | Texte seul, ou texte + images, vidéos et audio en référence |
| First and last frames | Première et dernière image | Une ou deux images imposées au début et à la fin |
| Multiframes | Images multiples | **Ne tourne pas sur la 2.5** : l'interface bascule sur Seedance 1.0 Fast |
| Smart edit (Beta) | Édition intelligente | Modifier une vidéo existante |
| Edit with marks | Éditer avec des repères | Délimiter une zone à modifier par un rectangle |
| Edit segment | Éditer le segment | Limiter la modification à un intervalle de temps |
| Long video (Beta) | Vidéo longue | 30 à 180 s, rendues en clips raccordés |
| Extend | Étendre | Prolonger une vidéo générée |
| Upscale | Améliorer | Augmenter la résolution |
| Generate soundtrack | Générer la bande son | Ajouter une musique de fond |
| Lip sync | Synchronisation labiale | Faire parler un personnage sur un audio |
| Elements | Éléments | Bibliothèque de personnages, objets et voix réutilisables |

**Précisions par mode :**
- **Première et dernière image** : une ou deux images ; le format suit automatiquement la première image ; 4 à 30 s. **C'est le seul moyen de verrouiller exactement la première image.** Écrire « @Image 1 is the first frame » dans le mode Références de tout type guide le modèle mais ne verrouille pas l'image à coup sûr.
- **Édition intelligente** : une vidéo source de 4 à 30 s (le meilleur résultat jusqu'à 20 s) et des références ; la durée suit la source ; prompt limité à 2 000 caractères ; réservée aux formules payantes. Le message de l'interface indique que l'édition n'est possible que sur des vidéos Seedance 2.5 **[à vérifier : vidéos générées uniquement, ou aussi vidéos importées]**.
- **Vidéo longue** : 30 à 180 s, en 480p, 720p ou 1080p.
- **Étendre** : uniquement sur une vidéo Seedance 2.5 de 30 s maximum, pas en 2K ni en 4K. Le format et la résolution ne changent pas. Chaque extension ajoute jusqu'à 30 s ; ByteDance annonce deux extensions possibles.

## 3. Les limites de Seedance 2.5

**Sortie**

| Paramètre | Valeur |
|---|---|
| Durée | 4 à 30 s, à la seconde près (5 s par défaut) |
| Vidéo longue | 30 à 180 s |
| Images par seconde | 24 fixes (l'outil d'interpolation monte à 30 ou 60) |
| Résolution | 480p, 720p, 1080p. **La 4K n'est pas native** : elle passe par l'outil Améliorer |
| Formats | 21:9, 16:9, 4:3, 1:1, 3:4, 9:16 (16:9 par défaut). Automatique en première/dernière image, édition et extension |
| Taille en 720p | 16:9 = 1280×720 ; 9:16 = 720×1280 ; 1:1 = 960×960 |
| Longueur du prompt | 15 000 caractères maximum (2 000 en édition). Recommandé : moins de 1 000 mots en anglais, au-delà les détails se perdent |
| Âge minimum | 16 ans |

**Références** (50 au total)

| Type | Nombre | Contraintes |
|---|---|---|
| Images | 30 max | 300 à 6000 px par côté, 30 Mo max, ratio entre 0,4 et 2,5 ; jpeg, png, webp, bmp, tiff, gif, heic, heif |
| Vidéos | 10 max | mp4 ou mov, 2 à 30 s chacune, **30 s au total**, 200 Mo max, 24 à 60 images/s |
| Audio | 10 max | wav ou mp3, 2 à 30 s chacun, **30 s au total**, 15 Mo max. Une référence uniquement audio est acceptée |

**Quantités recommandées par ByteDance** : 1 à 8 sujets en images (jusqu'à 12 en acceptant des ratés) ; 1 à 5 sujets en vidéo ou audio ; 5 à 10 s par vidéo de référence ; 15 cases maximum pour un storyboard ; 1 à 5 images de référence pour une édition.

## 4. Les limites de la famille Seedance 2.0

| Paramètre | Valeur |
|---|---|
| Durée | 4 à 15 s |
| Résolution | 2.0 : 720p, 1080p, 4K · Fast et Mini : 720p à 4K, probablement agrandies au-delà de 720p **[estimation]** |
| Références | 12 au total : 9 images, 3 vidéos (15 s au total), 3 audio (15 s au total). Au moins une image ou une vidéo : pas de référence uniquement audio |
| Prompt | 4 000 caractères |
| Repères temporels | **Ignorés.** Utilise `Shot 1:`, `Shot 2:` dans l'ordre de l'histoire |
| Absent | Vidéo longue, édition intelligente (renvoyées vers la 2.5) |

Conseils propres à la 2.0 : n'utilise pas toutes les places de référence (4 à 5 fichiers suffisent : 1 ou 2 images de personnage, 1 décor, 1 vidéo de mouvement, 1 audio) ; pas de planche à plusieurs vues (elle crée des doublons), mais un portrait serré et une image en pied ; rappelle la balise du personnage à chaque action.

## 5. Citer les références

- **Insère toujours une référence avec le sélecteur** : tape `@` dans le champ du prompt et choisis le fichier. Ne tape pas les balises à la main.
- Les balises sont **numérotées par type, dans l'ordre de chargement** :
  - interface anglaise : `@Image 1`, `@Video 1`, `@Audio 1` ;
  - interface française : `@Image 1`, `@Vidéo 1`, `@Contenu audio 1` ;
  - Éléments enregistrés : par leur nom (`@Mara`) ou `Élément N`.
- **Conseil** : comme les prompts sont rédigés en anglais, passe l'interface de Dreamina en anglais. Les balises correspondent alors au texte, et on ne sait pas si l'étiquette française est transmise telle quelle au modèle. Le test ne coûte rien.
- **Charge les sujets dans l'ordre de leur première apparition**, et garde la même numérotation entre images et audio d'un même personnage (Image 1 ↔ Audio 1).
- **Ne compte pas sur un nom écrit dans une image** : ça crée des confusions et des doublons. Lie chaque fichier à son rôle dans le texte.
- **Formulations officielles** : `The knight in Image 1` · `Images 1-2 are Character 1 and correspond to Audio 1` · `Image 1 depicts John and uses the voice timbre from Audio 1` · `Refer to the action in Video 1 and the orbiting camera movement in Video 2` · `Refer to Image 1 for lighting and filters`.
- **Pour copier fidèlement une vidéo**, ne la redécris pas : `Strictly refer to the actions and camera movements in Video 1.`
- **Images clés dans l'ordre** : en première phrase, `Use Images 1 to 4 in order as keyframes.`
- **Storyboard** : suivi seulement dans les grandes lignes. Préfère des cases simples au trait, sans texte, 15 maximum.
- La méthode complète des lignes de rôle est dans `continuity.md`.

## 6. Les langues

- **Langues officielles de Seedance 2.5** pour les prompts et la parole générée : chinois, anglais, espagnol, indonésien, malais, thaï, arabe, portugais, vietnamien, japonais, coréen.
- **Le français n'est sur aucune liste officielle.** Certains utilisateurs disent que des dialogues français fonctionnent, sans garantie.
- **Conséquences** :
  - écris les prompts en anglais ;
  - pour un dialogue en français, fais un test court avant de lancer une production ;
  - pour un résultat fiable, génère sans dialogue puis fais parler le personnage avec l'outil de synchronisation labiale sur un audio français enregistré ou synthétisé (`sound-music.md`).
- **Précise toujours l'accent** : des testeurs ont obtenu un accent britannique non voulu en anglais.

## 7. Les outils après génération

| Outil | Ce qu'il fait | Limites |
|---|---|---|
| Étendre | Prolonge la vidéo | Vidéos 2.5, 30 s maximum en source |
| Interpoler | Passe de 24 à 30 ou 60 images/s | Améliore d'abord, interpole ensuite : une vidéo interpolée ne peut plus être améliorée |
| Synchronisation labiale | Fait parler un personnage sur un audio importé (mp3, wav, m4a, flac, aac, ogg ; 10 Mo et 30 s max) ou une voix de synthèse | L'audio ne doit pas dépasser la vidéo ; fonction payante avec quelques essais gratuits |
| Améliorer | Agrandit en 2K ou 4K | Vidéos de 30 s maximum |
| Générer la bande son | Ajoute une musique de fond selon l'ambiance, le genre ou les instruments | — |
| Imiter le mouvement | Transfère un mouvement | — |
| Doublage | Les textes de l'interface mentionnent un doublage vers plusieurs langues, dont le français, depuis un audio d'origine en anglais | **[disponibilité à vérifier]** |

## 8. Les Éléments, l'avatar IA et les assistants intégrés

- **Les Éléments** : une bibliothèque de personnages, d'objets et de voix réutilisables, qu'on cite avec `@` dans n'importe quel prompt. Un élément image peut porter plusieurs images et une voix de référence. **C'est l'outil le plus pratique pour un personnage récurrent** : crée-le une fois à partir de ses images de référence, puis cite-le par son nom.
- **L'avatar IA** (OmniHuman 1.5) : une image et un audio donnent un personnage qui parle et bouge, bouche synchronisée. Idéal pour un face caméra parlé.
- **Les assistants intégrés** : dans le champ du prompt, `/` ouvre des aides de Dreamina (par exemple un rédacteur de prompts vidéo ou un plan-séquence cinématographique). Utiles pour comparer avec tes propres prompts.

## 9. Les restrictions de contenu

- **Vrais visages** : l'interface indique qu'ils ne sont pas pris en charge en référence sur la famille 2.0. Sur la 2.5, l'interface n'affiche pas cette restriction ; la documentation API de ByteDance la mentionne, mais des utilisateurs génèrent dans Dreamina avec des photos de vraies personnes. **Ne l'affirme pas comme un refus certain : fais tester.** La règle qui compte est légale : l'utilisateur peut utiliser sa propre image ; celle d'une autre personne demande son accord écrit (`legal-ethics.md`).
- **Personnalités politiques** : interdites.
- **Mineurs** : tout contenu qui sexualise, met en danger ou exploite une personne de moins de 18 ans est interdit, IA comprise. Ne représente pas d'enfants dans des scènes ambiguës.
- **Propriété intellectuelle** : la génération de personnages et d'univers protégés est bloquée (« Couldn't generate because it may contain copyrighted content »). Citer un studio ou un ayant droit comme référence de style déclenche aussi la modération : décris les qualités visuelles à la place.
- **Fichiers chargés** : n'importe ni musique protégée ni image d'autrui sans en détenir les droits.
- **Dreamina peut réécrire un prompt** jugé risqué.
- **Marquage** : chaque vidéo porte un filigrane invisible, des métadonnées C2PA et des mentions IA visibles. Les formules payantes retirent le filigrane de marque Dreamina ; un réglage séparé permet de retirer la mention IA visible, mais la loi peut l'exiger (`legal-ethics.md`).
- **Usage commercial** : les conditions générales décrivent un usage « généralement privé et non commercial », sauf conditions supplémentaires ; aucune page ne dit clairement quelle formule l'autorise. En utilisant le service, tu accordes aussi à ByteDance une licence large et perpétuelle sur tes contenus. **Avant un usage commercial, vérifie « See all benefits » connecté, et garde une copie des conditions au moment de l'achat.**

## 10. Les crédits et les formules

**Prix en France au 1er octobre 2026 (à revérifier) :**

| Formule | Prix mensuel | Crédits par mois |
|---|---|---|
| Basic | 13,99 € | 1 361 |
| Standard | 31 € | 3 336 |
| Advanced | 68 € à 277 € selon le palier | 7 483 à 30 727 |
| Ultra | 450 € | 51 067 |

Tous les plans payants : sans filigrane de marque, extension, meilleure résolution, jusqu'à 60 images/s, synchronisation labiale, file d'attente rapide.

**Promotion du 23 septembre au 9 octobre 2026** : Basic à 1,39 € le premier mois (carte ou PayPal uniquement) ; les autres formules à −40 % le premier mois. Pendant l'événement, Seedance 2.5 en 720p coûte 59 % de crédits en moins sur Standard et Advanced, 75 % en moins sur Ultra, **sans réduction sur Basic**. Toutes les formules se renouvellent au plein tarif.

**Le coût en crédits d'une génération n'est pas publié.** Les « N vidéos de 10 s par mois » affichées sur les formules sont calculées sur Seedance 2.0 Fast en 720p, pas sur la 2.5.
- Estimation pour Seedance 2.5 en 720p : environ **32 à 37 crédits par seconde** hors réduction, soit 320 à 370 crédits pour 10 s **[estimation]**.
- Au tarif normal, un crédit vaut environ 0,9 à 1 centime : un clip de 10 s en 2.5 720p revient donc à environ **3,30 à 3,80 € sur Basic** **[estimation]**.
- Le 1080p coûte environ 2,5 fois le 720p ; le 480p environ moitié moins.
- **Lis toujours le coût affiché sur le bouton Générer avant de lancer.**

**Formule gratuite** : des crédits quotidiens (Dreamina parlait de 120 par jour en août 2026), qui expirent le lendemain. L'accès gratuit à la 2.5 n'est pas clair : les sources se contredisent.

## 11. Produire de façon économique

1. **Teste en brouillon** avec Seedance 2.5 (for preview) en 480p : il valide la structure (plans, placement, identité), pas le jeu ni les détails fins.
2. **Génère d'abord des plans courts** (5 à 10 s) pour les plans difficiles, avant de lancer 30 s.
3. **Crée tes personnages en Éléments** une fois pour toutes.
4. **N'améliore en 2K ou 4K que les plans retenus**, à la fin.
5. **Estime le budget avant de commencer** : nombre de générations × prises par génération × coût d'une génération. Prévois plusieurs prises par plan important (`prompt-craft.md`, §16).

## 12. Ce qui reste à vérifier

À contrôler en étant connecté, puis à reporter dans ce fichier :
1. le coût exact en crédits sur le bouton Générer, en 480p, 720p et 1080p, avec ou sans vidéo de référence, et en vidéo longue ;
2. si l'interface française transmet `@Vidéo 1` au modèle, ou un identifiant neutre ;
3. si la 2.5 accepte les photos de vrais visages en référence, y compris celle de l'utilisateur lui-même, et dans quels modes ;
4. quelles formules incluent l'usage commercial ;
5. si Dreamina propose le téléchargement en MOV pour la 2.5.
