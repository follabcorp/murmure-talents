# Source NousResearch/hermes-agent v0.22.5 : deuxième lot (2026-11-04)

Quatre Talents candidats du deuxième lot (ticket `talents/13`) viennent de cette source, première de la liste du ticket.
**Thibault doit encore choisir ceux qui entrent** (voir `RELECTURE.md`).

## Sélection et droits

Source : [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent/tree/bf0203a794a07aac3ff764972ab9087baa4e4f4e),
tag `v0.22.5`, commit **`bf0203a794a07aac3ff764972ab9087baa4e4f4e`**, cloné hors du dépôt dans `/tmp/talents13-hermes`
le 4 novembre 2026. Le [LICENSE](LICENSE) du dépôt (copie exacte) est une licence **MIT**,
« Copyright (c) 2025 Nous Research ». Les 59 `SKILL.md` de `skills/` déclarent `license: MIT` ; c’est
aussi le cas des skills retenues dans `optional-skills/` (même dépôt, même licence). La licence n’est pas déduite du caractère
public du dépôt. Aucun programme n’a été exécuté.

Les quatre skills retenues sont les seules du dépôt qui servent la vie courante d’une personne non technicienne
sans outil, binaire, compte ni réseau : `weekly-review-planning`, `document-to-action-items`
(`skills/productivity/`, auteur Ben Barclay avec Hermes Agent), `one-three-one-rule`
(`optional-skills/communication/`, auteur Willard Moore) et `creative-ideation` (`optional-skills/creative/`, auteur SHL0MS).

## Chaîne de droits : `trouver-des-idees`

Le `SKILL.md` d’origine (`creative-ideation`) indique que son cœur par contraintes est adapté de [wttdotm.com/prompts.html](https://wttdotm.com/prompts.html) ; la bibliothèque de consignes de l’original renvoie à la même source. La licence de wttdotm.com n’est pas connue, et aucune licence n’est attribuée à ce site. La licence MIT de Nous Research couvre le fichier publié dans hermes-agent, mais elle ne prouve pas les droits sur cet amont cité. Thibault peut écarter ce Talent s’il veut une chaîne de droits stricte.

## Pistes écartées

- **Tout le reste de `skills/`** (51 skills sur 55) : outils, comptes ou binaires exigés (Apple Notes, Rappels, Messages et
  Localiser, Google Workspace, Notion, Airtable, Box, himalaya, maps, xurl, YouTube, GIF, arXiv, Obsidian, claude-code,
  codex, computer-use…), ou développement logiciel, DevOps, création de vidéos et de visuels ;
- `meeting-action-items` : écartée au profit de `meeting-summarizer` (JayRHa), sa jumelle plus simple ;
- `email-inbox-triage` et `himalaya` : exigent un accès à une boîte mail ;
- `humanizer` : porté d’un autre dépôt (blader) et centré sur la détection de formules de texte généré, sans rapport avec le public visé ;
- `decision-questionnaire` : porté du dépôt mattpocock/skills (licence MIT de cet auteur) dont la notice de copyright
  ne figure pas dans ce dépôt ; **écartée faute de pouvoir reproduire la notice exacte** (la conversion existe dans le rapport,
  mais aucun Talent n’en est tiré) ;
- `optional-skills/health/fitness-nutrition` et `finance/stocks` : exigent des API externes ; `finance/*` (modèles Excel) : hors public ;
- le reste de `optional-skills/` : développement, sécurité, blockchain, création vidéo, domotique, réseaux sociaux.

## Reformulations

Les quatre Talents sont **reformulés** pour fonctionner uniquement sur ce que la personne donne dans la Conversation : les
écritures dans Notion, un agenda ou un tableur, l’extraction de PDF et la planification automatique de l’original sont retirées
(détail dans chaque `ATTRIBUTION.md`).

## Organisation des preuves

- `original/<skill>/` : tous les fichiers du dossier retenu, octet pour octet (28 fichiers pour `creative-ideation`, dont
  ses références, qui ne sont pas distribuées avec le Talent) ;
- `inventory.json` : source, commit, licence, URL et SHA-256 de chaque original ;
- `conversion/conversion-report.json` : sortie **non retouchée** de
  `murmure-talents convert <arbre skills/<catégorie>/<skill>> --output … --json` sur les cinq skills présélectionnées
  (copies exactes de `SKILL.md` avec le `LICENSE` du dépôt) ; `conversion/<id>/draft-talent.json` : brouillons produits par l’outil.
  `accepted` ne vaut jamais accord de publication ;
- `../../talents/<id>/` : dérivé final relu, avec `ATTRIBUTION.md` et `LICENSE` exact.

L’outil produit `origin.kind: public` pour cette arborescence ; `origin.author` et `origin.url` identifient l’auteur de la skill
et l’URL au commit épinglé. L’auteur du manifeste est « Murmure » avec le compte `thibault-ballof`, comme pour les Talents existants.
