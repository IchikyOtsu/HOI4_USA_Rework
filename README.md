# USA Rework — mod Hearts of Iron IV

Rework historique jouable des États-Unis pour HOI4 1.17.x. Il contient désormais :

- un arbre américain de 95 priorités, du New Deal à la course spatiale ;
- trois chemins alternatifs complets : CPUSA/Amérique rouge, America First/Silver Shirts et MacArthur/American Caesar ;
- trois variantes de guerre civile avec reconstruction politique après la victoire ;
- une Balance of Power isolationnisme/interventionnisme ;
- un Congrès à soutien variable (100 sénateurs et 435 représentants) ;
- cinq phases de mobilisation industrielle et une démobilisation ;
- les War Plans Orange, Black et Rainbow Five ;
- les plans de contingence historiques Red, Green et Violet ;
- les Army Ground Forces, les forces aériennes stratégiques, les groupes aéronavals et une doctrine amphibie ;
- une capacité de prêt-bail limitée, partagée entre Grande-Bretagne, URSS et Chine ;
- le discours de la quarantaine, les Quatre Libertés, l'embargo japonais et la Charte de l'Atlantique ;
- des événements liés à l'opinion, aux élections, à la France et au Japon ;
- un chemin républicain Landon avec étalon-or, entreprise privée et bloc commercial panaméricain ;
- un endgame historique : GI Bill, Fair Deal, Bretton Woods, ONU, plan Marshall, occupations et démocratisation ;
- un cabinet de guerre historique : Marshall, Stimson, Knudsen, Nelson, King et Arnold ;
- une seconde Balance of Power d'après-guerre entre détente et endiguement mondial ;
- la doctrine Truman, le pont aérien de Berlin, l'OTAN, NSC-68, la Corée, Atomes pour la paix et le programme spatial ;
- des conclusions développées pour les régimes communiste, fasciste et militariste ;
- les localisations française et anglaise ;
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
| Régler la Balance of Power | `USA_Rework/common/bop/USA_rework_foreign_policy.txt` |
| Régler les effets réutilisables | `USA_Rework/common/scripted_effects/USA_rework_effects.txt` |
| Modifier les événements | `USA_Rework/events/USA_rework_events.txt` |

Les identifiants ajoutés commencent par `USA_rework_` pour éviter les collisions avec HOI4 ou d'autres mods. Après chaque modification, relancez le jeu et consultez `Documents/Paradox Interactive/Hearts of Iron IV/logs/error.log` s'il y a une erreur de script. Pour que les accents s'affichent correctement, enregistrez les fichiers de localisation en **UTF-8 avec BOM**.

Une localisation anglaise de secours est également présente dans `USA_Rework/localisation/english/`.

## Tester le rework

Le premier focus, **Poursuivre le New Deal**, initialise le Congrès, la Balance of Power et la phase économique de temps de paix. Il faut donc le terminer avant d'évaluer les décisions du mod. Pour un test rapide, lancez HOI4 avec `-debug`, ouvrez la console avec `²`, puis utilisez `focus.autocomplete` et `decision.nochecks`. Après le test, vérifiez `Documents/Paradox Interactive/Hearts of Iron IV/logs/error.log` et `game.log`.

La cible de compatibilité est HOI4 **1.17.x**. *Man the Guns* et *By Blood Alone* sont recommandés pour retrouver l'environnement de jeu ayant inspiré le rework, mais le mod ne déclare actuellement aucune dépendance DLC stricte.

## Périmètre actuel

La passe actuelle privilégie le parcours historique démocrate, la préparation à la guerre et l'après-1945. Les interfaces graphiques personnalisées, les personnages remaniés, les MIO historiques et la guerre civile dynamique à plusieurs factions restent à implémenter : ils nécessitent des assets dédiés et une campagne de tests séparée.

## Première extension conseillée

Dupliquez un bloc `focus = { ... }` dans `USA_rework.txt`, donnez-lui un nouvel `id` commençant par `USA_rework_`, puis reliez-le avec `prerequisite = { focus = ... }`. Ajoutez ensuite son nom et sa description dans le fichier de localisation. Les icônes `GFX_goal_generic_*` utilisées ici viennent du jeu de base, donc aucun asset graphique n'est requis pour commencer.
