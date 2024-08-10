# vue-todo-list

## À propos de ce tutoriel

Afin d'assoir les notions vues jusqu'à maintenant je vous propose un petit TP qui permettra de pratiquer ce que l'on a vu jusqu'à maintenant.
Article: [](https://grafikart.fr/tutoriels/todolist-vuejs-2227)

## Objectif

Pour ce premier TP votre objectif est de créer un petit système de tâches à faire.

- On affiche un message si il n'y a pas tâches à faire.
- Un champs texte accompagné d'un bouton "Ajouter" sera présent au dessus de la liste et permettra d'ajouter une nouvelle tâche.
- Pour chaque tâche, une case à cocher permettra de marquer la tâche comme faite.
- Une tâche terminée sera barrée (à l'aide de CSS).
- Les tâches à faire seront toujours affichées en premier.
- Une case, en bas de liste, permettra de masques les tâches terminées.

Les tâches respeceront le format suivant :

```json
[
  { "title": "Acheter la propriété 'Rue de la Paix'", "completed": false, "date": 20240730 },
  { "title": "Construire un hôtel sur 'Avenue Foch'", "completed": false, "date": 20240730 },
  { "title": "Éviter la case prison", "completed": false, "date": 20240730 }
]
```
