# TechPilot — Document de continuité

Ce document permet à un nouveau développeur ou agent IA de reprendre le projet sans dépendre de l'historique de conversation.

## Ce qu'est TechPilot

TechPilot est un SaaS B2B destiné aux professionnels de l'électronique : vente, achat, diagnostic, réparation, reconditionnement, certification et suivi.

## Ce qui est déjà défini

La vision produit, le cahier des charges, les directives agent, l'architecture cible, la roadmap et les décisions structurantes sont dans ce dépôt.

## Ce qui n'est volontairement pas encore figé

La stack technique définitive, le modèle de données final et les choix d'infrastructure doivent être confirmés après audit du code existant et des contraintes réelles.

## Méthode de reprise

1. Lire tous les documents de référence.
2. Inspecter le dépôt.
3. Produire un audit.
4. Identifier les écarts.
5. Proposer une architecture adaptée.
6. Faire valider les décisions structurantes.
7. Implémenter par petites étapes.
8. Tester.
9. Documenter.
10. Committer proprement.

## Principe de continuité

Un nouvel agent ne doit pas considérer le projet comme une page blanche uniquement parce que certaines fonctionnalités ne sont pas encore codées.

La documentation représente les décisions produit déjà prises.

Toute contradiction découverte entre le code et la documentation doit être signalée avant une modification structurante.

## Source de vérité

Ordre de référence :
1. décisions validées dans ce dépôt ;
2. cahier des charges maître ;
3. directives agent ;
4. architecture ;
5. roadmap ;
6. code existant ;
7. hypothèses temporaires explicitement signalées.
