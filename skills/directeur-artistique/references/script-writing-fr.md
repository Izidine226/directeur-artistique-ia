# Écriture de scénario en français

Ce fichier donne les formats d'écriture professionnels français, adaptés à la vidéo IA et aux formats courts. L'objectif : un script que l'utilisateur peut lire, corriger et transmettre, et un découpage qui se traduit directement en prompts.

## Sommaire
1. Les documents d'un projet
2. Logline, synopsis, note d'intention
3. Le scénario (continuité dialoguée)
4. Le découpage technique
5. Écrire pour le format court
6. Voix off et dialogues : le minutage
7. Écrire pour l'IA : ce qui passe et ce qui casse

---

## 1. Les documents d'un projet

Du plus court au plus détaillé. Pour une vidéo de 15 secondes, logline + découpage suffisent. Pour une mini-série, tout y passe.

| Document | Contenu | Quand l'utiliser |
|---|---|---|
| Logline | L'histoire en une phrase | Toujours, c'est le test de l'idée |
| Synopsis | L'histoire en 5 à 15 lignes | Court-métrage, clip narratif, série |
| Note d'intention | Le pourquoi, le ton, les choix visuels | Projet ambitieux, pitch à un client |
| Séquencier | Liste des séquences, une ligne chacune | Plus de 1 minute, série |
| Scénario | Action et dialogues, séquence par séquence | Dès qu'il y a des personnages qui parlent |
| Découpage technique | Plan par plan, avec cadre, mouvement, son, durée | Toujours avant de générer |
| Plan de génération | Les prompts Dreamina dans l'ordre, avec réglages et références | Toujours, c'est le livrable final |

## 2. Logline, synopsis, note d'intention

**Logline** : personnage + désir + obstacle + enjeu, en une phrase.
> Dans une laverie de nuit, une jeune femme qui attend son linge depuis trois heures comprend que l'inconnu assis à côté d'elle sait exactement ce qu'il y a dans la machine.

Si la logline ne donne pas envie, aucun plan ne sauvera la vidéo. Retravaille-la avant de découper.

**Synopsis** : début, milieu, fin, au présent, sans détail technique.

**Note d'intention** : trois paragraphes courts.
1. Ce qu'on veut faire ressentir, et pourquoi.
2. Les choix de mise en scène : look, caméra, rythme, musique.
3. Les références visuelles (films, clips, photographes).

## 3. Le scénario (continuité dialoguée)

Format français standard :

```
1. INT. LAVERIE AUTOMATIQUE – NUIT

Les néons grésillent. Une seule machine tourne. NORA (28 ans,
manteau trop grand, écouteurs autour du cou) attend, assise
sur un banc en plastique.

La porte s'ouvre. Un HOMME (40 ans, costume trempé, sac de sport
à la main) entre et s'assoit à côté d'elle. Il ne la regarde pas.

                         L'HOMME
          C'est le tien, le linge qui tourne ?

                         NORA
               (sans quitter la machine des yeux)
          Ça fait trois heures qu'il tourne.

Le tambour s'arrête net. Silence. Hors champ, une sirène s'éloigne.
```

Règles :
- **En-tête de séquence** : numéro, INT. ou EXT., lieu, moment (JOUR, NUIT, AUBE…).
- **Action au présent**, phrases courtes, uniquement ce qu'on voit et ce qu'on entend.
- **Nom du personnage en majuscules** à sa première apparition, avec une description brève et visuelle.
- **Dialogues centrés** sous le nom du personnage.
- **Didascalies** entre parenthèses, avec parcimonie.
- **V.O.** pour voix off, **H.C.** pour hors champ.
- **Une page ≈ une minute** à l'écran en fiction classique. En format court, c'est plutôt une demi-page par minute, car le rythme est plus rapide.

## 4. Le découpage technique

Le pont entre le scénario et les prompts. Chaque ligne devient un plan à générer ou un morceau de génération.

| Plan | Durée | Valeur / angle | Mouvement | Action | Son / dialogue | Transition |
|---|---|---|---|---|---|---|
| 1 | 3 s | Plan d'ensemble, légère plongée | `slow crane down` | La laverie vide, Nora assise face à la machine | Grésillement des néons, ronronnement du tambour | Cut |
| 2 | 2 s | Gros plan Nora | Fixe | Elle lève les yeux vers la porte qui s'ouvre | Clochette de la porte | Cut |
| 3 | 4 s | Plan moyen de l'homme, longue focale | `slow push-in` | Il s'assoit, pose le sac à ses pieds | « C'est le tien, le linge qui tourne ? » | Cut |

Conseils :
- **Numérote tout.** Les plans, les prompts et les fichiers générés doivent porter le même numéro, sinon le montage devient un enfer.
- **Indique la durée de chaque plan.** La somme doit tomber juste sur la durée cible.
- **Regroupe en générations.** Plusieurs plans courts peuvent tenir dans une seule génération si le modèle accepte l'enchaînement de plans (voir `dreamina-seedance.md`) ; sinon, un plan = une génération.

## 5. Écrire pour le format court

Un format court n'est pas un film raccourci. Sa structure est différente :

1. **Accroche (0-2 s)** : l'image ou la phrase qui arrête le pouce. Pas d'introduction, pas de logo.
2. **Mise en place (2-5 s)** : la situation ou la promesse, en un plan.
3. **Montée (5-20 s)** : chaque plan relance, rien ne doit être gratuit.
4. **Chute ou récompense** : la révélation, la blague, le résultat, le drop musical.
5. **Boucle ou appel à l'action** : soit la dernière image ramène à la première pour qu'on revoie la vidéo, soit une invitation claire (venir samedi, suivre, commenter).

Les structures d'accroche détaillées et les formats viraux sont dans `formats/trends-hooks.md`.

## 6. Voix off et dialogues : le minutage

- **En français, compte environ 2,5 mots par seconde** à un débit naturel, 3 pour un débit rapide de réseaux sociaux.
- Une vidéo de 15 secondes porte donc environ **35 mots** de voix off, pas plus. 30 secondes : environ 75 mots.
- **Une réplique ne doit pas dépasser la durée de son plan.** Une phrase de 12 mots demande environ 5 secondes.
- **Écris pour l'oreille** : phrases courtes, mots concrets, une idée par phrase.
- **Laisse respirer** : une demi-seconde de silence avant une chute vaut mieux que trois mots de plus.
- **Texte à l'écran** : 3 à 7 mots par carton, lisibles en moins de 2 secondes. Beaucoup de gens regardent sans le son.

## 7. Écrire pour l'IA : ce qui passe et ce qui casse

Ce qui passe bien :
- **Des actions physiques simples et lisibles** : marcher, se retourner, lever un verre, danser, courir, regarder.
- **Des émotions incarnées dans le corps** : `her jaw tightens`, `he exhales slowly and looks away`, plutôt que « elle est triste ».
- **Des dialogues courts**, une ou deux répliques par génération.

Ce qui casse souvent :
- **Les mains qui manipulent des objets précis** (jouer d'un instrument note par note, écrire, compter des billets).
- **Le texte lisible dans l'image** (enseignes, pancartes, écrans) : ajoute-le plutôt au montage.
- **Trop de personnages qui parlent ou bougent en même temps.**
- **Des actions qui demandent une logique de cause à effet complexe** dans un seul plan.
- **Les changements de tenue ou de décor au milieu d'un plan**, sauf effet de transition voulu.

Quand une idée de scénario repose sur une action fragile, change l'angle : filme la conséquence plutôt que l'action (le billet posé sur la table plutôt que les mains qui comptent), ou cache l'action hors champ et montre la réaction.
