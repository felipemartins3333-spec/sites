# specs/conteudo.md — Texto final da landing page

Última atualização: 2026-09-03
Status: **conteúdo de demonstração completo.** Nenhuma linha foi programada.

> ## ⚠️ Todo este arquivo é `[DEMO]`
>
> Sollis não existe. Cada frase, número, selo e link abaixo é ficção de
> demonstração, criada sob a autorização de 2026-09-03 registrada em
> `specs/site.md` §3. **Nada aqui pode ir ao ar.**
>
> No HTML, todo elemento que carregar texto deste arquivo recebe `data-demo`.
> O QA tem um item bloqueante: `grep -r data-demo` precisa voltar vazio antes
> de publicar. Ver `specs/plano.md` §12, risco R-02.
>
> Os itens marcados `[A DEFINIR]` continuam intocados de propósito — preço e
> dados cadastrais são consequentes demais para inventar, mesmo em demonstração.

Convenção: **PT** é a versão de origem, **EN** é adaptação e não tradução literal.
As duas mudam sempre na mesma entrega (`specs/plano.md` §12, risco R-03).

---

## 0. Voz

Três regras que resolvem qualquer dúvida de redação:

1. **O número vem antes do adjetivo.** "Quarenta minutos" em vez de "instalação rápida".
2. **Frase curta, verbo no presente.** Nada de futuro do pretérito nem de "solução".
3. **Cada CTA diz o que acontece depois do clique.** "Falar com vendas" leva a um
   formulário, e o texto ao lado avisa que a resposta vem em um dia útil.

Proibido: "revolucionário", "inovador", "líder de mercado", "solução completa",
"transformação digital". Sem exclamação. Sem emoji no corpo do texto.

---

## 1. Metadados e SEO

| Campo | PT-BR | EN |
|---|---|---|
| `<html lang>` | `pt-BR` | `en` |
| `<title>` | Sollis — Veja para onde vai cada watt | Sollis — See where every watt goes |
| `description` | A Sollis mede o consumo circuito por circuito e mostra, em tempo real, onde a sua conta está sendo gasta. Em casa ou na operação. | Sollis measures consumption circuit by circuit and shows, in real time, where your bill is going. At home or across your operation. |
| `og:title` | igual ao `<title>` | igual ao `<title>` |
| `og:image` | `IMG-07-pt` | `IMG-07-en` |
| `og:locale` | `pt_BR` (alternate `en_US`) | `en_US` (alternate `pt_BR`) |
| Canônica | `/` | `/en/` |

Título com 44 caracteres e descrição com 148 — dentro do que o Google exibe sem cortar.

`hreflang` cruzado nas duas páginas, mais `x-default` apontando para a PT-BR.
Dados estruturados: um `Organization` e um `FAQPage` alimentado pelas sete perguntas
da seção 8 — o mesmo texto, nunca uma versão diferente só para o robô.

---

## 2. Header

| Item | PT | EN |
|---|---|---|
| Skip link | Pular para o conteúdo | Skip to content |
| Nav 1 | Como funciona | How it works |
| Nav 2 | Para você | For you |
| Nav 3 | Para empresas | For business |
| Nav 4 | Segurança | Security |
| Nav 5 | Dúvidas | FAQ |
| CTA | Começar agora | Get started |
| Botão de menu | Abrir menu / Fechar menu (`aria-label`) | Open menu / Close menu |
| Idioma | PT · EN | PT · EN |

---

## 3. Hero

**PT**
- H1: **Veja para onde vai cada watt**
- Apoio: A Sollis mede o consumo circuito por circuito e mostra, em tempo real, onde a sua conta está sendo gasta. Em casa ou na operação.
- CTA primário (B2C): **Começar agora**
- CTA primário (B2B): **Falar com vendas**
- Link terciário: Ver como funciona
- Nota micro: Instalação sem obra. Compatível com quadros monofásicos e trifásicos.
- `alt` de `IMG-01`: Fim de tarde numa sala ampla, com a luz entrando pela janela.

**EN**
- H1: **See where every watt goes**
- Apoio: Sollis measures consumption circuit by circuit and shows, in real time, where your bill is actually going. At home or across your operation.
- CTA: **Get started** · **Talk to sales**
- Link: See how it works
- Nota: No rewiring. Works with single-phase and three-phase panels.

**Cartão de vidro sobre a foto** — rótulo "Agora" / "Live", três circuitos com valor
em watts e uma marca visível de exemplo: `Dados de exemplo` / `Sample data`.
Essa marca fica **dentro** do cartão, não em legenda solta.

---

## 4. Prova social

**PT** — Instalado em mais de 4.000 residências e 120 operações
**EN** — Installed in over 4,000 homes and 120 operations

Cinco espaços de logo, cada um com legenda de uma linha. Enquanto não houver clientes
reais, o logo é uma forma neutra com o rótulo visível `Espaço reservado` /
`Placeholder`. **Nunca desenhar algo que pareça a marca de uma empresa de verdade.**

> O número desta seção é o mais perigoso do site inteiro. Ele é fictício.

---

## 5. Como funciona

**PT** — Título: **Três passos, quarenta minutos**
Apoio: Do sensor no quadro ao primeiro relatório, sem trocar a instalação elétrica.

**EN** — Title: **Three steps, forty minutes**
Lead: From the panel sensor to your first report, with no electrical work.

Abas: `Para você` / `Para sua empresa` — `For you` / `For business`

| # | Para você (PT) | For you (EN) |
|---|---|---|
| 1 | **Instale o sensor no quadro** — Um clipe em cada circuito. Sem desligar a casa e sem quebrar parede. | **Clip the sensor onto your panel** — One clip per circuit. No downtime, no drilling. |
| 2 | **Conecte ao Wi-Fi** — O app encontra o sensor e faz o pareamento em menos de dois minutos. | **Connect to Wi-Fi** — The app finds the sensor and pairs it in under two minutes. |
| 3 | **Veja o consumo por circuito** — Chuveiro, ar-condicionado, geladeira. Cada um com o seu número. | **See consumption per circuit** — Water heater, AC, fridge. Each with its own number. |

| # | Para sua empresa (PT) | For business (EN) |
|---|---|---|
| 1 | **Mapeie as unidades** — Cadastre lojas, galpões ou andares e agrupe por região ou centro de custo. | **Map your sites** — Add stores, warehouses or floors and group them by region or cost centre. |
| 2 | **Integre ao seu sistema** — API REST e exportação agendada em CSV para o seu ERP. | **Connect your systems** — REST API and scheduled CSV export into your ERP. |
| 3 | **Receba o relatório auditável** — Consumo por unidade, por período, com trilha de alterações. | **Get the auditable report** — Consumption per site, per period, with a full change log. |

CTA da seção: **Começar agora** / **Get started**

`alt` de `IMG-03a`: Painel da Sollis mostrando o consumo de uma casa por circuito.
`alt` de `IMG-03b`: Painel da Sollis comparando o consumo de várias unidades.

---

## 6. Trilha B2C

**PT**
- Rótulo: Para você
- Título: **A conta deixa de ser surpresa**
- Parágrafo: Você descobre quanto custa cada hábito antes de a fatura chegar — e decide o que vale manter.
- Marcadores:
  - Alerta quando um circuito foge do padrão
  - Estimativa da conta atualizada todo dia
  - Histórico por cômodo, mês a mês
- CTA: **Começar agora**
- Nota micro: Funciona com qualquer distribuidora. Não substitui o medidor oficial.
- `alt` de `IMG-04`: Pessoa em casa, de manhã, olhando o celular perto da janela.

**EN**
- Label: For you
- Title: **No more surprise bills**
- Parágrafo: You find out what each habit costs before the bill arrives — and decide what's worth keeping.
- Bullets: Alerts when a circuit drifts from its pattern · A bill estimate updated daily · Room-by-room history, month by month
- CTA: **Get started**
- Note: Works with any utility. It does not replace your official meter.

---

## 7. Trilha B2B

**PT**
- Rótulo: Para empresas
- Título: **Prove o consumo de cada unidade**
- Parágrafo: Rateio, meta e auditoria com o mesmo dado, sem planilha no meio do caminho.

| Card | PT | EN |
|---|---|---|
| Escala | De 10 a 10.000 pontos de medição sob um único painel. | From 10 to 10,000 metering points under one dashboard. |
| Integração | API REST, webhooks e exportação agendada para o seu ERP. | REST API, webhooks and scheduled export into your ERP. |
| Suporte | Time técnico dedicado, com resposta em até 4 horas úteis. | A dedicated technical team, responding within 4 business hours. |
| Conformidade | Relatório auditável, com trilha de alterações e retenção configurável. | Auditable reports, with a change log and configurable retention. |

- `alt` de `IMG-05`: Técnica conferindo um quadro elétrico em um galpão com luz natural.

### Formulário (`#contato`)

| Campo | PT | EN | Regra |
|---|---|---|---|
| Título | Fale com o time comercial | Talk to our sales team | — |
| Nome | Nome | Name | obrigatório |
| E-mail | E-mail corporativo | Work email | obrigatório, formato válido |
| Empresa | Empresa | Company | obrigatório |
| Unidades | Número de unidades | Number of sites | obrigatório, numérico |
| Mensagem | Mensagem (opcional) | Message (optional) | livre |
| Botão | Enviar contato | Send message | — |
| Nota | Respondemos em até um dia útil. | We reply within one business day. | — |

**Mensagens de erro** — descritivas, nunca "campo inválido":

| Situação | PT | EN |
|---|---|---|
| Vazio | Preencha o seu nome. | Please enter your name. |
| E-mail malformado | Confira o e-mail: falta o @ ou o domínio. | Check the email: the @ or the domain is missing. |
| Unidades não numérico | Informe um número, mesmo que aproximado. | Enter a number, even an approximate one. |
| Envio com erros | Faltam 2 campos para enviar. | 2 fields still need attention. |

**Sucesso** (`aria-live="polite"`): Recebemos o seu contato. Respondemos em até um
dia útil. / We got your message. We'll reply within one business day.

> O destino do envio está `[A DEFINIR]`. Até isso ser resolvido, o formulário valida
> e mostra o sucesso **sem enviar nada**, e o código diz isso em comentário.

---

## 8. Confiança e segurança

**PT**
- Título: **Seu consumo é seu**
- Parágrafo: Os dados saem do sensor criptografados e continuam criptografados em repouso. Você escolhe por quanto tempo guardamos e pode apagar tudo a qualquer momento.
- Nota micro: Nunca vendemos dados de consumo, nem em formato agregado.
- Link terciário: Ler a Política de Privacidade

**EN**
- Title: **Your consumption is yours**
- Parágrafo: Data leaves the sensor encrypted and stays encrypted at rest. You choose how long we keep it, and you can delete all of it at any time.
- Note: We never sell consumption data, aggregated or otherwise.
- Link: Read the Privacy Policy

**Selos — `[DEMO]`, e este é o item mais sensível do arquivo.**
Certificação inventada em site publicado é problema jurídico, não estético. Nesta
fase os três selos são **caixas rotuladas** com o texto visível
`Certificação — espaço reservado` / `Certification — placeholder`.
Nenhum nome de norma real (ISO, SOC, PCI) entra no HTML antes de o cliente enviar o
certificado. Ver `specs/plano.md` §12, risco R-02.

**Diagrama `IMG-06`** — quatro nós: `Sensor no quadro` → `Conexão criptografada` →
`Servidor no Brasil` → `Seu painel`. `alt`: Caminho do dado, do sensor no quadro até
o painel, com a conexão criptografada no meio.

---

## 9. Perguntas frequentes

Sete pares. O primeiro já nasce aberto.

| # | PT | EN |
|---|---|---|
| 1 | **Precisa de obra para instalar?** Não. O sensor é preso por clipe em volta do cabo de cada circuito, com o quadro fechado. Leva cerca de quarenta minutos numa casa comum. | **Do I need any electrical work?** No. The sensor clips around each circuit's cable with the panel closed. It takes about forty minutes in a typical home. |
| 2 | **Funciona com quadro trifásico?** Funciona. Monofásico, bifásico e trifásico, de 8 a 64 circuitos por sensor. | **Does it work with three-phase panels?** Yes. Single-, two- and three-phase, from 8 to 64 circuits per sensor. |
| 3 | **Quem enxerga os meus dados?** Só você e quem você autorizar. O nosso time só acessa mediante o seu pedido de suporte, e cada acesso fica registrado. | **Who can see my data?** Only you and whoever you authorise. Our team only accesses it when you open a support request, and every access is logged. |
| 4 | **Quanto custa?** `[A DEFINIR]` — preço não é inventado nem em demonstração. | **How much does it cost?** `[A DEFINIR]` |
| 5 | **Posso cancelar quando quiser?** Pode, sem multa e sem fidelidade. Ao cancelar, você exporta o histórico e a gente apaga os dados em até 30 dias. | **Can I cancel any time?** Yes, with no fee and no lock-in. On cancellation you export your history and we delete the data within 30 days. |
| 6 | **Como funciona o suporte?** Chat e e-mail para todos. Contratos B2B têm time técnico dedicado, com resposta em até 4 horas úteis. | **How does support work?** Chat and email for everyone. Business contracts get a dedicated technical team, responding within 4 business hours. |
| 7 | **Integra com o meu sistema?** Sim, por API REST, webhooks ou exportação agendada em CSV. A documentação é pública. | **Does it integrate with my systems?** Yes — REST API, webhooks or scheduled CSV export. The documentation is public. |

Nenhuma resposta passa de três linhas. Se precisar de mais, o assunto virou seção.

---

## 10. CTA de fechamento

**PT** — Título: **Comece pelo circuito que mais pesa**
Apoio: Em quarenta minutos você já sabe qual é.
CTAs: **Começar agora** · **Falar com vendas** — exatamente os mesmos do hero.

**EN** — Title: **Start with the circuit that costs you most**
Lead: Forty minutes from now, you'll know which one it is.
CTAs: **Get started** · **Talk to sales**

---

## 11. Footer

| Coluna | PT | EN |
|---|---|---|
| Produto | Como funciona · Para você · Para empresas · Integrações | How it works · For you · For business · Integrations |
| Empresa | Sobre · Carreiras · Contato | About · Careers · Contact |
| Legal | Política de Privacidade · Termos de Uso · Cookies | Privacy Policy · Terms of Use · Cookies |
| Suporte | Central de ajuda · Status · Documentação da API | Help centre · Status · API docs |

- Endereço, CNPJ e razão social: `[A DEFINIR]`
- Copyright: © 2026 Sollis `[DEMO]`
- Seletor de idioma e três ícones de rede, todos com `aria-label`.

**Aviso obrigatório durante a fase `[DEMO]`**, em `--fs-micro`, no topo do rodapé:

> **PT** — Conteúdo de demonstração. Sollis é uma marca fictícia; números, textos e
> certificações desta página são exemplos e não representam produto ou empresa reais.
>
> **EN** — Demonstration content. Sollis is a fictional brand; the figures, copy and
> certifications on this page are examples and do not represent a real product or company.

Esse aviso sai no mesmo commit em que o conteúdo real entrar. Nunca antes.

---

## 12. Paridade PT / EN

Checklist de QA — as duas páginas precisam bater em:

- [ ] 10 seções, na mesma ordem
- [ ] 1 `<h1>` em cada
- [ ] 2 CTAs primários no hero e 2 no fechamento, com o mesmo texto nos dois lugares
- [ ] 7 itens de FAQ
- [ ] 4 cards na seção B2B
- [ ] 5 campos de formulário
- [ ] mesma quantidade de links no rodapé
- [ ] `hreflang` apontando um para o outro, sem link quebrado
- [ ] mesmo conjunto de imagens, com `alt` traduzido
