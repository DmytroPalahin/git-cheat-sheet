🇬🇧 [English](README.md) | 🇫🇷 [Français](README.fr.md)

# 📋 Git Cheat Sheet

## 🌀 Git - Système de contrôle de version distribué

## 🌐 GitHub - Service d'hébergement de dépôts Git

## 🛠️ Commandes Git de base

```bash
git --version      # afficher la version de Git
git --help         # afficher l'aide pour les commandes Git
```

### ⚙️ Configurer Git

```bash
git config --global user.name <nom>     # définir le nom d'utilisateur global
git config --global user.email <email>  # définir l'email global
git config --list                       # afficher la configuration de Git
```

Exemple :

```bash
git config --global user.name "Dmytro Palahin"
git config --global user.email "dmytro.palahin@gmail.com"
```

### 🏁 Initialiser un dépôt Git

```bash
git init                                # initialiser un dépôt Git dans le projet
git remote -v                           # afficher les dépôts distants
git remote add origin <repository-url>  # ajouter un dépôt distant
git push -u origin master               # envoyer les modifications au dépôt distant
```

### 📊 Vérifier l'état du dépôt

```bash
git status                              # afficher la zone de staging et les modifications à valider
```

### 📜 Voir l'historique des commits

```bash
git log                                 # afficher l'historique des commits
```

### ➕ Ajouter et supprimer des fichiers

```bash
git add .                               # ajouter tous les fichiers du répertoire de travail à la zone de staging
git add -f environment.yml              # ajouter un fichier spécifique avec force
git rm <file>                           # supprimer un fichier de la zone de staging et du répertoire de travail
```

### 💾 Valider les modifications

```bash
git commit -m "<message>"               # valider les modifications dans la zone de staging avec un message
```

### 🌿 Changer de branches et de commits

```bash
git checkout <commit hash>              # basculer sur un commit spécifique
git checkout <branch name>              # basculer sur une branche existante
git checkout -b <branch name>           # créer une nouvelle branche et basculer dessus
git checkout main                       # revenir à la branche principale
```

### 🌲 Gestion des branches

```bash
git branch <branch name>                # créer une nouvelle branche
git branch                              # lister toutes les branches
git branch -a                           # lister toutes les branches, y compris les branches distantes
git branch -m <new name>                # renommer la branche actuelle
git branch -d <branch>                  # supprimer une branche (impossible de supprimer la branche actuelle)
git branch -vv                          # lister toutes les branches avec des informations supplémentaires
```

### 🔀 Fusionner des branches

```bash
git merge <feature branch>              # fusionner une branche de fonctionnalité dans la branche actuelle
git merge -m "<message>" <branch>       # fusionner avec un message personnalisé
```

### 🔍 Inspecter les commits

```bash
git cat-file -t <commit hash>           # afficher le type d'un objet (commit, blob, etc.)
git cat-file -p <commit hash>           # afficher le contenu de l'objet
```

### 🔄 Envoyer et récupérer des modifications

```bash
git push                                # envoyer les modifications du dépôt local au dépôt distant
git pull                                # appliquer les modifications d'un dépôt distant dans votre branche locale actuelle
git clone <url>                         # cloner un dépôt distant sur la machine locale
```

### 🌐 Gestion des dépôts distants

```bash
git remote add origin <url>             # connecter un dépôt distant
git remote                              # lister les dépôts distants
git remote -v                           # afficher les URL des dépôts distants
```

### 🚀 Envoyer des modifications au dépôt distant

```bash
git push -u origin <branch>             # envoyer les modifications au dépôt distant et suivre la branche
git push -u origin main                 # envoyer les modifications à la branche principale
```

---

## 🔄 Workflow typique

### 📊 Vérifier l'état du répertoire de travail

```bash
git status
```

### ➕ Ajouter ou supprimer des fichiers

```bash
git add <file>              # ajouter un fichier spécifique à la zone de staging
git rm <file>               # supprimer un fichier spécifique du dépôt
git restore <file>          # annuler les modifications dans le répertoire de travail pour un fichier spécifique
```

### 💾 Valider vos modifications

```bash
git commit -m "<message>"
```

### 🚀 Envoyer les modifications au dépôt distant (workflow)

```bash
git push
git push --set-upstream origin <branch-name>
```

---

## 🌟 Configuration initiale pour un nouveau dépôt distant

### 🌐 Ajouter le dépôt distant

```bash
git remote add origin <url>
```

### ✅ Vérifier que le dépôt distant est correctement configuré

```bash
git remote -v
```

### 🌿 Renommer la branche actuelle en `main`

```bash
git branch -M main
```

### 🚀 Envoyer les modifications au dépôt distant

```bash
git push -u origin main
```

---

## 🏷️ Ajouter et gérer des tags

### 📜 Lister les tags

```bash
git tag   # lister tous les tags
```

### 🏷️ Créer un tag

```bash
git tag <tagname>                       # créer un tag léger
git tag -a <tagname> -m "<message>"     # créer un tag annoté avec un message
```

### 🔍 Afficher les détails d'un tag

```bash
git show <tagname>                      # afficher les détails d'un tag spécifique
```

### 🚀 Envoyer les tags au dépôt distant

```bash
git push origin <tagname>               # envoyer un tag spécifique au dépôt distant
git push origin --tags                  # envoyer tous les tags au dépôt distant
```

### 🗑️ Supprimer un tag

```bash
git tag -d <tagname>                    # supprimer un tag spécifique
git push origin --delete <tagname>      # supprimer un tag du dépôt distant
```

---

## 🔄 Renommer une branche localement et à distance

### 🌿 Renommer la branche localement

```bash
git branch -m <old-branch-name> <new-branch-name>
```

### 🚀 Envoyer la branche renommée au dépôt distant

```bash
git push origin <new-branch-name>
```

### 🗑️ Supprimer l'ancienne branche du dépôt distant

```bash
git push origin --delete <old-branch-name>
```

### 🌐 Réinitialiser la branche upstream pour la nouvelle branche

```bash
git push --set-upstream origin <new-branch-name>
```

---

## 🏷️ Renommer un tag localement et à distance

### 🏷️ Renommer le tag localement

```bash
git tag <new-tag-name> <old-tag-name>       # créer un nouveau tag avec le commit de l'ancien tag
git tag -d <old-tag-name>                   # supprimer l'ancien tag localement
```

### 🚀 Envoyer le nouveau tag au dépôt distant

```bash
git push origin <new-tag-name>
```

### 🗑️ Supprimer l'ancien tag du dépôt distant

```bash
git push origin --delete <old-tag-name>
```

---
