# imagens.md — Manifesto de imagens

Última atualização: 2026-09-03
Status: **nenhuma imagem existe ainda.** Este arquivo define os espaços, não o conteúdo.

Direção de arte governada por `specs/design.md` §10 e §11. Orçamento de peso
governado por `specs/site.md` §13. Origem das imagens: `[A DEFINIR]`.

---

## Regras que valem para todas

- Formato: **AVIF** como primeira fonte, **WebP** como alternativa, dentro de `<picture>`.
- `width` e `height` sempre declarados no HTML — é a defesa principal contra CLS.
- `srcset` com três larguras por imagem e `sizes` correspondente ao layout real.
- Abaixo da dobra: `loading="lazy"` e `decoding="async"`. No hero: `fetchpriority="high"`, sem lazy.
- Texto sobre foto exige véu `--ink-900` entre 35% e 55%, e o contraste é medido
  **na imagem final**, na região exata onde o texto cai.
- `alt` significativo em toda imagem informativa; `alt=""` nas decorativas.
- Proibido: marcas de terceiros visíveis, imagens da referência, stock de aperto de
  mãos, gráfico de bolsa, pessoa gerada que aparente ser alguém real e identificável.

---

## Inventário

| ID | Seção | Papel | Proporção | Larguras (`srcset`) | Peso máx. | Carga |
|---|---|---|---|---|---|---|
| `IMG-01` | Hero | Fotografia de fundo | 16:9 | 1200 · 1600 · 2400 | 200 KB | ansiosa, `high` |
| `IMG-02a…e` | Prova social | Logos monocromáticos | livre, altura óptica 28px | SVG | 4 KB cada | inline |
| `IMG-03a` | Como funciona · aba B2C | Mockup de interface | 4:3 | 800 · 1200 · 1600 | 140 KB | lazy |
| `IMG-03b` | Como funciona · aba B2B | Mockup de interface | 4:3 | 800 · 1200 · 1600 | 140 KB | lazy |
| `IMG-04` | Trilha B2C | Retrato em contexto | 4:5 | 600 · 900 · 1200 | 120 KB | lazy |
| `IMG-05` | Trilha B2B | Ambiente operacional | 3:2 | 800 · 1200 · 1600 | 150 KB | lazy |
| `IMG-06` | Segurança | Diagrama do fluxo de dados | 16:9 e 3:4 | SVG inline | 8 KB | inline |
| `IMG-07` | SEO | Open Graph | 1,91:1 | 1200×630 | 300 KB | fora da página |
| `LOGO-01` | Header e footer | Logotipo | ~120×28 | SVG | 3 KB | inline |
| `ICON-01…06` | Cards e redes | Ícones | 24×24 | SVG | 1 KB cada | inline |

Total previsto na página: **8 arquivos rasterizados**, todo o resto em SVG inline.
Soma estimada com tudo carregado: ~750 KB, dentro do teto de 1,5 MB.

---

## Direção por imagem

### `IMG-01` — Hero
Fim de tarde, luz quente e rasante. Uma pessoa de costas ou de perfil em ambiente
doméstico amplo, olhar fora da câmera. **Espaço negativo à esquerda**, onde entram o
H1 e os dois CTAs — o enquadramento precisa ser pensado para isso, não recortado
depois. Um assunto só. Sem colagem.
`alt`: descreve a cena, não o produto. A frase de venda já está no H1 ao lado.

### `IMG-02a…e` — Logos da prova social
Monocromáticos em `--ink-500`, altura óptica normalizada (não altura de caixa —
um logo circular precisa ser maior que um retangular para parecer do mesmo tamanho).
Enquanto não houver clientes reais, usar formas neutras **visivelmente rotuladas**
como espaço reservado. Nunca inventar um logo que pareça uma empresa de verdade.

### `IMG-03a` / `IMG-03b` — Mockups da interface
Ângulo leve, nunca frontal chapado. Cantos `--radius-lg`. Sangram para fora do quadro
na borda inferior. Sobre bloco escuro, halo suave de luz fria. As duas variantes
precisam ter **exatamente a mesma altura renderizada**, senão a troca de aba empurra
a página. Os dados na tela são plausíveis e marcados como exemplo.

### `IMG-04` — Trilha B2C
Retrato vertical, luz natural quente, pessoa em uso real do produto em casa. Espaço
negativo à direita. Sombras abertas, leve dessaturação nos verdes, sem HDR.
Sem pose de banco de imagens.

### `IMG-05` — Trilha B2B
Horizontal, ambiente técnico ou operacional, luz natural. Pessoas trabalhando de
verdade. Sem sala de reunião com gente apontando para gráfico, sem aperto de mãos.

### `IMG-06` — Diagrama de segurança
Desenhado por nós, SVG inline, traço de 1.5px, no máximo duas cores. Mostra o
caminho do dado do sensor até o painel. **Duas versões**: horizontal para desktop e
vertical para mobile — trocadas por `<picture>` ou CSS, nunca por rotação.
Substitui deliberadamente o render 3D simbólico da referência, proibido em
`specs/design.md` §11.

### `IMG-07` — Open Graph
1200×630, com o logotipo e a headline. Uma versão por idioma. Precisa ser legível
no tamanho de miniatura do WhatsApp, então nada de texto pequeno.

---

## Paridade entre idiomas

`IMG-01` a `IMG-06` são compartilhadas entre PT-BR e EN — não têm texto embutido, e
é por isso que não podem ter. `IMG-07` tem uma versão por idioma. Ao trocar qualquer
imagem, atualizar as duas páginas na mesma entrega.

## Pendências

- [ ] Definir a origem: banco de imagens, produção própria ou geração.
- [ ] Confirmar a categoria do produto — ela determina toda a direção fotográfica.
- [ ] Produzir ou licenciar `IMG-01`, `IMG-04` e `IMG-05`.
- [ ] Desenhar os mockups `IMG-03a` e `IMG-03b` com a mesma altura.
- [ ] Desenhar `IMG-06` nas duas orientações.
- [ ] Logotipo `LOGO-01` — fora do escopo atual (`specs/site.md` §14).
- [ ] Verificar licença de uso comercial de tudo que for licenciado.
