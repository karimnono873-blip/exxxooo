# Dashboard RTOS & Mutex I2C - Édition Master

## Description du Projet
Ce dépôt contient un tableau de bord interactif (interface web monolithique) conçu pour illustrer et simuler l'architecture logicielle et matérielle d'un robot embarqué. Il met en évidence l'utilisation d'un système d'exploitation temps réel (FreeRTOS) pour gérer des tâches concurrentes dans un système de contrôle en boucle fermée.

Le simulateur permet de visualiser en temps réel plusieurs concepts avancés d'ingénierie des systèmes embarqués et d'automatisation :
* **Ordonnancement des tâches :** Hiérarchisation des routines d'Acquisition, de Traitement et de Stockage.
* **Synchronisation et exclusion mutuelle :** Implémentation d'un Mutex pour protéger l'accès au bus matériel partagé (I2C) entre les capteurs et la mémoire (EEPROM).
* **Contrôle en boucle fermée :** Illustration de la réaction dynamique du système face aux données d'environnement (feedback).

## Fonctionnalités
* **Simulation d'Acquisition (Priorité Haute) :** Déclenche la lecture des capteurs (ex: Ultrason, Gyroscope) via le bus I2C.
* **Traitement des Données (Priorité Moyenne) :** Simule le calcul de l'erreur pour l'ajustement dynamique des consignes du robot.
* **Stockage EEPROM (Priorité Basse) :** Simule la sauvegarde des états en mémoire non volatile.
* **Visualisation du Mutex I2C :** Animation visuelle et interactive du verrouillage (Take) et déverrouillage (Give) de la ressource matérielle pour prévenir les conditions de course (*Race Conditions*).
* **Terminal de Log Système :** Suivi en temps réel des appels de fonctions FreeRTOS (`xSemaphoreTake`, `xSemaphoreGive`).

## Déploiement
Ce projet ne nécessite aucune installation de framework ou de serveur local.

1.  Clonez ce dépôt sur votre machine locale.
2.  Ouvrez le fichier `index.html` directement dans n'importe quel navigateur web moderne.
3.  **Hébergement en ligne :** Ce projet est optimisé pour être hébergé directement et gratuitement via **GitHub Pages**. Naviguez dans *Settings > Pages* de votre dépôt et sélectionnez la branche `main` pour générer votre lien public.

## Structure du Fichier
Le projet est conçu dans une approche monolithique (`index.html`) pour faciliter la portabilité :
* **Structure (HTML) :** Définition des panneaux de contrôle et de la zone de modélisation de l'architecture.
* **Design (CSS) :** Interface sombre (Dark Mode) avec variables CSS, optimisée pour la lisibilité technique et l'animation des flux de données.
* **Logique (JavaScript) :** Moteur de simulation qui gère l'état global du Mutex (`isMutexLocked`), l'enchaînement des tâches et les animations du bus I2C.

---
*Projet développé dans le cadre de la modélisation de systèmes temps réel et d'automatisation.*
