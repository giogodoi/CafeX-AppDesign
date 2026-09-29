# CafeX-AppDesign
Prototipagem de alta fidelidade para apresentação no Hackaton Avança Café 2026

# Guia de Design Consciente com IA 

> Este documento explica **como** chegamos a um arquivo como o `DESIGN-CAFEX.md` (tokens em YAML + especificação em Markdown) e **por que** cada etapa existe. Ele serve hoje como guia de boas práticas e, no futuro, como o roteiro de perguntas de uma skill que entrevista o usuário e gera um documento equivalente para qualquer novo projeto.

## Por que "design consciente" precisa ser um processo, não um prompt

Modelos de IA são treinados em milhões de interfaces e, sem restrições explícitas, convergem para os mesmos padrões: gradiente roxo-azul, cards com sombra pesada, grid genérico de 3 colunas, texto "Lorem ipsum" de marketing. Esse fenômeno já tem nome na comunidade de produto — "AI slop" — e a causa raiz identificada em múltiplas análises recentes é sempre a mesma: **o prompt pediu resultado antes de existir um sistema**. Quando não há uma decisão prévia de paleta, tipografia, tom de voz e anti-padrões, a IA preenche essas lacunas com a média estatística do que já viu — e a média é, por definição, genérica.

A saída documentada por essas análises é inverter a ordem: **extrair/definir o sistema de design primeiro, em um arquivo machine-readable, e só then gerar telas a partir dele** — exatamente o papel que o `DESIGN-CAFEX.md` cumpre. Documentos de design legíveis por humanos (Figma, Notion) não bastam, porque o agente de IA não os "lê" da mesma forma; a especificação precisa existir como regras estruturadas e explícitas (tokens + hex + medidas exatas), como fizemos nas seções de cor, tipografia e no card do carrossel.

Esse é o motivo de todo o rigor que aplicamos até aqui: cada hex, cada `px`, cada estado ("pressed", "skeleton", "indisponível") documentado é uma lacuna a menos para a IA preencher com o genérico.

## Anatomia do documento (o que o `DESIGN-CAFEX.md` já faz certo)

Antes das etapas, vale nomear a estrutura que o arquivo já segue, porque é o "esqueleto" que a futura skill vai reproduzir:

| Bloco do arquivo | Função |
|---|---|
| **Frontmatter YAML** (`colors`, `typography`, `rounded`, `spacing`) | Tokens em formato estruturado, consumível por código/agentes — não é só documentação, é dado. |
| **1. Visual Theme & Atmosphere** | A "tese" do projeto em prosa: de onde vêm as decisões e por quê. Sem isso, os tokens viram números soltos. |
| **2. Color Palette & Roles** | Cada cor amarrada a um **papel semântico** (`--cafex-bg-accent-core`), nunca só ao nome da cor. |
| **3. Typography Rules** | Hierarquia tabulada, com regras de uso ("nunca peso 400 em heading") — não só uma lista de tamanhos. |
| **4–6. Especificação de componentes** | Medidas exatas (px, cores, estados) de cada peça reutilizável — o nível de detalhe que elimina ambiguidade para a IA. |
| **7–8. Layout, elevação** | Como as peças se organizam no espaço e se sobrepõem. |
| **9. Do's and Don'ts** | Anti-padrões explícitos — a parte mais eficaz contra o "slop", segundo as análises mais recentes sobre prompting de UI. |
| **10. Responsive Behavior** | Comportamento por breakpoint, não só "responsivo". |
| **11. Agent Prompt Guide** | Prompts de exemplo já formatados — reduz a variância de interpretação do agente. |

Essa estrutura em 11 blocos é o "contrato" que a skill futura deve preencher, seção por seção, a partir das respostas do usuário.

## As Etapas do Processo

### Etapa 1 — Descoberta e Referências (antes de qualquer token)

O que precisa existir antes de abrir um editor de cores:

- **Contexto do negócio**: o que o produto faz, para quem, e qual problema real resolve (no CaféX, isso veio direto do documento de requisitos).
- **3 a 5 referências visuais concretas**, não abstratas. "Clean e moderno" não é uma referência; "Preply" e "Airbnb" são. A prática recomendada é sempre nomear produtos reais e extrair *padrões*, não copiar telas.
- **O que NÃO queremos parecer**: liste concorrentes ou clichês a evitar explicitamente (ex.: "não queremos parecer um dashboard SaaS genérico").
- **Emoção-alvo em 3 palavras**: no CaféX foram "acolhedor", "confiável", "raiz agrícola" — essas palavras é que guiaram a escolha de verde/marrom em vez do rosa da Preply ou do lima da Wise.

> Sem essa etapa, a IA não tem "gosto" para imitar — só tem estatística média para reproduzir.

### Etapa 2 — Fundamentos (Tokens Primitivos)

Definir os valores brutos, sem ainda atribuir função:

- **Paleta de cor bruta**: de 3 a 5 matizes (não mais que isso no início — sistemas de token devem começar pequenos e crescer por necessidade real, não por antecipação).
- **Escala tipográfica**: 2 famílias no máximo (uma para título, uma para corpo/UI), com pesos definidos por *intenção* ("peso mínimo 600 em heading para soar confiante"), não por acaso.
- **Escala de espaçamento e radius**: uma progressão consistente (o CaféX usa base 8px) — isso é o que garante que qualquer tela nova "encaixe" visualmente sem recalcular do zero.

### Etapa 3 — Papéis Semânticos (Tokens Semânticos)

Esta é a etapa mais frequentemente pulada, e a mais citada como prática recomendada em documentação de tokens: **nunca usar o token primitivo diretamente na interface**. Cada cor primitiva ganha um nome de **papel**:

- `#8BC34A` não é "usado no botão" — ele *é* `--cafex-bg-accent-core`, e a regra "essa cor só aparece em CTA, nunca como fundo de página" é parte do token, não uma lembrança solta.
- Essa separação primitivo → semântico é o que permite, no futuro, trocar a cor de marca inteira sem reescrever cada componente — e é o que faz o Do's/Don'ts (Etapa 6) ser aplicável de forma consistente.

### Etapa 4 — Tipografia e Hierarquia

- Tabular cada papel tipográfico com fonte, tamanho, peso, *line-height* e **quando usar** — nunca uma lista solta de tamanhos.
- Definir o **número máximo de níveis por tela/componente** (no CaféX, 3 por card) — isso é uma decisão de *disciplina visual*, não só de estilo, e é o que evita telas com 6 tamanhos de fonte diferentes brigando por atenção.
- Regra de truncamento (ellipsis, nº máximo de linhas) sempre que o layout for denso — detalhe pequeno que evita quebra de layout em produção.

### Etapa 5 — Especificação Exata de Componentes

Aqui vive o que fizemos na seção do carrossel: **toda medida em px, toda cor em hex, todo estado nomeado**. A regra prática é: se um desenvolvedor ou uma IA pudesse fazer duas escolhas diferentes lendo sua especificação, ela ainda não está pronta. Cada componente reutilizável precisa de:

1. Dimensões exatas por breakpoint (não "responsivo", e sim a tabela com os 3 valores).
2. Todos os estados: repouso, hover/pressed, desabilitado, carregando (skeleton), vazio/erro.
3. Regras de conteúdo: o que acontece quando o texto é maior que o espaço (truncamento), quando a imagem não existe (placeholder), quando a lista está vazia.

### Etapa 6 — Princípios, Do's/Don'ts e Anti-padrões

Segundo as análises mais recentes sobre por que interfaces geradas por IA "parecem IA", listar o que **não fazer** é tão importante quanto listar o que fazer — e deve ser específico, não genérico:

- Ruim: "evite design genérico".
- Bom (como já fizemos): "não use sombra em três camadas estilo Airbnb nos cards do carrossel — mantenha sombra única e rasa"; "não use preto puro, sempre `#2B2B26`".

Cada "Don't" deve ser algo que, se violado, é **detectável visualmente** por qualquer pessoa da equipe — isso é o que transforma a lista em critério de aceite, não em opinião.

### Etapa 7 — Prompting Consciente (como pedir para a IA gerar a partir do sistema)

Com o documento pronto, o prompt de geração de tela nunca deve dizer "deixe bonito" — a literatura recente é unânime nesse ponto. Um bom prompt de geração, apoiado no sistema, sempre inclui:

1. **Referência ao arquivo de design** (cole os tokens relevantes, não peça para a IA "lembrar").
2. **Um estilo nomeado** ("mobile-first, cards estilo Preply, sombra única e rasa") em vez de adjetivos vagos.
3. **Conteúdo real**, não placeholder ("Preciso de um agrônomo especialista em ferrugem próximo de Lavras", não "Lorem ipsum").
4. **Hex exatos e medidas exatas**, copiados do documento, não descritos de memória.
5. **Um componente por vez** quando o resultado começar a fugir do padrão — pedir a tela inteira de uma vez tende a fazer a IA "preencher lacunas" com genérico nas partes que você não especificou.

### Etapa 8 — Validação, Acessibilidade e Iteração

Gerar não é o fim — é o início de um ciclo de crítica:

- **Contraste**: checar AA (4.5:1) em todo par texto/fundo definido no sistema, não só nos principais.
- **Comparação com as referências da Etapa 1**: a tela gerada parece com a "tese" definida, ou regrediu para o genérico? Uma prática recomendada é rodar essa checagem *tela a tela*, não só olhando a primeira screenshot.
- **Auditoria de anti-padrões**: percorrer a lista de Don'ts da Etapa 6 como um checklist literal antes de aprovar qualquer tela.
- **Iteração é normal**: é esperado precisar de várias passagens até a tela "grudar" no sistema — o objetivo da documentação é reduzir quantas passagens são necessárias, não eliminá-las.

### Etapa 9 — Governança e Versionamento

- O documento de design é **fonte única da verdade** — se uma tela gerada diverge dele, a tela erra, não o documento (a menos que o documento seja atualizado deliberadamente).
- Toda mudança de token (ex.: trocar um hex) deve ser versionada e propagada, nunca corrigida "na tela" isoladamente — isso é o que evita o sistema derivar com o tempo.
- Novas seções (como fizemos com a Barra Inferior e a Aba de Turmas) devem seguir o mesmo nível de detalhe das seções originais — um documento de design perde valor rapidamente se partes novas forem menos rigorosas que as antigas.

## Checklist Rápido (para usar antes de gerar qualquer tela nova)

- [ ] Existem 3–5 referências nomeadas e o que evitar está explícito?
- [ ] Toda cor usada tem um papel semântico documentado, não só um hex solto?
- [ ] A hierarquia tipográfica tem regra de "máximo de níveis por tela"?
- [ ] O componente tem todos os estados (repouso, pressed, vazio, erro, loading) especificados?
- [ ] Existe uma lista de Don'ts específica e verificável a olho nu?
- [ ] O prompt de geração referencia o documento e usa conteúdo real, não placeholder?
- [ ] A tela gerada foi comparada com as referências originais antes de aprovar?
- [ ] Contraste e acessibilidade foram checados, não assumidos?

## Nota para a Futura Skill

Quando construirmos a skill que entrevista o usuário e gera um markdown equivalente, o roteiro de perguntas deve mapear diretamente as 9 etapas acima — por exemplo: "Cite 3 a 5 produtos cuja interface você admira" (Etapa 1), "Em 3 palavras, que sensação a marca deve passar?" (Etapa 1), "Qual cor de marca e qual papel funcional ela cumpre — ação, estrutura ou identidade?" (Etapas 2–3), "Que padrões visuais você quer evitar explicitamente?" (Etapa 6). O output da skill deve seguir a mesma anatomia de 11 blocos descrita acima, para manter compatibilidade com tudo que já documentamos para o CaféX.

## Leituras de Referência

- Design Tokens Community Group / W3C — especificação técnica de design tokens (2025.10)
- design.dev — guia de boas práticas de tokens (nomenclatura, tokens primitivos vs. semânticos, versionamento)
- designsystemproblems.com — boas práticas de documentação de tokens
- Artigos técnicos de 2025–2026 sobre por que interfaces geradas por IA parecem genéricas ("AI slop") e como estruturar prompts e sistemas de design para evitar isso (StyleKit, GenDesigns, bswen.com, superdesign.dev, dev.to)



*Todos os direitos reservados. O autor permite apenas a visualização dos documentos, sendo proibida qualquer utilização do mesmo, no todo ou em parte.*
