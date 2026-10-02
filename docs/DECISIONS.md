# TechPilot — Journal des décisions

Ce document conserve les décisions structurantes du projet.

## D-001 — Positionnement

**Décision :** TechPilot est un SaaS B2B vertical pour les professionnels de l'électronique.

**Conséquence :** l'architecture doit privilégier les workflows professionnels et la gestion d'entreprise.

## D-002 — TechPilot et TrouveTout

**Décision :** TechPilot et TrouveTout sont deux produits distincts.

**Conséquence :** l'intégration passe par une couche d'API / adaptateur et ne doit pas contaminer le cœur métier.

## D-003 — Compte professionnel

**Décision :** boutique, atelier et réparateur ne sont pas des types de comptes séparés.

**Conséquence :** un tenant / une entreprise peut gérer plusieurs activités et plusieurs employés.

## D-004 — IA

**Décision :** l'IA assiste le produit mais n'est pas la source de vérité des opérations critiques.

**Conséquence :** les règles déterministes restent responsables des données critiques, de la sécurité, des permissions, des paiements et des mesures.

## D-005 — Données de diagnostic

**Décision :** aucune donnée indisponible ne doit être présentée comme mesurée.

**États :** REAL, ESTIMATED, DECLARED, UNAVAILABLE.

## D-006 — Certification

**Décision :** une certification représente l'état d'un appareil au moment du diagnostic.

**Conséquence :** le certificat doit conserver le contexte temporel et les résultats qui ont servi à le produire.

## D-007 — Développement

**Décision :** développement progressif et contrôlé.

**Conséquence :** audit avant modification structurante, conservation de l'existant et validation humaine des changements majeurs.

## D-008 — Extensibilité

**Décision :** TechPilot ne doit pas être limité architecturalement aux smartphones.

**Conséquence :** le domaine appareil doit être abstrait et extensible.

## D-009 — Sécurité constructeur

**Décision :** aucune fonctionnalité de contournement de protections constructeur ou antivol.

**Conséquence :** privilégier les méthodes officielles et légitimes.

## D-010 — UX

**Décision :** simplicité d'utilisation malgré la richesse fonctionnelle.

**Conséquence :** interface simple par défaut, détails techniques accessibles à la demande.
