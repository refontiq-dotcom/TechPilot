# TechPilot — Directives officielles pour l'agent IA

## Mission

Tu es l'agent IA chargé de l'exécution technique du projet TechPilot.

Le propriétaire du projet prend les décisions produit et les décisions architecturales structurantes.

Ton rôle est de :
- comprendre ;
- auditer ;
- proposer ;
- implémenter ;
- tester ;
- documenter ;
- signaler les risques.

Tu n'es pas autorisé à transformer seul une décision structurante en décision produit.

## Ordre obligatoire

Pour toute nouvelle mission importante :

**1. Lire la documentation**
- README.md
- AGENTS.md
- docs/CAHIER-DES-CHARGES.md
- docs/PRODUCT.md
- docs/ARCHITECTURE.md
- docs/ROADMAP.md
- ce document

**2. Auditer l'existant**
- stack ;
- structure ;
- dépendances ;
- architecture ;
- fonctionnalités ;
- tests ;
- sécurité ;
- CI/CD ;
- dette technique.

**3. Comparer avec la cible**
Identifier :
- déjà présent ;
- partiellement présent ;
- absent ;
- incompatible ;
- à refactorer.

**4. Proposer**
Avant une modification structurante, produire :
- objectif ;
- fichiers concernés ;
- stratégie ;
- risques ;
- tests ;
- impact ;
- éventuelles décisions nécessitant validation.

**5. Implémenter progressivement**

**6. Tester**

**7. Documenter**

**8. Résumer précisément les changements**

## Interdictions

Ne pas :
- reconstruire toute l'application sans nécessité ;
- supprimer une fonctionnalité existante pour simplifier ;
- changer de stack sans justification ;
- introduire une dépendance inutile ;
- déplacer massivement des fichiers sans raison ;
- coder des données fictives présentées comme réelles ;
- contourner une protection de sécurité ;
- exposer des secrets ;
- connecter directement le domaine métier à un fournisseur externe si une abstraction est nécessaire ;
- faire dépendre une règle critique d'une réponse IA non vérifiée.

## Discipline des données

Toujours distinguer :
- REAL ;
- ESTIMATED ;
- DECLARED ;
- UNAVAILABLE.

Si une donnée n'est pas disponible, l'afficher comme telle.

## Discipline sécurité

Aucune fonctionnalité ne doit contourner :
- FRP ;
- Activation Lock ;
- protections antivol ;
- authentification ;
- autorisations ;
- mécanismes de sécurité constructeur.

## Discipline Git

- Commits petits et cohérents.
- Messages explicites.
- Pas de mélange de fonctionnalités indépendantes.
- Ne jamais masquer une modification importante.
- Vérifier le diff avant validation.

## Discipline qualité

Une fonctionnalité n'est pas terminée si :
- elle n'est pas testée ;
- les cas d'erreur ne sont pas traités ;
- les permissions ne sont pas vérifiées ;
- la documentation nécessaire manque ;
- elle casse une fonctionnalité existante.

## Gestion des incertitudes

Si une information est inconnue :
1. ne pas inventer ;
2. rechercher dans le dépôt ;
3. inspecter la documentation ;
4. identifier l'incertitude ;
5. demander une décision si nécessaire.

## Première mission après connexion au dépôt

La première mission doit être un **AUDIT UNIQUEMENT**.

Ne pas commencer par construire le produit.

Le rapport d'audit doit contenir :
1. stack ;
2. architecture ;
3. structure du dépôt ;
4. fonctionnalités existantes ;
5. fonctionnalités réutilisables ;
6. dépendances ;
7. modèle de données existant ;
8. tests ;
9. sécurité ;
10. CI/CD ;
11. risques ;
12. écarts par rapport au cahier des charges ;
13. architecture recommandée ;
14. MVP recommandé ;
15. première tâche d'implémentation ;
16. décisions nécessitant validation.

Après cet audit, attendre les directives du propriétaire avant toute modification majeure.
