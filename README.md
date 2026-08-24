# USA Rework — mod Hearts of Iron IV

Base jouable pour refaire l'arbre de priorités des États-Unis. Elle contient :

- un arbre américain alternatif (`common/national_focus/USA_rework.txt`) ;
- une idée nationale et une décision de démonstration ;
- les textes français associés ;
- les deux descripteurs attendus par le launcher.

## Installer le mod

1. Ouvrez le dossier des mods de HOI4 :
   - Windows : `%USERPROFILE%\\Documents\\Paradox Interactive\\Hearts of Iron IV\\mod`
   - Linux/Steam Proton : `~/Documents/Paradox Interactive/Hearts of Iron IV/mod`
2. Copiez dans ce dossier **le dossier** `USA_Rework` et **le fichier** `USA_Rework.mod` présents à la racine de ce projet.
3. Lancez le launcher Paradox, créez ou ouvrez un playset, puis activez **USA Rework**.
4. Démarrez une nouvelle partie en 1936 avec les États-Unis. Le focus « Relancer la nation » doit apparaître : il confirme que le mod est chargé.

Le mod n'altère pas les fichiers d'installation de HOI4. Désactivez-le simplement dans le playset pour revenir au jeu vanilla.

## Où modifier quoi

| Objectif | Fichier |
| --- | --- |
| Ajouter ou modifier des priorités | `USA_Rework/common/national_focus/USA_rework.txt` |
| Ajouter des bonus nationaux | `USA_Rework/common/ideas/USA_rework_ideas.txt` |
| Ajouter des décisions | `USA_Rework/common/decisions/USA_rework_decisions.txt` |
| Modifier les noms et descriptions | `USA_Rework/localisation/french/USA_rework_l_french.yml` |

Les identifiants ajoutés commencent par `USA_rework_` pour éviter les collisions avec HOI4 ou d'autres mods. Après chaque modification, relancez le jeu et consultez `Documents/Paradox Interactive/Hearts of Iron IV/logs/error.log` s'il y a une erreur de script. Pour que les accents s'affichent correctement, enregistrez les fichiers de localisation en **UTF-8 avec BOM**.

Une localisation anglaise de secours est également présente dans `USA_Rework/localisation/english/`.

## Première extension conseillée

Dupliquez un bloc `focus = { ... }` dans `USA_rework.txt`, donnez-lui un nouvel `id` commençant par `USA_rework_`, puis reliez-le avec `prerequisite = { focus = ... }`. Ajoutez ensuite son nom et sa description dans le fichier de localisation. Les icônes `GFX_goal_generic_*` utilisées ici viennent du jeu de base, donc aucun asset graphique n'est requis pour commencer.
