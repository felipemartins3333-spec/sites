# memoria.md — Histórico vivo do projeto

Registro apenas o que ajuda na continuidade. Não registrar conversas inteiras.

Última atualização: 2026-09-03

---

## Decisões aprovadas

| Data | Decisão | Onde vive |
|---|---|---|
| 2026-09-03 | Idioma: PT-BR + EN, com seletor | `specs/site.md` §4 |
| 2026-09-03 | Estrutura: landing page única (por idioma), navegação por âncoras | `specs/site.md` §5 |
| 2026-09-03 | Público: B2B e B2C com peso igual, em trilha dupla bifurcada no hero | `specs/site.md` §2 |
| 2026-09-03 | Stack: HTML + CSS + JS puro, sem framework e sem build | `specs/site.md` §10 |
| 2026-09-03 | Revolut PT-BR adotado como referência de estrutura e atmosfera apenas | `specs/design.md` §0 |
| 2026-09-03 | Identidade final deve ser original: nada copiado da referência | `CLAUDE.md` |
| 2026-09-03 | Conteúdo fictício de demonstração autorizado, sob marcação `[DEMO]` / `data-demo` e proibido de ir ao ar | `specs/site.md` §3 |
| 2026-09-03 | Tipografia: Schibsted Grotesk (títulos 500/600) + Inter (corpo 400/500) | `specs/design.md` §4 |
| 2026-09-03 | Controle segmentado B2C/B2B fica na seção "Como funciona", sem criar 11ª seção | `specs/plano.md` §2 |
| 2026-09-03 | CSS em arquivo único por camadas; JS em 6 módulos ES | `specs/plano.md` §9 |

## Decisões rejeitadas

| Data | Rejeitado | Motivo |
|---|---|---|
| 2026-09-03 | Site multipágina completo | Cliente optou por landing única |
| 2026-09-03 | Frameworks (Next.js, Astro, Vite/React) e Tailwind | Cliente optou por stack sem build |
| 2026-09-03 | Site só em PT-BR | Cliente quer alcance internacional |
| 2026-09-03 | Priorizar um único público na home | Trilha dupla é requisito |
| 2026-09-03 | Paleta acromática e composição centralizada da referência | Precisa ser identidade própria |
| 2026-09-03 | Estética metálica / renders 3D simbólicos da referência | Muito colada na marca original |

## Alterações realizadas

| Data | O que |
|---|---|
| 2026-09-03 | Criada a pasta `referências - site/` com `revolut.md` (link do site de referência) |
| 2026-09-03 | Criados `CLAUDE.md`, `specs/site.md`, `specs/design.md` e `memoria.md` |
| 2026-09-03 | Cliente subiu o print da referência (1366 × 6157 px) direto no branch |
| 2026-09-03 | Análise visual refeita sobre o arquivo real e detalhada em `specs/design.md` §0 |
| 2026-09-03 | Criados `specs/plano.md` (plano de implementação) e `imagens.md` (manifesto de imagens) |
| 2026-09-03 | Marca de demonstração definida: **Sollis**, gestão inteligente de energia `[DEMO]` |
| 2026-09-03 | Criado `specs/conteudo.md` com o texto completo PT-BR + EN, todo `[DEMO]` |
| 2026-09-03 | Adicionados ao plano os passes de SEO (§13) e QA (§14), com itens bloqueantes |

## Problemas encontrados

1. **Resolvido — imagem da referência não chegava ao repositório.** O print
   colado no chat não tinha arquivo correspondente no ambiente, e o caminho
   enviado era local do navegador (`chrome-extension://…`).
2. **Ambiente sem acesso à internet aberta.** A política de rede bloqueia
   `revolut.com`, então não foi possível capturar o site automaticamente.
3. **Nenhuma informação real sobre o produto foi fornecida.** Isso trava a
   escrita de qualquer conteúdo comercial.
4. **Nome da pasta de referências diverge do combinado.** Está
   `referências - site/`; o pedido posterior mencionou `referencias`.
5. **A cor de acento reprova em contraste.** `--accent-600` `#C2551F` dá 4,26:1
   sobre `--paper-50` e 3,87:1 sobre `--paper-100`, abaixo do mínimo de 4,5:1 do
   WCAG AA. Como é o fundo do botão primário, todo botão primário em bloco claro
   reprovaria. Descoberto por cálculo, não por estimativa visual.
6. **`specs/design.md` §12 se contradiz.** Manda animar só `transform` e `opacity`
   e, na mesma seção, abrir o acordeão por `height`/`grid-template-rows`.

## Soluções aplicadas

1. O cliente subiu o PNG direto no branch pelo GitHub. O arquivo foi integrado
   por merge e a análise visual foi refeita sobre ele, fatiado em quatro faixas.
   O resultado está escrito em `specs/design.md` §0 — o conhecimento fica no
   repositório, não só no arquivo de imagem.
2. O link ficou versionado em `referências - site/revolut.md`.
3. Tudo que depende do produto foi marcado como `[A DEFINIR]` em vez de inventado,
   conforme a regra de não inventar informações.
4. Mantido o nome atual da pasta até o cliente decidir renomear.
5. Calculado `--accent-700` `#AD4A1A`, mesmo matiz, com 5,21:1 e 4,74:1. Registrado
   como proposta em `specs/design.md` §2, **aguardando aprovação** — o token antigo
   não foi removido, só restrito a usos de 3:1.
6. Proposto registrar `grid-template-rows` como a única exceção documentada à regra
   de animação, por ser o único caminho para altura automática sem JavaScript.

## Pendências

**Bloqueiam conteúdo** — destravadas em demonstração por `specs/conteudo.md`,
mas todas continuam obrigatórias antes de publicar.
- [ ] Nome do produto/empresa e o que ele faz em uma frase
- [ ] Setor de atuação e restrições regulatórias
- [ ] Três diferenciais verificáveis
- [ ] Prova social real (logos, números, certificações)
- [ ] Modelo de preço
- [ ] Textos e destinos dos CTAs
- [ ] Destino do formulário B2B
- [ ] Objetivo principal do site e métrica de sucesso

**Bloqueiam design**
- [x] Tipografia definida: Schibsted Grotesk + Inter (`specs/design.md` §4)
- [ ] **Aprovar a correção de contraste `--accent-700`** (`specs/plano.md` R-01)
- [ ] **Aprovar a exceção de animação do acordeão** (`specs/plano.md` R-04)
- [ ] Confirmação da paleta proposta ou entrega do manual de marca
- [ ] Origem das fotografias
- [ ] Produzir as 8 imagens do manifesto (`imagens.md`)

**Operacionais**
- [ ] Domínio e hospedagem
- [ ] Ferramenta de analytics
- [ ] Texto das páginas legais (Privacidade e Termos)
- [x] Salvar o print da referência como arquivo na pasta de referências
- [ ] Decidir se a pasta `referências - site/` é renomeada para `referencias/`

## Próximos passos

1. Cliente aprova (ou corrige) o plano em `specs/plano.md`.
2. Cliente decide os dois itens travados: correção de contraste R-01 e exceção R-04.
3. Cliente confirma se **Sollis** segue como marca de demonstração ou entrega a real.
4. Implementar na ordem de `specs/plano.md` §11 — a fundação de tokens vem primeiro.
5. Substituir todo conteúdo `[DEMO]` antes de qualquer publicação. Item bloqueante.
6. Atualizar este arquivo a cada decisão importante aprovada.
