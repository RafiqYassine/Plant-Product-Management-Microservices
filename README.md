# Plant-Product-Management-Microservices
This project is a small but fully functional microservices-based application built with Node.js and Docker Compose. It is designed to demonstrate service isolation, containerization, and inter-service communication using a clean and modular architecture.

The system is split into multiple independent services:

🔐 Auth Service

Handles user authentication, JWT token generation, and user management.
Connects to a MongoDB database via MONGO_URI.

🛒 Product Service

Manages product data and validates incoming requests by communicating with the Auth Service through an internal Docker URL (http://auth-service:3001).
Uses MongoDB for data storage.

🌱 Plant Service

Handles plant-related logic and integrates with an external public API to fetch real plant information.
Also communicates with the Auth Service for protected routes.

💻 Client Application

A standalone frontend (React or Node-based) communicating with the backend microservices through exposed ports.

⚙ Architecture & Workflow

Each service runs inside its own Docker container.
Docker Compose orchestrates the services and ensures startup order through depends_on.
Internal communication uses Docker service names, while MongoDB is accessed through host.docker.internal.

This architecture mimics real production environments where services are isolated, scalable, and independently deployable.

Ce projet est une application microservices complète mais légère, développée avec Node.js et Docker Compose. Il illustre l’isolation des services, la containerisation et la communication inter-services tout en suivant une architecture propre et modulaire.

Le système est divisé en plusieurs services indépendants :

🔐 Service d’Authentification

Gère l’authentification des utilisateurs, la génération de tokens JWT et la gestion des comptes.
Se connecte à MongoDB via MONGO_URI.

🛒 Service Produit

Gère les données des produits et valide les requêtes entrantes en communiquant avec le service d’authentification via une URL interne Docker (http://auth-service:3001).
Stocke les données dans MongoDB.

🌱 Service Plante

Gère les informations liées aux plantes et consomme une API publique externe pour obtenir des données réelles et mises à jour.
Vérifie également les accès via le service d’authentification.

💻 Application Client

Une application frontend indépendante (React ou Node) qui communique avec les microservices via les ports exposés.

⚙ Architecture & Fonctionnement

Chaque service fonctionne dans son propre conteneur Docker.
Docker Compose orchestre l’ensemble et assure l’ordre de démarrage grâce à depends_on.
La communication interne se fait via les noms des services Docker, tandis que MongoDB est accessible via host.docker.internal.

Cette architecture reproduit un environnement réel où les services sont isolés, évolutifs et déployables indépendamment.
