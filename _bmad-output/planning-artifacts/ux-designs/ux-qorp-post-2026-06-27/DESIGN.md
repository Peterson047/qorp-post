---
version: 1.0.0
name: Qorp Blog Visual Identity
status: final
updated: 2026-06-27
project: Qorp Blog
colors:
  primary: "#1a1a1a"
  secondary: "#757575"
  accent: "#424242"
  background: "#fafafa"
  surface: "#ffffff"
  error: "#d32f2f"
  success: "#388e3c"
  warning: "#f57c00"
typography:
  font_family:
    primary: '"Literata", "Merriweather", Georgia, serif'
    secondary: '"Inter", system-ui, sans-serif'
    mono: '"JetBrains Mono", "SF Mono", monospace'
  font_sizes:
    xs: "0.75rem"
    sm: "0.875rem"
    base: "1rem"
    lg: "1.125rem"
    xl: "1.25rem"
    "2xl": "1.5rem"
    "3xl": "1.875rem"
    "4xl": "2.25rem"
    "5xl": "3rem"
rounded:
  sm: "4px"
  md: "6px"
  lg: "8px"
  xl: "12px"
spacing:
  xs: "0.25rem"
  sm: "0.5rem"
  md: "1rem"
  lg: "1.5rem"
  xl: "2rem"
  "2xl": "3rem"
  "3xl": "4rem"
components:
  button:
    variant: default
    size: md
  input:
    variant: default
    size: md
  card:
    variant: default
    size: md
---

# Qorp Blog — DESIGN.md

## Brand & Style

**Qorp Blog** é uma plataforma de publicação focada em leitura imersiva, minimalista e elegante. Inspirada na estética clean do Medium com header funcional estilo Substack.

### Voz Visual

- **Minimalista**: Cada elemento tem propósito; nada é ornamental
- **Contemplativo**: Espaço generoso consegue absorção e reflexão
- **Sophisticated**: Monocromático com nuances sutis de cinza
- **Editorial**: Autoridade tipográfica serifada no corpo do texto

### Princípios

1. **Tipografia é protagonista** — A fonte serifada é a estrela; tudo mais serve ela
2. **Monocromático elegante** — Variação de cinzas, sem cores competitivas
3. **Espaço respirável** — Margens largas, line-height generoso
4. **Contraste控制** — Hierarquia clara através de peso e escala, não cor

---

## Colors

### Paleta Monocromática (Tons de Cinza)

```yaml
# Tokens
colors:
  # Neutros primários
  gray-950:  "#1a1a1a"   # Texto principal, headers
  gray-900:  "#212121"   # Texto secundário
  gray-800:  "#424242"   # Acentos sutis, links
  gray-700:  "#616161"   # Meta informação
  gray-600:  "#757575"   # Texto terciário
  gray-500:  "#9e9e9e"   # Bordas, divisores
  gray-400:  "#bdbdbd"   # Bordas sutis
  gray-300:  "#e0e0e0"   # Fundo inputs
  gray-200:  "#eeeeee"   # Divisores, fundo terciário
  gray-100:  "#f5f5f5"   # Fundo secundário
  gray-50:   "#fafafa"   # Fundo primário
  white:     "#ffffff"   # Superfícies

  # Semânticos (tons de cinza)
  primary:   gray-950   # Ações primárias, CTAs
  secondary: gray-600    # Ações secundárias
  accent:    gray-800    # Highlights, estados ativos
```

### Aplicação

| Elemento | Token | Uso |
|----------|-------|-----|
| Título H1 | `gray-950` | Headers principais |
| Corpo do texto | `gray-900` | Conteúdo principal |
| Links | `gray-800` | Navegação, hyperlinks |
| Meta info | `gray-600` | Datas, categorias |
| Bordas | `gray-300` | Separadores |
| Fundo página | `gray-50` | Background principal |
| Cards/superfícies | `white` | Containers de conteúdo |

### Regras

- Nunca usar cor fora do espectro cinza
- Contraste mínimo WCAG AAA (7:1) para texto
- Links sem sublinhado; apenas cor + cursor pointer
- Hover states: um tom mais escuro na escala

---

## Typography

### Fontes

```yaml
families:
  # Corpo do texto — serifada para leitura longa
  serif:
    stack: '"Literata", "Merriweather", Georgia, serif'
    fallback: Georgia, serif
    weight: [300, 400, 500]

  # UI — sans-serif para elementos de interface
  sans:
    stack: '"Inter", system-ui, sans-serif'
    fallback: system-ui, sans-serif
    weight: [400, 500, 600]

  # Código — monospaced
  mono:
    stack: '"JetBrains Mono", "SF Mono", monospace'
    fallback: monospace
```

### Escala Tipográfica

```yaml
font_sizes:
  # Display
  display:     "3rem"      # 48px — Page titles

  # Headings
  h1:          "2.25rem"   # 36px — Article titles
  h2:          "1.75rem"   # 28px — Section headings
  h3:          "1.5rem"    # 24px — Subsections
  h4:          "1.25rem"   # 20px — Component titles

  # Body
  body-lg:     "1.125rem"  # 18px — Leitura confortável
  body:        "1rem"      # 16px — Base
  body-sm:     "0.875rem"  # 14px — Meta info

  # UI
  xs:          "0.75rem"   # 12px — Labels, captions
```

### Aplicação por Contexto

| Contexto | Fonte | Tamanho | Weight | Line-height |
|----------|-------|---------|--------|-------------|
| Título do artigo | serif | 2.25rem | 400 | 1.2 |
| Título de seção | serif | 1.75rem | 400 | 1.3 |
| Corpo do texto | serif | 1.125rem | 400 | 1.8 |
| Meta (data, autor) | sans | 0.875rem | 400 | 1.4 |
| Header/navegação | sans | 1rem | 500 | 1.5 |
| Código inline | mono | 0.9em | — | — |
| Bloco de código | mono | 0.875rem | — | 1.6 |

### Detalhes

- **Literata/Google Fonts**: Carregar via CDN
- **Tracking**: -0.01em para serif display, 0 para corpo
- **Kerning**: Ativo para headings above 1.5rem

---

## Layout & Spacing

### Container

```yaml
content:
  max_width: "720px"       # Largura de livro otimizada
  padding:
    mobile: "1rem"         # 16px
    tablet: "2rem"         # 32px
    desktop: "3rem"        # 48px

  margin:
    section: "3rem"        # Espaço entre seções maiores
    paragraph: "1.5rem"    # Entre parágrafos
  }
```

### Grid System

Mobile-first, single column:

```
┌─────────────────────┐
│  [Header fixo]      │  60px altura
├─────────────────────┤
│                     │
│  [Conteúdo]         │  Single column,
│  max-width 720px    │  centralizado
│                     │
├─────────────────────┤
│  [Footer]           │
└─────────────────────┘
```

### Breakpoints

```yaml
breakpoints:
  mobile:   "0px"        # Base
  tablet:   "768px"      # md
  desktop:  "1024px"     # lg
  wide:     "1280px"     # xl
```

---

## Elevation & Depth

Sutil; sombras apenas para separar camadas quando necessário:

```yaml
shadows:
  sm:  "0 1px 2px rgba(0,0,0,0.05)"     # Cards sutis
  md:  "0 2px 8px rgba(0,0,0,0.08)"     # Dropdowns, modais
  lg:  "0 4px 16px rgba(0,0,0,0.12)"    # Toasts
```

### Z-Index

```yaml
z:
  base:     1
  header:   10
  dropdown: 100
  modal:    200
  toast:    300
```

---

## Shapes

### Border Radius

```yaml
radius:
  sm:  "4px"    # Botões, inputs
  md:  "6px"    # Cards
  lg:  "8px"    # Imagens
  xl:  "12px"   # Componentes grandes
```

### Bordas

```yaml
border:
  width: "1px"
  style: "solid"
  color: "gray-300"
```

---

## Components

### Header (Estilo Substack)

```yaml
header:
  height: "60px"
  background: "white"
  border_bottom: "1px solid gray-300"
  position: "sticky"
  top: 0
  z_index: 10

  logo:
    font: "sans, weight-600, size-xl"
    color: "gray-950"

  nav:
    items: [
      { label: "Home", href: "/" },
      { label: "Sobre", href: "/sobre" },
      { label: "Arquivo", href: "/arquivo" }
    ]
    font: "sans, weight-500, size-sm"
    color: "gray-800"
    spacing: "2rem"
```

### Botão (Post Card)

```yaml
post_card:
  background: "white"
  border: "none"
  border_radius: "md"
  padding: "lg"

  title:
    font: "serif, weight-400, size-xl"
    color: "gray-950"
    line_height: 1.3

  meta:
    font: "sans, weight-400, size-xs"
    color: "gray-600"
    text_transform: "uppercase"
    letter_spacing: "0.05em"

  hover:
    title_color: "gray-800"
```

### Botão Primário

```yaml
button:
  primary:
    background: "gray-950"
    color: "white"
    border_radius: "sm"
    padding: "sm md"
    font: "sans, weight-500, size-sm"

    hover:
      background: "gray-900"
```

### Código

```yaml
code:
  inline:
    background: "gray-100"
    color: "gray-900"
    border_radius: "sm"
    padding: "0.2em 0.4em"
    font: "mono, size-xs"

  block:
    background: "gray-100"
    border: "1px solid gray-300"
    border_radius: "md"
    padding: "lg"
    font: "mono, size-sm"
    line_height: 1.6
```

---

## Do's and Don'ts

### ✅ Do

- Use apenas escala monocromática de cinza
- Deixe tipografia serifada brilhar no corpo
- Mantenha largura de conteúdo em 720px máximo
- Use espaço generoso entre seções
- Centralize conteúdo com margens simétricas
- Line-height 1.8+ para corpo de texto

### ❌ Don't

- Nunca introduza cores fora do espectro cinza
- Não exceda 720px de largura de conteúdo
- Não use font-weight bold abusivamente
- Não comprima espaçamento para "caber mais"
- Não use sombras pesadas
- Não decore sem propósito funcional
