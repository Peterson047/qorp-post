# 🚀 Guia Rápido - Qorp Blog

## Como Usar Seu Blog

### 1️⃣ Criar Novo Artigo

Basta criar um arquivo `.md` na pasta `_posts/` com este formato:

```
_posts/2026-06-27-meu-artigo.md
```

### 2️⃣ Front Matter (Cabeçalho do Post)

```yaml
---
layout: post
title: "Título do Seu Artigo"
date: 2026-06-27 14:30:00 -0300
categories: tecnologia
---

Seu conteúdo em markdown aqui...
```

### 3️⃣ Adicionar Imagens

1. Coloque a imagem em `assets/images/`
2. No markdown, use:

```markdown
![Descrição]({{ site.baseurl }}/assets/images/nome-da-imagem.jpg)
```

### 4️⃣ Publicar

```bash
git add .
git commit -m "Novo post: Título do Post"
git push
```

O GitHub Actions vai publicar automaticamente! 🎉

---

## 📝 Markdown Rápido

| O que quer | Como escreve |
|------------|--------------|
| **Negrito** | `**texto**` |
| *Itálico* | `*texto*` |
| [Link](url) | `[texto](url)` |
| `código` | `` `código` `` |
| ![Imagem](url) | `![alt](url)` |
| > Citação | `> texto` |
| - Lista item | `- item` |
| 1. Lista num | `1. item` |
| ```Bloco código``` | \`\`\` ... \`\`\` |

---

## 🎨 Exemplo de Post Completo

```markdown
---
layout: post
title: "Como Usar Markdown"
date: 2026-06-27 10:00:00 -0300
categories: tutorial
---

# Como Usar Markdown

Markdown é uma forma simples de formatar texto.

## Exemplo de Código

```python
print("Olá, mundo!")
```

## Imagem

![Exemplo]({{ site.baseurl }}/assets/images/exemplo.jpg)

## Lista

- Item 1
- Item 2
- Item 3

> "Markdown é poderoso!" — Alguém
```

---

## 🖼️ Imagens de Exemplo

Você pode usar imagens de:
- **Unsplash**: https://unsplash.com (gratis, alta qualidade)
- **Pexels**: https://pexels.com (gratis)
- **Pixabay**: https://pixabay.com (gratis)

---

**É só isso!** Escreva em markdown, commit, e pronto! ✨
