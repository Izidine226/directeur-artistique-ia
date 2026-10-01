# Dépannage : symptôme, cause, correction

Quand l'utilisateur revient avec un résultat raté, identifie le symptôme ici, puis corrige **une seule chose à la fois** et redonne le prompt complet corrigé (`prompt-craft.md`, §16).

**Avant tout : défaut systématique ou aléatoire ?** Le même défaut à chaque prise vient du prompt ou des références. Des défauts différents d'une prise à l'autre, c'est de la variance : garde le prompt et génère plusieurs prises.

## Sommaire
1. Refus et blocages
2. Image : déformations, mouvement, caméra
3. Personnages
4. Mains, objets, physique
5. Texte à l'écran
6. Son
7. Édition et extension
8. Fichiers et lecture

---

## 1. Refus et blocages

| Symptôme | Cause | Correction |
|---|---|---|
| Refus immédiat d'une scène légitime | Le filtre lit toute la scène : mots d'âge, noms de personnes ou de marques, verbes violents, description du corps | Réécris la scène : un rôle plutôt qu'un âge, la conséquence plutôt que la violence, `her shoulders` plutôt que `her bare shoulders`. Ne renvoie jamais un prompt refusé tel quel |
| « Couldn't generate because it may contain copyrighted content » | Un personnage, un univers, un studio ou un ayant droit est reconnaissable ou cité | Supprime le nom et crée un personnage ou un univers original ; décris les qualités visuelles au lieu de citer une référence protégée |
| Image de référence refusée | La modération l'a bloquée : visage d'une personnalité, contenu jugé sensible, ou règle qui a changé | Vérifie qu'il ne s'agit pas d'une personnalité publique ou politique ; essaie une autre photo (visage net, de face, fond simple, sans filtre) ; sinon, utilise un personnage généré. N'utilise jamais la photo d'une autre personne sans son accord écrit |

Ces corrections servent à reformuler une scène **légitime** qui déclenche un faux positif. Elles ne servent jamais à contourner les protections des vraies personnes, des mineurs ou des œuvres protégées.

## 2. Image : déformations, mouvement, caméra

| Symptôme | Cause | Correction |
|---|---|---|
| Flou, saccades, morphings | Trop d'actions pour la durée | 1 à 2 actions pour 5 s ; découpe ; reviens à sujet + action + caméra |
| La caméra tourne ou tremble | Mouvements empilés | Un seul mouvement (plus un modificateur) ; phases chronométrées ou coupes |
| La caméra revient en arrière à la fin | Pas de point d'arrivée | Nomme le cadre final |
| L'action se rejoue à l'envers | Temps restant à remplir | Enchaîne 2 ou 3 actions dans la même direction, ou commence dans l'état |
| Un plan presque figé | Image de départ redécrite | Décris seulement ce qui change, et un mouvement de caméra |
| Les générations multi-plans sortent en un seul plan | Durées incohérentes entre réglage, en-tête et déroulé | Aligne les trois ; ajoute `cuts only at the specified points` |
| Une transition s'étale sur plusieurs secondes | Verbe ouvert sans échéance | Donne le type, l'heure de début et de fin, et deux contraintes |
| Le décor grandit, des meubles apparaissent | Le modèle invente l'environnement | `the set contains only what the reference shows`, plus les absences explicites |
| Les positions sautent après une coupe | Positions non rappelées | Bloc géographie ; replace les personnages après chaque coupe |
| Un plan de 30 s se dégrade à mi-parcours | Trop long pour la complexité | Découpe en générations plus courtes, ou en étapes avec un seul événement chacune |
| Mouvement rapide qui se décompose | Limite connue du modèle | Ralentis l'action, garde la vitesse sur un seul élément, ou découpe en coupes |
| Textures en empreinte digitale sur l'herbe ou le feuillage | Images de référence IA en très haute résolution | Réduis les références à la résolution de sortie ; le défaut est moins fréquent en 1080p |

## 3. Personnages

| Symptôme | Cause | Correction |
|---|---|---|
| Le visage change en cours de plan | Référence de visage trop faible, ou texte qui contredit la référence | Ajoute un portrait serré et neutre à part ; attribue le visage et la tenue à deux images distinctes ; recopie le bloc identité mot pour mot |
| Les cheveux dérivent (le plus fréquent) | Description variable | Bloc identité identique partout ; une référence par état de coiffure |
| Deux personnages échangent leurs traits | Balises utilisées comme sujets ; plage d'images pour plusieurs personnages | Une ligne par sujet, verrou `characters never swap appearances`, nom + repère visible dans les actions |
| Personnage dédoublé | Vues multiples non déclarées comme un seul sujet | `these images show one subject; output exactly one` |
| Mauvais personnage associé à une référence | Ordre de chargement | Charge dans l'ordre de première apparition ; numérotation image ↔ audio identique |
| La référence est copiée avec son fond | Pas d'exclusion | `Do not use the grey background / the people in the image` |
| Foule de clones | Une seule référence réutilisée | La foule comme décor (`20+ people`), avec une planche de silhouettes variées |
| Yeux qui brillent | Mots d'émotion intense | Signes physiques neutres ; `normal human eyes` |
| Yeux morts, jeu plat | Pas de tâche pour le regard | Donne une tâche aux yeux ; un micro-événement toutes les 1 à 2 s (`acting-direction.md`) |
| Tailles égalisées entre personnages | Pas de repère de taille | Les tailles en centimètres |

## 4. Mains, objets, physique

| Symptôme | Cause | Correction |
|---|---|---|
| Les mains miment, l'objet ne réagit pas | Verbe sans mécanisme | La chaîne causale : prise → force → réaction de la matière → état final |
| Troisième main, membres orphelins | Mains sans propriétaire | Compte les mains, donne à chacune un propriétaire et un côté d'entrée |
| Marche qui glisse | Le modèle dessine l'apparence d'une marche | `heel lands first, strict left-right alternation, one foot always on the ground` |
| Objet à la mauvaise échelle | Pas de repère | Un repère corporel réel ; une image de référence de taille |
| Un géant rétrécit | Échelle vague | Repère corporel + `at least N times` + référence de taille |
| Un effet a l'air collé | Seule la couleur est accordée | Clause d'intégration : direction de la lumière, rebond, voile, ombres de contact, grain (`motion-vfx.md`) |
| L'effet ne correspond pas à la description | Description insuffisante | Fournis une vidéo de référence de l'effet |

## 5. Texte à l'écran

| Symptôme | Cause | Correction |
|---|---|---|
| Lettres déformées, fautes | Le rendu du texte reste peu fiable | Ajoute le texte au montage. Si indispensable : 5 mots maximum, gros caractères simples, mot épelé lettre par lettre ou fourni en image de référence |
| Sous-titres non voulus | Comportement par défaut, ou dialogue répété dans le prompt | `No subtitles.` au début et à la fin ; ne répète pas les mots du dialogue ; format `Name's line (emotion): {…}` ; vérifie que les vidéos de référence n'ont pas de sous-titres. Le format horizontal en produit moins que le vertical |
| Logo ou filigrane inventé | Comportement par défaut | `Do not generate a logo or watermark.` |

## 6. Son

| Symptôme | Cause | Correction |
|---|---|---|
| Musique malgré « no BGM » | Comportement par défaut du modèle | Liste les sons voulus, puis tous les mots de musique exclus, au début et à la fin ; sinon retire la piste au montage |
| Marmonnements autour d'une réplique courte | Le son comble le silence | Allonge la réplique, raccourcis le plan, ou écris le silence |
| Synchronisation labiale qui décroche | Plan trop long, tête qui bouge, plusieurs visages | 3 à 8 s, plan rapproché, un seul personnage qui parle, caméra fixe |
| Mauvais accent | Accent non précisé | `Dialogue language: French from France` (ou l'accent voulu) avant chaque réplique |
| Mauvaise voix depuis une référence audio | Voix non décrite | Décris la voix en mots, en plus de la référence |
| Bouillonnements, écho parasite | Mots d'eau, de vagues ou d'écho | Retire ces mots de la description sonore |
| Clic ou bruit à la fin | Artefact de génération | Régénère, ou ajoute un fondu sonore au montage |
| Phrase prononcée deux fois | La même réplique collée à deux endroits | Une liste maîtresse des répliques, citées par identifiant |
| Un regard « dit » quelque chose à voix haute | Texte entre guillemets dans l'action | `a cold look toward the door` au lieu de `a look that says "get out"` |

## 7. Édition et extension

| Symptôme | Cause | Correction |
|---|---|---|
| L'extension fait apparaître des éléments de la suite | `then connect to the source video` | Aligne d'abord l'image de raccord, puis décris la nouvelle action |
| Coupe visible au raccord d'une extension | Raccord imparfait | Fais correspondre la pose, les accessoires, la caméra et la vitesse ; au montage, retire quelques images au point de jonction |
| La qualité baisse au fil des extensions | Trop de maillons | 2 ou 3 maillons maximum, puis repars des références d'origine |
| L'objet remplacé suit son propre rythme | Pas d'héritage du déroulé | `the new object inherits every motion, occlusion and exit` + nombre exact |
| Vidéo éditée un peu plus courte (0,3-0,4 s) | Comportement connu | Utilise le mode Références avec une durée explicite |
| Changer le format en édition remplit l'image n'importe comment | Limite de l'édition | Refais en mode Références avec un déroulé plan par plan |
| Une tâche combinée complexe échoue | Trop de changements à la fois | Découpe en plusieurs passes d'édition et de référence |
| La transformation vidéo vers vidéo rate à chaque lot | La vidéo source ne contient pas l'action demandée | Arrête-toi ; capture une image comme première image et écris l'action de zéro (`motion-vfx.md`, §8) |

## 8. Fichiers et lecture

| Symptôme | Cause | Correction |
|---|---|---|
| Une image JPG refusée | Encodage non standard | Convertis-la en PNG |
| La vidéo 1080p ne se lit pas | Codec H.265 10 bits | Lis-la avec VLC ou mpv, ou convertis-la |
| Un bon brouillon impossible à reproduire | Pas de graine fixe | Fige la première image ; juge les détails en résolution finale |

## Quand rien ne marche

Après 10 à 15 retouches sans progrès, le problème n'est plus dans les mots : c'est le plan qui est trop ambitieux. **Simplifie le plan** : découpe-le, retire une action, change d'angle, cache l'action difficile hors champ et montre la réaction.
