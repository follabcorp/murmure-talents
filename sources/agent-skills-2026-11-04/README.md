# Source JayRHa/agent-skills : deuxième lot (2026-11-04)

Quatorze Talents candidats du deuxième lot (ticket `talents/13`) viennent de cette source,
la même que le [premier lot](../agent-skills-2026-10-14/README.md), mais avec des skills **non encore converties**.
**Thibault doit encore choisir ceux qui entrent** (voir `RELECTURE.md`) ; `featured.json` n’est pas modifié.

## Sélection et droits

Source : [JayRHa/agent-skills](https://github.com/JayRHa/agent-skills/tree/f9a456bf34c297bd23fb234f410ec9b239ebed14),
commit **`f9a456bf34c297bd23fb234f410ec9b239ebed14`**, daté du 14 octobre 2026, cloné hors du dépôt
dans `/tmp/talents13-agent-skills` le 4 novembre 2026. Auteur : **Jannik Reinhard**
(notice de copyright du [LICENSE](LICENSE), copie exacte). L’historique de chacun des
quatorze dossiers retient JayRHa comme auteur de l’ajout au commit
`9cacaa0d2bb781c63f0af58fd663e803bc5f6821`.

Chaque `SKILL.md` retenu déclare `license: MIT` ; les 75 skills du dépôt le font. Aucun
`NOTICE`, `COPYRIGHT` ou avis spécifique n’existe dans les quatorze dossiers. MIT fait partie de C9.
La licence n’est pas déduite du caractère public du dépôt : déclaration et texte de permission
sont conservés. Aucun programme du dépôt cloné n’a été exécuté.

Le choix privilégie la vie courante d’une personne non technicienne sans doublon avec les
quinze Talents déjà présents : budget, sport doux, repas, révision, lecture, écriture,
négociation salariale, relecture, e-mail, décisions, réunions, projets, bilan personnel, présentations.

## Pistes écartées

Les 61 autres skills du dépôt sont techniques (code, infrastructure, sécurité, données) et sans
rapport avec le public visé, ou doublonnent un Talent existant. Plus précisément :

- `trip-planner` : doublon de `planifier-un-voyage`, et son déroulement appelle `scripts/budget_calc.py` ;
- `gift-advisor`, `cover-letter-writer`, `resume-writer`, `interview-prep`, `habit-builder`, `event-planner`,
  `language-tutor`, `study-plan-builder`, `public-speaking-coach`, `concept-explainer` : déjà convertis au premier lot ;
- `okr-writer`, `job-description-writer`, `people-data` : vocabulaire d’entreprise, sans usage pour une personne seule ;
- toutes les autres (API, bases de données, Docker, Kubernetes, SQL, tests, sécurité…) : hors public.

Ces exclusions sont un choix de ce lot, pas un verdict de licence ou de qualité.

## Reformulations et tri

Aucune des quatorze skills n’exige un outil, une variable d’environnement ou un accès réseau
dans son déroulement ; les scripts Python qu’elles proposent sont facultatifs et **ne sont pas distribués**
(ni dans les Talents, ni dans `original/`, qui n’a pas de programmes : leurs SHA-256 et URL sont dans
`inventory.json`, rubrique `scriptsNotCopied`). Quatre skills touchent à un domaine sensible et sont **reformulées**
avec renvoi vers un professionnel : `budget-du-foyer` (finance), `programme-de-sport` (santé),
`repas-de-la-semaine` (nutrition), `negocier-son-salaire` (droit du travail). Le détail est dans
l’`ATTRIBUTION.md` de chaque Talent.

## Organisation des preuves

- `original/<skill>/` : fichiers de texte du dossier retenu, octet pour octet (sans les scripts), y compris références,
  exemples et modèles anglais ; données de comparaison, jamais des instructions à suivre. Les dix dossiers dont l’original
  contient des `scripts/*.py` (inventaire, rubrique `scriptsNotCopied`) ne les conservent pas, parce que le Catalogue n’accepte
  pas de scripts ; ils restent lisibles au lien source épinglé ;
- `inventory.json` : source, commit, licence, URL et SHA-256 de chaque original ;
- `conversion/<id>/conversion-report.json` et `draft-talent.json` : sorties **non retouchées** de
  `murmure-talents convert` (`target/release/murmure-talents convert <entrée> --id <id> --output … --json`), une conversion
  par skill. L’entrée passée à l’outil est le `SKILL.md` d’origine dont la description est réduite à un extrait
  contigu exact de moins de 141 caractères, avec le `LICENSE` exact, hors annexes ;
  `accepted` désigne un brouillon (`TODO-fr`, auteur « À renseigner »), jamais un accord de publication ;
- `../../talents/<id>/` : dérivé final relu, avec `ATTRIBUTION.md` et `LICENSE` exact.

`origin.kind: public` est ce que l’outil produit pour cette source ; `origin.author` et `origin.url` identifient
JayRHa et le dépôt au commit épinglé. L’auteur du manifeste est « Murmure » avec le compte `thibault-ballof`, comme pour
les Talents existants : le Catalogue exige un compte GitHub (`CODEOWNERS`), et on ne désigne pas un tiers comme
responsable sans son accord.
