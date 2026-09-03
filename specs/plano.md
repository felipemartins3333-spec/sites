# specs/plano.md — Plano de implementação da landing page

Última atualização: 2026-09-03
Status: **plano aprovado para revisão. Nenhuma linha de código escrita.**

Marcadores: `[APROVADO]` · `[PROPOSTO]` · `[A DEFINIR]` · `[DEMO]` conteúdo fictício
de demonstração, autorizado pelo cliente em 2026-09-03, obrigatoriamente substituível
antes de qualquer publicação real.

---

## 0. Aviso de conflito com as especificações

Este plano **contradiz duas regras já registradas** e só existe porque o cliente
autorizou expressamente a exceção em 2026-09-03:

| Regra afetada | Onde está | O que muda |
|---|---|---|
| "Não invente informações comerciais, médicas ou técnicas sobre o produto" | `CLAUDE.md` | Passa a ser permitido criar conteúdo fictício, **desde que marcado `[DEMO]`** |
| "Nenhum número, benefício, depoimento ou credencial pode ser escrito sem origem confirmada" | `specs/site.md` §3 | Idem, com a mesma obrigação de marcação |

A exceção vale apenas para **conteúdo de demonstração**. A regra original volta a
valer integralmente no momento em que o cliente entregar as informações reais.
Nenhum texto `[DEMO]` pode ir ao ar sem substituição — ver §12, risco R-02.

Nenhuma outra decisão aprovada foi contrariada. Idioma, número de páginas,
público, stack e a proibição de copiar a referência continuam intactos.

---

## 1. Resumo da direção escolhida

**Marca de demonstração `[DEMO]`: Sollis** — plataforma de gestão inteligente de
energia. Mostra para onde vai cada watt, por circuito, em casa e na operação.

Por que esta categoria: ela sustenta as duas trilhas com peso real (uma casa e uma
empresa querem coisas genuinamente diferentes do mesmo produto), justifica a seção
de confiança e segurança exigida por `specs/site.md` §6.7 (dados de consumo são
dados pessoais sob LGPD), e abre espaço para a fotografia quente e ampla que
`specs/design.md` §10 pede. Trocar a categoria depois muda **conteúdo, não estrutura**.

**Posicionamento `[DEMO]`**
- Uma frase: "Veja para onde vai cada watt — e reduza a conta sem mudar de hábito."
- B2C: entender e cortar o desperdício da casa.
- B2B: provar consumo por unidade, com relatório auditável.

**Direção visual**: mantém "Clareza calorosa" de `specs/design.md` §1. A referência
entra como **ritmo** (blocos full-bleed alternando claro e escuro, uma ideia por
bloco, botões em pílula, chips que trocam conteúdo dentro da seção) e **não** como
aparência. O que nos separa dela, de propósito:

| Revolut | Sollis |
|---|---|
| Acromático, frio | Neutro quente com acento de cobre |
| Quase tudo centralizado | Assimetria editorial ancorada em 12 colunas |
| Renders 3D metálicos simbólicos | Produto em contexto de uso real |
| Cor só na fotografia | Cor de marca conduzindo a ação |

**Tipografia definida `[PROPOSTO]`** — pendência de `specs/design.md` §4 resolvida
dentro da autorização recebida:

| Papel | Família | Pesos | Por quê |
|---|---|---|---|
| Títulos | **Schibsted Grotesk** | 500, 600 | Grotesca de traço largo e formas abertas, licença OFL, auto-hospedável. Dá o traço largo que a referência tem sem imitar o desenho dela. |
| Corpo / interface | **Inter** | 400, 500 | Legibilidade comprovada em 15–17px e **numerais tabulares**, exigidos pelo spec para as telas de consumo. |

Duas famílias, quatro pesos — exatamente o teto de `specs/design.md` §4.
Alternativa descartada por ora: serifa contemporânea nos títulos. Ganha
personalidade, perde neutralidade no contexto B2B.

---

## 2. Estrutura completa e ordem das seções

O ritmo de fundos é o mecanismo de separação. Não há divisórias entre seções.

| # | Âncora | Seção | Fundo | Alinhamento |
|---|---|---|---|---|
| 1 | — | Header | transparente → `--paper-50` a 85% + blur | — |
| 2 | `#inicio` | Hero com bifurcação | foto + véu `--ink-900` 45% | esquerda |
| 3 | `#numeros` | Faixa de prova social | `--paper-50` | centro |
| 4 | `#como-funciona` | Como funciona (com tabs) | `--ink-900` | centro + mockup |
| 5 | `#para-voce` | Trilha B2C | `--paper-50` | texto à esquerda |
| 6 | `#para-empresas` | Trilha B2B + formulário | `--teal-100` | texto à direita |
| 7 | `#seguranca` | Confiança e segurança | `--ink-900` | texto à esquerda |
| 8 | `#duvidas` | Perguntas frequentes | `--paper-50` | coluna estreita |
| 9 | `#comecar` | CTA de fechamento | `--paper-100` | centro |
| 10 | — | Footer | `--ink-900` | grade densa |

Sequência de fundos: escuro → claro → escuro → claro → teal → escuro → claro →
claro → escuro. As duas claras seguidas (8 e 9) são intencionais: `--paper-100` é
meio tom mais fechado que `--paper-50` e marca a pausa antes do fechamento.

Alternância de lado exigida por `specs/design.md` §13: seção 5 texto à esquerda,
seção 6 texto à direita, seção 7 texto à esquerda. Cumprido.

**Decisão de arquitetura**: o controle segmentado B2C/B2B fica na **seção 4**, e não
em uma seção própria. Assim a página explica o produto uma vez e deixa o visitante
escolher a lente, exatamente como os chips da referência trocam conteúdo sem sair do
bloco. As seções 5 e 6 continuam existindo como aprofundamento de cada trilha. Isso
mantém as 10 seções aprovadas em `specs/site.md` §6, sem inventar uma décima primeira.

---

## 3. Detalhamento por seção

Cada bloco segue a hierarquia de três níveis herdada da referência:
**título → parágrafo de apoio → nota em micro-tipografia**, sem tamanhos no meio do caminho.

### 1. Header

**Objetivo** — dar orientação permanente e manter uma ação sempre à mão, sem roubar
a primeira dobra.

**Conteúdo** — logo Sollis (SVG inline, ~120×28); navegação por âncoras: Como
funciona · Para você · Para empresas · Segurança · Dúvidas; seletor PT/EN; um único
CTA (`Começar agora`).

**Imagem** — nenhuma. Só o logo em SVG.

**Componentes** — `skip-link`, `logo`, `nav-ancoras`, `seletor-idioma`, `botao-primario`, `botao-menu`.

**Interações** — transparente sobre o hero; ao passar de 80px de scroll, ganha fundo
`--paper-50` a 85%, `backdrop-filter: blur(12px)`, borda inferior de 1px e reduz a
altura de 88px para 64px, em 240ms. Scrollspy marca a âncora ativa com sublinhado de
2px em `--accent-700`, e também com `aria-current="true"` — nunca só por cor.

**Responsivo** — nav horizontal a partir de 900px; abaixo disso, botão de menu abre
drawer de tela cheia. O CTA sai do header no mobile e reaparece dentro do drawer.

### 2. Hero — bifurcação

**Objetivo** — dizer o que é em uma frase e separar os dois públicos no primeiro
gesto. É a seção que define se a trilha dupla funciona ou não.

**Conteúdo `[DEMO]`**
- H1: "Veja para onde vai cada watt"
- Apoio: "A Sollis mede o consumo circuito por circuito e mostra, em tempo real, onde a sua conta está sendo gasta. Em casa ou na operação."
- Par de CTAs: `Começar agora` (sólido, cobre, B2C) e `Falar com vendas` (contornado claro, B2B)
- Link terciário: `Ver como funciona ↓`
- Nota micro: "Instalação sem obra. Compatível com quadros monofásicos e trifásicos."

**Imagem** — `IMG-01`: fotografia horizontal, luz de fim de tarde, pessoa de costas
em ambiente doméstico amplo, espaço negativo à esquerda para o texto. Véu `--ink-900`
a 45%. Sobre ela flutua um cartão de interface em vidro translúcido com borda de 1px,
mostrando consumo por circuito — dados marcados como exemplo.

**Componentes** — `hero`, `par-cta`, `cartao-vidro`, `nota-legal`, `indicador-scroll`.

**Interações** — sem animação de entrada: o hero já nasce no estado final, para não
atrasar o LCP. O cartão de vidro sobe 8px em 600ms depois que a imagem decodifica, e
só isso.

**Responsivo** — desktop: texto em 6 colunas à esquerda, imagem sangrando à direita.
Tablet: texto em 8 de 8 colunas, imagem como fundo full-bleed com véu mais forte
(55%). Mobile: título → texto → CTAs empilhados em largura total → imagem abaixo,
altura limitada a 60vh. O hero nunca ultrapassa a altura da tela.

### 3. Faixa de prova social

**Objetivo** — dar lastro antes de pedir atenção. É a seção mais frágil do plano,
porque depende inteiramente de dados que não existem.

**Conteúdo `[DEMO]`** — uma linha de apoio ("Instalado em mais de 4.000 residências
e 120 operações") e três a cinco logos monocromáticos, cada um com legenda de uma
linha. **Todo número aqui é fictício e está sob a marcação `[DEMO]`.**

**Imagem** — `IMG-02a…e`: logos em SVG monocromático, altura óptica normalizada em
28px, cor `--ink-500`. Enquanto não houver clientes reais, usar formas neutras
explicitamente rotuladas como espaço reservado.

**Componentes** — `faixa-logos`, `legenda-micro`.

**Interações** — entrada escalonada de até 4 filhos, 60ms entre eles. Sem carrossel,
sem rotação automática.

**Responsivo** — desktop 5 colunas; tablet 3; mobile 2, com os logos em grade e não
em rolagem horizontal.

### 4. Como funciona — com controle segmentado

**Objetivo** — explicar o produto uma única vez e deixar o visitante escolher a lente.
É aqui que a trilha dupla vira mecânica de interface.

**Conteúdo `[DEMO]`** — título "Três passos, quarenta minutos"; controle segmentado
`Para você` / `Para sua empresa`; três passos que trocam conforme a aba:

| Passo | Para você | Para sua empresa |
|---|---|---|
| 1 | Instale o sensor no quadro | Mapeie as unidades |
| 2 | Conecte ao Wi-Fi da casa | Integre ao seu ERP |
| 3 | Veja o consumo por circuito | Receba o relatório auditável |

**Imagem** — `IMG-03a` e `IMG-03b`: mockup da interface em ângulo leve sobre fundo
escuro, com halo frio, sangrando para fora do quadro na borda inferior. Uma variante
por aba. Ambas mostram dados plausíveis e rotulados como exemplo.

**Componentes** — `controle-segmentado`, `lista-passos`, `mockup-produto`, `botao-primario`.

**Interações** — o controle segmentado é um `role="tablist"` real: setas ← → navegam,
Home/End vão aos extremos, `aria-selected` reflete o estado. A troca faz crossfade de
160ms na imagem e nos passos. **A altura do painel é travada pela maior das duas
variantes**, para que a troca não empurre a página (proteção de CLS).

**Responsivo** — desktop: passos em 3 colunas sob o mockup. Tablet: 3 colunas
estreitas. Mobile: o controle vira rolagem horizontal com máscara de gradiente
indicando que há mais, e os passos viram lista vertical numerada.

### 5. Trilha B2C

**Objetivo** — dar o benefício pessoal concreto e um caminho de autoatendimento.

**Conteúdo `[DEMO]`** — rótulo "Para você"; título "A conta deixa de ser surpresa";
parágrafo curto; três marcadores; CTA `Começar agora`; nota micro sobre compatibilidade.

**Imagem** — `IMG-04`: retrato vertical 4:5, alguém em casa com luz natural quente,
olhar fora da câmera, espaço negativo à direita. Tratamento uniforme: sombras
abertas, leve dessaturação nos verdes, sem HDR.

**Componentes** — `bloco-editorial`, `rotulo-trilha`, `lista-marcadores`, `botao-primario`, `nota-legal`.

**Interações** — entrada por `IntersectionObserver` a 15%, uma vez só. Desencontro
vertical de 48px entre a coluna de texto e a de imagem, criado no CSS e não na foto.

**Responsivo** — desktop: texto 5 colunas à esquerda, imagem 6 à direita. Tablet:
texto 4, imagem 4. Mobile: título → texto → imagem → botão, nesta ordem, sempre.

### 6. Trilha B2B + formulário

**Objetivo** — responder às perguntas de quem decide por uma empresa (escala,
integração, suporte, segurança) e capturar o contato comercial.

**Conteúdo `[DEMO]`** — rótulo "Para empresas"; título "Prove o consumo de cada
unidade"; quatro cards (Escala · Integração · Suporte · Conformidade); formulário
ancorado em `#contato` com nome, e-mail corporativo, empresa, número de unidades e
mensagem.

**Imagem** — `IMG-05`: horizontal 3:2, ambiente técnico ou operacional com luz
natural, sem pose de banco de imagens, sem aperto de mãos.

**Componentes** — `bloco-editorial` (espelhado), `grade-cards`, `formulario`,
`campo`, `mensagem-erro`, `mensagem-sucesso`, `botao-primario` (variante teal).

**Interações** — validação no `blur` e no envio, nunca a cada tecla. Erro descrito em
texto, associado por `aria-describedby`, com ícone além da cor. Sucesso anunciado em
`aria-live="polite"`. O destino do envio está `[A DEFINIR]` — até lá o formulário
valida e mostra o estado de sucesso sem enviar nada, e isso fica visível no código.

**Responsivo** — desktop: 4 cards em 2×2 ao lado do texto, formulário em 6 colunas.
Tablet: cards 2×2 em largura cheia. Mobile: cards viram lista vertical; campos em
largura total com alvo de toque de 48px.

### 7. Confiança e segurança

**Objetivo** — remover a última objeção. Vale para os dois públicos e é onde as duas
trilhas se cruzam, como manda `specs/site.md` §2.

**Conteúdo `[DEMO]`** — título "Seu consumo é seu"; parágrafo sobre criptografia em
trânsito e em repouso, retenção e exclusão; três selos de certificação; link para a
Política de Privacidade.

**Imagem** — `IMG-06`: **diagrama SVG inline**, não fotografia. Mostra o caminho do
dado do sensor até o painel. Desenhado por nós, em traço de 1.5px, duas cores no
máximo. Escolha deliberada: `specs/design.md` §11 proíbe o render 3D simbólico da
referência (o escudo metálico), então a confiança aqui é comunicada por explicação,
não por metáfora.

**Componentes** — `bloco-editorial`, `diagrama-svg`, `lista-selos`, `link-terciario`.

**Interações** — o diagrama tem entrada em `opacity` apenas, sem desenho progressivo
de traço — animar `stroke-dashoffset` sairia do par transform/opacity permitido.

**Responsivo** — o diagrama tem duas versões: horizontal no desktop e vertical no
mobile, trocadas por `<picture>` ou por CSS, nunca por rotação.

### 8. Perguntas frequentes

**Objetivo** — absorver as objeções que sobraram sem inchar as outras seções.

**Conteúdo `[DEMO]`** — sete perguntas cobrindo instalação, compatibilidade,
privacidade, preço, cancelamento, suporte e integração.

**Imagem** — nenhuma. Coluna estreita de texto, respiro em volta.

**Componentes** — `acordeao`, `item-acordeao`, `link-terciario`.

**Interações** — `<button>` real com `aria-expanded`; abre por `grid-template-rows:
0fr → 1fr` em 280ms; primeiro item aberto por padrão; abrir um não fecha os outros.
Ver risco R-04 sobre a propriedade animada.

**Responsivo** — coluna de 7 colunas no desktop, alinhada à esquerda; largura cheia
no mobile. Cada cabeçalho com no mínimo 56px de altura.

### 9. CTA de fechamento

**Objetivo** — repetir o par de ações. Sem novo argumento, sem nova informação.

**Conteúdo `[DEMO]`** — título curto e o mesmo par de CTAs do hero, com o mesmo
texto, como exige `specs/site.md` §8.

**Imagem** — nenhuma. Esta é a única seção centralizada da página, por decisão de
`specs/design.md` §13.

**Componentes** — `par-cta`.

**Interações** — entrada padrão. Nada além disso.

### 10. Footer

**Objetivo** — concentrar toda a densidade da página em um só lugar, como na
referência.

**Conteúdo** — logo; quatro colunas de links (Produto · Empresa · Legal · Suporte);
seletor de idioma; redes; endereço e CNPJ `[A DEFINIR]`; aviso de conteúdo de
demonstração enquanto durar a fase `[DEMO]`.

**Imagem** — logo em SVG e ícones sociais em SVG inline, do mesmo traço.

**Componentes** — `grade-footer`, `seletor-idioma`, `lista-links`, `texto-legal-micro`.

**Interações** — nenhuma além do foco visível.

**Responsivo** — 4 colunas no desktop, 2 no tablet, acordeão de 1 coluna no mobile.

---

## 4. Componentes necessários

Inventário fechado. Nada fora desta lista entra sem decisão registrada.

**Base** — `botao` (primário, secundário, terciário), `link-ancora`, `rotulo`,
`nota-legal`, `divisoria`, `container`, `secao`.

**Navegação** — `header`, `nav-ancoras`, `drawer`, `skip-link`, `seletor-idioma`, `scrollspy`.

**Conteúdo** — `bloco-editorial` (texto + imagem assimétrico, espelhável),
`grade-cards`, `card`, `lista-passos`, `lista-marcadores`, `faixa-logos`, `cartao-vidro`.

**Interativos** — `controle-segmentado` (tablist), `acordeao`, `formulario`, `campo`,
`mensagem-erro`, `mensagem-sucesso`.

**Mídia** — `figura-responsiva` (`<picture>` com AVIF/WebP), `mockup-produto`, `diagrama-svg`.

Total: 30 componentes. Todos com estado de foco visível próprio.

---

## 5. Interações e animações

Tudo abaixo respeita `specs/design.md` §12 e é desligado por
`@media (prefers-reduced-motion: reduce)`, que reduz transições a 1ms e entrega o
conteúdo já no estado final.

| Interação | Gatilho | Duração | Propriedades |
|---|---|---|---|
| Entrada de seção | `IntersectionObserver` a 15%, uma vez | 500ms `cubic-bezier(.22,1,.36,1)` | `opacity`, `translateY(16px→0)` |
| Escalonamento de filhos | mesma entrada, até 4 filhos | 60ms de atraso entre eles | idem |
| Compactação do header | scroll > 80px | 240ms | `height`, `background`, `backdrop-filter` |
| Scrollspy | `IntersectionObserver` por seção | imediato | classe + `aria-current` |
| Hover de botão | ponteiro | 160ms `ease-out` | `translateY(-2px)`, cor |
| Troca de aba | clique ou seta | 160ms | `opacity` (crossfade) |
| Acordeão | clique ou Enter/Espaço | 280ms | `grid-template-rows` |
| Drawer | botão de menu | 240ms | `transform: translateX` |
| Cartão do hero | após decodificar a imagem | 600ms | `opacity`, `translateY(8px→0)` |

**Proibido nesta página**, conforme spec: parallax pesado, sequestro de rolagem,
carrossel automático, contadores numéricos animados, texto letra a letra.

---

## 6. Estratégia por dispositivo

| | Celular < 640px | Tablet 640–1199px | Desktop ≥ 1200px |
|---|---|---|---|
| Grade | 4 colunas | 8 colunas | 12 colunas |
| Gutter | 24px | 32px | 48px |
| Padding de seção | 64–96px | 96–128px | 128–160px |
| Display (H1) | 40px | fluido | 88px |
| Navegação | drawer de tela cheia | horizontal a partir de 900px | horizontal |
| Blocos editoriais | coluna única, título → texto → imagem → botão | 2 colunas, sem desencontro vertical | 2 colunas com desencontro de 48px |
| Cards | lista vertical | 2 por linha | até 3 por linha |
| Controle segmentado | rolagem horizontal com máscara | inteiro | inteiro |
| CTAs | empilhados, largura total, 12px entre eles | lado a lado | lado a lado |

Breakpoints: 640 · 900 · 1200 · 1600. Testar em 320, 375, 414, 768, 1024, 1440, 1920.
Nenhum scroll horizontal a partir de 320px. Alvo de toque mínimo de 44×44px, e 48px
nos campos de formulário.

Tablet merece atenção porque é onde a assimetria costuma quebrar: entre 640 e 900px
o layout é de duas colunas **sem** o desencontro vertical, que só entra a partir de
900px. Sem isso, a imagem descola do texto e o bloco parece quebrado.

---

## 7. Estratégia de desempenho

Orçamento de `specs/site.md` §13: LCP < 2,0s · INP < 200ms · CLS < 0,05 ·
primeira dobra < 500KB · página < 1,5MB · < 30 requisições · JS próprio < 30KB.

**Orçamento previsto da primeira dobra**

| Recurso | Peso estimado |
|---|---|
| HTML com CSS crítico inline | ~14 KB |
| Hero em AVIF, 1600px de largura | ~180 KB |
| Duas fontes woff2 subsetadas (títulos 600 + corpo 400) | ~48 KB |
| JS inicial (header + drawer) | ~4 KB |
| **Total** | **~246 KB** — folga confortável sobre os 500 KB |

**Requisições previstas**: 1 HTML + 1 CSS + 2 JS + 4 fontes + 8 imagens = **16**.
Metade do teto.

**Práticas**
- CSS crítico da primeira dobra inline no `<head>`; o resto em um `main.css` único,
  carregado sem bloquear. Um arquivo só, não seis — sem build, cada `@import` custa
  uma requisição e uma cascata em série.
- Fontes: `preload` apenas das duas faces da primeira dobra; as outras duas com
  `font-display: swap`. Fallback com `size-adjust` e `ascent-override` calibrados
  para que a troca não mexa no layout — é aqui que a maioria dos CLS nasce.
- Imagens: `<picture>` com AVIF e WebP, `srcset` + `sizes`, `width`/`height` sempre
  declarados. Hero com `fetchpriority="high"` e sem `lazy`. Tudo abaixo da dobra com
  `loading="lazy"` e `decoding="async"`.
- `content-visibility: auto` com `contain-intrinsic-size` nas seções 6 a 10, com
  fallback silencioso onde não houver suporte.
- Zero terceiros na primeira dobra. Analytics `[A DEFINIR]`, carregado no `load`.
- Animações só em `transform` e `opacity`, com a exceção documentada do acordeão.
- Painel de abas com altura travada pela maior variante — CLS zero na troca.

---

## 8. Estratégia de acessibilidade

Meta: **WCAG 2.2 AA**.

**Estrutura** — um `<h1>` por página; hierarquia sem saltos; landmarks `header`,
`nav`, `main`, `section` com `aria-labelledby`, `footer`; `skip-link` como primeiro
elemento focável.

**Teclado** — ordem de foco igual à ordem visual; anel de foco de 3px com offset de
2px, na cor de acento sobre claro e `--paper-50` sobre escuro; drawer com foco preso
e fechamento por `Esc`, devolvendo o foco ao botão que o abriu; abas com
`roving tabindex` e navegação por setas; acordeão operável por Enter e Espaço.

**Contraste** — todos os pares verificados por cálculo antes de entrar no CSS.
Resultado da verificação em §12, risco R-01: **um par reprova hoje**.

**Formulário** — `<label>` real e visível (nunca só `placeholder`); erros em texto,
associados por `aria-describedby`, com ícone além da cor; sucesso em `aria-live="polite"`.

**Conteúdo** — `alt` significativo em toda imagem informativa e `alt=""` nas
decorativas; nunca cor como único portador de significado (a aba ativa tem
`aria-selected` e peso tipográfico diferente, não só cor); zoom até 200% sem perda de
função; `prefers-reduced-motion` desliga todas as entradas.

**Verificação antes de entregar** — navegação inteira só com teclado; leitura com
leitor de tela em uma seção de cada tipo; zoom 200% e 400%; simulação de daltonismo
nas seções que usam cobre e teal juntos.

---

## 9. Organização dos arquivos

```
index.html                    PT-BR, idioma padrão
privacidade.html
termos.html
en/
  index.html                  EN
  privacy.html
  terms.html
assets/
  css/
    main.css                  arquivo único, organizado por @layer
  js/
    main.js                   ponto de entrada, importa os módulos
    header.js                 compactação + scrollspy + drawer
    tabs.js                   controle segmentado
    accordion.js              FAQ
    reveal.js                 entradas por IntersectionObserver
    form.js                   validação do formulário B2B
  fonts/
    schibsted-grotesk-500.woff2   schibsted-grotesk-600.woff2
    inter-400.woff2               inter-500.woff2
  img/
    hero/  trilhas/  produto/  logos/  og/
imagens.md                    manifesto de imagens
specs/
  site.md  design.md  plano.md  conteudo.md
referências - site/
memoria.md
CLAUDE.md
sitemap.xml
robots.txt
site.webmanifest
```

**Ordem das camadas em `main.css`**:
`@layer reset, tokens, base, layout, components, sections, utilities;`
Declarada uma vez no topo. Isso resolve especificidade sem `!important` e sem
seletor aninhado profundo.

**Por que um CSS só e seis módulos JS**: CSS em série bloqueia a renderização, então
vale concatenar à mão. JS em módulos carrega em paralelo e cada arquivo é pequeno
— a legibilidade compensa as requisições, e ainda sobra folga no orçamento.

---

## 10. Conteúdo necessário — inventário

| Seção | Itens | Origem |
|---|---|---|
| Hero | H1, apoio, 2 CTAs, link, nota | `[DEMO]` |
| Prova social | 1 linha, 3–5 logos + legendas | `[DEMO]` — **exige substituição** |
| Como funciona | título, 2 rótulos de aba, 6 passos | `[DEMO]` |
| B2C | rótulo, título, parágrafo, 3 marcadores, CTA, nota | `[DEMO]` |
| B2B | rótulo, título, 4 cards, 5 campos, CTA | `[DEMO]` |
| Segurança | título, parágrafo, 3 selos, link | `[DEMO]` — **exige substituição** |
| FAQ | 7 pares pergunta/resposta | `[DEMO]` |
| Fechamento | título + par de CTAs repetidos | `[DEMO]` |
| Footer | ~18 links, endereço, CNPJ, legal | `[A DEFINIR]` |
| SEO | title, description, OG, dados estruturados | `[DEMO]` |

Tudo isso em duas línguas. O texto em EN é adaptação, não tradução literal.

**O texto já está escrito.** As duas versões completas — headlines, parágrafos,
rótulos, marcadores, mensagens de erro do formulário, FAQ, rodapé, `alt` de cada
imagem e metadados de SEO — estão em `specs/conteudo.md`, marcadas `[DEMO]`.
Preço e dados cadastrais ficaram `[A DEFINIR]` de propósito: são consequentes demais
para inventar, mesmo em demonstração.

---

## 11. Ordem de implementação

Cada etapa termina em algo verificável. Nada começa antes da anterior fechar.

1. **Fundação** — `@layer`, reset, tokens de cor/tipo/espaço/raio, escala fluida com
   `clamp()`, fontes auto-hospedadas com fallback calibrado. Entregável: uma página
   de amostra dos tokens.
2. **Componentes base** — botão nas três variantes, campo, card, chip, rótulo, nota.
   Todos com foco visível. Entregável: uma página de componentes.
3. **Casca** — header, drawer, footer, skip-link, seletor de idioma. Já com teclado
   funcionando.
4. **Hero** — a seção mais cara em desempenho. Medir LCP aqui, antes de seguir.
5. **Seções 3 a 9**, na ordem da página, cada uma revisada em 320, 768 e 1440 antes
   da próxima.
6. **Interações** — abas, acordeão, scrollspy, entradas, validação do formulário.
7. **Passe de acessibilidade** — teclado, leitor de tela, zoom, contraste.
8. **Passe de desempenho** — imagens em AVIF/WebP, CSS crítico, `preload`, medição
   real contra o orçamento.
9. **SEO e legais** — meta, OG, dados estruturados, `hreflang`, sitemap, robots,
   Privacidade e Termos.
10. **Versão EN** — página irmã completa. Publicar as duas juntas, nunca uma só.
11. **QA final** — 320 → 1920, os dois idiomas, teclado e leitor de tela.

Etapas 1 a 4 são o caminho crítico: se a fundação estiver errada, tudo depois herda o erro.

---

## 12. Riscos e inconsistências

**R-01 · A cor de acento reprova em contraste. Verificado por cálculo.**
`--accent-600` `#C2551F` sobre `--paper-50` dá **4,26:1** e sobre `--paper-100`,
**3,87:1**. O mínimo para texto normal é 4,5:1. Como esse token é o fundo do botão
primário com texto claro, **todo botão primário em bloco claro reprova hoje**.

Correção proposta: criar `--accent-700: #AD4A1A`, mesmo matiz (19,9°), que dá
**5,21:1** sobre `--paper-50` e **4,74:1** sobre `--paper-100`. Passa nos dois.
`--accent-600` continua válido para texto grande, bordas, ícones e uso decorativo,
onde o mínimo é 3:1. Isso altera `specs/design.md` §2 e §3 e **precisa da sua
aprovação** antes de virar CSS.

Os demais pares foram verificados e passam: `--ink-900` sobre `--paper-50` 16,98:1 ·
`--ink-500` sobre `--paper-50` 6,61:1 · `#A9B4C2` sobre `--ink-900` 8,64:1 ·
`--teal-700` sobre `--paper-50` 7,07:1 · `--accent-500` com texto `--ink-900` 5,38:1 ·
`--success` 4,99:1 · `--error` 6,12:1.

**R-02 · Conteúdo fictício vazando para produção.** É o risco mais caro do projeto:
números e certificações inventados em um site no ar são um problema jurídico, não
estético. Mitigação: todo texto `[DEMO]` recebe o atributo `data-demo` no HTML, o
footer exibe um aviso enquanto durar a fase, e a etapa 11 do QA tem um item
bloqueante — `grep data-demo` precisa voltar vazio antes de publicar.

**R-03 · Duas páginas irmãs saem de sincronia.** Sem build, PT e EN são dois arquivos
independentes e toda edição é feita duas vezes. Mitigação: uma tabela de paridade em
`imagens.md` e um item de QA que compara a contagem de seções e de CTAs entre as
duas versões. Aceitamos o custo porque a alternativa (trocar idioma por JavaScript)
prejudica SEO e foi descartada.

**R-04 · O acordeão contradiz a regra de animação.** `specs/design.md` §12 diz
"somente `transform` e `opacity`", e na mesma seção manda abrir o acordeão por
`height`/`grid-template-rows`. São instruções incompatíveis. Proposta: registrar
`grid-template-rows` como a **única exceção documentada**, porque é o único jeito de
animar altura automática sem JavaScript medindo o conteúdo. Impacto de desempenho
contido: um item de FAQ é uma área pequena.

**R-05 · O véu sobre a fotografia é verificado no mockup, não na foto final.**
`specs/design.md` §10 já alerta. Mitigação: fechar o texto do hero só depois da
imagem definitiva e medir o contraste na região exata onde o texto cai, não na média
da imagem.

**R-06 · A escolha da categoria do produto é minha, não sua.** Toda a camada de
conteúdo assume gestão de energia. Se o seu negócio for outro, a estrutura, os
componentes e o sistema visual continuam válidos — só o texto e as imagens mudam.
Mas quanto mais tarde essa troca acontecer, mais caro fica refazer a direção
fotográfica.

**R-07 · Quatro arquivos de fonte contra o orçamento.** 4 faces × ~24KB = ~96KB, e só
duas entram na primeira dobra. Cabe, mas some com a folga se depois quisermos um
terceiro peso. Regra: nenhum peso novo sem remover outro.

**R-08 · `backdrop-filter` no header.** Sem suporte, o fundo translúcido deixa o texto
sobre a foto ilegível. Mitigação: `@supports` com fundo sólido `--paper-50` a 96%
como alternativa.

**R-09 · Pastas citadas que não existem.** O pedido mencionou `imagens.md`,
`referencias - sites` e `imagens-site`. No repositório existe apenas
`referências - site/`. O manifesto `imagens.md` está sendo criado agora; a pasta de
imagens será `assets/img/`, e não `imagens-site/`, para ficar coerente com a
estrutura já aprovada em `specs/site.md` §10.

---

## 13. SEO on-page

Escopo de `specs/site.md` §14. Sem terceiros, sem script de rastreamento na primeira dobra.

**Por página** — `<title>` até 60 caracteres, `description` até 155, canônica
absoluta, `og:title`, `og:description`, `og:image` (1200×630), `og:locale`,
`twitter:card="summary_large_image"`. Textos finais em `specs/conteudo.md` §1.

**Bilíngue** — `hreflang` cruzado nas duas páginas mais `x-default` apontando para a
PT-BR. Cada página se autorreferencia no `hreflang`, senão o Google ignora o par.
Sem redirecionamento automático por idioma do navegador (`specs/site.md` §4).

**Dados estruturados** — dois blocos `application/ld+json`: um `Organization` e um
`FAQPage` alimentado pelas mesmas sete perguntas visíveis na seção 8. Texto idêntico
ao da página: marcação que descreve conteúdo que o usuário não vê é penalizada.

**Arquivos de apoio** — `sitemap.xml` com as 6 URLs e `hreflang` por entrada;
`robots.txt` apontando para o sitemap; `site.webmanifest` com ícones.

**Semântica que o SEO herda de graça** — um `<h1>` por página, hierarquia sem saltos,
`alt` real em toda imagem informativa, âncoras com texto descritivo (nunca "clique
aqui"). Isso já está exigido pela acessibilidade; o ganho de busca é subproduto.

**Enquanto durar a fase `[DEMO]`** — `robots.txt` com `Disallow: /` e
`<meta name="robots" content="noindex">` nas duas páginas. Conteúdo fictício indexado
é o mesmo risco R-02 por outra porta. As duas linhas saem no commit que substitui o
conteúdo, não antes.

---

## 14. QA — o que precisa passar antes de publicar

Lista de verificação da etapa 11. Os itens marcados **bloqueiam a publicação**.

**Bloqueantes**
- [ ] **`grep -r data-demo` volta vazio.** Nenhum conteúdo de demonstração no ar.
- [ ] Nenhum nome de norma real (ISO, SOC, PCI) sem o certificado em mãos.
- [ ] `noindex` e `Disallow: /` removidos — e removidos só agora.
- [ ] Preço, CNPJ, razão social e endereço preenchidos ou ausentes, nunca inventados.
- [ ] Contraste verificado por cálculo em todos os pares, inclusive o texto sobre a
      foto do hero, medido na região exata onde ele cai.

**Funcional**
- [ ] Navegação inteira só com teclado, do skip-link ao último link do rodapé.
- [ ] Drawer prende o foco, fecha com `Esc` e devolve o foco ao botão que o abriu.
- [ ] Abas navegam por ← → e Home/End, com `aria-selected` correto.
- [ ] Acordeão opera por Enter e Espaço; abrir um não fecha os outros.
- [ ] Formulário: erro descrito em texto, ligado por `aria-describedby`, com ícone
      além da cor; sucesso anunciado em `aria-live`.
- [ ] Scrollspy marca a seção ativa com `aria-current`, não só com cor.

**Responsivo** — sem scroll horizontal e sem sobreposição em 320, 375, 414, 768,
1024, 1440 e 1920. Alvo de toque de 44px, e 48px nos campos.

**Desempenho** — medição real, não estimativa: LCP < 2,0s, INP < 200ms, CLS < 0,05,
primeira dobra < 500KB, página < 1,5MB, menos de 30 requisições, JS próprio < 30KB.

**Acessibilidade** — leitor de tela em uma seção de cada tipo; zoom em 200% e 400%;
simulação de daltonismo nas seções que usam cobre e teal juntos;
`prefers-reduced-motion` desliga todas as entradas.

**Paridade PT/EN** — checklist de `specs/conteudo.md` §12.

---

## 15. O que ainda falta

**Só você pode responder**
1. Categoria e nome reais do produto — ou o aval para seguir com Sollis como demonstração.
2. Objetivo de negócio e métrica de sucesso.
3. Destino do formulário B2B (e-mail, CRM ou serviço externo).
4. Domínio, hospedagem e ferramenta de analytics.
5. Existe manual de marca, logo ou paleta? Se existir, ele substitui `specs/design.md` §2.
6. Texto das páginas legais.
7. Origem das fotografias: banco de imagens, produção própria ou geração.

**Preciso da sua aprovação**
8. A correção de contraste do risco R-01.
9. A exceção de animação do risco R-04.
10. A tipografia definida em §1 (Schibsted Grotesk + Inter).
11. O aviso de conteúdo de demonstração no footer durante a fase `[DEMO]`.

**Eu resolvo, mas depende de 1 a 7**
12. Texto final em PT-BR e a adaptação para EN.
13. As oito imagens do manifesto em `imagens.md`.
14. Verificação de marca registrada do nome escolhido.
