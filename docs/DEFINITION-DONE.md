# TechPilot — Definition of Done

Une fonctionnalité est considérée comme terminée uniquement lorsque les éléments applicables suivants sont satisfaits.

## Produit
- comportement conforme au besoin ;
- parcours utilisateur clair ;
- cas limites identifiés ;
- états d'erreur prévus.

## Technique
- code intégré proprement ;
- architecture respectée ;
- pas de duplication inutile ;
- dépendances justifiées.

## Sécurité
- authentification ;
- autorisation ;
- isolation tenant ;
- validation des entrées ;
- secrets protégés ;
- logs sensibles maîtrisés.

## Qualité
- tests adaptés ;
- typecheck/lint si disponibles ;
- absence de régression connue ;
- vérification manuelle lorsque nécessaire.

## Données
- provenance des données claire ;
- REAL / ESTIMATED / DECLARED / UNAVAILABLE respectés ;
- migrations versionnées lorsque nécessaires.

## Observabilité
- erreurs observables ;
- événements importants traçables ;
- automatisations avec états explicites.

## Documentation
- documentation fonctionnelle mise à jour ;
- documentation technique mise à jour si nécessaire ;
- décisions importantes ajoutées au journal.

## Git
- diff relu ;
- commit cohérent ;
- message explicite ;
- aucun secret ou fichier temporaire.
