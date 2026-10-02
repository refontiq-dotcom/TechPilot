# TechPilot — Cahier des charges maître

> Document de référence produit et fonctionnel. Toute implémentation doit respecter ce document ou signaler explicitement l'écart proposé.

## 1. Vision

TechPilot est un SaaS B2B vertical destiné aux professionnels qui vendent, achètent, diagnostiquent, réparent, reconditionnent, certifient et revendent des appareils électroniques.

TechPilot doit devenir le système de pilotage quotidien du professionnel.

Parcours cible :

**Appareil → Détection → Identification → Tests → Analyse → Score → Rapport → Certification → Stock → Vente → Suivi**

Le produit doit automatiser les tâches répétitives autant que possible, sans masquer les limites techniques ni inventer des résultats.

## 2. Produits

### TechPilot
Produit B2B destiné aux professionnels.

### TrouveTout
Produit grand public / marketplace distinct.

TechPilot peut alimenter TrouveTout, mais les deux produits doivent rester découplés par une API ou une couche d'intégration.

## 3. Utilisateurs

Le compte professionnel correspond à un tenant / une entreprise.

Une entreprise peut posséder :
- plusieurs utilisateurs ;
- plusieurs employés ;
- plusieurs rôles ;
- plusieurs sites / boutiques / ateliers ;
- plusieurs activités.

Ne pas créer artificiellement des types de comptes séparés pour « boutique » et « réparateur » : ce sont des usages d'un même environnement professionnel.

Rôles possibles à terme :
- propriétaire ;
- administrateur ;
- responsable ;
- technicien ;
- vendeur ;
- comptable ;
- observateur.

Le modèle doit rester extensible.

## 4. Gestion d'entreprise

Fonctions prévues :
- profil entreprise ;
- coordonnées ;
- identité commerciale ;
- sites ;
- employés ;
- rôles ;
- permissions ;
- préférences ;
- abonnement ;
- historique des actions ;
- audit.

## 5. Clients

Le module client doit permettre :
- création ;
- recherche ;
- historique ;
- appareils associés ;
- réparations ;
- ventes ;
- certificats ;
- notes et informations nécessaires au métier.

Les données personnelles doivent être minimisées et protégées.

## 6. Appareils

Un appareil est une entité centrale.

Informations possibles :
- fabricant ;
- modèle ;
- variante ;
- numéro de série lorsque disponible ;
- IMEI lorsque légalement et techniquement disponible ;
- système ;
- version ;
- capacité ;
- mémoire ;
- batterie ;
- état ;
- propriétaire/client ;
- statut de stock ;
- historique ;
- diagnostics ;
- réparations ;
- certificats.

L'architecture doit être générique afin de supporter progressivement :
- smartphones ;
- ordinateurs ;
- tablettes ;
- montres ;
- consoles ;
- autres appareils électroniques.

Les spécificités constructeur doivent être encapsulées par des adaptateurs.

## 7. Inventaire

Le stock doit permettre :
- entrée ;
- sortie ;
- réservation ;
- transfert ;
- statut ;
- emplacement ;
- coût ;
- prix ;
- historique ;
- lien avec appareil ;
- lien avec vente ;
- lien avec réparation lorsque pertinent.

Le système doit pouvoir distinguer au minimum :
- disponible ;
- réservé ;
- vendu ;
- en réparation ;
- en diagnostic ;
- en attente ;
- retiré.

## 8. Diagnostic

Le diagnostic est un ensemble de tests indépendants, traçables et reproductibles.

Tests possibles selon l'appareil :
- identification ;
- écran ;
- tactile ;
- caméra ;
- microphone ;
- haut-parleur ;
- écouteur ;
- boutons ;
- vibration ;
- capteurs ;
- réseau ;
- Wi-Fi ;
- Bluetooth ;
- GPS ;
- USB ;
- stockage ;
- mémoire ;
- processeur ;
- GPU ;
- batterie ;
- température ;
- stabilité ;
- performance ;
- système ;
- connectivité.

Chaque test doit déclarer :
- son type ;
- son statut ;
- ses mesures ;
- ses unités ;
- sa source ;
- sa date ;
- sa version ;
- sa fiabilité.

### États de données obligatoires

Une donnée doit pouvoir être :
- **REAL** : mesurée réellement ;
- **ESTIMATED** : estimée/calculée ;
- **DECLARED** : déclarée par l'utilisateur ou une source externe ;
- **UNAVAILABLE** : non disponible.

Une donnée UNAVAILABLE ne doit jamais être remplacée silencieusement par une valeur inventée.

## 9. Appareil totalement hors service

Si un appareil ne répond à aucun mécanisme logiciel disponible, TechPilot doit l'indiquer.

Le système ne doit pas présenter un appareil comme « entièrement diagnostiqué » lorsqu'une partie des tests n'a pas pu être exécutée.

Un parcours « diagnostic matériel limité / appareil non communicant » doit être prévu.

## 10. Application compagnon

Certains tests nécessiteront éventuellement une application compagnon sur téléphone/tablette.

Cette architecture doit permettre :
- appairage sécurisé ;
- identification ;
- collecte de mesures ;
- exécution de tests ;
- remontée des résultats ;
- association avec le dossier TechPilot.

## 11. Diagnostic informatique

Pour les ordinateurs, prévoir progressivement des adaptateurs capables de collecter, selon l'OS et les permissions :
- CPU ;
- GPU ;
- RAM ;
- stockage ;
- batterie ;
- température ;
- réseau ;
- système ;
- pilotes ;
- performances ;
- stabilité.

Le système doit respecter les permissions de l'OS.

## 12. Performance et benchmark

TechPilot doit présenter les performances de manière compréhensible.

Ne pas afficher uniquement des nombres bruts.

Le moteur doit séparer :
1. mesures brutes ;
2. normalisation ;
3. classification ;
4. scores par usage ;
5. présentation.

Profils d'usage prévus :
- quotidien ;
- réseaux sociaux ;
- vidéo ;
- photographie ;
- travail ;
- GPS ;
- jeu léger ;
- jeu intensif ;
- batterie ;
- stabilité thermique.

La comparaison doit tenir compte de la classe et de la génération de l'appareil.

Un appareil d'entrée de gamme ne doit pas obtenir artificiellement un score maximal simplement parce qu'il fonctionne correctement dans sa catégorie.

## 13. Batterie et thermique

Prévoir :
- état de santé lorsque mesurable ;
- capacité lorsqu'elle est accessible ;
- charge ;
- température ;
- évolution dans le temps ;
- stabilité ;
- comportement sous charge ;
- throttling lorsque mesurable.

Les résultats doivent distinguer mesure réelle et estimation.

## 14. Réparation

Le module réparation doit permettre :
- création d'un dossier ;
- diagnostic initial ;
- description du problème ;
- devis ;
- statut ;
- pièces ;
- main-d'œuvre ;
- technicien ;
- étapes ;
- diagnostic après réparation ;
- comparaison avant/après ;
- clôture ;
- garantie / retour lorsque le modèle commercial le prévoit.

## 15. Avant / après

Une réparation peut comporter deux diagnostics :
- avant ;
- après.

TechPilot doit permettre de comparer :
- tests ;
- résultats ;
- défauts ;
- scores ;
- état général.

## 16. Firmware

Le module firmware doit :
- identifier précisément l'appareil ;
- identifier la variante lorsque possible ;
- détecter la version actuelle ;
- rechercher les versions compatibles ;
- vérifier les sources ;
- afficher les risques ;
- journaliser les opérations.

Les méthodes officielles doivent être privilégiées.

Apple doit utiliser les mécanismes officiels disponibles.

Aucun contournement de :
- FRP ;
- Activation Lock ;
- verrouillage opérateur ou constructeur lorsqu'il s'agit d'un mécanisme de sécurité ;
- protections antivol ;
- contrôle d'accès.

## 17. Récupération de données

Le système peut proposer des workflows de récupération lorsque techniquement possibles.

Il doit toujours :
- indiquer les prérequis ;
- signaler les limites ;
- éviter de promettre une récupération garantie ;
- tracer les opérations ;
- protéger les données ;
- distinguer les données récupérées avec succès des résultats incertains.

Si les données sont écrasées ou si le stockage est physiquement inaccessible, le système doit pouvoir conclure à une impossibilité ou à une récupération partielle.

## 18. Certification

Après un diagnostic éligible, TechPilot peut générer un certificat.

Un certificat doit contenir au minimum :
- identifiant unique ;
- appareil ;
- professionnel ;
- date ;
- résultats ;
- scores ;
- statut ;
- QR code ;
- URL publique de vérification ;
- mécanisme d'intégrité adapté.

Le certificat décrit l'état de l'appareil **au moment du diagnostic**.

Il ne constitue pas une garantie permanente de l'état futur.

## 19. Rapports

Un rapport doit pouvoir être :
- consulté ;
- partagé ;
- exporté ;
- associé à un appareil ;
- associé à un client ;
- associé à une réparation ;
- associé à une certification.

Le rapport doit être compréhensible par un professionnel non spécialiste.

Une vue technique détaillée peut être disponible séparément.

## 20. Ventes et facturation

Prévoir progressivement :
- panier / vente ;
- client ;
- appareil vendu ;
- prix ;
- remise ;
- paiement ;
- facture ;
- statut ;
- historique.

Les calculs financiers critiques doivent être déterministes et testés.

## 21. Abonnements SaaS

Modèle cible possible :
- FREE ;
- PRO ;
- PRO+ ;
- BUSINESS.

Les limites doivent être configurables et non codées en dur partout dans l'application.

Les fonctionnalités payantes doivent être contrôlées côté serveur.

## 22. IA

L'IA doit servir notamment à :
- expliquer les diagnostics ;
- générer des rapports ;
- assister le professionnel ;
- résumer un historique ;
- suggérer des actions ;
- aider à classifier des problèmes ;
- automatiser des workflows non critiques.

L'IA ne doit pas devenir la source de vérité pour :
- authentification ;
- permissions ;
- paiements ;
- mesures ;
- intégrité ;
- calculs critiques ;
- opérations de sécurité.

## 23. Automatisation

Vision cible :

**connexion appareil → identification → tests → analyse → score → rapport → certificat → stock → publication**

Chaque étape doit rester observable et pouvoir signaler :
- succès ;
- échec ;
- partiel ;
- non disponible ;
- intervention humaine requise.

## 24. TrouveTout

TechPilot peut publier des appareils certifiés ou des annonces vers TrouveTout.

Flux cible :

**Professionnel → TechPilot → Diagnostic → Certification → Stock → Publication optionnelle → TrouveTout → Acheteur**

L'intégration doit être réversible et ne doit pas coupler directement le cœur métier de TechPilot aux détails internes de TrouveTout.

## 25. Notifications

Prévoir :
- diagnostic terminé ;
- réparation mise à jour ;
- appareil prêt ;
- paiement ;
- abonnement ;
- certificat ;
- stock ;
- alertes techniques.

Les canaux doivent être abstraits pour permettre leur évolution.

## 26. Statistiques

Prévoir progressivement :
- chiffre d'affaires ;
- ventes ;
- stock ;
- réparations ;
- diagnostics ;
- certifications ;
- performance des employés ;
- taux de réussite ;
- appareils les plus traités ;
- évolution temporelle.

Les statistiques doivent être calculées à partir de données fiables et traçables.

## 27. Sécurité

Principes obligatoires :
- isolation multi-tenant ;
- autorisation côté serveur ;
- gestion sécurisée des secrets ;
- validation des entrées ;
- journalisation des actions sensibles ;
- audit ;
- protection des données ;
- sauvegardes ;
- limitation des accès ;
- principe du moindre privilège.

## 28. UX

TechPilot doit rester simple malgré sa richesse fonctionnelle.

Priorités :
- interface visuelle ;
- actions évidentes ;
- libellés courts ;
- informations importantes immédiatement visibles ;
- parcours guidés ;
- niveau simple par défaut ;
- détails techniques accessibles sans surcharger l'écran.

## 29. Architecture multi-tenant

Un utilisateur appartient à un ou plusieurs contextes autorisés selon les besoins futurs.

Toute donnée métier doit être correctement rattachée au tenant approprié.

Une requête ne doit jamais pouvoir exposer les données d'un autre tenant.

## 30. Observabilité

Prévoir :
- logs structurés ;
- métriques ;
- erreurs ;
- événements métier ;
- traces des opérations sensibles ;
- état des automatisations.

## 31. Extensibilité

L'architecture doit permettre d'ajouter de nouveaux appareils, constructeurs, tests, fournisseurs et intégrations sans réécrire le cœur du système.

## 32. Règle absolue

TechPilot doit privilégier :

**fiabilité > automatisation aveugle**

et

**clarté > complexité inutile**.
