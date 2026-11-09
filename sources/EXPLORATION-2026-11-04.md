# Exploration des sources du deuxième lot (2026-11-04)

Ordre du ticket `talents/13`. Chaque source a été clonée hors du dépôt (`/tmp/talents13-<source>`) à un commit noté ;
aucun programme cloné n’a été exécuté. Seules les deux premières donnent des Talents.

| Source | Commit | Licence vérifiée | Résultat |
| --- | --- | --- | --- |
| NousResearch/hermes-agent, tag `v0.22.5` | `bf0203a794a07aac3ff764972ab9087baa4e4f4e` | MIT (dépôt et chaque `SKILL.md` retenu) | 4 Talents : [README](hermes-agent-v0.22.5-2026-11-04/README.md) |
| Skills publiques de l’écosystème OpenClaw / ClawHub | non cloné | non admissible | Aucune skill admissible d’après l’inventaire OpenClaw v2026.10.4 déjà fait (cité par le ticket) ; **cette source n’a pas été ré-explorée** : le ticket limitait l’effort à quelques minutes et les deux autres sources suffisaient pour atteindre 18 candidats. Aucun Talent. |
| JayRHa/agent-skills | `f9a456bf34c297bd23fb234f410ec9b239ebed14` | MIT (`license: MIT` dans chacune des 75 skills, notice de Jannik Reinhard) | 14 Talents : [README](agent-skills-2026-11-04/README.md) |
| anthropics/skills | `ca45fc496a3436251f191354091d557da31c15b5` | variable selon la skill | Aucun Talent, voir ci-dessous |

## anthropics/skills : aucune skill retenue

La licence se lit skill par skill (`license:` du `SKILL.md` puis `LICENSE.txt` du dossier) et il n’y a pas de licence à la racine du dépôt :

- `docx`, `pdf`, `pptx`, `xlsx` : « Proprietary. LICENSE.txt has complete terms », avec « © 2025 Anthropic, PBC. All rights reserved » : **refusées** (propriétaires) ;
- `doc-coauthoring` : aucun `LICENSE.txt` dans le dossier ni licence déclarée : **refusée** (pas de licence explicite) ;
- les treize autres (`academy-guide`, `algorithmic-art`, `brand-guidelines`, `canvas-design`, `claude-api`, `discernment-nudge`,
  `frontend-design`, `internal-comms`, `mcp-builder`, `skill-creator`, `slack-gif-creator`, `theme-factory`, `web-artifacts-builder`,
  `webapp-testing`) : `LICENSE.txt` Apache-2.0, admise, mais **sans usage pour une personne non technicienne** (développement,
  création d’illustrations, outils d’agent, communication d’entreprise) ou exigeant des outils : écartées pour leur thème, pas leur licence.

## Autres pistes écartées

Les motifs de tri pour Hermès et JayRHa sont dans le README de chaque source.
