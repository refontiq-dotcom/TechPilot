# TechPilot — Architecture cible

## Objectif

Construire une plateforme B2B multi-tenant, modulaire, sécurisée et extensible.

L'architecture finale sera adaptée à la stack découverte lors de l'audit initial.

## Domaines

### Fondation
- AUTH
- TENANTS
- USERS
- ROLES
- COMPANIES
- LOCATIONS
- AUDIT

### Métier
- CUSTOMERS
- DEVICES
- INVENTORY
- SALES
- REPAIRS

### Diagnostic
- DIAGNOSTICS
- BENCHMARK
- BATTERY
- THERMAL
- REPORTS
- CERTIFICATES

### Technique
- FIRMWARE
- DATA_RECOVERY

### Plateforme
- AI
- AUTOMATIONS
- SUBSCRIPTIONS
- PAYMENTS
- NOTIFICATIONS
- API
- ADMIN

### Écosystème
- TROUVETOUT

## Multi-tenancy

Toutes les données métier doivent être correctement isolées par tenant / entreprise.

Les contrôles d'autorisation doivent être appliqués côté serveur et ne doivent jamais dépendre uniquement de l'interface.

## Appareils

Le domaine DEVICE doit être abstrait afin de permettre l'extension future vers :
- smartphones ;
- ordinateurs ;
- tablettes ;
- montres ;
- consoles ;
- autres appareils électroniques.

Les opérations spécifiques à un constructeur ou une plateforme doivent être encapsulées derrière des adaptateurs.

## Diagnostics

Un diagnostic est composé de tests indépendants et traçables.

Chaque résultat doit pouvoir porter :
- type de test ;
- valeur ;
- unité ;
- source ;
- état de fiabilité ;
- horodatage ;
- appareil concerné ;
- version du moteur de test.

## Scoring

Le moteur de scoring doit séparer :
1. mesures brutes ;
2. normalisation ;
3. classification ;
4. profils d'usage ;
5. présentation utilisateur.

Les règles de calcul doivent être versionnées afin de permettre la reproductibilité des rapports.

## IA

L'IA doit être accessible via une couche de service indépendante.

Les fonctions IA ne doivent pas être directement couplées aux données critiques sans validation déterministe.

## Intégrations

Les services externes doivent être encapsulés derrière des interfaces/adaptateurs afin de pouvoir remplacer un fournisseur sans réécrire le domaine métier.

## Sécurité et audit

Prévoir :
- journalisation des actions sensibles ;
- contrôle d'accès ;
- séparation des tenants ;
- gestion sécurisée des secrets ;
- validation des entrées ;
- protection des données ;
- traçabilité des opérations techniques ;
- sauvegardes ;
- observabilité.

## Règle d'évolution

Toute modification architecturale importante doit être précédée d'un audit de l'existant et d'une justification documentée.
