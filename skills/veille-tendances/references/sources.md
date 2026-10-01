# Où chercher les tendances, et comment

> Accès testés le 1er octobre 2026 avec une simple lecture de page web. Les plateformes changent souvent leurs pages : si une source ne répond plus, dis-le dans le rapport et passe à la suivante.

## Sommaire
1. Les sources disparues
2. Le tableau des sources
3. La recherche quotidienne sur un pays
4. Le tour du monde hebdomadaire
5. La revue mensuelle

---

## 1. Les sources disparues

Ne perds pas de temps avec :
- **la page Tendances de YouTube**, supprimée le 21 juillet 2025 ;
- **les classements Viral 50 de Spotify**, supprimés en mai 2026. Remplace-les par Shazam et par les plus fortes progressions sur Kworb.

## 2. Le tableau des sources

| Source | Ce qu'elle apprend | Accès | Comment l'interroger |
|---|---|---|---|
| **Google Trends, flux « Trending now »** | Les recherches qui s'envolent maintenant, par pays | Fonctionne sans compte | `https://trends.google.com/trending/rss?geo=FR` (remplace FR par BE, CH, CA, US, GB, NG, CI, SN, BR, MX, JP, KR, IN, SA…). Pour un mot-clé : `trends.google.com/trends/explore?geo=FR&date=now%207-d&q=MOT` ; ajoute `&gprop=youtube` pour les recherches YouTube |
| **TikTok Creative Center** | Hashtags, sons, créateurs et vidéos en tête par pays ; fenêtres de 7, 30 ou 120 jours ; « New to top 100 » ; filtre des sons autorisés pour un usage commercial | Pages générées en JavaScript : **il faut un navigateur**. Les listes sont visibles sans compte, le détail demande un compte TikTok for Business | `ads.tiktok.com/business/creativecenter/pc/en`, puis Trends ; ajoute `?countryCode=FR&period=7` |
| **Pages « discover » de TikTok** | Si un format ou un sujet existe déjà, avec des exemples | Publiques, indexées par les moteurs | Recherche web : `site:tiktok.com/discover MOT` |
| **YouTube Charts, Top Songs on Shorts** | Les musiques les plus utilisées dans les Shorts, dans 12 pays (FR, US, UK, DE, BR, MX, IN, JP, KR, AE, AU, CA) | **Il faut un navigateur** | `charts.youtube.com/charts/TopShortsSongs/fr/weekly` (vérifie le chemin selon le pays) |
| **Sons tendance d'Instagram** | Les audios en progression | **Uniquement dans l'application**, aucune page web | Utilise les récapitulatifs hebdomadaires des agences comme confirmation tardive |
| **Kworb** | Classements Spotify quotidiens et hebdomadaires par pays, avec les progressions ; pages Apple Music, iTunes, Deezer, Shazam, YouTube | Fonctionne | `kworb.net/spotify/country/fr_daily.html` (ng, za, br, mx, co, jp, kr, in…) ; Apple Music : `kworb.net/charts/apple_s/ci.html` |
| **Shazam** | Signal précoce : les musiques que les gens identifient après les avoir entendues dans des vidéos ou en soirée | Fonctionne | `shazam.com/charts/top-200/france`, `/viral/france`, `/discovery/france`, plus des classements par ville (Paris, Lyon, Marseille…) et par pays (Côte d'Ivoire, Nigeria, Afrique du Sud, Sénégal, Cameroun, Ghana…) |
| **Tendances de X par pays** | Les sujets du moment, heure par heure, et leur durée | Fonctionne | `trends24.in/france/`, `getdaytrends.com/france/` (aussi /japan, /saudi-arabia, /nigeria…) |
| **Know Your Meme** | L'origine, la date et le statut d'un mème : utile pour dater le cycle de vie | Fonctionne | `knowyourmeme.com`, rubriques Top Entries This Month et Fresh Entries |
| **Exploding Topics** | Les tendances lentes de produits et de modes de vie, avec leur croissance | La liste gratuite fonctionne | `explodingtopics.com` |
| **Recherches chaudes de Douyin** | Les 50 sujets les plus chauds en Chine | Fonctionne (adresse non officielle, peut casser) | `https://www.iesdouyin.com/web/api/v2/hotsearch/billboard/word/` |
| **Recherches chaudes de Weibo** | Les sujets du moment en Chine | La page officielle demande un compte ; **une archive horaire sur GitHub fonctionne** | `raw.githubusercontent.com/justjavac/weibo-trending-hot-search/master/archives/AAAA-MM-JJ.md` |
| **Baidu** | Recherches en temps réel, romans, films, séries | Fonctionne | `top.baidu.com/board?tab=realtime` |
| **Bilibili** | Vidéos populaires | Fonctionne | `api.bilibili.com/x/web-interface/popular?ps=20&pn=1` |
| **Kuaishou, Xiaohongshu** | Listes de tendances | Bloquées sans compte ; essaie un navigateur | Recherche web « 小红书 热门 » suivie du mois |
| **Lettres de tendances** | Confirmation et mécanique des formats | Publiques | Les récapitulatifs mensuels des agences françaises de social media, les tendances TikTok mensuelles d'Epidemic Sound, Later |

**Si un outil de navigateur est disponible** (navigateur intégré ou extension Chrome), utilise-le pour TikTok Creative Center et YouTube Charts : ce sont les deux meilleures sources pour la vidéo courte. Sinon, signale dans le rapport qu'elles n'ont pas pu être consultées.

## 3. La recherche quotidienne sur un pays (environ 15 minutes)

Exemple pour la France ; remplace les codes pays selon la cible.

1. **Flux Google Trends** du pays et de ses voisins francophones (FR, BE, CH, CA) : repère la musique, les événements, la météo, les fêtes, les moments télévisés.
2. **Tendances de X** du pays : les sujets qui durent (émissions, sport) nourrissent les mèmes d'actualité.
3. **Kworb** (Spotify du jour : nouvelles entrées, progressions de plus de dix places) et **Shazam** (viral, découverte, villes) : les sons candidats.
4. **TikTok Creative Center**, pays, 7 jours, dans un navigateur : sons en percée et autorisés pour un usage commercial, hashtags « New to top 100 ». Garde les sons qui montent **et** sont autorisés.
5. **Chasse les formats**, pas seulement les sons : pages discover de TikTok, récapitulatifs mensuels des agences.
6. Pour chaque candidat, note les preuves (date, nombre de vidéos, nombre de créateurs), attribue un stade et une note (`scoring.md`). Garde au maximum cinq fiches.

## 4. Le tour du monde hebdomadaire

Répète les étapes 1 à 4 pour chaque marché. À l'étranger, le but est d'importer **des formats et des effets visuels qui voyagent sans la langue**, pas des sujets locaux.

| Marché | Sources |
|---|---|
| États-Unis, Royaume-Uni | TikTok Creative Center, Know Your Meme, musiques des Shorts |
| Nigeria, Afrique du Sud | Spotify NG et ZA sur Kworb, Shazam, Google Trends (NG, ZA) |
| Afrique francophone (Côte d'Ivoire, Sénégal, Cameroun, Burkina Faso…) | Shazam CI et SN, Apple Music sur Kworb (CI, BF, SN, CM), Google Trends, recherches web du type « tendance TikTok Côte d'Ivoire » |
| Brésil, Mexique, Colombie | Spotify BR, MX, CO ; musiques des Shorts BR et MX ; Google Trends |
| Japon, Corée | Musiques des Shorts JP et KR, trends24 Japon, Spotify JP et KR |
| Inde | Musiques des Shorts IN, Spotify IN, Google Trends IN (TikTok y est interdit) |
| Golfe, Moyen-Orient | Google Trends SA, AE, EG ; trends24 Arabie saoudite ; musiques des Shorts AE |
| Chine | Douyin, Baidu, Bilibili, archive Weibo |

## 5. La revue mensuelle

- Know Your Meme (Top Entries This Month) et Exploding Topics.
- Les annonces officielles des plateformes (règles, nouvelles fonctions).
- La vérification des chiffres marqués « à revérifier » dans `regions.md`.
