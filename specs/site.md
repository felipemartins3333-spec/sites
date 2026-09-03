# specs/site.md — Fonte de verdade do produto

Última atualização: 2026-09-03

Marcadores usados neste arquivo:
- `[APROVADO]` — decidido pelo cliente, não alterar sem autorização.
- `[PROPOSTO]` — recomendação minha, aguardando confirmação.
- `[A DEFINIR]` — informação que ainda não existe. **Não inventar.**

---

## 1. Objetivo do site

`[A DEFINIR]` — o objetivo de negócio ainda não foi declarado.

Objetivo estrutural já assumido `[PROPOSTO]`: apresentar o produto de forma clara
para dois públicos distintos na mesma página, e converter cada um deles em uma
ação diferente (autoatendimento para B2C, contato comercial para B2B).

Métrica de sucesso: `[A DEFINIR]`

## 2. Público-alvo

Peso igual entre os dois públicos — **trilha dupla** `[APROVADO]`.

| Trilha | Quem é | O que quer | Ação esperada |
|---|---|---|---|
| B2C | Consumidor final | Entender rápido o benefício pessoal | Começar sozinho (cadastro/download/teste) |
| B2B | Empresa / decisor | Entender escala, integração, suporte e segurança | Falar com o time comercial |

A bifurcação acontece **explicitamente no hero**: dois caminhos, dois CTAs,
duas trilhas de conteúdo que se cruzam nas seções de confiança.

Detalhamento de personas, setores e porte das empresas: `[A DEFINIR]`

## 3. Produto e proposta de valor

`[A DEFINIR]` — nenhuma informação real sobre o produto foi fornecida até agora.

Pendente de definição pelo cliente:
- Nome do produto/marca
- O que o produto faz, em uma frase
- Três diferenciais concretos e verificáveis
- Prova social real (clientes, números, prêmios, certificações)
- Preço ou modelo de cobrança
- Restrições legais/regulatórias do setor

**Regra:** nenhum número, benefício, depoimento ou credencial pode ser escrito
sem origem confirmada pelo cliente. Textos provisórios devem ficar visivelmente
marcados como placeholder.

## 4. Idiomas

`[APROVADO]` PT-BR + EN, com seletor de idioma.

Implementação `[PROPOSTO]` (stack sem framework):
- `index.html` (PT-BR, idioma padrão) e `/en/index.html` (EN) como páginas estáticas irmãs.
- `<html lang>` correto em cada uma.
- `<link rel="alternate" hreflang="pt-BR|en|x-default">` cruzado entre as duas.
- Seletor de idioma no header e no footer, apontando para a página equivalente.
- Sem detecção automática por navegador com redirecionamento forçado (prejudica SEO e controle do usuário).

Conteúdo em EN é tradução adaptada, não literal. Ambas as versões devem ser
publicadas juntas — não subir uma versão pela metade.

## 5. Quantidade de páginas

`[APROVADO]` **Landing page única**, por idioma.

Total real de arquivos HTML: 2 páginas principais (PT-BR + EN),
mais páginas legais obrigatórias `[PROPOSTO]`:
- Política de Privacidade
- Termos de Uso

Navegação interna por âncoras entre seções, com scroll suave e header fixo.

## 6. Seções necessárias

Ordem da landing page `[PROPOSTO]` — segue o ritmo alternado analisado na referência,
com identidade e conteúdo próprios:

1. **Header** — logo, navegação por âncoras, seletor de idioma, CTA principal.
2. **Hero (bifurcação)** — headline, subheadline, dois CTAs lado a lado (B2C / B2B), visual do produto.
3. **Prova social** — faixa de logos ou números. Só entra com dados reais `[A DEFINIR]`.
4. **O que é / como funciona** — 3 a 4 passos ou pilares, linguagem neutra para os dois públicos.
5. **Trilha B2C** — benefício pessoal, visual de produto em uso, CTA de autoatendimento.
6. **Trilha B2B** — escala, integração, suporte, segurança, CTA de contato comercial.
7. **Confiança e segurança** — como os dados são tratados, certificações `[A DEFINIR]`.
8. **Perguntas frequentes** — acordeão, 6 a 8 perguntas.
9. **CTA de fechamento** — repetição do par de ações, sem novo conteúdo.
10. **Footer** — navegação secundária, legal, contato, idioma, redes.

Seções condicionais, entram apenas se houver conteúdo real:
- Depoimentos / cases
- Planos e preços
- Integrações

## 7. Funcionalidades

- Navegação por âncoras com scroll suave e destaque da seção ativa.
- Header fixo que reage ao scroll (compacta após a primeira dobra).
- Seletor de idioma PT-BR / EN.
- Alternância de trilha B2C / B2B em seção com controle segmentado (tabs).
- Acordeão de FAQ acessível por teclado.
- Formulário de contato B2B — destino do envio `[A DEFINIR]` (e-mail, CRM ou serviço externo).
- Menu mobile (drawer) com foco preso enquanto aberto.
- Animações de entrada discretas por seção, respeitando `prefers-reduced-motion`.

Fora de qualquer versão inicial: login, área logada, blog, busca, e-commerce, chat ao vivo.

## 8. Chamadas para ação

Hierarquia `[PROPOSTO]`, textos finais `[A DEFINIR]` porque dependem do produto:

| Nível | Trilha | Função | Estilo |
|---|---|---|---|
| Primário | B2C | Começar sozinho | Botão sólido, cor de acento |
| Primário | B2B | Falar com o time | Botão contornado, mesma altura |
| Secundário | Ambos | Ver como funciona | Link com seta, sem caixa |

Regras:
- O par de CTAs primários aparece no hero e no fechamento, sempre com o mesmo texto.
- Nunca mais de dois CTAs primários visíveis na mesma dobra.
- Todo CTA precisa dizer o que acontece depois do clique.

## 9. Informações que ainda precisam ser definidas

Bloqueiam a escrita de conteúdo real:
1. Nome do produto e da empresa.
2. O que o produto faz (uma frase) e para qual dor.
3. Setor de atuação e restrições regulatórias.
4. Três diferenciais verificáveis.
5. Prova social real (logos, números, certificações).
6. Modelo de preço.
7. Textos exatos dos CTAs e para onde levam.
8. Destino do formulário B2B.
9. Domínio de publicação e hospedagem.
10. Existe manual de marca, logo ou paleta já definidos?

Bloqueiam decisões visuais (ver também `specs/design.md`):
11. Tipografia definitiva.
12. Origem das fotografias (banco de imagens, produção própria, render 3D).

## 10. Stack técnica

`[APROVADO]` **HTML + CSS + JavaScript puro**, sem framework e sem build.

Regras da stack (não alterar sem autorização):
- HTML5 semântico, um `<h1>` por página, hierarquia de headings correta.
- CSS moderno nativo: custom properties para todos os tokens, `clamp()` para escala fluida,
  CSS Grid e Flexbox para layout, `@layer` para ordenar cascata.
- JavaScript ES modules, sem dependências externas, sem jQuery, sem bundler.
- Zero CSS frameworks (sem Tailwind, sem Bootstrap).
- Fontes auto-hospedadas em `woff2`, com `font-display: swap`. Sem Google Fonts via CDN.
- SVG inline para ícones. Sem biblioteca de ícones.
- Estrutura de pastas proposta:
  ```
  index.html
  en/index.html
  assets/css/   assets/js/   assets/fonts/   assets/img/
  ```
- Hospedagem estática `[A DEFINIR]`.

## 11. Regras de responsividade

- Abordagem **mobile-first**. O layout de celular é o padrão; desktop é progressão.
- Breakpoints `[PROPOSTO]`: `640px` (large phone), `900px` (tablet/landscape), `1200px` (desktop), `1600px` (wide).
- Largura máxima do conteúdo: `1200px`, centralizada, com gutter lateral de `24px` no mobile e `48px` no desktop.
- Seções de imagem podem ser full-bleed; o texto nunca ultrapassa o container.
- Tipografia fluida com `clamp()` — sem saltos bruscos entre breakpoints.
- Nenhum scroll horizontal em qualquer largura a partir de `320px`.
- Alvos de toque com no mínimo `44 × 44px`.
- Tabelas e blocos largos rolam dentro do próprio container (`overflow-x: auto`), nunca a página.
- Testar em: 320, 375, 414, 768, 1024, 1440, 1920.

## 12. Requisitos de acessibilidade

Meta: **WCAG 2.2 nível AA**.

- Contraste mínimo 4.5:1 para texto normal e 3:1 para texto grande e elementos de interface.
- Toda a navegação operável por teclado, na ordem visual, sem armadilhas de foco.
- Indicador de foco visível e próprio (nunca `outline: none` sem substituto).
- Link "pular para o conteúdo" como primeiro elemento focável.
- Landmarks semânticos: `header`, `nav`, `main`, `section`, `footer`.
- Toda imagem com `alt` significativo; imagens decorativas com `alt=""`.
- FAQ e tabs com `aria-expanded` / `aria-selected` e navegação por setas.
- Formulários com `<label>` real, erros descritos em texto e associados por `aria-describedby`.
- Respeitar `prefers-reduced-motion: reduce` desligando animações de entrada e parallax.
- Não usar cor como único portador de significado.
- Zoom até 200% sem perda de conteúdo ou função.

## 13. Requisitos de desempenho

Orçamento por página, em conexão 4G `[PROPOSTO]`:

| Métrica | Alvo |
|---|---|
| LCP | < 2,0 s |
| INP | < 200 ms |
| CLS | < 0,05 |
| Peso total da primeira dobra | < 500 KB |
| Peso total da página | < 1,5 MB |
| Requisições | < 30 |
| JS próprio | < 30 KB não comprimido |

Práticas obrigatórias:
- Imagens em AVIF/WebP com `srcset` + `sizes`, `width`/`height` sempre declarados.
- `loading="lazy"` e `decoding="async"` em tudo abaixo da dobra; imagem do hero com `fetchpriority="high"`.
- CSS crítico inline no `<head>`, restante carregado sem bloquear.
- Duas famílias tipográficas no máximo, subsetadas para latim.
- Sem scripts de terceiros na primeira dobra. Analytics `[A DEFINIR]`, carregado de forma diferida.
- Animações apenas em `transform` e `opacity`.

## 14. Escopo

**Dentro do escopo**
- Landing page única, responsiva, em PT-BR e EN.
- Seções listadas no item 6, com trilha dupla B2C/B2B.
- Sistema de tokens de design em CSS (cores, tipografia, espaçamento, raios).
- Interações: menu mobile, tabs, acordeão, scroll suave, animações discretas.
- Formulário de contato B2B (front-end).
- SEO on-page: title, description, Open Graph, dados estruturados, sitemap, `hreflang`.
- Páginas legais (Privacidade e Termos), com texto fornecido pelo cliente.

**Fora do escopo**
- Back-end, banco de dados, autenticação, área logada.
- CMS ou painel de edição de conteúdo.
- Blog, busca interna, e-commerce, checkout.
- Aplicativo móvel.
- Redação de conteúdo comercial sem informação fornecida.
- Criação de logotipo e manual de marca completo.
- Produção fotográfica e modelagem 3D.
- Campanhas, tráfego pago e integração com CRM.
