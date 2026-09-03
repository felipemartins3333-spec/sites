# CLAUDE.md

Arquivo principal do projeto. Leia sempre que esta pasta for aberta.

## O projeto

Site institucional/comercial com foco em experiência do usuário, comunicando
para dois públicos ao mesmo tempo: **B2B e B2C, com peso igual (trilha dupla)**.

Estado atual: **fase de documentação**. Nada foi programado ainda.

## Fontes de verdade

- **@specs/site.md** — o que precisa ser construído (escopo, seções, funcionalidades, stack).
- **@specs/design.md** — como deve parecer (paleta, tipografia, espaçamento, movimento).
- **@specs/plano.md** — plano de implementação: mapa da página, componentes, riscos, ordem de execução.
- **@specs/conteudo.md** — texto final PT-BR e EN de cada seção. Hoje inteiro `[DEMO]`.
- **@imagens.md** — manifesto de imagens: qual imagem entra em cada seção e com que especificação.
- **@memoria.md** — histórico vivo de decisões, problemas e próximos passos.

Leia todos antes de qualquer trabalho de implementação.

## Regra de conflito (obrigatória)

> Se algum pedido meu contradisser uma decisão registrada em @specs/site.md,
> @specs/design.md ou @memoria.md, pare e me avise antes de realizar qualquer
> alteração. Explique qual decisão seria afetada e pergunte se desejo substituí-la.

## Regras de trabalho

- Não altere a stack técnica sem minha autorização.
- Não remova uma decisão aprovada silenciosamente.
- Não invente informações comerciais, médicas ou técnicas sobre o produto.
  Se o dado não existe nos specs, use um marcador explícito `[A DEFINIR]` e me pergunte.
  **Exceção autorizada em 2026-09-03**: conteúdo fictício de demonstração é permitido,
  desde que marcado `[DEMO]` na documentação e `data-demo` no HTML. Nada marcado assim
  pode ir ao ar. Ver @specs/site.md §3.
- Sempre preserve a consistência visual e estrutural entre as seções.
- Antes de uma mudança grande, apresente um plano resumido e espere aprovação.
- Depois de uma decisão importante aprovada, atualize @memoria.md.

## Regras de referência

A pasta `referências - site/` guarda material de inspiração (hoje: Revolut PT-BR).
A referência serve **apenas como direção de estrutura e atmosfera**.

Nunca copiar: textos, logotipo, nome, identidade proprietária, imagens,
elementos exclusivos da marca ou layouts idênticos. A identidade final é original.

## Idioma

Conteúdo do site: **PT-BR e EN**. A documentação do projeto é escrita em PT-BR.
