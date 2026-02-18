# Supervision Cloud Hybride avec Zabbix sur AWS

## Description du Projet
Ce projet présente la mise en œuvre d'une infrastructure de monitoring centralisée sur **AWS** utilisant **Zabbix** (déployé via Docker). L'objectif est de surveiller en temps réel un parc hybride composé d'instances **Linux (Ubuntu)** et **Windows Server**.

## Architecture Technique
**Cloud Provider :** AWS (Région us-east-1).
**Conteneurisation :** Docker & Docker-Compose.
**Instances EC2 :**
    * **Serveur Zabbix : t3.large (Ubuntu).
    * **Client Linux : t3.medium (Ubuntu).
    * **Client Windows : t3.large (Windows Server).

## Sécurité (Security Groups)
Les flux réseaux suivants ont été autorisés pour permettre le monitoring:
* **Port 80/443 :** Interface Web Zabbix.
* **Ports 10050/10051 :** Communications entre le serveur et les agents.
* **Port 22 (SSH) & 3389 (RDP) :** Administration à distance.

## Guide de Déploiement

### 1. Prérequis
Installer Docker et Docker-Compose sur l'instance Serveur :
```bash
sudo apt update && sudo apt install docker.io docker-compose -y
