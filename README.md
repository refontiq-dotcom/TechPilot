# TechPilot

**TechPilot** est un SaaS B2B destiné aux professionnels qui vendent, achètent, diagnostiquent, réparent, reconditionnent, certifient et revendent des appareils électroniques.

## Vision

TechPilot doit devenir le système de pilotage quotidien du professionnel de l'électronique :

**Détection → Identification → Diagnostic → Analyse → Score → Rapport → Certification → Stock → Vente → Suivi**

Le produit doit automatiser au maximum les tâches répétitives tout en conservant une séparation claire entre :
- la logique métier déterministe ;
- les opérations techniques sur les appareils ;
- les fonctions d'intelligence artificielle.

## Principes

1. Préserver les fonctionnalités existantes lors de toute évolution.
2. Construire progressivement, par phases validées.
3. Ne pas reconstruire inutilement une fonctionnalité déjà présente.
4. Privilégier une architecture modulaire et extensible.
5. Ne jamais inventer une donnée de diagnostic : distinguer REAL, ESTIMATED, DECLARED et UNAVAILABLE.
6. L'IA assiste et interprète ; elle ne remplace pas les règles métier critiques.
7. Les interfaces doivent rester simples, visuelles et compréhensibles.
8. Les opérations sensibles doivent être traçables et sécurisées.
9. Les mécanismes de sécurité des constructeurs ne doivent pas être contournés.

## Produits de l'écosystème

- **TechPilot** : outil B2B professionnel.
- **TrouveTout** : marketplace / plateforme grand public.

L'intégration TechPilot ↔ TrouveTout doit être conçue comme une intégration entre deux produits distincts, via une couche d'abstraction/API.

## État du projet

Le dépôt constitue la base officielle du projet TechPilot. Toute implémentation doit commencer par un audit du dépôt et une validation de l'architecture avant les modifications structurantes.

Voir :
- [AGENTS.md](AGENTS.md)
- [Documentation produit](docs/PRODUCT.md)
- [Architecture cible](docs/ARCHITECTURE.md)
- [Feuille de route](docs/ROADMAP.md)
