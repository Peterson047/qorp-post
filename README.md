# Qorp Blog

Um blog simples baseado em Jekyll + GitHub Pages, focado em leitura agradável de artigos em markdown.

## 🚀 Como Funciona

Este blog usa **Jekyll** (gerador de sites estáticos) com o tema **Minima**. Quando você faz push de um arquivo markdown para a pasta `_posts/`, o Jekyll automaticamente gera uma página HTML para esse post.

## ✍️ Criar Novo Post

1. Crie um arquivo na pasta `_posts/` com o formato:
   ```
   YYYY-MM-DD-titulo-do-post.md
   ```

2. Adicione o front matter no início:
   ```yaml
   ---
   layout: post
   title: "Título do Post"
   date: 2026-06-27 18:30:00 -0300
   categories: tecnologia
   ---
   ```

3. Escreva seu conteúdo em markdown!

## 🖼️ Usar Imagens

Coloque suas imagens na pasta `assets/images/` e referencie assim:

```markdown
![Descrição da imagem]({{ site.baseurl }}/assets/images/nome.jpg)
```

## 📦 Estrutura do Projeto

```
qorp-post/
├── _posts/           # Seus artigos em markdown
├── assets/
│   └── images/       # Imagens do blog
├── _config.yml       # Configuração do Jekyll
├── index.md          # Página inicial
└── README.md         # Este arquivo
```

## 🌐 Publicar no GitHub Pages

### Opção 1: GitHub Pages Automático
1. Vá em Settings > Pages do seu repositório
2. Selecione "Source: GitHub Actions"
3. Ou use "Source: Deploy from a branch" (branch: main, folder: /root)

### Opção 2: GitHub Actions (Recomendado)

Crie `.github/workflows/jekyll.yml`:

```yaml
name: Deploy Jekyll site
on:
  push:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: ruby/setup-ruby@v1
        with:
          ruby-version: '3.3'
          bundler-cache: true
      - uses: jeffreytse/jekyll-deploy-action@v0.5.0
        with:
          provider: github
          token: ${{ secrets.GITHUB_TOKEN }}
```

## 🎨 Personalização

Edite o `_config.yml` para personalizar:
- `title`: Nome do blog
- `description`: Descrição
- `author`: Seu nome
- `url`: URL do site

## 📝 Comandos Úteis

Para testar localmente:
```bash
# Instalar Jekyll (primeira vez)
gem install jekyll bundler

# Instalar dependências
bundle install

# Rodar localmente
bundle exec jekyll serve
```

Acesse em: `http://localhost:4000`

---

**Simples assim!** ✨
