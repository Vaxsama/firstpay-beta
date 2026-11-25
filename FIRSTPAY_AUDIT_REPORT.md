# FIRSTPAY — Audit technique préliminaire (25 novembre 2026)

## Périmètre
18 pages HTML disponibles localement ont été examinées: pages 33 à 47 (avec les versions brandées 44–47), `firstpay-journey.html`, `firstpay-mobile.html`, et `firstpay-readiness.html`.

## Résultats
- Syntaxe JavaScript inline: **18/18 PASS**.
- Liens internes manquants détectés: **3**, corrigés dans ce pack.
- Aucun lien interne manquant restant dans les pages du périmètre après correction, selon les fichiers locaux.
- Les pages techniques historiques (33–43) affichent encore des numéros de version et des termes de développement. Elles sont à considérer comme outils internes/legacy, non comme pages destinées aux nouveaux testeurs.
- Les pages de parcours et mobile ont une navigation cohérente vers les pages principales.

## Liens corrigés
1. V33: ancien lien vers `firstpay-v32.html` remplacé par `firstpay-v37.html` (dashboard existant).
2. V38: lien `index.html` remplacé par `firstpay-journey.html` (entrée utilisateur actuelle).
3. V40: ancien lien vers `firstpay-v32.html` remplacé par `firstpay-v33.html` (Cashflow existant).

## Limites de l'audit
- Audit effectué sur les copies locales disponibles, pas sur la version live GitHub. L'outil de consultation web n'a pas pu récupérer les pages publiques.
- Pas de test navigateur réel, pas de simulation des interactions, ni vérification de cohérence des données entre localStorage, car les pages utilisent plusieurs schémas et un navigateur réel est requis.
- La navigation interne a été vérifiée en existence de fichiers, mais pas en testant l'URL déployée.

## Priorités recommandées
1. Faire de `firstpay-journey.html` la porte d'entrée principale (index/root) plutôt que laisser les visiteurs arriver sur des pages modules.
2. Masquer les modules legacy dans les menus/public navigation; garder les versions dans un dossier interne ou retirer les pages non destinées aux testeurs du déploiement.
3. Tester sur iPhone les actions: sauvegarde/export, import, calcul, navigation, états sans données, et scénarios avec données.
4. Après validation, créer une release candidate 1.0 plutôt qu'ajouter encore des modules.
