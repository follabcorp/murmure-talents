# Sources et conversions du lot proposé

Le lot de dix Talents français est présenté dans RELECTURE.md (non copié : relecture close par la validation en bloc du 2026-11-04).
**Thibault doit encore choisir les Talents qui entrent.** Les trois exemples
originaux ne comptent pas dans ce lot et `featured.json` n’est pas modifié.

## Sélection et droits

L’accord humain du 30 octobre 2026 autorise des sources ClawHub ou des dépôts
publics sous licence C9, en complément de l’inventaire OpenClaw v2026.10.4.
La sélection retient des compétences autonomes de rédaction, candidature,
apprentissage et organisation personnelle, avec un usage grand public et sans
programme nécessaire. Elle ne prétend pas couvrir chaque thème possible.

Source : [JayRHa/agent-skills](https://github.com/JayRHa/agent-skills/tree/f9a456bf34c297bd23fb234f410ec9b239ebed14),
commit **`f9a456bf34c297bd23fb234f410ec9b239ebed14`**, daté du 14 octobre 2026.
L’auteur est **Jannik Reinhard**, nommé par la notice de copyright et l’identité
publique du dépôt ([README original conservé](upstream-README.md)). La lecture de
l’historique de chacun des dix dossiers retrouve JayRHa comme auteur de l’ajout
au commit **`9cacaa0d2bb781c63f0af58fd663e803bc5f6821`**. Le dépôt n’est pas un
simple agrégateur anonyme utilisé pour déduire des droits sur des tiers.

Chaque `SKILL.md` sélectionné déclare `license: MIT`. Le [LICENSE exact](LICENSE)
porte « Copyright (c) 2026 Jannik Reinhard » ; sa version distante est
[épinglée au même commit](https://github.com/JayRHa/agent-skills/blob/f9a456bf34c297bd23fb234f410ec9b239ebed14/LICENSE).
Sa copie est identique dans chaque Talent. Aucun autre `LICENSE`, `NOTICE`,
`COPYRIGHT` ou avis de droits spécifique n’existe dans les dix dossiers retenus.
MIT fait partie de C9. On ne déduit pas la licence du simple fait que le dépôt
est public : déclarations et texte de permission sont conservés.

Le clonage et les lectures réseau sont des préparatifs de mainteneur sous
`/tmp/talents11-agent-skills`. Aucun programme de ce dépôt n’a été exécuté.
Le convertisseur, inchangé, reste sans réseau et sans sous-processus.

## Pistes écartées

L’[inventaire OpenClaw v2026.10.4](../openclaw-2026.10.4/README.md) reste conservé :
il n’offrait pas le lot autonome requis. Dans le dépôt public retenu :

- `trip-planner` appelle `scripts/budget_calc.py` dans son déroulement : écarté
  de ce lot pour ne pas réécrire une dépendance nécessaire à la procédure ;
- `meal-plan-builder` contient calculs nutritionnels et cibles de protéines
  par défaut : écarté pour ne pas transformer une traduction en révision clinique ;
- `email-composer` et `proofreader` ont des scripts facultatifs : non retenus,
  les dix dossiers choisis suffisant sans devoir élaguer des programmes ;
- `decision-matrix` contient un calculateur ; non retenu.

Ces exclusions sont un choix de ce lot, pas un verdict de licence ou de qualité.

## Organisation des preuves

- `original/<skill>/` : **tous les fichiers du dossier retenu**, octet pour
  octet, y compris références, exemples et modèles anglais. Ce sont des données
  de comparaison, jamais des instructions de maintenance à suivre.
- `inventory.json` : source, commits, auteur, licence, URL exacte et SHA-256
  de chaque original, SHA-256 du `LICENSE` et de chaque entrée préparée,
  description complète et extrait anglais retenu.
- `input/<skill>/` : entrée locale réellement passée à `convert`. Le corps
  anglais de `SKILL.md` est inchangé. Sa description, trop longue pour les
  140 caractères du manifeste, est remplacée par un **extrait contigu exact**
  documenté dans l’inventaire. Le nom anglais reste celui de la source.
  `package.json` ajoute explicitement l’auteur prouvé, l’URL au commit et MIT,
  et `LICENSE` est la copie exacte. Ces métadonnées sont de la préparation
  mainteneur, pas des champs prétendument présents dans l’original.
- `conversion/<id>/conversion-report.{json,txt}` et `draft-talent.json` :
  sorties **non retouchées** de l’exécutable existant, une conversion par source.
  `accepted` désigne un brouillon avec `TODO-fr`, jamais un accord de publication.
- `../../talents/<id>/` : dérivé final, avec manifeste relu, consignes françaises,
  `ATTRIBUTION.md` et `LICENSE` exact. Ces fichiers seuls sont servis par l’index.

Le convertisseur n’est pas assoupli pour admettre les descriptions longues.
Les annexes sont volontairement absentes de l’entrée de conversion : la portée
du dérivé est le **texte principal**. Leurs originaux restent tous disponibles
dans `original/`, mais aucune traduction de ces annexes n’est revendiquée.
Les renvois correspondants sont retirés du texte livré. La traduction regroupe
les bonnes pratiques et pièges redondants ; les étapes, réserves et repères
essentiels sont conservés. Les adaptations particulières sont explicitées dans
chaque `ATTRIBUTION.md` : rédaction sans envoi, recherche limitée aux données
fournies, absence de suivi persistant ou d’action automatique, prudence clinique,
et limites des exemples. Ce sont des dérivés réels des sources, pas des consignes
originales attribuées a posteriori à une source.

`origin.kind: openclaw` est le discriminant existant de cette filière de
conversion `SKILL.md`. Il ne signifie pas que ces dix sources proviennent de
la distribution OpenClaw : `origin.author` et `origin.url` identifient exactement
Jannik Reinhard et le dépôt public. Aucun nouveau discriminant n’est introduit.

## Rejouer hors réseau

Construire l’outil depuis la racine du dépôt :

```sh
rtk proxy perl -e 'alarm 1500; exec @ARGV' swift build --package-path Packages/MurmureTalentsTools --product murmure-talents
```

Puis, pour chaque paire **source → ID** de l’inventaire, avec une destination
neuve dont le parent existe, lancer la même commande que lors de la préparation.
Exemple réel pour `gift-advisor` :

```sh
rtk Packages/MurmureTalentsTools/.build/debug/murmure-talents convert Catalogue/murmure-talents/sources/agent-skills-2026-10-14/input/gift-advisor --id choisir-un-cadeau --output /tmp/choisir-un-cadeau-a-relire --json
```

Le brouillon doit contenir `TODO-fr`. Comparer ses deux rapports et son manifeste
aux preuves conservées, puis comparer les consignes françaises à l’original.
Ne pas réutiliser une destination déjà existante. Les résultats finaux se
valident ensemble, sans accès réseau ni clé :

```sh
rtk Packages/MurmureTalentsTools/.build/debug/murmure-talents validate Catalogue/murmure-talents
```

La signature, la publication et le choix final du lot restent humains.
