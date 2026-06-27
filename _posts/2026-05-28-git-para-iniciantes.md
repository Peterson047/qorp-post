---
layout: post
title: "Git: Dominando Controle de Versão"
date: 2026-05-28 16:00:00 -0300
categories: git ferramentas
tags: [git, versionamento, tutorial]
---

# Git: Dominando Controle de Versão

Git é essencial para todo desenvolvedor. Vamos dominar os conceitos e comandos mais importantes.

## Conceitos Fundamentais

### Working Directory, Staging e Repository

```
Working Directory    →    Staging Area    →    Repository
     (seus arquivos)       (git add)         (git commit)
```

## Comandos Essenciais

### Iniciar e Configurar

```bash
git init
git config user.name "Seu Nome"
git config user.email "seu@email.com"
```

### Workflow Básico

```bash
# Ver status
git status

# Adicionar arquivos
git add .           # tudo
git add arquivo.js  # específico

# Commitar
git commit -m "Mensagem descritiva"

# Ver histórico
git log --oneline
```

### Branches

```bash
# Criar branch
git branch feature-login

# Trocar branch
git checkout feature-login
# ou
git switch feature-login

# Criar e trocar
git checkout -b feature-login
```

### Merge e Rebase

```bash
# Merge (cria commit de merge)
git merge feature-login

# Rebase (histórico linear)
git rebase main
```

## Boas Práticas

1. **Commits pequenos e descritivos**
2. **Branches por feature**
3. **Pull requests para code review**
4. **Nunca rebase em commits públicos**

---

No próximo artigo, vamos falar de workflows Git (Gitflow, trunk-based)!
