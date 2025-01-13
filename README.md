# **SIEM avec Suricata, Grafana, Promtail et Loki**

### **Description du projet**

Ce projet est en cours de développement et consiste à créer un système de gestion des événements et des informations de sécurité (**SIEM**) en utilisant **Suricata**, **Grafana**, **Promtail** et **Loki**. L'objectif est d'intégrer **Suricata** pour la détection d'intrusions réseau, d'envoyer les logs via **Promtail** vers **Loki**, et de les visualiser dans **Grafana**. Le but est de fournir une solution simple et efficace pour la surveillance des événements réseau.

### **Structure du projet**

Le projet comprend plusieurs composants clés :

- **Suricata** : utilisé pour détecter les intrusions sur le réseau et générer des logs détaillant les événements.
- **Grafana** : utilisé pour visualiser les logs générés par Suricata via Loki.
- **Promtail** : sert à récupérer les logs Suricata et à les envoyer à Loki pour l'indexation.
- **Loki** : utilisé pour stocker et indexer les logs avant qu'ils ne soient récupérés par Grafana pour l'affichage.

### **Configuration du projet**

#### **Fichiers et répertoires importants**

- **`data/suricata-log/`** : dans ce répertoire, vous trouverez un fichier **`.gitignore`**. Ce fichier est conçu pour éviter que des logs sensibles ou inutiles ne soient envoyés au dépôt Git.
  
  **Note importante** : Il est essentiel de copier vos logs Suricata dans ce répertoire, en particulier le fichier **`eve.json`**. Le fichier **`eve.json`** contient les événements générés par Suricata et doit être surveillé par **Promtail** pour être envoyé à **Loki**.

#### **Étapes pour démarrer**

1. **Copier les logs de Suricata** :
   - Assurez-vous que vos logs Suricata, notamment **`eve.json`**, sont copiés dans le répertoire **`data/suricata-log/`**.
   - Ce fichier est essentiel pour que **Promtail** puisse collecter et envoyer les logs à **Loki**.

2. **Configurer Promtail** :
   - **Promtail** est configuré pour surveiller le répertoire **`data/suricata-log/`** et envoyer les logs à **Loki**. Assurez-vous que Promtail est bien configuré et fonctionne correctement pour l'indexation des logs.

3. **Démarrer Grafana** :
   - Une fois que **Loki** reçoit les logs via **Promtail**, **Grafana** peut être utilisé pour visualiser les données. Assurez-vous que **Grafana** est configuré pour se connecter à **Loki** en tant que source de données.

4. **Suricata** :
   - Assurez-vous que **Suricata** est correctement installé et que les logs sont générés dans le format **`eve.json`**. Vous pouvez personnaliser les règles de **Suricata** en fonction des besoins du projet.
