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

## Problemas encontrados

1. **Imagem da referência não pôde ser salva no repositório.**
   O print foi colado no chat e o caminho enviado era local do navegador
   (`chrome-extension://…`), sem arquivo correspondente no ambiente.
2. **Ambiente sem acesso à internet aberta.** A política de rede bloqueia
   `revolut.com`, então não foi possível capturar o site automaticamente.
3. **Nenhuma informação real sobre o produto foi fornecida.** Isso trava a
   escrita de qualquer conteúdo comercial.
4. **Nome da pasta de referências diverge do combinado.** Está
   `referências - site/`; o pedido posterior mencionou `referencias`.

## Soluções aplicadas

1. A análise visual da referência foi feita a partir do print exibido no chat e
   registrada por escrito em `specs/design.md` §0 — assim o conhecimento fica no
   repositório mesmo sem o arquivo de imagem.
2. O link ficou versionado em `referências - site/revolut.md`.
3. Tudo que depende do produto foi marcado como `[A DEFINIR]` em vez de inventado,
   conforme a regra de não inventar informações.
4. Mantido o nome atual da pasta até o cliente decidir renomear.

## Pendências

**Bloqueiam conteúdo**
- [ ] Nome do produto/empresa e o que ele faz em uma frase
- [ ] Setor de atuação e restrições regulatórias
- [ ] Três diferenciais verificáveis
- [ ] Prova social real (logos, números, certificações)
- [ ] Modelo de preço
- [ ] Textos e destinos dos CTAs
- [ ] Destino do formulário B2B
- [ ] Objetivo principal do site e métrica de sucesso

**Bloqueiam design**
- [ ] Tipografia definitiva (recomendação em `specs/design.md` §4)
- [ ] Confirmação da paleta proposta ou entrega do manual de marca
- [ ] Origem das fotografias

**Operacionais**
- [ ] Domínio e hospedagem
- [ ] Ferramenta de analytics
- [ ] Texto das páginas legais (Privacidade e Termos)
- [ ] Salvar o print da referência como arquivo na pasta de referências
- [ ] Decidir se a pasta `referências - site/` é renomeada para `referencias/`

## Próximos passos

1. Cliente responde as pendências que bloqueiam conteúdo e design.
2. Confirmar ou substituir a paleta e a tipografia propostas — vira `[APROVADO]`.
3. Escrever o conteúdo real das 10 seções em PT-BR e depois adaptar para EN.
4. Só então iniciar a implementação: tokens em CSS → estrutura HTML → seções → interações.
5. Atualizar este arquivo a cada decisão importante aprovada.
