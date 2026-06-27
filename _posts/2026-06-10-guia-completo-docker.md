---
layout: post
title: "Docker: Do Zero ao Deploy"
date: 2026-06-10 14:30:00 -0300
categories: devops docker
tags: [docker, containers, devops]
---

# Docker: Do Zero ao Deploy

Containers mudaram completamente como desenvolvemos e deployamos software. Neste guia, vamos do básico ao deploy em produção.

## O que é Docker?

Docker é uma plataforma que permite empacotar aplicações em containers — leves, portáteis e independentes.

## Dockerfile Básico

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

## Comandos Essenciais

```bash
# Build de imagem
docker build -t minha-app .

# Rodar container
docker run -p 3000:3000 minha-app

# Ver containers rodando
docker ps

# Parar container
docker stop <container-id>
```

## Docker Compose

Orquestre múltiplos containers:

```yaml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "3000:3000"
    depends_on:
      - db

  db:
    image: postgres:15
    environment:
      POSTGRES_PASSWORD: secret
```

---

No próximo artigo, vamos cobrir Kubernetes e orquestração de containers em escala!
