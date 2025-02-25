# README - Configuration Ansible pour Docker et Réseau

## Description
Ce projet contient un playbook Ansible permettant d'automatiser plusieurs tâches sur un serveur Linux. Les tâches incluent l'installation et la configuration de Docker, la gestion des utilisateurs, la récupération des interfaces réseau, et l'exposition de Docker en HTTP.

## Prérequis
- Un serveur Linux avec un accès SSH
- Ansible installé sur votre machine de contrôle
- Droits sudo sur le serveur cible

## Instructions d'Installation

1. **Cloner le Repository**
   ```bash
   git clone https://github.com/worketyamo-devops/ansible-docker-setup.git
   cd ansible-docker-setup
   ```

2. **Configurer l'Inventaire**
   Modifier le fichier `inventory.ini` pour ajouter l'adresse IP ou le nom d'hôte de votre serveur cible.
   
   Exemple :
   ```ini
   [servers]
   192.168.1.100 ansible_user=your_user ansible_ssh_private_key_file=~/.ssh/id_rsa
   ```

3. **Exécuter le Playbook**
   ```bash
   ansible-playbook -i inventory.ini playbook.yml
   ```

## Détails des Tâches Ansible

### 1. Installation et Configuration de Docker
- Installation des paquets nécessaires
- Ajout du dépôt officiel de Docker
- Installation de Docker Engine et activation du service
- Ajout des utilisateurs au groupe Docker

### 2. Création d'un Groupe et de Deux Utilisateurs
- Création d'un groupe nommé `docker_users`
- Création de deux utilisateurs avec un home directory et ajout au groupe `docker_users`

### 3. Récupération des Interfaces Réseau
- Extraction des noms des interfaces réseau et des passerelles par défaut
- Stockage des informations dans une variable Ansible

### 4. Exposition du Service Docker en HTTP
- Modification du fichier de service Docker pour permettre l'accès HTTP
- Redémarrage du service Docker pour appliquer les changements

## Bonus
- **Commenter chaque tâche** : Chaque étape du playbook est documentée pour faciliter la compréhension.
- **Versionner le code Ansible** : Utilisation de Git pour suivre les modifications.
- **Création de modules** : Possibilité d'organiser le code en rôles pour plus de modularité.
- **Déploiement sur GitHub** : Le code est disponible sur [GitHub](https://github.com/worketyamo-devops/ansible-docker-setup).

## Auteur
[ROBERTO]  Worketyamo DevOps Team

