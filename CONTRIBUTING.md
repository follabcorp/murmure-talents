# Contribuer au Catalogue / Contributing to the Catalogue

## Français

Proposez une PR ; un mainteneur relit tous les fichiers avant toute publication.
Le Catalogue V1 accepte uniquement du texte UTF-8, sans code exécutable, lien,
fichier spécial ou téléchargement de code. Une validation verte ne remplace pas la relecture.

Créez `talents/<id>/talent.json`, `SKILL.md` à la racine du Talent et ses annexes
(y compris les notices de licence). Le format simple est recommandé ; le format
multiple `skills/<nom>/SKILL.md` reste accepté. Les fichiers servis sont limités
à 32, 256 Kio au total, huit segments par chemin ; `talent.json` est séparé,
limité à 16 Kio. Aucun bit exécutable, en-tête Mach-O/ELF/`#!`, lien dur multiple
ou lien symbolique n'est admis. Écrivez un frontmatter `name` et `description`
puis des consignes, en anglais, qui décrivent ce que l’Agent personnel doit faire.

Le manifeste suit BobProtocol : identifiant `[a-z0-9-]` (1 à 64 caractères),
version `MAJEUR.MINEUR.CORRECTIF`, `kind: textOnly`, `localized.fr` et
`localized.en` avec `name` et `summary`, `needs`, `capabilities`, `requires`,
`minimumMurmureVersion`, `author`, `license` ; `platforms` et `origin` sont facultatifs.
Les trois exemples originaux MIT de ce dépôt montrent un manifeste complet.

Auteurs : `author.github` liste de 1 à 4 identifiants GitHub distincts, sans `@`
(1 à 39 caractères ASCII alphanumériques ou tirets, sans tiret en tête ou en fin,
sans tiret double). Il est obligatoire pour tout Talent du Catalogue. Les comptes listés sont
désignés comme propriétaires de `talents/<id>/` dans `CODEOWNERS`.

Montée de version : toute modification d’un fichier d’un Talent (manifeste,
`SKILL.md`, annexe, notice de licence, ajout ou retrait compris) exige une `version`
strictement supérieure à celle de la base, en comparaison semver. Une `version` qui
recule, un changement d’`id` ou des fichiers changés à version égale sont refusés par
`murmure-talents diff`. La PR doit donc relever la version.

`CODEOWNERS` est généré depuis les manifestes, ne le modifiez pas à la main :
`murmure-talents codeowners .` l’imprime (outil installé comme indiqué plus bas).
Chaque `talents/<id>/` est attribué à l’équipe `@follabcorp/murmure` et aux Auteurs
déclarés ; `.github/`, `featured.json` et `revoked.json` ne sont attribués qu’à l’équipe.
`validate` refuse un `CODEOWNERS` présent qui diffère de ce résultat.

Approbations : une PR qui touche `talents/<id>/` demande l’approbation d’un Mainteneur
ou d’un Auteur déclaré, jamais celle de l’auteur de la PR. Une PR qui ajoute une
capacité à un Talent demande **deux approbations de Mainteneurs** ; le rapport de
`diff` le signale. `.github/`, `featured.json` et `revoked.json` sont réservés à
l’équipe, avec deux approbations. Le nombre d’approbations s’impose par la règle de
branche GitHub, configurée par un Mainteneur ; l’outil ne fait que le signaler.

Choisissez un ou deux besoins : `mail`, `calendar`, `organizing`, `writing`,
`paperwork`, `cooking`, `travel`, `home`, `health`, `learning`.
Déclarez uniquement les capacités nécessaires : `read-mail`, `send-mail`,
`organize-mail`, `read-calendar`, `edit-calendar`, `read-reminders`, `edit-reminders`, `read-notes`,
`edit-notes`, `web-search`, `browse-web`.
Chaque capacité doit être couverte par une dépendance directe ; `requires` cite
un Talent du Catalogue ou un manifeste embarqué de BobProtocol. Pas de cycle,
ni de chaîne de plus de quatre niveaux. Un Talent en texte seul n’ajoute aucun outil.

Licences admises : MIT, Apache-2.0, BSD-2-Clause, BSD-3-Clause, ISC, 0BSD,
Unlicense, CC0-1.0, CC-BY-4.0. Conservez les notices, attributions et auteurs
d’origine ; un identifiant SPDX seul ne prouve pas vos droits. Le copyleft et
les restrictions non commerciales sont refusés.

Règle de langue : les consignes d’un Talent (corps et `description` du `SKILL.md`,
annexes lues par l’Agent) s’écrivent en anglais. Chaque `SKILL.md` contient la phrase
« Reply in the language the person uses. », qui demande à l’Agent de répondre dans la
langue de la personne. Les noms et résumés montrés à la personne restent localisés
dans `localized.fr` et `localized.en`, obligatoires. Les identifiants (`id`, `name` de
l’en-tête, `requires`) ne changent pas.

Installez l’outil (`cargo install --locked --git https://github.com/follabcorp/murmure-talents-tools --tag v20261107-7ecfdff murmure-talents`),
puis lancez `murmure-talents validate .` depuis la racine du dépôt.
Joignez le rapport à la PR. La recherche de consignes suspectes, l’envoi de mail
sans capacité, un `SKILL.md` qui semble ne pas être en anglais ou qui ne contient pas
la consigne de répondre dans la langue de la personne émettent des avertissements
non bloquants à expliquer ou à corriger.
Le mainteneur vérifie l’utilité, les sources, les licences, les capacités,
les dépendances et toutes les consignes. Il choisit `featured.json` (au plus trois
identifiants) et gère `revoked.json` (`[{"id":"…","reason":"policy"}]` ; motifs
`malicious`, `broken`, `authorRequest`, `policy`). La clé et la publication restent humaines.

## English

Open a PR. A maintainer reviews every file before publication; a passing automated
check does not replace human review. V1 accepts UTF-8 text only, with no executable
code, special files, symbolic links or multiple hard links.

Add `talents/<id>/talent.json`, a root `SKILL.md` and any text attachments including
license notices. The multiple-skill layout `skills/<name>/SKILL.md` is also supported.
Payload limits are 32 files, 256 KiB total and eight path segments; the separate
manifest is limited to 16 KiB. Executable permission bits, Mach-O/ELF headers and
shebangs are rejected. Give `SKILL.md` a `name` and `description` frontmatter, and
write its instructions in English.

Use the complete original MIT examples as a starting point. Required manifest
fields are `id`, strict three-number `version`, `kind: textOnly`, `localized.fr`
and `localized.en` names and summaries, `needs`, `capabilities`,
`minimumMurmureVersion`, `author` and `license`; include `requires` for dependencies.
`platforms` and conversion provenance `origin` are optional.

Authors: `author.github` lists 1 to 4 distinct GitHub accounts, without `@`
(1 to 39 ASCII letters, digits or hyphens, no leading or trailing hyphen, no double
hyphen). It is mandatory for every Catalogue Talent. The listed accounts are named
as owners of `talents/<id>/` in `CODEOWNERS`.

Version bump: any change to a file of a Talent (manifest, `SKILL.md`, attachment,
license notice, including an addition or a removal) requires a `version` strictly
greater than the base's, compared as semver. `murmure-talents diff` refuses a
`version` that goes back, a changed `id`, and files that change at an equal
`version`. The PR must therefore raise the version.

`CODEOWNERS` is generated from the manifests; do not edit it by hand:
`murmure-talents codeowners .` prints it (tool installed as described below).
Each `talents/<id>/` is owned by the team `@follabcorp/murmure` and by the declared
Authors; `.github/`, `featured.json` and `revoked.json` are owned by the team alone.
`validate` refuses a present `CODEOWNERS` that differs from this result.

Approvals: a PR touching `talents/<id>/` requires the approval of a Maintainer or of
a declared Author, never that of the PR's author. A PR adding a capability to a Talent
requires **two approvals of Maintainers**; the `diff` report says so. `.github/`,
`featured.json` and `revoked.json` are reserved to the team, with two approvals. The
number of approvals is enforced by the GitHub branch rule, configured by a Maintainer;
the tool only reports it.

Choose one or two needs from `mail`, `calendar`, `organizing`, `writing`, `paperwork`,
`cooking`, `travel`, `home`, `health`, `learning`. Capabilities are `read-mail`,
`send-mail`, `organize-mail`, `read-calendar`, `edit-calendar`, `read-reminders`,
`edit-reminders`, `read-notes`, `edit-notes`, `web-search`, `browse-web`. Each declared capability must
be covered by a direct dependency. Dependencies must exist in the Catalogue or
BobProtocol's built-in manifests; cycles and chains exceeding four levels are refused.
Text-only Talents do not provide tools themselves.

Accepted licenses: MIT, Apache-2.0, BSD-2-Clause, BSD-3-Clause, ISC, 0BSD,
Unlicense, CC0-1.0, CC-BY-4.0. Retain notices, attribution and original authors;
an SPDX identifier alone is not evidence of permission. Copyleft and noncommercial
licenses are refused.

Language rule: a Talent's instructions (the body and the `description` of `SKILL.md`,
and any attachment the Agent reads) are written in English. Each `SKILL.md` contains
the sentence "Reply in the language the person uses.", which asks the Agent to answer
in the person's language. The names and summaries shown to the person stay localized
in `localized.fr` and `localized.en`, which are mandatory. Identifiers (`id`, the
`name` in the header, `requires`) do not change.

Install the tool (`cargo install --locked --git https://github.com/follabcorp/murmure-talents-tools --tag v20261107-7ecfdff murmure-talents`),
then run `murmure-talents validate .` from the repository root,
and attach its report.
Explain warnings about suspicious instructions, email sending without capability, or
a `SKILL.md` that does not seem to be in English or lacks the reply-language sentence.
Maintainers review usefulness, provenance, licenses, dependencies, capabilities and
all instructions. They curate at most three IDs in `featured.json` and revocations
in `revoked.json` with reasons `malicious`, `broken`, `authorRequest`, `policy`.
Key custody, signing and publication remain human operations.
