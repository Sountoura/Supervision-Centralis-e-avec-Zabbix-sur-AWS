# Supervision Cloud Hybride avec Zabbix sur AWS

## Description du Projet
Ce projet présente la mise en œuvre d'une infrastructure de monitoring centralisée sur **AWS** utilisant **Zabbix** (déployé via Docker). L'objectif est de surveiller en temps réel un parc hybride composé d'instances **Linux (Ubuntu)** et **Windows Server**.

## Architecture Technique
* [cite_start]**Cloud Provider :** AWS (Région us-east-1)[cite: 65].
* [cite_start]**Conteneurisation :** Docker & Docker-Compose[cite: 44].
* **Instances EC2 :**
    * [cite_start]Serveur Zabbix : t3.large (Ubuntu)[cite: 8].
    * [cite_start]Client Linux : t3.medium (Ubuntu)[cite: 8].
    * [cite_start]Client Windows : t3.large (Windows Server)[cite: 9].

## Sécurité (Security Groups)
[cite_start]Les flux réseaux suivants ont été autorisés pour permettre le monitoring[cite: 6]:
* **Port 80/443 :** Interface Web Zabbix.
* **Ports 10050/10051 :** Communications entre le serveur et les agents.
* **Port 22 (SSH) & 3389 (RDP) :** Administration à distance.

## Guide de Déploiement

### 1. Prérequis
Installer Docker et Docker-Compose sur l'instance Serveur :
```bash
sudo apt update && sudo apt install docker.io docker-compose -y
