# Provenance et adaptation

Dérivé de **meal-plan-builder**, par **Jannik Reinhard (JayRHa)**,
[agent-skills](https://github.com/JayRHa/agent-skills/blob/f9a456bf34c297bd23fb234f410ec9b239ebed14/meal-plan-builder/SKILL.md), commit
`f9a456bf34c297bd23fb234f410ec9b239ebed14` (14 octobre 2026).
Licence **MIT**, copyright © 2026 Jannik Reinhard ; [notice intégrale](LICENSE)
reproduite sans modification. L’historique du dossier attribue son ajout à JayRHa au commit `9cacaa0d2bb781c63f0af58fd663e803bc5f6821`.

Traduction et adaptation françaises préparées par les mainteneurs du Catalogue
Murmure, 4 novembre 2026, sous la même licence. Les noms et résumés (français et
anglais) sont éditoriaux. La source n’est ni une création de Murmure ni une skill
distribuée avec OpenClaw. Le texte livré n’est pas présenté comme écrit par Murmure.

Les consignes principales sont reprises en anglais à partir de l’original, condensées
et réécrites pour une personne non technicienne, de façon autonome : les annexes
anglaises (références, modèles, exemples, scripts) ne sont pas distribuées avec ce Talent
et les renvois qui y menaient sont retirés ; aucune annexe n’est présentée comme traduite.
L’original et ses fichiers de texte sont conservés dans le dossier
`sources/agent-skills-2026-11-04/original/meal-plan-builder/` du Catalogue préparatoire, et
accessibles par le lien source ci-dessus au commit épinglé. Les scripts (`scripts/*.py`) de cet original ne sont pas conservés, parce que le Catalogue n’accepte pas de scripts ; ils restent lisibles au lien source ci-dessus au commit épinglé.

Adaptation propre à ce Talent : Annexes, modèle, exemple et script `plan_calc.py` retirés (le script n’est pas distribué). **Reformulé** : l’original calculait calories et macronutriments (formule de Mifflin-St Jeor, plancher de protéines, tolérances de ±5 %) ; ces calculs sont supprimés pour ne pas transformer le Talent en conseil diététique. Restent l’enquête, les ingrédients communs, les restes volontaires, le plan de préparation par lots, la liste de courses regroupée par rayon et le renvoi vers un médecin ou un diététicien en cas de maladie, grossesse ou trouble alimentaire. Allergies traitées comme contraintes absolues.

Besoins relus ; capacités et dépendances vides : travail sur le contenu fourni
dans la Conversation. Aucun code, binaire, compte, secret ou service nécessaire.
La validation technique ne remplace pas le choix final de Thibault à la relecture.
