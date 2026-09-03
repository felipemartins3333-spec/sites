# specs/design.md — Fonte de verdade visual

Última atualização: 2026-09-03

Marcadores: `[APROVADO]` decidido · `[PROPOSTO]` aguardando confirmação · `[A DEFINIR]` sem informação.

---

## 0. Análise da referência

Material analisado em `referências - site/`:
- `revolut.md` — arquivo com o link: https://www.revolut.com/pt-BR/
- `screencapture-revolut-pt-BR-2026-09-03-18_43_20.png` — captura da página
  inteira, 1366 × 6157 px, versão PT-BR. Analisada em quatro faixas.

### O que foi observado

**Estrutura e ritmo**
Página construída como uma sequência de blocos full-bleed empilhados, cada um
ocupando toda a largura da viewport e uma altura generosa. O ritmo vem da
**alternância entre blocos claros e escuros** — céu claro, branco, preto,
fotografia escura, branco, preto, branco, footer escuro. Nenhuma borda ou
divisória: a mudança de fundo é o separador. Blocos de respiro em branco puro,
com pouquíssimo conteúdo, funcionam como pausas entre os blocos densos.

**Hierarquia**
Contraste de escala muito agressivo: headline enorme (~72px no hero, ~52px nas
seções) contra corpo de texto pequeno (~15–16px), sem tamanhos intermediários.
Cada bloco carrega uma única mensagem, um parágrafo curto de apoio e um botão.
Onde há obrigação legal, aparece um terceiro nível: uma nota em ~12px, cinza de
baixo contraste, logo abaixo do parágrafo — a densidade regulatória é sempre
empurrada para o menor tamanho disponível.

Alinhamento: o hero é alinhado à esquerda, a maior parte das seções é
centralizada, e uma seção editorial ("O porto seguro do seu dinheiro") quebra o
padrão com texto à esquerda em ~5 colunas e o objeto à direita. Essa quebra é o
único respiro de assimetria da página.

**Tipografia**
Sans-serif geométrica de traço largo, com kerning apertado nos títulos e peso
regular ou medium — não bold. Títulos em duas linhas, quebra controlada.
Corpo de texto pequeno, cinza de baixo contraste sobre fundo escuro.
O rodapé usa um corpo minúsculo para um volume enorme de texto legal.

**Cor**
Paleta essencialmente acromática: preto, branco e cinza. A cor vem quase toda
da fotografia (azul do céu, laranja do pôr do sol). Botões sólidos de alto
contraste — pretos sobre claro, brancos sobre escuro. Nenhuma cor de marca
compete com a imagem.

**Espaçamento**
Padding vertical muito alto dentro de cada bloco. O conteúdo textual ocupa uma
coluna estreita e centralizada, mesmo em telas largas — muita margem lateral
vazia. A densidade só aumenta no rodapé, com grade de links em várias colunas.

**Tratamento das imagens**
Duas linguagens convivendo: fotografia editorial ampla e atmosférica
(pessoa em ambiente aberto, céu, oceano, pôr do sol) e renders 3D do produto
sobre fundo preto, com acabamento metálico, reflexos e profundidade de campo.
O produto aparece em ângulo e sangra para fora do quadro. Cartões de interface
flutuam sobre a fotografia como sobreposições.

**Interface e detalhes**
Botões em formato de pílula, altura contida (~48px), texto curto de 2 a 3
palavras, peso medium. Em bloco claro são pretos com texto branco; em bloco
escuro, brancos com texto preto — sempre sólidos, nunca contornados.

Chips de filtro aparecem em duas posições: sobre a imagem do produto ("Cartões
físicos" / "Cartões virtuais") e abaixo dela ("Aventura" / "Casamento" /
"Mudança"). São pílulas contornadas em branco translúcido, com a ativa
preenchida em branco sólido. Servem para trocar o conteúdo sem sair da seção.

Cantos arredondados em todos os cartões e mockups. Cartões de interface
flutuando sobre a foto usam vidro translúcido com borda de 1px. Nenhuma sombra
pesada: a separação vem do contraste de fundo. O header não aparece na captura
— provavelmente transparente sobre o hero.

**Tom**
Aspiracional e confiante, com frases curtas e diretas. Nada de jargão técnico
na superfície; toda a complexidade regulatória é empurrada para o rodapé.

### O que herdamos e o que descartamos

**Herdamos como direção** (estrutura e atmosfera):
- Blocos full-bleed alternando claro/escuro como mecanismo de ritmo.
- Uma mensagem, um parágrafo e um CTA por bloco.
- Contraste de escala agressivo entre título e corpo.
- Hierarquia de três níveis de texto: título, parágrafo de apoio e nota legal
  em micro-tipografia — nunca no meio do caminho.
- Botões em pílula e controle segmentado para trocar conteúdo dentro da seção.
- Fotografia ampla e atmosférica combinada com tratamento tridimensional do produto.
- Densidade concentrada apenas no rodapé.

**Descartamos** (para a identidade ser original):
- Paleta acromática pura — vamos ter cor de marca própria.
- Centralização quase total — usaremos composição assimétrica editorial.
- Qualquer texto, nome, logo, imagem ou ícone da referência.
- Estética financeira metálica escura como assinatura visual.
- Layouts replicados seção a seção.

---

## 1. Direção visual

`[PROPOSTO]` — **"Clareza calorosa"**: precisão de produto com temperatura humana.

Três princípios que decidem qualquer dúvida futura:

1. **Uma ideia por tela.** Cada bloco defende uma única afirmação. Se precisa de
   duas, são dois blocos.
2. **O calor vem do neutro, o foco vem do acento.** Fundos são neutros quentes,
   nunca branco puro nem preto puro. A cor de acento aparece pouco e sempre
   marca a próxima ação.
3. **Assimetria com eixo.** A composição é editorial e desalinhada de propósito,
   mas sempre ancorada na mesma grade de 12 colunas. Nada flutua sem eixo.

Diferença deliberada em relação à referência: onde ela é fria, centralizada e
acromática, nós somos quentes, assimétricos e cromaticamente ancorados.

## 2. Paleta

Todos os valores abaixo são `[PROPOSTO]` e viram `[APROVADO]` quando a marca for definida.
Se já existir manual de marca, ele substitui esta seção inteira.

**Principal**

| Token | Hex | Uso |
|---|---|---|
| `--ink-900` | `#0F1621` | Fundo escuro, texto sobre claro |
| `--ink-700` | `#232F3E` | Superfície escura elevada |
| `--ink-500` | `#4A5A6D` | Texto secundário sobre claro |
| `--paper-50` | `#FAF7F2` | Fundo claro padrão (off-white quente) |
| `--paper-100` | `#F1ECE4` | Superfície clara alternativa |
| `--paper-300` | `#DDD5C9` | Bordas e divisórias sobre claro |

**Acento** — a cor da ação

| Token | Hex | Uso |
|---|---|---|
| `--accent-600` | `#C2551F` | Botão primário, estados ativos |
| `--accent-500` | `#E0692C` | Hover do primário, detalhes |
| `--accent-100` | `#FBE7D8` | Fundo de destaque suave, badges |

**Secundária** — apoio e diferenciação de trilha

| Token | Hex | Uso |
|---|---|---|
| `--teal-700` | `#155E5A` | Trilha B2B, gráficos, ícones |
| `--teal-100` | `#DCEDEB` | Fundo de blocos B2B |

**Semânticas**

| Token | Hex | Uso |
|---|---|---|
| `--success` | `#1E7A4B` | Confirmação de formulário |
| `--error` | `#B3261E` | Erro de validação |

**Regras de cor**
- Nunca `#000000` nem `#FFFFFF` como fundo ou texto.
- Acento é a cor da ação: se um elemento não é clicável, não usa `--accent-600` como fundo.
- Máximo de duas famílias cromáticas visíveis por bloco (neutro + uma cor).
- A distinção B2C/B2B é feita por acento (`--accent`) versus secundária (`--teal`),
  mas **nunca só por cor** — sempre acompanhada de rótulo textual.
- Todo par de cores precisa passar 4.5:1 antes de entrar no CSS.

## 3. Fundo, texto, botões e detalhes

| Contexto | Fundo | Texto principal | Texto secundário | Botão primário | Botão secundário |
|---|---|---|---|---|---|
| Bloco claro | `--paper-50` | `--ink-900` | `--ink-500` | fundo `--accent-600`, texto `--paper-50` | contorno `--ink-900`, texto `--ink-900` |
| Bloco escuro | `--ink-900` | `--paper-50` | `#A9B4C2` | fundo `--accent-500`, texto `--ink-900` | contorno `--paper-50`, texto `--paper-50` |
| Bloco B2B | `--teal-100` | `--ink-900` | `--ink-500` | fundo `--teal-700`, texto `--paper-50` | contorno `--teal-700`, texto `--teal-700` |

Detalhes: divisórias sempre com `--paper-300` (ou `--paper-50` a 12% no escuro),
espessura `1px`. Nada de linhas duplas ou ornamentos.

## 4. Tipografia

`[A DEFINIR]` — pendente de aprovação. Recomendação abaixo.

**Recomendação `[PROPOSTO]`**: duas famílias, ambas auto-hospedadas em `woff2`.

| Papel | Família | Pesos | Observação |
|---|---|---|---|
| Títulos | Geral sem-serifa de traço largo e formas abertas | 500, 600 | Nunca 700+. Peso alto engrossa demais em corpos grandes. |
| Corpo / interface | Sem-serifa neutra com boa legibilidade em 15–17px | 400, 500 | Precisa ter numerais tabulares. |

Alternativa `[PROPOSTO]`: uma serifa contemporânea nos títulos com sem-serifa no
corpo — dá mais personalidade e afasta mais da referência, ao custo de um pouco
de neutralidade em contexto B2B.

**Regras tipográficas**
- Máximo de duas famílias e quatro pesos no site inteiro.
- Títulos com `letter-spacing` negativo (`-0.02em` a `-0.03em`); corpo em `0`.
- Altura de linha: `1.05`–`1.15` em títulos grandes, `1.6` em corpo.
- Medida de linha do corpo entre 60 e 75 caracteres (`max-width: 65ch`).
- Sem texto em caixa alta longo. Caixa alta só em rótulos curtos, com `letter-spacing: 0.08em`.
- Sem itálico decorativo. Sem sublinhado, exceto em links dentro de parágrafo.
- Números e unidades nunca separados do valor por quebra de linha.

## 5. Escala tipográfica

Fluida com `clamp()`, razão ~1.25 no mobile e ~1.333 no desktop.

| Token | Mobile | Desktop | Uso |
|---|---|---|---|
| `--fs-display` | 40px | 88px | H1 do hero, uma ocorrência por página |
| `--fs-h1` | 32px | 60px | Título de seção |
| `--fs-h2` | 26px | 40px | Subtítulo de seção |
| `--fs-h3` | 21px | 26px | Título de card |
| `--fs-lead` | 17px | 20px | Parágrafo de apoio sob o título |
| `--fs-body` | 16px | 17px | Corpo padrão |
| `--fs-small` | 14px | 15px | Legenda, nota |
| `--fs-micro` | 12px | 13px | Rótulo, texto legal do rodapé |

Exemplo de implementação: `--fs-display: clamp(2.5rem, 1.2rem + 5.6vw, 5.5rem);`

Regra herdada da referência: **salto grande entre display e corpo**, sem
tamanhos intermediários competindo dentro do mesmo bloco.

## 6. Espaçamentos

Escala base de `4px`. Usar somente estes degraus:

`4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96 · 128 · 160`

| Token | Valor | Uso |
|---|---|---|
| `--space-2` … `--space-4` | 8–16px | Dentro de componentes |
| `--space-6` | 24px | Gutter mobile, gap de grid |
| `--space-8` | 32px | Separação entre blocos de texto |
| `--space-12` | 48px | Gutter desktop |
| `--space-16` / `--space-24` | 64 / 96px | Padding vertical de seção no mobile |
| `--space-32` / `--space-40` | 128 / 160px | Padding vertical de seção no desktop |

- Container: `max-width: 1200px`, centralizado.
- Grade de 12 colunas no desktop, 4 no mobile, gutter `24px`.
- Espaço vertical entre seções é sempre maior que qualquer espaço interno da seção.
- Blocos de imagem podem sangrar até a borda; texto nunca.

## 7. Bordas e raios

| Token | Valor | Uso |
|---|---|---|
| `--radius-sm` | 8px | Inputs, chips, badges |
| `--radius-md` | 16px | Cards, blocos de conteúdo |
| `--radius-lg` | 28px | Painéis grandes, mockups, imagens em card |
| `--radius-pill` | 999px | Botões, controle segmentado |

- Bordas de `1px` apenas; sem bordas grossas decorativas.
- Sombras usadas com muita moderação e sempre difusas e frias:
  `0 12px 32px -12px rgb(15 22 33 / 0.18)`. Em blocos escuros, sem sombra —
  a separação vem do contraste de fundo.

## 8. Botões

Formato pílula (`--radius-pill`) em todos os casos.

| Variante | Altura | Padding | Aparência |
|---|---|---|---|
| Primário | 52px (44px mobile) | `0 28px` | Fundo sólido de acento, texto claro |
| Secundário | 52px | `0 28px` | Contorno `1.5px`, fundo transparente |
| Terciário / link | — | `0` | Só texto + seta, sublinhado no hover |

- Peso do texto 500, tamanho `--fs-body`, sem caixa alta.
- Hover: escurece 8% e sobe `2px` (`transform: translateY(-2px)`), `160ms ease-out`.
- Foco: anel de `3px` com offset de `2px`, na cor de acento (ou `--paper-50` no escuro).
- Ativo: volta à posição original, sem sombra.
- Desabilitado: opacidade `0.5`, cursor `not-allowed`, sem hover.
- Máximo de dois botões lado a lado. No mobile eles empilham em largura total.
- Texto sempre no infinitivo ou imperativo curto — no máximo 3 palavras.

## 9. Cards

- Fundo `--paper-100` sobre bloco claro; `--ink-700` sobre bloco escuro.
- Raio `--radius-md`, borda `1px` `--paper-300` (ou nenhuma no escuro).
- Padding interno `--space-8` no mobile e `--space-12` no desktop.
- Estrutura fixa: ícone ou número → título (`--fs-h3`) → texto (`--fs-body`) → link opcional.
- Todos os cards de uma mesma linha têm a mesma altura (grid, não flex com alturas soltas).
- Cards não clicáveis inteiros não recebem hover. Cards clicáveis sobem `2px` e clareiam o fundo.
- Sem gradiente, sem borda colorida à esquerda, sem ícone dentro de círculo colorido.

## 10. Fotografia

Direção `[PROPOSTO]`; origem das imagens `[A DEFINIR]`.

- Fotografia ampla, com ar, luz natural e temperatura quente — coerente com `--paper-50`.
- Pessoas reais em contexto de uso, olhar fora da câmera, sem pose de banco de imagens.
- Enquadramento com espaço negativo intencional do lado onde o texto vai entrar.
- Um assunto por imagem. Sem colagens, sem montagens, sem molduras dentro de molduras.
- Tratamento uniforme: leve dessaturação nos verdes, sombras abertas, sem HDR.
- Sobreposição escura (`--ink-900` a 35–55%) sempre que houver texto sobre foto,
  e o contraste do texto precisa ser verificado na imagem final, não no mockup.
- Proibido: fotos com marcas visíveis de terceiros, imagens da referência,
  stock genérico de aperto de mãos, gráficos de bolsa, e qualquer imagem
  gerada que insinue pessoa real identificável.

## 11. Tratamento do produto

- O produto aparece em **contexto de uso**, não flutuando isolado.
- Mockups de interface renderizados em ângulo leve (não frontal chapado),
  cantos `--radius-lg`, sangrando para fora do quadro quando estiverem na borda.
- Sobre bloco escuro, o produto ganha halo suave de luz fria; sobre bloco claro,
  sombra difusa longa e discreta.
- Interfaces mostradas devem exibir **dados plausíveis e marcados como exemplo**.
  Nunca números de performance, preços ou métricas inventados — `[A DEFINIR]`
  até o cliente fornecer dados reais.
- Descartado da referência: acabamento metálico e renders 3D de objetos
  simbólicos (escudos, moedas). Não faz parte desta identidade.

## 12. Movimento e animações

- Entrada por seção: `opacity 0 → 1` + `translateY(16px → 0)`, `500ms`, `cubic-bezier(0.22, 1, 0.36, 1)`,
  disparada por `IntersectionObserver` a 15% de visibilidade, uma única vez.
- Escalonamento de até 4 filhos com `60ms` de atraso entre eles. Nunca mais que isso.
- Micro-interações (hover, foco, tabs): `160ms ease-out`.
- Header compacta em `240ms` ao passar da primeira dobra.
- Acordeão abre por `height`/`grid-template-rows`, `280ms`.
- Somente `transform` e `opacity` são animados.
- Proibido: parallax pesado, animação de scroll que sequestra a rolagem,
  carrossel automático, contadores numéricos animados, texto que aparece letra a letra.
- `@media (prefers-reduced-motion: reduce)` desliga todas as animações de entrada
  e reduz transições a `1ms` — o conteúdo aparece imediatamente no estado final.

## 13. Regras para desktop

- Grade de 12 colunas, container `1200px`, gutter `48px`.
- Composição assimétrica: texto em 5 ou 6 colunas, imagem em 6, com desencontro
  vertical proposital entre as duas. Alternar o lado a cada seção.
- Padding vertical de seção: `128–160px`.
- Máximo de 3 cards por linha.
- Header fixo com fundo translúcido e `backdrop-filter` após o scroll.
- Não centralizar blocos longos de texto: centralização reservada ao CTA de fechamento.

## 14. Regras para celular

- Coluna única, gutter `24px`, padding vertical de seção `64–96px`.
- Ordem sempre: título → texto → imagem → botão. A imagem nunca vem antes do título.
- Botões primários em largura total, empilhados, com `12px` entre eles.
- Menu em drawer de tela cheia, com foco preso e fechamento por `Esc`.
- Escala display reduzida para `40px` — o hero não pode ocupar mais que a tela.
- Controle segmentado vira rolagem horizontal, com indicação visual de que há mais.
- Nada de hover como único caminho para uma informação.
- Cards viram lista vertical; sem carrossel.

## 15. Elementos a evitar

- Branco puro e preto puro.
- Gradientes coloridos, glassmorphism, neon, brilhos e "aurora".
- Sombras pesadas e duplas.
- Mais de duas famílias tipográficas ou mais de quatro pesos.
- Texto sobre imagem sem sobreposição de contraste.
- Ícones de bibliotecas genéricas misturando estilos.
- Emoji como ícone de interface.
- Carrossel automático, pop-up de entrada, barra fixa de cookies cobrindo o CTA.
- Vídeo em autoplay com som.
- Números, prêmios, depoimentos ou logos de clientes sem origem confirmada.
- Qualquer elemento copiado da referência: texto, nome, logo, imagem, ícone ou layout idêntico.
