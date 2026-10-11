# TP DevOps — Git et GitHub

## Auteurs

- Lydia Abdelhamid
- Lynda Kerbous

## Objectif du TP

Ce TP permet de mettre en pratique les fonctionnalités avancées
de Git et GitHub : branches, Pull Requests, Code Review,
rebase interactif, squash et résolution de conflits.

## Travaux réalisés

### Étape 1 — Correctif de sécurité

Ajout d'une vérification des critères de sécurité du mot de passe.

Pull Request #9 : hotfix/password-strength.

### Étape 2 — Développement de la fonctionnalité

Création de la branche feature/feedback-password.

Ajout d'un indicateur de robustesse du mot de passe.

### Étape 3 — Rebase interactif

Utilisation de git rebase -i pour regrouper les commits
et conserver un historique lisible.

### Étape 4 — Pull Request et Code Review

- Création de la Pull Request #10.
- Code Review réalisée par Lynda.
- Demande de modification des critères du mot de passe.
- Correction effectuée par Lydia.
- Regroupement des commits avec git rebase -i.
- Mise à jour avec git push --force-with-lease.
- Approbation de la Pull Request par Lynda.
- Fusion dans main.

Commit final : 98567f3.

## Graphe Git

Commande utilisée :

```bash
git log --graph --oneline --all
```

Le graphe Git final est présenté dans la capture d'écran
jointe au rapport.

## Questions

### Q1 — Différence entre git push --force et git push --force-with-lease

git push --force remplace l'historique de la branche distante,
même si un autre développeur y a ajouté des commits.

git push --force-with-lease vérifie que la branche distante
n'a pas été modifiée depuis la dernière récupération locale
de ses références.

Cette deuxième commande réduit donc le risque d'écraser
le travail d'un collaborateur.

### Q2 — Pourquoi privilégier git rebase plutôt que git merge ?

git rebase permet de réorganiser les commits et d'obtenir
un historique plus linéaire et lisible.

git merge conserve l'historique des branches et peut créer
un commit de fusion supplémentaire.

Le rebase est particulièrement utile pour nettoyer une
branche de fonctionnalité avant son intégration.

Il faut toutefois éviter de réécrire l'historique d'une
branche partagée sans coordination.

### Q3 — Pourquoi utiliser le Squash dans un pipeline CI/CD ?

Le Squash permet de regrouper plusieurs commits de
développement en un seul commit lors de la fusion.

Il facilite la lecture de l'historique et permet de
retrouver plus facilement une fonctionnalité.

Il simplifie également le retour arrière lorsqu'une
modification doit être annulée.

Les tests CI/CD doivent néanmoins être exécutés sur
le code final avant son intégration.
