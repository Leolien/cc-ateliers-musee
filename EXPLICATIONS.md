================================================================================
                    COMPTE-RENDU ET EXPLICATIONS DU PROJET
================================================================================

1. POINT DE DÉPART
------------------
* Tag de départ         : 67aeb4f (HEAD -> main, tag: depart-cc) 
                          Fournir le site fonctionnel des ateliers
* Branche active        : main
* Vérification initiale : Le site fonctionne correctement et toutes les 
                          fonctionnalités de base sont opérationnelles.


2. TABLEAU DE SUIVI DES TESTS
-----------------------------
+-------------------------+-------------------------------+----------------------------------+------------------------------------------------------------------------+
| Étape / Version testée  | Action                        | Résultat attendu                 | Résultat constaté                                                      |
+-------------------------+-------------------------------+----------------------------------+------------------------------------------------------------------------+
| Point de départ         | Vérification initiale         | Les fonctionnalités de base      | Les fonctionnalités marchent bien.                                     |
| (67aeb4f)               | du site                       | marchent                         |                                                                        |
+-------------------------+-------------------------------+----------------------------------+------------------------------------------------------------------------+
| Évolution A             | Modification des couleurs     | Les couleurs changent selon      | Les couleurs ont bien changé.                                          |
| (feature/mode_nuit)     | dans le CSS                   | le mode nuit                     |                                                                        |
+-------------------------+-------------------------------+----------------------------------+------------------------------------------------------------------------+
| Évolution B             | Modification de la logique    | Le message de confirmation       | Message présent dans le DOM, mais invisible                            |
| (develop/reservation)   | dans afficherConfirmation     | s'affiche                        | (même couleur que le fond).                                            |
+-------------------------+-------------------------------+----------------------------------+------------------------------------------------------------------------+
| Hotfix                  | Remplacement de la couleur    | Le texte de confirmation         | Tout marche, le texte s'affiche correctement.                          |
| (hotfix/couleur_confirm)| fixe par var(--page-text)     | devient lisible                  |                                                                        |
+-------------------------+-------------------------------+----------------------------------+------------------------------------------------------------------------+
| Évolution C             | Modification du code JS       | Le site affiche le message       | Après correction d'une erreur de manipulation,                        |
| (feature/nom_atelier)   | pour l'intitulé de l'atelier  | avec le nom de l'atelier         | le site affiche bien le nom de l'atelier.                              |
+-------------------------+-------------------------------+----------------------------------+------------------------------------------------------------------------+


3. OBSERVATIONS SUR LE CORRECTIF (HOTFIX)
-----------------------------------------
* Avant le travail hotfix :
  Le message de confirmation s'insérait bien dans la page (on voyait l'espace
  se créer), mais le texte était invisible car sa couleur (#17223b) se 
  confondait avec la couleur du fond.

* Après le travail hotfix :
  En modifiant la classe .receipt pour utiliser la variable dynamique 
  (color: var(--page-text);), le texte de confirmation est désormais 
  parfaitement lisible sur tous les thèmes.


4. VÉRIFICATION FINALE DE LA VERSION MAIN
-----------------------------------------
1. Ouverture ou actualisation :
   Compteur à zéro, confirmation masquée.

2. Première réservation :
   Compteur à un, confirmation lisible avec le nom de l'atelier et une place.

3. Trois réservations au total :
   Compteur et confirmation indiquent trois places.

4. Recommencer :
   Compteur à zéro, confirmation masquée.

5. Nouvelle réservation après remise à zéro :
   Compteur à un et confirmation de nouveau visible.

6. Affichage à 390 px :
   Textes et boutons lisibles, aucun défilement horizontal.


Aides utilisées : 

Avec Ia : MAIS UNIQUEMENT le md final au propre le md "brouillion" ressemblait à ça voir si dessous


Point de départ : 

	Tag de départ : 

	67aeb4f (HEAD -> main, tag: depart-cc) Fournir le site fonctionnel des ateliers

	Vérification des branches : 
	Main

	Vérification du nom pour les commits : c'est bon

	1ère vérification du site , il marche bien et tt les fonctionnalités déjà mises marchent
Grand 1 : 

ajoute des 2 branches : 

Évolution A : 
-git switch -c feature/mode_nuit
	Changement des couleurs dans le css
	1er commit 
	Test : Les couleurs ont bien changées
	
On revient sur la branche main 

Évolution B : 
-git switch -c develop/reservation
	Changement de booléen dans afficherConfirmation
	2ème commit 
	Test : Après la modification le site est censé donner un message de confirmation. Ça marche bien le message apparait
	
Intégrer les branches dans main : 
on retourne dans la branche main 
Intégration de feature/mode_nuit
Test : Les couleurs ont bien changées

Grand 2 

Intégration de develop/reservation
Test : Le site est censé donner un message de confirmation. Au premier abbord il ne s'affiche pas mais on voit bien que la case s'espace . Si on select tt la page on voit que le message s'affiche bel et bien mais qu'on ne peut pas le voir car il est de la même couleur que le fond. Il faut donc le changer. 

Le problème est dans le css , j'ai remplacé : 

.receipt { color: #17223b; font-weight: bold; padding: 12px 0; }

par : 

.receipt { color: var(--page-text); font-weight: bold; padding: 12px 0; }

Création d'une branche hotfix

-git switch -c hotfix/couleur_confirm


On integrer hotfix à main 

Tours marche le texte à bien été changé et on le voit maintenant


Grand 3 : 
nouvelle branche : 
-git switch -c feature/nom_atelier

Changmeent dans le js : 
commit 

Oups , erreur dans le changement du js de ma part 

Deuxième commit pour effacer mon erreur

Le site affiche bien le message avec le nom de l'atelier

On inclue nom_atelier dans main

On refait les tests , tout marche comme prévue. 

Maintenant on crée notre dépot github





