---
name: CaféX
colors:
  surface: '#fcf9f4'
  surface-dim: '#dcdad5'
  surface-bright: '#fcf9f4'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f6f3ee'
  surface-container: '#f0ede9'
  surface-container-high: '#ebe8e3'
  surface-container-highest: '#e5e2dd'
  on-surface: '#1c1c19'
  on-surface-variant: '#404945'
  inverse-surface: '#31302d'
  inverse-on-surface: '#f3f0eb'
  outline: '#707974'
  outline-variant: '#c0c9c3'
  surface-tint: '#376757'
  primary: '#003629'
  on-primary: '#ffffff'
  primary-container: '#1b4d3e'
  on-primary-container: '#8abda9'
  inverse-primary: '#9ed1bd'
  secondary: '#3e6a00'
  on-secondary: '#ffffff'
  secondary-container: '#b9f474'
  on-secondary-container: '#437000'
  tertiary: '#442814'
  on-tertiary: '#ffffff'
  tertiary-container: '#5d3e28'
  on-tertiary-container: '#d5aa8e'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#baeed9'
  primary-fixed-dim: '#9ed1bd'
  on-primary-fixed: '#002117'
  on-primary-fixed-variant: '#1d4f40'
  secondary-fixed: '#b9f474'
  secondary-fixed-dim: '#9ed75b'
  on-secondary-fixed: '#0f2000'
  on-secondary-fixed-variant: '#2e4f00'
  tertiary-fixed: '#ffdcc6'
  tertiary-fixed-dim: '#eabda0'
  on-tertiary-fixed: '#2d1604'
  on-tertiary-fixed-variant: '#5f402a'
  background: '#fcf9f4'
  on-background: '#1c1c19'
  surface-variant: '#e5e2dd'
typography:
  headline-lg:
    fontFamily: Poppins
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
  headline-md:
    fontFamily: Poppins
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 31px
  headline-sm:
    fontFamily: Poppins
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
  subtitle:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '500'
    lineHeight: 22px
  body:
    fontFamily: Inter
    fontSize: 15px
    fontWeight: '400'
    lineHeight: 22px
  body-emphasis:
    fontFamily: Inter
    fontSize: 15px
    fontWeight: '600'
    lineHeight: 22px
  button:
    fontFamily: Inter
    fontSize: 15px
    fontWeight: '600'
    lineHeight: 18px
  caption:
    fontFamily: Inter
    fontSize: 13px
    fontWeight: '400'
    lineHeight: 19px
  badge:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 14px
  micro:
    fontFamily: Inter
    fontSize: 11px
    fontWeight: '500'
    lineHeight: 13px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 24px
  margin: 32px
  space-xs: 4px
  space-sm: 8px
  space-md: 16px
  space-lg: 24px
  space-xl: 32px
  space-2xl: 48px
---

# Design System — Projeto CaféX (v2, com referência Preply)

## 1. Visual Theme & Atmosphere

O CaféX é um ecossistema digital para a cadeia produtiva do café, acessado pela web (dashboard de administradores e membros) e por um chatbot de IA no WhatsApp. A tela central do produto — a **busca/seleção por categoria** (Agrônomos, Mão de Obra, Insumos e Maquinários) — segue o padrão de marketplace de tutores da **Preply**: filtros/categorias no topo, e cartões de resultado em **carrossel horizontal mobile-first**, com foto no topo e informações objetivas logo abaixo, sem excesso de texto.

Da Preply, absorvemos três coisas centrais: (1) a **navegação por categoria em pills/tabs horizontais** no topo da página, que troca todo o conjunto de resultados abaixo; (2) o **cartão de resultado "foto em cima, dados em baixo"**, denso em informação mas visualmente limpo, com preço/avaliação sempre nas mesmas posições para permitir comparação rápida; (3) o uso de **texto quase preto sobre fundo branco puro**, com cor de marca reservada apenas para badges, preços e botões — nunca como fundo de página.

Do sistema já definido para o CaféX, mantemos: canvas branco/creme, Verde Escuro como cor estrutural, Verde Claro como cor de ação, Marrom Café como cor de identidade rural. A cor "hero" da Preply (rosa/magenta) e o azul de "accent" **não são usados** — o CaféX substitui esses papéis por Verde Claro (ação) e Marrom (badges/identidade), mantendo o mesmo *princípio* de "uma cor de marca por função", mas com paleta própria.

**Key Characteristics:**
- Canvas branco (`#FFFFFF`) / creme (`#FAF7F2`) com Verde Escuro (`#1B4D3E`) estrutural e Verde Claro (`#8BC34A`) como única cor de ação
- Navegação por **categoria em pills horizontais** (Agrônomos, Mão de Obra, Insumos, Maquinários) fixas no topo da listagem, inspiradas nos filtros de assunto da Preply
- Cartões de resultado em **carrossel horizontal com scroll-snap**, foto no topo (quadrada para pessoas, 4:3 para produtos) e dados em bloco abaixo, replicando a densidade informacional da Preply
- Preço/avaliação sempre na mesma posição do cartão, para comparação rápida entre profissionais ou insumos
- Badges de status sobrepostos à foto (`Disponível`, `Verificado`, `Popular`) no canto superior, como o badge "Super Tutor" da Preply
- Botão de ação único e full-width dentro do cartão (`Ver perfil`, `Solicitar contato`, `Ver oferta`)
- Texto quase preto (`#2B2B26`) sobre branco puro — sem tons acinzentados excessivos
- Peso tipográfico moderado a forte em nomes/títulos de card (600–700), corpo leve (400) nas descrições curtas

## 2. Color Palette & Roles

### Primary Brand
- **Verde Escuro** (`#1B4D3E`): `--cafex-bg-primary-core` — header, tabs de categoria ativas, textos de marca
- **Verde Escuro Hover** (`#123529`): `--cafex-bg-primary-hover` — pressed do verde escuro
- **Verde Claro** (`#8BC34A`): `--cafex-bg-accent-core` — botão de ação dos cards ("Ver perfil", "Solicitar"), preço em destaque, badge "Disponível"
- **Verde Claro Hover** (`#6FA036`): `--cafex-bg-accent-hover`

### Marrom (Cor de Calor / Café)
- **Marrom Café** (`#6F4E37`): `--cafex-bg-brown-core` — badge "Popular"/"Verificado", ícones de categoria (Insumos, Maquinários)
- **Marrom Claro / Latte** (`#C8A27E`): `--cafex-bg-brown-soft` — fundo de tag neutra, chip de especialidade dentro do card
- **Marrom Escuro** (`#3E2B1F`): `--cafex-text-brown-strong` — texto sobre chip marrom claro

### Text Scale
- **Grafite** (`#2B2B26`): `--cafex-text-primary` — nome do profissional/produto, título de card
- **Texto Secundário** (`#5B5B54`): `--cafex-text-secondary` — especialidade, localização, unidade de medida
- **Texto Desabilitado** (`rgba(43,43,38,0.38)`): campos/cards indisponíveis
- **Texto sobre Verde Escuro** (`#FFFFFF`): tabs ativas, header
- **Texto sobre Verde Claro** (`#123529`): texto do botão de ação sobre fundo verde claro

### Semantic
- **Sucesso / Disponível** (`#4C9A2A`): badge "Disponível agora"
- **Alerta** (`#E8A33D`): estoque baixo (Insumos), poucas vagas (Mão de Obra)
- **Erro** (`#C0392B`): indisponível, penalidade grave
- **Avaliação (estrelas)** (`#E8A33D`): ícone de estrela preenchida — mesmo tom do alerta, papel visual isolado (rating), nunca reaproveitado para texto de erro

### Surface & Neutros
- **Branco** (`#FFFFFF`): fundo de página e do cartão
- **Off-white / Creme** (`#FAF7F2`): fundo da página atrás dos cartões, separando o carrossel do restante do layout
- **Cinza Borda** (`#E1DCD3`): borda 1px do cartão em repouso
- **Sombra Card** (`rgba(27,77,62,0.10) 0px 2px 8px`): elevação única e sutil do cartão (inspirada na sombra rasa da Preply, sem camadas múltiplas)

## 3. Typography Rules

### Font Family
- **Títulos / Nomes de card**: `Poppins` (fallbacks: `Nunito, -apple-system, system-ui, Roboto`)
- **Corpo / UI / Formulários**: `Inter` (fallbacks: `Helvetica Neue, Arial, sans-serif`)
- **WhatsApp (bot)**: negrito (`*texto*`), itálico (`_texto_`) e emojis de categoria (🌱👷📦🚜) para simular a hierarquia dos cards fora do site

### Hierarchy

| Papel | Fonte | Tamanho | Peso | Line Height | Uso |
|---|---|---|---|---|---|
| Título de Página | Poppins | 28px (1.75rem) | 700 | 1.25 | Título da tela de busca ("Encontre profissionais") |
| Tab de Categoria | Inter | 14px (0.88rem) | 600 | 1.20 | Texto da pill de categoria |
| Nome do Card (Pessoa) | Poppins | 16px (1.00rem) | 600 | 1.30 | Nome do agrônomo/trabalhador |
| Título do Card (Produto) | Poppins | 15px (0.94rem) | 600 | 1.30 | Nome do insumo/maquinário |
| Preço em Destaque | Poppins | 16px (1.00rem) | 700 | 1.20 | Valor da diária/hora ou preço do produto |
| Subtítulo do Card | Inter | 13px (0.81rem) | 500 | 1.35 | Especialidade, categoria, marca |
| Corpo do Card | Inter | 12px (0.75rem) | 400 | 1.40 | Localização, distância, disponibilidade |
| Rating | Inter | 12px (0.75rem) | 600 | 1.20 | Nota + nº de avaliações, ao lado das estrelas |
| Badge / Tag | Inter | 11px (0.69rem) | 600 | 1.15 | "Disponível", "Verificado", "Popular" |
| Botão do Card | Inter | 14px (0.88rem) | 600 | 1.20 | "Ver perfil", "Solicitar contato" |
| Legenda / Caption | Inter | 11px (0.69rem) | 400 | 1.30 | Unidade de medida, "por hora", "por saca" |

### Principles
- **Hierarquia em 3 níveis por card**: nome/título (mais forte) → preço/rating (destaque secundário) → metadados (mais leve). Nunca mais que 3 pesos tipográficos dentro de um mesmo cartão, replicando a disciplina visual da Preply.
- **Poppins só em nome/título e preço** — o resto do card usa Inter, mantendo densidade de informação legível em espaços pequenos (card mobile de ~160px de largura útil de texto).
- **Truncamento obrigatório**: nome/título do card em 1 linha (`text-overflow: ellipsis`), subtítulo em no máximo 2 linhas — essencial porque os cards do carrossel são estreitos.

## 4. Navegação por Categoria (Tabs de Filtro)

Inspirada diretamente na barra de filtros de assunto da Preply, mas simplificada para 4 categorias fixas do MVP.

### Especificação exata

- **Container**: barra horizontal fixa logo abaixo do header, `position: sticky; top: [altura do header]`, fundo `#FFFFFF`, borda inferior `1px solid #E1DCD3`.
- **Padding do container**: `12px 16px`, scroll horizontal (`overflow-x: auto`, `scrollbar-width: none` — sem barra de rolagem visível).
- **Espaçamento entre pills**: `8px`.
- **Pill (estado inativo)**: fundo `#FFFFFF`, borda `1px solid #E1DCD3`, texto `#2B2B26`, radius `999px` (pill total), padding `8px 16px`, ícone emoji/SVG de 16px à esquerda do texto com `4px` de gap.
- **Pill (estado ativo)**: fundo `#1B4D3E`, texto `#FFFFFF`, sem borda, mesmo padding e radius. Transição de 150ms no background ao trocar de categoria.
- **Pill (hover/tap, mobile = active state via `:active`)**: fundo `#FAF7F2` quando inativa; `#123529` quando ativa.
- **As 4 categorias fixas, nesta ordem**: 🌱 Agrônomos · 👷 Mão de Obra · 📦 Insumos · 🚜 Maquinários.
- **Comportamento**: apenas uma categoria ativa por vez; ao trocar, o carrossel de cards abaixo é recarregado com uma transição de fade de 150ms (sem reload de página).
- **Contador opcional**: à direita do nome da categoria ativa, um texto secundário (`12px`, `#5B5B54`) exibindo o total de resultados — ex.: "Agrônomos · 24 encontrados".

## 5. Carrossel de Cards — Especificação Exata

Esta é a peça central da tela, e deve seguir rigorosamente as medidas abaixo em todas as 4 categorias (o conteúdo interno varia; a estrutura, não).

### 5.1. Contêiner do carrossel

- `display: flex`, `overflow-x: auto`, `scroll-snap-type: x mandatory`.
- **Padding lateral do trilho**: `16px` no início e no fim (mesmo gutter da página), garantindo que o primeiro e o último card nunca colem na borda da tela.
- **Gap entre cards**: `12px` fixo, em todas as resoluções.
- **Peek do próximo card**: o layout deve revelar entre `10%` e `15%` do card seguinte na borda direita da viewport — é o que sinaliza visualmente que há mais conteúdo para o lado, exatamente como a lista de tutores da Preply em mobile.
- **Scrollbar**: oculta (`scrollbar-width: none` / `::-webkit-scrollbar { display: none }`).
- **Indicador de posição** (opcional, abaixo do carrossel): dots de `6px` de diâmetro, espaçados em `6px`, cor ativa `#1B4D3E`, cor inativa `#E1DCD3`.

### 5.2. Dimensões do card (mobile-first)

| Propriedade | Mobile (<576px) | Tablet (576–992px) | Desktop (>992px) |
|---|---|---|---|
| Largura do card | `164px` | `200px` | `224px` |
| `scroll-snap-align` | `start` | `start` | `start` |
| Border radius | `16px` | `16px` | `16px` |
| Borda | `1px solid #E1DCD3` | idem | idem |
| Sombra | `rgba(27,77,62,0.10) 0px 2px 8px` | idem | idem |
| Fundo | `#FFFFFF` | idem | idem |
| Overflow | `hidden` (para a foto respeitar o radius no topo) | idem | idem |

O card **nunca** tem altura fixa — a altura é definida pelo conteúdo (foto + bloco de texto), mas o bloco de texto interno deve seguir a estrutura fixa da seção 5.4 para manter todos os cards da mesma fileira com altura consistente.

### 5.3. Área da foto (topo do card)

- **Pessoas** (Agrônomos, Mão de Obra): proporção **1:1** (quadrada), `object-fit: cover`, ocupando 100% da largura do card.
- **Produtos** (Insumos, Maquinários): proporção **4:3** (paisagem), `object-fit: cover`, 100% da largura do card — mostra o produto/equipamento por inteiro, diferente da foto de rosto usada para pessoas.
- **Badge sobreposto** (canto superior esquerdo da foto, `8px` de distância das bordas): pill pequena, padding `4px 8px`, radius `999px`, fundo sólido conforme o tipo:
  - `Disponível agora` → fundo `#4C9A2A`, texto branco
  - `Verificado` → fundo `#1B4D3E`, texto branco, ícone de check
  - `Popular` → fundo `#6F4E37`, texto branco
- **Ícone de favorito/salvar** (canto superior direito da foto, `8px` de distância): círculo `28px`, fundo `rgba(255,255,255,0.9)`, ícone de coração/estrela em `#2B2B26`, sem sombra própria.

### 5.4. Bloco de informações (abaixo da foto)

Padding interno do bloco: `12px` em todos os lados. Estrutura em **4 linhas fixas**, nesta ordem, para todas as categorias:

1. **Linha 1 — Título**: nome da pessoa (`Poppins 16px/600`) ou nome do produto (`Poppins 15px/600`), 1 linha, `ellipsis` se ultrapassar.
2. **Linha 2 — Subtítulo categórico**: especialidade (ex.: "Agrônomo · Manejo de pragas"), função (ex.: "Colhedor de café"), ou categoria do insumo/maquinário (ex.: "Fertilizante · NPK"). Fonte `Inter 13px/500`, cor `#5B5B54`, até 2 linhas.
3. **Linha 3 — Métrica de confiança + preço**: `display: flex; justify-content: space-between`.
   - Esquerda: para pessoas, ⭐ ícone `12px` + nota (`Inter 12px/600`, cor `#2B2B26`) + "(nº avaliações)" em `#5B5B54`. Para produtos, texto de disponibilidade/estoque (ex.: "Em estoque").
   - Direita: preço em destaque, `Poppins 16px/700`, cor `#2B2B26`, com a unidade em caption menor ao lado (ex.: "R$ 180 `/dia`" ou "R$ 89 `/saca`") — a unidade usa `Inter 11px/400` na cor `#5B5B54`.
4. **Linha 4 — Botão de ação**: full-width (`width: 100%`), altura `36px`, fundo `#8BC34A`, texto `#123529` (`Inter 14px/600`), radius `8px`, sem borda. Texto do botão varia por categoria:
   - Agrônomos / Mão de Obra → `"Ver perfil"`
   - Insumos / Maquinários → `"Ver oferta"`
   - Espaçamento acima do botão: `10px` (separando da linha 3).

Espaçamento vertical entre as linhas 1→2→3: `4px` cada. Entre a linha 3 e o botão: `10px` (conforme acima).

### 5.5. Estados do card

- **Repouso**: conforme especificado acima.
- **Pressed (tap mobile)**: `scale(0.98)` + sombra reduzida para `rgba(27,77,62,0.06) 0px 1px 4px`, transição `100ms`.
- **Indisponível**: foto com overlay `rgba(255,255,255,0.6)`, badge cinza `"Indisponível"` (fundo `#E1DCD3`, texto `#5B5B54`) substituindo o badge de status, botão de ação desabilitado (fundo `#F0EDE8`, texto `rgba(43,43,38,0.38)`, sem interação).
- **Carregando (skeleton)**: retângulo cinza-claro (`#F0EDE8`) pulsante no lugar da foto e 3 barras cinza no lugar das linhas de texto, mesmo radius e dimensões do card final.

## 6. Componentes Complementares

### Botões (fora do card)

**Primário (Verde Claro)** — mesma regra da v1: fundo `#8BC34A`, texto `#123529`, padding `10px 24px`, radius `10px`.

**Secundário (Verde Escuro)** — fundo `#1B4D3E`, texto `#FFFFFF`, mesma métrica.

**Terciário / Contorno (Marrom)** — borda `1px solid #6F4E37`, texto `#6F4E37`, fundo transparente.

### Barra de busca (acima das tabs de categoria)

- Fundo `#FFFFFF`, borda `1px solid #E1DCD3`, radius `12px`, altura `44px`, padding `0 16px`, ícone de lupa `18px` em `#5B5B54` à esquerda.
- Placeholder: `Inter 14px/400`, cor `#5B5B54` a 70% — ex.: "Buscar por nome, especialidade ou região".

### Cards & Containers (herdado da v1)
- Radius geral: `16px` (cards de listagem/formulário), `24px` (cards hero), `999px` (badges/pills).
- Sombra padrão fora do carrossel: `rgba(27,77,62,0.08) 0px 2px 4px, rgba(27,77,62,0.06) 0px 8px 16px`.

## 7. Layout Principles

### Spacing System
- Unidade base: `8px`. Escala: `4px, 8px, 10px, 12px, 16px, 20px, 24px, 32px, 40px`.

### Estrutura da página de seleção (mobile)
1. Header fixo (Verde Escuro, `64px`).
2. Barra de busca (`16px` de padding lateral e vertical).
3. Tabs de categoria (sticky, seção 4).
4. Título da seção + contador de resultados (`16px` de padding lateral).
5. Carrossel de cards (seção 5) — um carrossel por categoria ativa; ao rolar a página verticalmente, pode haver múltiplos carrosséis (ex.: "Recomendados perto de você", "Mais bem avaliados") como faz a Preply com múltiplas fileiras de tutores.
6. Botão "Ver todos" ao final de cada carrossel, levando a uma lista vertical completa (grid 2 colunas em mobile, 3–4 em desktop).

### Border Radius Scale
- Sutil (`8px`): inputs, botão de ação do card.
- Padrão (`10px`): botões gerais.
- Card (`16px`): card do carrossel, listagens.
- Destaque (`24px`): cards hero.
- Pill (`999px`): tabs de categoria, badges.

## 8. Depth & Elevation

| Nível | Tratamento | Uso |
|---|---|---|
| Flat (0) | Sem sombra | Fundo de página, tabs inativas |
| Card (1) | `rgba(27,77,62,0.10) 0px 2px 8px` | Cards do carrossel (sombra única, rasa — estilo Preply) |
| Pressed (1b) | `rgba(27,77,62,0.06) 0px 1px 4px` | Card tocado/pressionado |
| Elevado (2) | `rgba(27,77,62,0.08) 0px 2px 4px, rgba(27,77,62,0.06) 0px 8px 16px` | Modais, pop-ups de confirmação |

**Filosofia de sombra**: diferente da Airbnb (três camadas) e mais próxima da Preply (sombra única e discreta), os cards do carrossel usam apenas uma camada de sombra rasa — a densidade de informação do card já cria hierarquia visual suficiente, sem precisar de elevação dramática.

## 9. Do's and Don'ts

### Do
- Manter a estrutura de 4 linhas fixas em todo card do carrossel (título → subtítulo → métrica/preço → botão), independentemente da categoria
- Usar foto quadrada (1:1) para pessoas e 4:3 para produtos — nunca misturar proporções dentro do mesmo carrossel
- Garantir o "peek" de 10–15% do próximo card para indicar scroll horizontal em mobile
- Colocar preço/avaliação sempre na mesma posição (linha 3) para permitir comparação rápida entre cards
- Usar badge sobreposto na foto apenas para status curtos (1–2 palavras): "Disponível", "Verificado", "Popular"
- Aplicar sombra única e rasa nos cards do carrossel — não empilhar múltiplas camadas de sombra aqui

### Don't
- Não usar mais de 4 linhas de texto dentro do bloco de informação do card
- Não permitir que o nome/título quebre em 2 linhas — sempre truncar com ellipsis
- Não usar cor de marca (verde escuro/claro) como fundo da foto ou do card — reservada a badges, preço e botão
- Não remover o gutter lateral de `16px` no início/fim do carrossel
- Não usar sombra em três camadas (padrão Airbnb) nos cards do carrossel — mantenha a sombra rasa e única
- Não misturar o botão "Ver perfil" (pessoas) com "Ver oferta" (produtos) fora do contexto correto

## 10. Responsive Behavior

### Breakpoints
| Nome | Largura | Comportamento do carrossel |
|---|---|---|
| Mobile | <576px | Card `164px`, peek de ~12%, 1 carrossel por categoria visível por vez |
| Tablet | 576–992px | Card `200px`, mais cards visíveis simultaneamente, peek reduzido |
| Desktop | 992–1440px | Card `224px`, setas de navegação (`◀ ▶`) aparecem sobre o carrossel no hover, substituindo o gesto de swipe |
| Desktop Grande | >1440px | Mesma medida do card; aumenta o número de cards visíveis, sem aumentar o card individual |

### Touch Targets
- Botão de ação do card: altura mínima `36px` (abaixo do padrão geral de `44px` por ser uma ação secundária dentro de um card já clicável; o card inteiro também é clicável e leva ao perfil/oferta completo).
- Tabs de categoria: altura mínima `36px` de área tocável, com padding generoso (`8px 16px`) compensando o texto pequeno.

## 11. Agent Prompt Guide

### Quick Color Reference
- Fundo: Branco (`#FFFFFF`) / Creme (`#FAF7F2`)
- Estrutura: Verde Escuro (`#1B4D3E`)
- Ação/CTA: Verde Claro (`#8BC34A`) com texto `#123529`
- Identidade rural: Marrom (`#6F4E37` / `#C8A27E`)
- Texto: Grafite (`#2B2B26`), Secundário (`#5B5B54`)

### Example Component Prompts
- "Crie uma tab de categoria ativa: fundo `#1B4D3E`, texto branco, radius `999px`, padding `8px 16px`, Inter 14px peso 600, ícone emoji à esquerda."
- "Crie um card de carrossel para Agrônomo: largura 164px, foto quadrada 1:1 no topo com badge 'Disponível agora' (fundo `#4C9A2A`) no canto superior esquerdo, bloco de texto com nome em Poppins 16px/600, especialidade em Inter 13px/500 cinza, linha de rating (⭐ 4.9 · 32 avaliações) à esquerda e preço 'R$ 150/dia' em Poppins 16px/700 à direita, botão 'Ver perfil' full-width verde claro."
- "Crie um card de carrossel para Insumo: largura 164px, foto 4:3 do produto, badge 'Popular' marrom no canto, nome do produto em Poppins 15px/600, categoria 'Fertilizante · NPK' em Inter 13px cinza, 'Em estoque' à esquerda e 'R$ 89/saca' à direita, botão 'Ver oferta' verde claro."
- "Monte o trilho do carrossel: scroll horizontal com snap, gutter de 16px nas pontas, gap de 12px entre cards, revelando 12% do próximo card na borda direita."

### Iteration Guide
1. Comece pelas 4 tabs de categoria fixas (Agrônomos, Mão de Obra, Insumos, Maquinários) — apenas uma ativa por vez, cor verde escuro
2. Estruture o card do carrossel em 4 linhas fixas: título, subtítulo, métrica/preço, botão — nunca mais que isso
3. Foto quadrada para pessoas, 4:3 para produtos — badge de status sempre sobreposto na foto, nunca no bloco de texto
4. Sombra única e rasa nos cards (estilo Preply), radius 16px, gutter lateral de 16px no trilho
5. Peek de 10–15% do próximo card para sinalizar scroll horizontal em mobile
6. Preço e avaliação sempre na mesma posição (linha 3) para comparação rápida entre resultados