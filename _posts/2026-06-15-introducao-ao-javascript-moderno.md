---
layout: post
title: "Introdução ao JavaScript Moderno"
date: 2026-06-15 09:00:00 -0300
categories: javascript desenvolvimento
tags: [javascript, es6, frontend]
---

# JavaScript Moderno: O Guia Definitivo

JavaScript evoluiu muito nos últimos anos. O que antes era uma linguagem de script simples agora é uma ferramenta poderosa para desenvolvimento de aplicações complexas.

## O que mudou?

### ES6+ Features

```javascript
// Arrow functions
const soma = (a, b) => a + b;

// Destructuring
const { nome, idade } = usuario;

// Spread operator
const novosItens = [...itens, novoItem];

// Template literals
const mensagem = `Olá, ${nome}!`;
```

### Async/Await

Promises ficaram muito mais legíveis:

```javascript
async function buscarDados() {
  try {
    const response = await fetch('/api/dados');
    const dados = await response.json();
    return dados;
  } catch (erro) {
    console.error('Erro:', erro);
  }
}
```

## Módulos

Organize seu código em módulos:

```javascript
// utils.js
export const formataData = (data) => {
  return new Date(data).toLocaleDateString('pt-BR');
};

// main.js
import { formataData } from './utils.js';
```

---

**Próximo artigo**: Vamos falar sobre React e como ele revolucionou o desenvolvimento frontend!
