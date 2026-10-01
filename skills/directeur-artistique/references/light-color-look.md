# Lumière, couleur et rendu — direction de la photographie

Ce fichier sert à définir le « look » d'une vidéo : la lumière, la palette, la texture et l'époque. Le look est ce qui fait qu'une vidéo IA ressemble à du cinéma plutôt qu'à une démo.

## Sommaire
1. Méthode : un look = une lumière + une palette + une texture
2. Lumière naturelle
3. Lumière de studio et schémas classiques
4. Lumières pratiques et ambiances de nuit
5. Atmosphère : fumée, pluie, poussière
6. Palettes et étalonnage
7. Pellicules et textures
8. Époques et esthétiques
9. Signatures de réalisateurs et chefs opérateurs
10. Bien éclairer les peaux foncées
11. Règles pour la vidéo IA
12. Contre le rendu « IA »

---

## 1. Méthode : un look = une lumière + une palette + une texture

Décris toujours ces trois couches, et pas plus d'une ou deux références de style par prompt :

1. **La lumière** : d'où elle vient, sa qualité (dure ou douce), sa couleur, sa direction.
2. **La palette** : deux ou trois couleurs dominantes, et leur rapport (contraste chaud/froid, camaïeu, monochrome).
3. **La texture** : propre et numérique, ou grain de pellicule, halation, flou.

Exemple : `warm golden hour backlight from frame-right, soft rim light on her hair, teal shadows and warm skin tones, natural film-like contrast`.

Une source de lumière motivée (une lampe, un néon, le soleil couchant visible dans le cadre) rend l'image crédible. Une lumière sans source paraît artificielle.

**Nomme la source, pas l'ambiance.** Donne sa position, sa qualité et sa physique : `key light from screen-left, about 30 degrees above eye line` ; `warm bounce off the floor lifting the shadow under the jaw` ; `haze softening contrast beyond 6 m`.
- **Une seule logique de lumière par lieu** : jamais deux soleils.
- **Fixe la température de couleur par scène** : 3200 K pour le tungstène chaud, 5600 K pour la lumière du jour.
- **Place la caméra du côté de l'ombre** : les visages gardent leur volume.

## 2. Lumière naturelle

| Prompt | Rendu | Usage |
|---|---|---|
| `golden hour`, `warm low sunlight` | Lumière dorée rasante, ombres longues | Romance, nostalgie, été, lifestyle |
| `blue hour`, `twilight` | Bleu profond après le coucher du soleil | Mélancolie, ville qui s'allume, transition jour-nuit |
| `harsh midday sun`, `hard shadows` | Contraste dur, ombres nettes | Chaleur, western, désert, tension |
| `overcast soft light` | Lumière diffuse sans ombres | Réalisme, drame social, mode douce |
| `backlit`, `sun flare through the trees` | Contre-jour, halo | Rêve, liberté, silhouette |
| `dappled light through leaves` | Lumière tachetée sous les arbres | Été, terrasse ombragée, poésie |
| `moonlight`, `cool blue night light` | Nuit bleutée | Mystère, romance nocturne |

## 3. Lumière de studio et schémas classiques

| Prompt | Rendu | Usage |
|---|---|---|
| `high-key lighting` | Très lumineux, peu d'ombres | Pub, comédie, beauté, produit |
| `low-key lighting` | Majorité d'ombres, contraste fort | Thriller, film noir, drame |
| `chiaroscuro` | Clair-obscur pictural | Drame intense, portrait de caractère |
| `Rembrandt lighting` | Triangle de lumière sur la joue | Portrait noble, gravité |
| `split lighting` | Visage coupé en deux par l'ombre | Dualité, ambiguïté, menace |
| `butterfly lighting` | Lumière frontale haute, ombre sous le nez | Beauté, glamour |
| `rim light`, `edge light` | Liseré de lumière sur le contour | Détacher le sujet du fond, nuit, héroïsme |
| `silhouette against a bright background` | Sujet noir sur fond clair | Mystère, iconique, épure |
| `softbox key light`, `beauty dish` | Lumière douce et enveloppante | Interview, beauté, produit |

## 4. Lumières pratiques et ambiances de nuit

Les lumières pratiques sont des sources visibles dans le décor. Elles sont essentielles pour les ambiances de soirée.

| Prompt | Rendu | Usage |
|---|---|---|
| `warm string lights`, `festoon lights` | Guirlandes lumineuses, bokeh doré | Terrasse, fête en plein air, mariage, été |
| `neon signs`, `neon-lit street` | Néons colorés, reflets | Nuit urbaine, néo-noir, Asie, clip |
| `candlelight`, `firelight` | Flamme chaude et vacillante | Intimité, rituel, veillée |
| `club strobe lights`, `stage lights with haze` | Faisceaux, stroboscope, scène | Concert, DJ set, clip |
| `practical lamp in frame` | Lampe visible qui motive la lumière | Intérieur réaliste, drame |
| `fluorescent overhead lighting` | Néon blafard verdâtre | Malaise, bureau, hôpital, ironie |
| `car headlights`, `police lights` | Phares, gyrophares | Polar, tension nocturne |
| `projector light on a face` | Image projetée sur un visage | Clip, surréalisme, rêve |

## 5. Atmosphère : fumée, pluie, poussière

L'atmosphère rend la lumière visible et donne de la profondeur.

- `light haze`, `atmospheric smoke` : les faisceaux deviennent visibles.
- `volumetric light`, `god rays` : rais de lumière à travers une fenêtre, des arbres, une fumée.
- `rain-soaked street with reflections` : reflets, néons démultipliés, polar.
- `dust particles floating in the sunlight` : grenier, désert, nostalgie.
- `steam rising` : cuisine, rue la nuit, bain.

## 6. Palettes et étalonnage

| Prompt | Rendu | Usage |
|---|---|---|
| `teal and orange color grade` | Contraste peaux chaudes / fonds froids | Blockbuster, action, pub |
| `warm amber palette` | Chaud, doré | Nostalgie, été, convivialité |
| `cold desaturated palette` | Froid, peu saturé | Thriller, solitude, hiver |
| `muted earthy tones` | Terres, ocres, verts sourds | Naturel, artisanat, désert, cinéma d'auteur |
| `pastel palette` | Couleurs douces | Mode, romance légère, Wes Anderson |
| `saturated vibrant colors` | Couleurs franches | Clip, afro-pop, fête, comédie |
| `monochrome red`, `monochromatic` | Une seule teinte | Clip graphique, tension, style |
| `high-contrast black and white` | Noir et blanc dur | Intemporel, mode, drame |
| `bleach bypass look` | Désaturé, contrasté, métallique | Guerre, dureté |

Choisis la palette en fonction de l'émotion, puis tiens-la sur tous les plans de la vidéo. C'est l'un des premiers signes de qualité d'une série de plans.

- **La règle 60:30:10** : une couleur dominante (60 %), une secondaire (30 %), une d'accent (10 %), chacune rattachée à une source de lumière et à une surface.
- **Réserve une couleur saturée à l'histoire** : l'objet ou le moment clé est le seul à la porter.
- **Contiens les couleurs qui débordent** : `yellow exists only inside the lamp bulb and a palm-sized halo beneath it`.
- **Quand l'étalonnage compte**, précise la courbe des tons, le traitement des hautes lumières et le nom du rendu.

## 7. Pellicules et textures

| Prompt | Rendu |
|---|---|
| `shot on Kodak Portra 400` | Peaux chaudes et douces, pastel naturel, lifestyle haut de gamme |
| `Kodak Vision3 500T film stock` | Nuit cinéma, tungstène, grain fin |
| `CineStill 800T, red halation around lights` | Halos rouges autour des lumières de nuit, très tendance |
| `Fuji Velvia` | Paysages saturés, verts et bleus profonds |
| `16mm film grain` | Grain marqué, indé, documentaire, clip |
| `Super 8 home video` | Souvenir, vintage, bords irréguliers |
| `VHS camcorder footage, scan lines` | Années 90, found footage, nostalgie |
| `clean digital cinema look, ARRI Alexa` | Cinéma moderne propre |
| `iPhone vertical footage, natural look` | UGC, authentique, lifestyle réseaux |
| `halation`, `bloom`, `light leaks` | Douceur, rêve, lumière qui bave |
| `chromatic aberration` | Défaut d'optique, psyché, clip |

**Attention au grain dans le prompt** : un `film grain` ajouté seul en fin de prompt adoucit souvent toute l'image, et un grain fort crée des artefacts en mouvement. Pour une texture de pellicule fiable, intègre-la dans l'image de référence ou ajoute-la au montage.

**L'anamorphique est un rendu, pas un format** : bokeh ovale, flares horizontaux, légère courbure des bords. `16:9 anamorphic` est incohérent.

## 8. Époques et esthétiques

- `1970s film look` : couleurs chaudes, zooms lents, grain, cols pelle à tarte.
- `1980s neon synthwave` : néons rose et cyan, brume, rétro-futur.
- `1990s camcorder` : VHS, flash direct, spontané.
- `Y2K aesthetic` : chrome, bleu glacier, fish-eye, brillances.
- `Afrofuturism` : futur africain, textiles wax réinventés, architecture organique, or et lumière.
- `French New Wave` : noir et blanc, caméra libre, Paris, jump cuts.
- `K-drama soft romance` : lumière diffuse, pastel, ralentis, regards.
- `Wong Kar-wai-esque Hong Kong night` : néons, ralentis saccadés, rouges et verts saturés.

## 9. Signatures de réalisateurs et chefs opérateurs

Une référence d'auteur résume tout un look en quelques mots. Mais **dans le prompt, décris les traits plutôt que le nom** : la description est plus fiable, et citer un studio ou un ayant droit déclenche souvent la modération de Dreamina. Le tableau sert surtout à choisir un parti pris et à en extraire les traits à écrire.

| Référence | Traits à décrire dans le prompt |
|---|---|
| Wong Kar-wai / Christopher Doyle | Néons saturés, ralentis saccadés (`step-printed motion blur`), cadres obstrués, mélancolie urbaine |
| Roger Deakins | Une source de lumière maîtrisée, silhouettes, compositions épurées, naturalisme |
| Emmanuel Lubezki | Lumière naturelle, grand angle très proche des visages, plans-séquences flottants |
| Denis Villeneuve | Échelle monumentale, brume, palettes sourdes, architecture brutaliste |
| Wes Anderson | Symétrie frontale, pastel, mouvements à angle droit, décors de maison de poupée |
| Bradford Young | Sous-exposition riche, peaux noires lumineuses et profondes, ombres veloutées |
| James Laxton (Moonlight) | Couleurs saturées, peaux brillantes, bleus nocturnes, intimité |
| Hiro Murai | Surréalisme pince-sans-rire, plans fixes longs, malaise poétique |
| Romain Gavras | Foules immenses, grand angle, énergie collective, chaos chorégraphié |
| Michel Gondry | Trucages artisanaux, bricolage poétique, transformations dans le champ |
| Hype Williams | Fish-eye, couleurs pop, contre-plongées, clip hip-hop iconique |
| Sofia Coppola | Pastel doux, lumière naturelle diffuse, solitude élégante |
| David Fincher | Vert-jaune désaturé, cadres précis, mouvements imperceptibles |
| Stanley Kubrick | Perspective centrale à point de fuite unique, symétrie froide |

## 10. Bien éclairer les peaux foncées

Les modèles IA ont tendance à aplatir ou griser les peaux foncées si le prompt ne les guide pas. Pour un rendu riche et respectueux :

- Demande une peau lumineuse et texturée : `rich deep skin tones with natural sheen`, `luminous dark skin`.
- Utilise une lumière chaude ou un liseré qui sculpte le visage : `warm key light`, `soft rim light sculpting the face`.
- Évite les lumières plates et frontales qui écrasent les volumes.
- Précise une exposition pensée pour la peau : `exposed for skin tones`, `detailed skin texture, no flattening`.
- Les références Bradford Young et James Laxton (section 9) sont les meilleurs repères pour ce rendu.

## 11. Règles pour la vidéo IA

- **Une ou deux références de style maximum par prompt.** Mélanger Wes Anderson, Blade Runner et Kodak Portra donne une image confuse.
- **Garde le même look sur tous les plans d'une vidéo.** Recopie le bloc look (lumière + palette + texture) à l'identique dans chaque prompt de la série.
- **Motive la lumière.** Mentionne la source visible : `lit only by the streetlight outside the window`.
- **Le piège de la nuit.** Une « nuit » demandée sans plus de précision revient éclairée uniformément, avec un voile bleu. Écris uniquement des sources pratiques (lampadaires au sodium, phares, écrans, néons, bougies), pas de lune ni de ciel qui éclaire, des noirs presque bouchés, et une légère brume qui rend les faisceaux visibles.
- **Un seul registre, et son contraire.** `photoreal live-action, not a 3D render` ou `cel-shaded 2D animation, clean flat fills`. Au-delà de deux ou trois termes de style, le rendu devient générique.

## 12. Contre le rendu « IA »

Le rendu trop lisse, trop propre, trop parfait est ce qui trahit l'IA au premier regard.
- **La peau** : pores visibles, fin duvet, grains de beauté asymétriques, rougeurs légères, aucune retouche : `visible pores, fine facial hair, natural skin, no retouching`.
- **Les matières** : deux à quatre propriétés chacune (base, finition, usure, bord) : `matte ceramic mug, chipped rim`, `scuffed leather, worn at the elbows`.
- **L'imperfection vit dans la scène, pas dans l'image** : des objets ordinaires et nommés (`a charger cable, a half-empty glass, a crumpled receipt`) valent mieux que `a lived-in room`. Mais évite `dreamy`, `soft focus` ou `blurry background`, qui adoucissent tout.
- **Pour un rendu « filmé au téléphone »** : `handheld phone feel, not a professional set`, un léger tremblé, une lumière de fenêtre.
- **La texture se dose**, et elle est plus fiable au montage ou dans l'image de référence que dans le prompt (voir §7).
