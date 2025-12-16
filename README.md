# Mon Projet Laravel avec Docker

## Prérequis
- Docker
- Docker Compose

## Installation

1. Cloner le projet
```bash
git clone https://github.com/kiady06/lari.git
cd lari
```

2. Créer le dossier src
```bash
mkdir src
```

3. Lancer Docker
```bash
docker compose up -d --build
```

4. Installer Laravel
```bash
docker exec -it laravel-app composer create-project laravel/laravel .
```

5. Configurer .env
```bash
cp src/.env.example src/.env
docker exec -it laravel-app php artisan key:generate
```

6. Lancer les migrations
```bash
docker exec -it laravel-app php artisan migrate
```

## Accès
- Application : http://localhost:8080
- Base de données : localhost:3306

## Commandes utiles
```bash
# Arrêter les conteneurs
docker compose down

# Voir les logs
docker compose logs -f

# Accéder au conteneur
docker exec -it laravel-app bash
```