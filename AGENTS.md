# Règles de développement — TechPilot

## 1. Rôle

L'utilisateur est le décideur produit.

L'agent IA de développement est l'exécutant technique. Il doit analyser, proposer, implémenter, tester et documenter sans prendre de décision produit majeure de manière autonome.

## 2. Règle fondamentale : auditer avant de modifier

Avant toute modification importante :
1. inspecter le dépôt ;
2. identifier la stack ;
3. identifier l'architecture ;
4. identifier ce qui existe déjà ;
5. identifier ce qui est réutilisable ;
6. identifier les dépendances et risques ;
7. proposer un plan ;
8. demander validation lorsque la décision est structurante.

Ne jamais commencer par une reconstruction globale.

## 3. Préservation

- Ne pas supprimer une fonctionnalité existante sans justification et validation.
- Ne pas remplacer une architecture entière si une évolution progressive suffit.
- Éviter les changements massifs non nécessaires.
- Conserver la compatibilité autant que possible.

## 4. Architecture

TechPilot doit évoluer vers une architecture modulaire, multi-tenant et extensible.

Les domaines fonctionnels prévus comprennent notamment :

AUTH, TENANTS, USERS, ROLES, COMPANIES, LOCATIONS, CUSTOMERS, DEVICES, INVENTORY, SALES, REPAIRS, DIAGNOSTICS, BENCHMARK, BATTERY, THERMAL, FIRMWARE, DATA_RECOVERY, CERTIFICATES, REPORTS, AI, AUTOMATIONS, SUBSCRIPTIONS, PAYMENTS, NOTIFICATIONS, TROUVETOUT, API, ADMIN, AUDIT.

La stack technique définitive doit être déterminée à partir de l'audit et des contraintes réelles du projet, pas imposée arbitrairement avant analyse.

## 5. IA vs logique déterministe

La logique déterministe doit rester responsable notamment de :
- authentification ;
- autorisations ;
- calculs métier critiques ;
- paiements ;
- stockage ;
- intégrité des données ;
- opérations techniques ;
- résultats de tests ;
- sécurité.

L'IA peut notamment :
- expliquer les résultats ;
- produire des rapports ;
- assister l'utilisateur ;
- classer ou synthétiser des informations ;
- proposer des actions ;
- automatiser des workflows non critiques.

L'IA ne doit jamais transformer une donnée indisponible en donnée présentée comme mesurée.

## 6. Diagnostics

Les diagnostics doivent séparer :
- données mesurées ;
- données estimées ;
- données déclarées ;
- données indisponibles.

Les appareils complètement hors service doivent avoir un parcours spécifique et ne doivent pas être présentés comme entièrement diagnostiqués lorsque les tests techniques sont impossibles.

## 7. Sécurité

Ne jamais concevoir de mécanisme visant à contourner :
- FRP ;
- Activation Lock ;
- protections antivol ;
- verrouillages constructeur ;
- contrôles d'accès ;
- autres mécanismes de sécurité.

Les fonctions firmware doivent privilégier les mécanismes officiels et les procédures légitimes.

## 8. UX

TechPilot doit être utilisable par des professionnels avec des niveaux différents de maîtrise informatique.

Priorités :
- actions évidentes ;
- libellés courts ;
- repères visuels ;
- informations importantes visibles immédiatement ;
- niveau simple par défaut ;
- détails techniques accessibles lorsque nécessaires.

## 9. Développement

Chaque fonctionnalité significative doit être :
- isolée ;
- testable ;
- documentée ;
- observable ;
- réversible lorsque possible.

Avant un commit important, vérifier :
- tests ;
- lint/typecheck si disponibles ;
- sécurité ;
- régressions ;
- documentation.

## 10. Git

Utiliser des commits petits et explicites.

Ne pas mélanger dans un même commit :
- refonte non liée ;
- correction ;
- nouvelle fonctionnalité ;
- changement d'infrastructure.

## 11. Processus recommandé

**Audit → proposition → validation → implémentation → tests → revue → commit**

Toute décision structurante qui affecte l'architecture, les données, la sécurité, les coûts ou le périmètre doit être signalée à l'utilisateur.
