# Clips musicaux

Un clip donne une identité visuelle à une musique. En IA, c'est l'un des formats les plus forts : la musique porte le rythme, et les images peuvent être aussi impossibles que la chanson le permet.

## Sommaire
1. Choisir le mode
2. Calquer la structure de la chanson
3. Couper sur le beat
4. Méthode de production dans Dreamina
5. Le clip court pour les réseaux
6. Droits

---

## 1. Choisir le mode

| Mode | Principe | Quand l'utiliser | Difficulté en IA |
|---|---|---|---|
| **Performance** | Un personnage chante ou danse face à nous | Chanson avec un refrain vocal fort | Élevée : cohérence du personnage et synchronisation labiale |
| **Narratif** | Une mini-histoire posée sur la chanson | Chanson avec une émotion ou un récit | Moyenne |
| **Conceptuel** | Une idée visuelle déclinée (une métaphore, un univers, une transformation) | Musique électronique, instrumentale, ambiance | Faible : c'est le terrain idéal de l'IA |
| **Hybride** | Narratif entrecoupé de performance | Clip complet | Élevée |

Variantes : visualiseur, lyric video en typographie animée (le texte s'ajoute au montage), clip de lancement d'une danse.

Pour un premier clip IA, le mode conceptuel ou narratif sans dialogue donne les meilleurs résultats : pas de synchronisation labiale à réussir.

## 2. Calquer la structure de la chanson

| Partie | Fonction visuelle |
|---|---|
| Intro | Installer l'univers, mais vite : l'image 0 doit déjà accrocher |
| Couplet | Mise en place : le personnage, le lieu, la situation |
| Pré-refrain | Tension qui monte : plans plus serrés, mouvements qui accélèrent |
| Refrain | Sommet émotionnel : l'image iconique, le mouvement spectaculaire |
| Pont | Retournement ou séquence surréaliste |
| Dernier refrain | Résolution, le plus grand plan du clip |
| Outro | Image finale qui boucle ou qui reste en tête |

## 3. Couper sur le beat

- **Durée d'une mesure en 4/4 = 240 ÷ BPM secondes.** À 120 BPM, une mesure dure 2 s ; à 90 BPM, 2,67 s ; à 128 BPM, 1,875 s.
- **Un temps = 60 ÷ BPM secondes.** À 120 BPM, un temps dure 0,5 s.
- **Rythme de coupe habituel** :
  - couplets : une coupe par mesure ;
  - pré-refrain : une coupe par demi-mesure, le rythme s'accélère ;
  - refrain : alterne coupes rapides et un plan tenu sur la phrase forte ;
  - notes tenues : plans longs.
- **Le plus grand changement visuel tombe pile sur le premier temps du drop** : morphing, changement d'échelle, explosion de lumière.
- Calcule les points de coupe à l'avance et note-les en secondes dans le découpage technique.

## 4. Méthode de production dans Dreamina

1. **Découpe le morceau en sections** dont la durée ne dépasse pas la durée maximale d'une génération (voir `dreamina-seedance.md`).
2. **Charge l'audio de chaque section comme référence** quand le modèle accepte l'audio en entrée, et donne les repères de temps dans le prompt : `at ~6s, on the drop, snap to an extreme close-up`.
3. **Réutilise la même fiche personnage et la même image de style** dans chaque génération (`continuity.md`).
4. **Écris le découpage seconde par seconde** dans le prompt pour caler l'action sur la musique (`prompt-craft.md`).
5. **Assemble au montage**, puis réaligne chaque coupe sur la grille du tempo. Les générations IA ne tombent jamais parfaitement sur le temps : c'est au montage qu'on gagne la précision.
6. **Génère chaque section en 2 à 4 prises** et garde la meilleure.

## 5. Le clip court pour les réseaux

- Coupe un extrait de 15 à 30 s **autour du refrain**, et démarre sur l'accroche vocale, jamais sur l'intro.
- La première image doit être la plus forte du clip.
- Pense la fin pour qu'elle boucle sur le début.
- Les morceaux au-dessus de 120 BPM tendent à améliorer le taux de visionnage complet sur TikTok.

## 6. Droits

- **Musique** : il faut une licence écrite pour le morceau, sauf si c'est le tien ou une musique libre de droits pour l'usage visé.
- **Artiste** : il faut son accord écrit avant de le représenter, que ce soit à partir de sa photo ou sous forme d'avatar stylisé. Selon le modèle, Dreamina peut refuser les photos de vrais visages : c'est signalé sur la famille 2.0, à tester sur la 2.5.
- **Voix** : ne demande jamais une voix qui imite un artiste reconnaissable.
- **Étiquette IA** : obligatoire selon les plateformes et le droit européen (`legal-ethics.md`).
