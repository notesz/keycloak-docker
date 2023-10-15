# keycloak-docker

Docker for Keycloak. \
Keycloak is an Open Source Identity and Access Management solution for modern Applications and Services.

Repository: https://github.com/notesz/keycloak-docker \
Keycloak documentation: https://www.keycloak.org/documentation.html

## Goal of this project

The goal of this container is to provide an example for running Keycloak.

The Dockerfile based on [quay.io/keycloak/keycloak:latest](http://quay.io/keycloak/keycloak:latest).

## Usage

### Preparation

1. Download the files
2. Create a .env from .env.example and modify it in the main folder (the example contains my recommended settings)

### Run container

In the main directory run the container with docker-compose

```shell
docker-compose up -d
```

When your environment was launched you can open it in your browser: \
http://localhost:8080

### Stop container

In the main directory stop tha container with docker-compose

```shell
docker-compose down
```
