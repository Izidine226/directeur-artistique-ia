# Court-métrage et film IA

Un court-métrage IA de 1 à 5 minutes est un vrai film : une histoire, des personnages, une mise en scène. La technique ne remplace pas l'écriture : le public tolère les défauts d'image, pas une histoire vide.

## Sommaire
1. Choisir une histoire qui se tourne en IA
2. La structure en trois actes, compressée
3. Le découpage en scènes et en générations
4. La méthode de production
5. Le budget réaliste

---

## 1. Choisir une histoire qui se tourne en IA

**Ce que l'IA fait bien** : les atmosphères, les décors impossibles, les plans larges et aériens, le surréalisme, les transformations, les silences, les regards, les personnages peu nombreux.

**Ce qu'elle fait mal** : les dialogues longs entre plusieurs personnages, les mains qui manipulent précisément, le texte à l'écran, les foules qui interagissent, les combats chorégraphiés longs.

Choisis donc une histoire qui repose sur ses forces :
- **peu de personnages** (un à trois) ;
- **peu de décors** (deux à cinq) ;
- **peu de dialogue** : une histoire qui se raconte par l'image, la voix off ou quelques répliques courtes ;
- **une idée visuelle forte** qui ne peut exister qu'en IA ou qui coûterait une fortune en tournage.

Le test : peux-tu raconter le film en une phrase, et le résumer en cinq images clés ?

## 2. La structure en trois actes, compressée

| Acte | Part du film | Contenu |
|---|---|---|
| **Acte 1** | 20-25 % | Le personnage dans son monde ; l'élément déclencheur qui le bouscule. L'accroche doit arriver dans les premières secondes, pas après une longue installation. |
| **Acte 2** | 50-60 % | Le personnage poursuit un objectif contre des obstacles qui s'intensifient ; un retournement au milieu ; le pire moment avant la fin. |
| **Acte 3** | 20-25 % | La confrontation ou le choix décisif ; la résolution ; une dernière image qui reste en tête. |

Pour un film de 2 minutes : environ 25-30 s d'acte 1, 60-70 s d'acte 2, 25-30 s d'acte 3.

**La dernière image** est souvent ce dont le spectateur se souvient. Pense-la dès le début, et fais-la répondre à la première (écho, contraste, boucle).

## 3. Le découpage en scènes et en générations

1. **Séquencier** : une ligne par scène (`script-writing-fr.md`).
2. **Scénario** des scènes dialoguées.
3. **Découpage technique** de chaque scène, plan par plan.
4. **Regroupement en générations** :
   - regroupe des lignes du script seulement si elles partagent les mêmes personnages, le même lieu et la même unité émotionnelle ;
   - coupe à chaque changement de lieu, entrée d'un personnage ou insert ;
   - ne fragmente jamais un moment émotionnel continu (une confession, un effondrement) ;
   - une scène longue se répartit en plusieurs générations (5a, 5b, 5c).
5. **Repères de durée** : 4-8 s pour une action forte ; 8-12 s pour une action et une révélation ; 12-15 s pour deux ou trois actions simples ; jusqu'à 30 s pour une séquence à étapes si le modèle le permet.

## 4. La méthode de production

L'ordre qui économise le plus d'argent et de temps :

1. **Les éléments d'abord** : fiches personnages, images de référence, décors, préfixe de style (`continuity.md`). C'est l'étape qui fait gagner le plus, avant toute vidéo.
2. **Un essai de rendu** : un plan court par personnage et par décor, pour valider le look avant de lancer la production.
3. **Un premier montage brut** avec toutes les générations, même imparfaites, pour juger le rythme et l'histoire.
4. **Les moments clés** : retravaille d'abord les plans qui portent l'émotion (la révélation, la fin).
5. **La supervision des générations** : la seule fenêtre où l'on régénère. Ensuite, on fige.
6. **Le montage fin**, le son, l'étalonnage : la première tâche de l'étalonnage est d'unifier les plans voisins issus de générations différentes.
7. **Le registre** : pour chaque génération, le prompt, les références, la prise gardée et pourquoi. Il évite de refaire deux fois les mêmes erreurs.

**Pose des critères de réussite avant de commencer**, par exemple : le spectateur oublie que c'est de l'IA ; l'histoire tient ; les personnages ont l'air habités ; les moments forts portent.

## 5. Le budget réaliste

- Un film IA se monte avec les meilleures secondes de **nombreuses prises**. Sur une production professionnelle de long-métrage, une infime partie des générations a été gardée ; les créateurs indépendants comptent souvent plusieurs dizaines de générations par plan gardé pour les plans difficiles.
- Pour un premier court-métrage, **vise un film de 1 à 2 minutes** avec des plans simples, plutôt que 5 minutes ambitieuses jamais terminées.
- **Estime le coût en crédits** avant de commencer : nombre de générations prévues × prises par génération × coût d'une génération (`dreamina-seedance.md`).
- **Récupère les bons fragments** : une prise ratée peut contenir deux secondes parfaites.
