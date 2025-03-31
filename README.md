# Cours-Conteneur-et-devops

# README - Introduction à Docker

## Introduction

Docker est une plateforme permettant de développer, expédier et exécuter des applications sous forme de conteneurs. Ce fichier README propose une introduction aux commandes de base et un cours pratique pour débuter avec Docker.

## Installation

Pour installer Docker, suivez les instructions officielles sur le site : [Docker Documentation](https://docs.docker.com/get-docker/).

## Commandes de Base

### Gestion des images
- **Rechercher une image Docker :**  
  ```sh
  docker search <nom_image>
  ```
- **Télécharger une image Docker :**  
  ```sh
  docker pull <nom_image>
  ```
- **Lister les images locales :**  
  ```sh
  docker images
  ```
- **Supprimer une image :**  
  ```sh
  docker rmi <image_id>
  ```

### Gestion des conteneurs
- **Exécuter un conteneur :**  
  ```sh
  docker run <nom_image>
  ```
- **Exécuter un conteneur en mode détaché :**  
  ```sh
  docker run -d <nom_image>
  ```
- **Lister les conteneurs actifs :**  
  ```sh
  docker ps
  ```
- **Lister tous les conteneurs (actifs et stoppés) :**  
  ```sh
  docker ps -a
  ```
- **Arrêter un conteneur :**  
  ```sh
  docker stop <container_id>
  ```
- **Supprimer un conteneur :**  
  ```sh
  docker rm <container_id>
  ```

### Gestion des volumes
- **Lister les volumes :**  
  ```sh
  docker volume ls
  ```
- **Créer un volume :**  
  ```sh
  docker volume create <nom_du_volume>
  ```
- **Supprimer un volume :**  
  ```sh
  docker volume rm <nom_du_volume>
  ```

## Cours Pratique : Premier Projet avec Docker

### 1. Créer un projet Docker

Créez un dossier et placez-y un fichier `Dockerfile` :

```dockerfile
# Utilisation de l'image officielle de Python
FROM python:3.9

# Définition du dossier de travail
WORKDIR /app

# Copier les fichiers nécessaires
COPY . /app

# Installer les dépendances
RUN pip install -r requirements.txt

# Commande de démarrage
CMD ["python", "app.py"]
```

### 2. Construire l'image Docker

```sh
docker build -t mon_app .
```

### 3. Exécuter le conteneur

```sh
docker run -d -p 5000:5000 mon_app
```

Accédez ensuite à `http://localhost:5000` pour voir l'application en cours d'exécution.

### 4. Arrêter et Supprimer le Conteneur

```sh
docker stop <container_id>
docker rm <container_id>
```

## Conclusion

Docker simplifie le déploiement et la gestion des applications en encapsulant tout dans des conteneurs isolés. Ce guide vous donne une introduction aux bases, mais il y a encore beaucoup à explorer, comme Docker Compose, la gestion des réseaux et l'orchestration avec Kubernetes !

Bonne découverte de Docker ! 🚀

