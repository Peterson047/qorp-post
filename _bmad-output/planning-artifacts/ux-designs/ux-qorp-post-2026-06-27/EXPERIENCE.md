# Qorp Blog — EXPERIENCE.md

## Foundation

**Form-factor**: Web responsivo, mobile-first. Otimizado para leitura em desktop (720px content width) com experiência completa em mobile (single column, touch-optimized).

**UI System**: Custom design system implementado em Jekyll/Liquid. Não há framework de componentes — o HTML/CSS é construído diretamente. DESIGN.md especifica todos os tokens visuais.

**Plataformas**:
- Desktop (1024px+): Leitura imersiva, layout otimizado
- Tablet (768px-1023px): Adaptado, mesmo conteúdo
- Mobile (<768px): Single column, elementos touch-friendly

---

## Information Architecture

### Estrutura Principal

```
/ (Home)
├── Sobre
├── Arquivo
│   ├── Por Categoria
│   └── Por Data
└── {slug-do-post} (Página de post individual)
```

### Home (/)

**Seções**:
1. **Header fixo** — Logo + navegação
2. **Hero** — Título "Qorp Blog" + descrição breve
3. **Posts recentes** — Lista de 10 posts mais recentes
4. **Footer** — Copyright + link RSS

### Post Individual (/{slug})

**Seções**:
1. **Header fixo** — Logo + navegação
2. **Título do post** — H1 grande
3. **Meta** — Data, categoria, tempo de leitura
4. **Conteúdo** — Corpo do artigo (markdown → HTML)
5. **Footer do post** — Tags, autor
6. **Navegação entre posts** — Anterior/próximo
7. **Footer global** — Copyright

### Arquivo (/arquivo)

**Seções**:
1. **Header fixo**
2. **Filtros** — Por categoria / Por data
3. **Lista agrupada** — Posts organizados por critério

---

## Voice and Tone

### Voz Editorial

**Qorp Blog** fala como um especialista experiente, acessível e reflexivo. Não acadêmico, não informal — equilibrado.

### Tom

| Contexto | Tom | Exemplo |
|----------|-----|---------|
| Títulos | Confidente, claro | "Arquitetura Limpa na Prática" |
| Corpo | Conversacional, educado | "Vamos explorar como..." |
| Tutoriais | Instrutivo, paciente | "Primeiro, faça X..." |
| Opinião | Reflexivo, nuanciado | "Na minha experiência..." |
| CTAs | Direto, polido | "Leia mais →" |

### Microcopy

| Elemento | Copy |
|----------|-------|
| Loading spinner | "Carregando..." |
| Vazio (sem posts) | "Nenhum post ainda. Em breve!" |
| Erro 404 | "Página não encontrada. <a href='/'>Voltar ao início</a>." |
| Read more | "Ler artigo →" |
| Post date | "27 jun 2026" |
| Reading time | "5 min de leitura" |

---

## Component Patterns

### Post Card (Lista)

**Comportamento**:
- Hover: escurece título em 10%
- Click: navega para página do post
- Focus: anel 2px `gray-400` ao redor

**Anatomia**:
```
┌─────────────────────┐
│ [Título do Post]    │  Serif 1.25rem, gray-950
│ [Data] • [Cat]      │  Sans 0.75rem, gray-600
└─────────────────────┘
```

**Estados**:
- Default: título `gray-950`
- Hover: título `gray-800`, cursor pointer
- Focus: anel outline `2px gray-400`

### Header Fixo

**Comportamento**:
- Sticky: permanece no topo ao scroll
- Background: `white` com `opacity 0.95` + backdrop blur
- Shadow: aparece ao scroll (sombra `sm`)

**Anatomia**:
```
┌─────────────────────────────┐
│ [Qorp Blog]  Home Sobre Arq│
└─────────────────────────────┘
```

### Botão (CTA)

**Comportamento**:
- Click: ação primária
- Loading: spinner + opacidade 50%
- Disabled: opacidade 40%, cursor not-allowed

**Estados**:
- Default: `gray-950` bg, `white` texto
- Hover: `gray-900` bg
- Active: `gray-800` bg
- Focus: anel `2px gray-400`

---

## State Patterns

### Loading States

| Componente | Estado |
|-------------|--------|
| Página | Skeleton loader ou spinner central |
| Lista posts | 3 skeleton cards |
| Botão | Spinner + texto original |

### Empty States

| Contexto | Tratamento |
|----------|-------------|
| Lista vazia | Mensagem "Nenhum post ainda" |
| Busca sem resultados | "Nenhum resultado para '{query}'" |
| Categoria vazia | "Nenhum post em {categoria}" |

### Error States

| Erro | Tratamento |
|------|------------|
| 404 | "Página não encontrada" + link home |
| 500 | "Algo deu errado. Tente novamente." |
| Offline | "Você está offline. Verifique sua conexão." |

---

## Interaction Primitives

### Scroll

- **Comportamento**: Scroll natural, scroll-to-top suave ao clicar no logo
- **Header**: Sticky com backdrop blur
- **Anchor links**: Scroll suave (+ CSS `scroll-behavior: smooth`)

### Hover

- **Links**: Cor escurece 10%, transição 150ms
- **Botões**: Background escurece 10%, transição 150ms
- **Cards**: Sombra aparece (sm → md)

### Focus

- **Acessibilidade**: Anel 2px `gray-400` em todos os elementos interativos
- **Skip links**: "Pular para conteúdo" disponível (visível apenas no focus)

### Touch (Mobile)

- **Tap targets**: Mínimo 44×44px
- **Gestos**: Pull-to-refresh desabilitado (evita conflito)
- **Swipe**: Não aplicável (single column layout)

---

## Accessibility Floor

### Comportamental

- **Navegação por teclado**: Todo conteúdo acessível via Tab
- **Skip links**: "Pular para conteúdo" no topo
- **Focus visible**: Sempre indicado (anel outline)
- **ARIA labels**: Em elementos interativos sem texto

### Visual (coberto por DESIGN.md)

- Contraste mínimo WCAG AAA (7:1)
- Fonte mínima 14px no corpo
- Links não dependem apenas de cor

### Leitor de Tela

- Heading structure: H1 → H2 → H3 (sem saltos)
- Alt text em imagens: Descritivo
- Listas: Marcadas corretamente (`<ul>`, `<ol>`)
- Landmarks: `<header>`, `<main>`, `<footer>`, `<nav>`

---

## Key Flows

### Flow 1: Leitura de Artigo (Maria, dev em casa)

**Persona**: Maria, desenvolvedora, lendo artigo sobre arquitetura no laptop após o trabalho.

**Cenário**: Quer ler artigo completo sobre Clean Architecture.

1. Maria acessa `qorp-post.github.io`
2. Vê header com logo "Qorp Blog"
3. Scrola e encontra post "Arquitetura Limpa na Prática"
4. Clica no título (hover: escurece)
5. Navega para página do post
6. Lê título H1 grande, meta info (data, categoria)
7. Consome conteúdo tipografia serifada confortável
8. Ao final, vê tags e link "Próximo post"
9. Clica em "Próximo" para continuar lendo

**Climax**: Momento de absorção — Maria encontra insight útil sobre Clean Architecture, aplica no trabalho dia seguinte.

**Superfícies**: Home → Post

### Flow 2: Descoberta por Categoria (João, mobile)

**Persona**: João, entusiasta de IA, buscando conteúdo específico no celular durante通勤.

**Cenário**: Quer encontrar todos os posts sobre LLMs.

1. João abre blog no mobile Chrome
2. Vê header comprimido (logo + menu hambúrguer)
3. Toca menu, seleciona "Arquivo"
4. Vê filtros, toca "Por Categoria"
5. Seleciona "IA"
6. Vê lista de posts sobre IA/LLMs
7. Toca "Introdução a LLMs"
8. Lê artigo em formato mobile-optimized
9. Termina leitura, toca "Voltar" para ver mais posts

**Climax**: João encontra exatamente o que procurava — tutorial LLM prático.

**Superfícies**: Home → Arquivo → Categoria → Post

### Flow 3: Primeira Visita (Ana, curiosa)

**Persona**: Ana, não técnica, curiosidade sobre tecnologia apósindicar por amigo.

**Cenário**: Primeira vez no blog, explorando.

1. Ana clica link compartilhado
2. Landing na Home
3. Lê título "Qorp Blog" + descrição
4. Scrola posts recentes, vê "Carreira em Desenvolvimento"
5. Título acessível, tipografia convidativa
6. Clica, lê artigo opinativo
7. Identifica-se com reflexões sobre carreira
7. Fecha aba satisfeita, retorna futuramente

**Climax**: Ana encontra conteúdo acessível que engaja, torna-se leitora recorrente.

**Superfícies**: Home → Post

---

## Responsive & Platform

### Desktop (1024px+)

- Content width: 720px max
- Header: Logo left, nav right
- Posts: 2-column grid (home) ou single column centered

### Tablet (768px-1023px)

- Content width: 100% com padding 2rem
- Header: Logo left, nav below (hambúrguer)
- Posts: Single column

### Mobile (<768px)

- Content width: 100% com padding 1rem
- Header: Logo center, menu hambúrguer
- Posts: Single column, card spacing reduzido
- Touch targets: Mínimo 44×44px

---

## Platform-Specific Concerns

### Dark Mode (Future)

Não implementado em v1. DESIGN.md monocromático facilita extensão.

### PWA (Future)

Considerar para v2: offline reading, app-like experience.

### Print (Support)

CSS print-friendly: esconder header/footer, tipografia otimizada para papel.

---

## Cross-References to DESIGN.md

- `{colors.primary}` — Botões primários, links
- `{colors.secondary}` — Meta info
- `{typography.serif}` — Corpo do texto
- `{typography.sans}` — UI elements
- `{spacing.content.max_width}` — Container width
- `{components.header}` — Header spec
- `{components.post_card}` — Post card spec

---

*Status: Final — Ready for implementation*
