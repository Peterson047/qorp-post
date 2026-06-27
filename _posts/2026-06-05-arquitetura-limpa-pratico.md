---
layout: post
title: "Arquitetura Limpa na Prática"
date: 2026-06-05 10:15:00 -0300
categories: arquitetura design-patterns
tags: [clean-architecture, solid, design]
---

# Arquitetura Limpa: Guia Prático

Arquitetura limpa não é só teoria — é sobre criar sistemas que funcionem, testem e mantenham.

## Os Princípios

### 1. Dependency Rule

As dependências sempre apontam para dentro:

```
┌─────────────────┐
│   Frameworks    │ ←
├─────────────────┤
│  Adaptadores    │ ←
├─────────────────┤
│   Casos de Uso  │ ←
├─────────────────┤
│  Entidades      │ ← Core
└─────────────────┘
```

### 2. Use Cases são o coração

```typescript
interface RegistrarUsuario {
  execute(dados: UsuarioDTO): Promise<Usuario>;
}

class RegistrarUsuarioImpl implements RegistrarUsuario {
  constructor(
    private repo: UsuarioRepository,
    private hasher: PasswordHasher
  ) {}

  async execute(dados: UsuarioDTO): Promise<Usuario> {
    const senhaHash = await this.hasher.hash(dados.senha);
    const usuario = Usuario.criar(dados.email, senhaHash);
    return this.repo.salvar(usuario);
  }
}
```

## Benefícios

- **Testável**: Cada camada pode ser testada isoladamente
- **Flexível**: Troque framework sem mudar regras de negócio
- **Manutenível**: Separação clara de responsabilidades

---

Acompanhe o próximo artigo sobre SOLID na prática!
