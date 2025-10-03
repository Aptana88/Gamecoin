# Gamecoin App
WEB APP

Bienvenue dans le dépôt Git de l'appli gamecoin Ce document est votre référence pour comprendre le flux de travail (workflow) Git et les conventions de nommage que nous utilisons.

Adopter ces règles est essentiel pour maintenir un historique de code propre, un déploiement fiable et une collaboration efficace.


## 1. Modèle de Flux de Travail : Git Flow 🌊
Nous utilisons le modèle Git Flow pour structurer le développement.

🌳 Branches Principales (Longue Durée)
Ces branches existent en permanence.

Branche	Objectif	État
master (ou main)	Production – Contient uniquement le code de la dernière version en ligne.	Stable et Déployable
develop	Développement – Branche d'intégration principale. Toutes les nouvelles fonctionnalités (feature/) y sont fusionnées.	Instable, contient les fonctionnalités de la prochaine version.

Exporter vers Sheets
🛠️ Branches de Support (Courte Durée)
Ces branches sont créées à partir de develop (ou master pour les hotfix) et sont supprimées après la fusion.

Type de Branche	Préfixe	Point de Départ	But
Feature	feature/	develop	Développement d'une nouvelle fonctionnalité (ex: feature/auth-login).
Release	release/	develop	Préparation d'une nouvelle version stable. Tag de version créé à la fin (v1.0.0).
Hotfix	hotfix/	master	Correction de bugs critiques sur la version en production.

Exporter vers Sheets


## 2. Commandes Git Flow Essentielles
Veuillez utiliser les commandes git flow pour structurer votre travail.

Action	Commande	Description
Démarrer une tâche	git flow feature start [nom-court]	Crée et bascule vers la branche feature/[nom-court] à partir de develop.
Partager le travail	git flow feature publish [nom-court]	Pousse la feature vers GitHub pour la collaboration (recommandé).
Basculer entre Features	git checkout feature/[nom-court]	Permet de passer rapidement d'une tâche à l'autre sans finir la précédente.
Terminer/Fusionner	git flow feature finish [nom-court]	Fusionne la feature dans develop, supprime la branche locale et distante.
Lister les Features	git flow feature list	Affiche toutes les branches de feature en cours.

Exporter vers Sheets


## 3. Conventions de Nommage : Conventional Commits
Chaque message de commit doit commencer par un type prédéfini pour une meilleure lisibilité et pour l'automatisation.

📝 Format du Message de Commit
<type>(<portée - optionnelle>): <description_succincte>
Types de Commit Obligatoires
Type	Objectif	Exemple
feat	Ajout ou modification d'une nouvelle fonctionnalité.	feat: implémentation du formulaire d'inscription Livewire
fix	Correction d'un bug.	fix: le mot de passe ne peut plus être vide lors de la réinitialisation
chore	Maintenance, changements de construction sans impact sur le code.	chore: mise à jour de la dépendance Laravel vers la version 12.x
docs	Changement de la documentation (README, commentaires de code, etc.).	docs: ajout des instructions Git Flow au README
refactor	Restructuration du code sans changement fonctionnel.	refactor(auth): extraction de la logique de validation vers un Trait
test	Ajout ou modification de tests unitaires/fonctionnels (Pest).	test: ajout d'un test pour la route dashboard

Exporter vers Sheets
Conventions de Noms de Branches
Le nom des branches doit être court, en minuscules et descriptif.

Format Feature : [préfixe]/[nom-descriptif-en-tiret]

Bon : feature/auth-setup, feature/user-profile-page

Mauvais : feature/chose1, feature/authlogin


## 4. Pré-requis et Démarrage Rapide
Installation de Git Flow (git flow init sur windows)
Chaque participant doit installer l'extension Git Flow sur sa machine :

Assurez-vous que Git est installé (via Git for Windows, etc.).

Vérifiez l'installation : git flow version

Cloner et Initialiser
Cloner le dépôt :

Bash

git clone https://github.com/Aptana88/Gamecoin.git
Initialiser Git Flow localement : (Acceptez les valeurs par défaut et définissez le préfixe de tag sur v)

Bash

cd [Nom du Projet]
git flow init
Démarrer le Développement
Assurez-vous d'être sur la branche develop (normalement fait par git flow init).

Démarrez votre première tâche :

Bash

git flow feature start ma-premiere-tache
Faites vos modifications et committez en utilisant le préfixe feat: :

Bash

git add .
git commit -m "feat: ajout du modèle et de la factory User"


## 5. Pratiques de Sécurité
NE JAMAIS committer les fichiers contenant des données sensibles :

.env (contient les clés secrètes WorkOS, les mots de passe BDD, etc.)

Si vous travaillez sur une feature, publiez-la régulièrement pour éviter la perte de données 