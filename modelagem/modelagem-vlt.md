# Modelagem — VLT (Vendas e Lideranca Training)

> Documento de referencia para a construcao da landing page do **VLT — Instituto Felipe Castro**.
> Baseado na analise das paginas IFC (institucional), O6S (imersao) e VOICER (imersao).
> Data: 2026-08-19

---

## 1. Identidade do Produto

| Elemento | Detalhe |
|---|---|
| **Sigla** | VLT |
| **Nome completo** | VLT — Lideranca & Vendas Training |
| **Tipo** | Imersao Tematica (Camada 2 do ecossistema IFC) |
| **Posicao no ecossistema** | Mesma camada do VOICER e PNL Experience — acima do O6S |
| **Logo local** | `VLT/logo/Logo_VLT.png` |
| **Logo CDN (IFC page)** | `https://assets.cdn.filesafe.space/VrEgg6CoAE8kU4AthR7m/media/6a446835a7501a002a17769b.png` |
| **Descricao oficial (IFC)** | "Onde tecnica encontra proposito. Treinamento intensivo para empresarios e lideres comerciais que querem vender mais sem perder a essencia — transformando comunicacao, presenca e estrategia em resultado consistente." |

---

## 2. Analise Comparativa das 3 Paginas Existentes

### 2.1 Visao Geral

| Aspecto | IFC (institucional) | O6S (LP imersao) | VOICER (LP imersao) |
|---|---|---|---|
| **Objetivo** | Apresentar instituto + ecossistema | Converter vaga em evento | Converter vaga em evento |
| **Tema visual** | Claro (branco/cinza) | Escuro (`#0a0a0c`) | Escuro (`#090c09`) |
| **Cor accent** | Azul `#1D51A3` + Gold `#C9A655` | Vermelho `#ec1c2e` / `#d11a2a` | Verde `#1a5c1a` / `#22731f` |
| **Fonte heading** | Montserrat | Sora | Sora |
| **Fonte body** | Inter | Inter | Inter |
| **Wrapper CSS** | `.ifc-page` | `.o6s-page` | `.vcr-page` |
| **Prefixo classes** | `.ifc-page .ifc-*` | `.o6s-page .classe` ou global | `.vcr-page .classe` |
| **Max-width conteudo** | 1140px | 1140px | 1140px |
| **GHL Full-Bleed** | Sim (`:has()`) | Sim (`:has()`) | Sim (`:has()`) |
| **Scroll reveal** | Nao | Sim (IntersectionObserver) | Sim (IntersectionObserver) |
| **Countdown** | Nao | Sim | Sim |
| **FAQ accordion** | Nao | Sim | Sim |
| **Mobile CTA** | WhatsApp FAB fixo | Sticky bar bottom | Sticky bar bottom |
| **Formulario** | HTML nativo + embed | Modal + secao oculta (TaticaLeads) | Modal + secao oculta (TaticaLeads) |

### 2.2 Paleta de Cores — Padrao por Produto

| Token | O6S (vermelho) | VOICER (verde) | VLT (sugestao) |
|---|---|---|---|
| `--bg` | `#0a0a0c` | `#090c09` | Extrair do logo |
| `--accent` | `#d11a2a` | `#1a5c1a` | Extrair do logo |
| `--accent-bright` | `#ec1c2e` | `#22731f` | Extrair do logo |
| `--accent-deep` | `#8e1320` | `#0f3a0e` | Extrair do logo |
| `--accent-soft` | `rgba(209,26,42,.12)` | `rgba(26,92,26,.12)` | `rgba(cor,.12)` |
| `--gold` | `#e8c267` | `#e8c267` | `#e8c267` (heranca IFC) |
| `--grad-accent` | `linear-gradient(135deg,#ec1c2e,#a30f1c)` | `linear-gradient(135deg,#22731f,#0f3a0e)` | Adaptar |

> **ACAO:** Abrir `Logo_VLT.png` para extrair a cor dominante e definir a paleta.

---

## 3. Estrutura de Secoes — Modelo Consolidado

Baseado na analise das 3 paginas, o modelo mais completo para LP de imersao e o do **VOICER** (evolucao do O6S). A estrutura recomendada para o VLT:

| # | Secao | Classe | Funcao | Referencia |
|---|---|---|---|---|
| 1 | **Topbar** | `.topbar` | Urgencia (lote/vagas) | O6S + VOICER |
| 2 | **Header sticky** | `header.nav` | Brand VLT + nav + CTA | O6S + VOICER |
| 3 | **Hero** | `.hero` | Headline + chips (data/local/formato) + CTA + countdown | O6S + VOICER |
| 4 | **Strip de pilares** | `.pillars-strip` | 4 colunas com os temas da imersao | O6S + VOICER |
| 5 | **Dor do avatar** | `.section` (pain) | Identificacao com problemas de vendas/lideranca | O6S + VOICER |
| 6 | **O que e o VLT** | `.about` | Conceito + quote do Felipe Castro | O6S + VOICER |
| 7 | **Pilares do Metodo** | `.steps` | Etapas progressivas da jornada (3-5 etapas) | VOICER |
| 8 | **Secao Tecnica Diferenciada** | `.diff-section` | Aprofundamento no diferencial competitivo | VOICER |
| 9 | **Ferramentas e Tecnicas** | `.tech-grid` | Grid de tecnicas ensinadas (6-8 cards) | VOICER |
| 10 | **Beneficios Principais** | `.cards-4` + `.bgrid` | 4 cards + checklist de transformacao | VOICER |
| 11 | **CTA Intermediaria** | `.mid-cta` | Botao de conversao no meio da pagina | VOICER |
| 12 | **Para quem e / nao e** | `.foryou-grid` | Qualificacao do lead (2 colunas) | O6S + VOICER |
| 13 | **Agenda / Timeline** | `.timeline` | Estrutura do dia com horarios | O6S + VOICER |
| 14 | **Mentor** | `.mentor` | Felipe Castro: foto + bio + stats | O6S + VOICER |
| 15 | **Depoimentos** | `.tgrid` | Grid 3 colunas com prova social | O6S + VOICER |
| 16 | **Oferta VIP** | `.vip-box` | Escassez + condicao especial | VOICER |
| 17 | **Detalhes do evento** | `.details` | Data / Horario / Local / Formato (4 cells) | O6S + VOICER |
| 18 | **Pricing / Lotes** | `.pricing` | 3 planos (encerrado / atual / em breve) | O6S + VOICER |
| 19 | **Formulario (oculto)** | `.vlt-hidden` | Embed TaticaLeads (revela no clique) | O6S + VOICER |
| 20 | **Garantia** | `.guarantee` | 7 dias de garantia incondicional | O6S + VOICER |
| 21 | **FAQ** | `.faq-list` | Accordion com perguntas frequentes | O6S + VOICER |
| 22 | **Final CTA** | `.final` | Fechamento emocional | O6S + VOICER |
| 23 | **Footer** | `footer` | Brand + links sociais + copyright | O6S + VOICER |
| 24 | **Mobile Sticky CTA** | `.mobile-cta` | Barra fixa bottom: preco + botao | O6S + VOICER |
| 25 | **Modal formulario** | `.vlt-modal` | TaticaLeads embed popup | O6S + VOICER |

---

## 4. Conteudo — Modelos de Copy para o VLT

### 4.1 Hero

**Estrutura padrao (O6S + VOICER):**
```
Eyebrow:    "Imersao Presencial"
H1:         [Dor central]. [Promessa com highlight]
Paragrafo:  Descricao do produto + para quem e + o que transforma
Chips:      [DATA] | Araraquara SP | Dia inteiro / Presencial
CTA 1:      [Verbo + resultado desejado] →
CTA 2:      "Entender a imersao" (ghost)
Countdown:  Contagem regressiva ate o evento
```

**Sugestao para VLT:**
```
Eyebrow:    "Imersao Presencial"
H1:         "Voce vende. Voce lidera. [Mas sera que esta fazendo isso no nivel que poderia?]"
Paragrafo:  "VLT e uma imersao intensiva de Vendas e Lideranca para empresarios e lideres
             comerciais que querem vender mais sem perder a essencia — unindo tecnica,
             presenca e estrategia em resultado consistente."
CTA 1:      "Quero vender e liderar no proximo nivel →"
CTA 2:      "Entender a imersao"
```

### 4.2 Pilares (Strip)

**Padrao identificado:** 4 pilares por produto

| Produto | Pilar 1 | Pilar 2 | Pilar 3 | Pilar 4 |
|---|---|---|---|---|
| O6S | Inteligencia Emocional | Mentalidade | Alta Performance | Espiritualidade |
| VOICER | Presenca Vocal | Autoridade | Clareza | Influencia |
| **VLT** | **[PENDENTE]** | **[PENDENTE]** | **[PENDENTE]** | **[PENDENTE]** |

**Sugestao para VLT (a validar):**
```
Pilar 1: Estrategia de Vendas
Pilar 2: Lideranca Comercial
Pilar 3: Comunicacao Persuasiva
Pilar 4: Alta Performance em Resultados
```

### 4.3 Secao de Dor

**Padrao identificado:** 6 pain points em grid 2x3, cada um com icone "!" e texto descritivo com `<strong>` no ponto-chave.

**Sugestao para VLT:**
```
1. Voce bate meta, mas sente que poderia vender [muito mais] com a mesma equipe.
2. Voce lidera um time comercial, mas as pessoas [nao executam] com a intensidade que voce espera.
3. Voce conhece tecnicas de vendas, mas na hora H [trava] e nao consegue aplicar com naturalidade.
4. Voce perde negociacoes que deveria fechar porque [nao transmite valor] com clareza.
5. Sua equipe depende de voce para [cada decisao] — e voce ja esta esgotado.
6. Voce sabe que resultado vem de pessoas, mas nao sabe como [tirar o melhor] de cada uma.
```

**Bridge (frase de transicao):**
```
"A diferenca entre o lider que bate meta e o que transforma equipes nao e tecnica.
E [como ele vende, lidera e inspira]."
```

### 4.4 O que e o VLT (About)

**Padrao:** Coluna esquerda com eyebrow + titulo + texto + quote. Coluna direita com card de contexto.

**Sugestao:**
```
Eyebrow:    "O que e o VLT"
Titulo:     "Onde tecnica encontra [proposito]."
Texto:      "VLT nao e mais um treinamento de vendas. E uma imersao que une estrategia
             comercial, lideranca e presenca para que voce pare de vender no automatico
             e comece a liderar resultados com intencao. Com Felipe Castro, voce vai
             descobrir que vender mais e liderar melhor sao consequencias de quem voce
             se torna no processo."
Quote:      "Quando voce para de vender por pressao e comeca a vender por presenca,
             o resultado muda de patamar."
```

### 4.5 Etapas do Metodo (Steps)

**Padrao VOICER:** 5 etapas progressivas (Diagnostico → Fundacao → Estrutura → Execucao → Consolidacao)

**Sugestao para VLT (a validar):**
```
01. Diagnostico Comercial — Mapeamento dos padroes atuais de venda e lideranca
02. Mentalidade de Vendas — Crencas e bloqueios que limitam o resultado comercial
03. Estrategia e Tecnica — Frameworks de vendas, negociacao e fechamento
04. Lideranca Comercial — Como formar, engajar e extrair o melhor do time
05. Consolidacao — Plano de acao pratico para aplicar a partir do dia seguinte
```

### 4.6 Secao Tecnica Diferenciada

**Padrao VOICER:** Grid 2 colunas — texto a esquerda, 4 itens com icone a direita.

**Sugestao para VLT:**
```
Titulo:     "Va Alem do Script: [Domine a Arte de Vender com Proposito]"
Subtitulo:  "Muitos treinamentos ensinam o que dizer. No VLT, voce aprende
             COMO vender e liderar de um jeito que gera resultado e respeito."

Itens:
1. Negociacao Estrategica — Como conduzir negociacoes complexas com seguranca
2. Leitura Comportamental — Entender o perfil do cliente e adaptar a abordagem
3. Gestao de Pipeline — Transformar oportunidades em fechamentos consistentes
4. Lideranca pelo Exemplo — Inspirar o time pela presenca, nao pela pressao
```

### 4.7 Ferramentas e Tecnicas (Tech Grid)

**Padrao VOICER:** Grid 4x2 com 8 cards (icone + titulo + descricao curta)

**Sugestao para VLT:**
```
1. Tecnicas de Fechamento
2. Gestao de Objecoes
3. Perfil Comportamental (DISC)
4. Comunicacao Persuasiva
5. Formacao de Equipe de Vendas
6. KPIs e Metricas Comerciais
7. Rapport e Conexao
8. Inteligencia Emocional em Vendas
```

### 4.8 Beneficios Principais (4 Cards)

**Padrao:** 4 cards com icone + titulo + descricao

**Sugestao para VLT:**
```
Card 1: Resultado Comercial       — Vender mais com estrategia, nao com pressao
Card 2: Lideranca que Engaja      — Formar um time que executa sem depender de voce
Card 3: Negociacao com Autoridade  — Fechar com seguranca e transmitir valor real
Card 4: Consistencia              — Resultado que se mantem, mes apos mes
```

### 4.9 Para quem e / Nao e

**Padrao:** 2 colunas (sim/nao) com 4-5 itens cada

**Sugestao para VLT:**

**E para voce se:**
- Voce e empresario ou lider comercial e quer multiplicar resultado com o mesmo time
- Voce vende todos os dias e sente que poderia fechar mais e melhor
- Voce quer formar liderancas comerciais dentro da sua empresa
- Voce acredita que vender com etica e proposito da mais resultado do que pressao
- Voce esta cansado de treinamentos teoricos e quer algo pratico e aplicavel

**Nao e para voce se:**
- Voce procura um script magico para decorar e repetir
- Voce acredita que pressao e o unico caminho para resultado
- Voce nao esta disposto a mudar a forma como lidera e vende
- Voce quer assistir passivamente e sair como entrou

### 4.10 CTA Intermediaria

```
Titulo:     "Pronto para transformar seus [resultados comerciais]?"
Texto:      "Nao espere o proximo mes para perceber que esta vendendo abaixo
             do potencial. O VLT vai te dar as ferramentas antes."
CTA:        "Quero garantir minha vaga →"
```

### 4.11 Oferta VIP

```
Badge:      "Acesso Exclusivo"
Titulo:     "Entre no Grupo VIP do VLT"
Texto:      "Receba uma condicao especial para a proxima turma do VLT com
             Felipe Castro. A oferta sera revelada diretamente para os
             membros do grupo — antes de qualquer divulgacao publica."
CTA:        "Garantir Minha Vaga VIP →" → WhatsApp
```

### 4.12 CTA Final

```
Eyebrow:    "Sua decisao comeca agora"
Titulo:     "Voce chegou ate aqui porque [algo fez sentido]."
Texto:      "Aquela sensacao de que voce poderia estar vendendo mais, liderando
             melhor, construindo resultado com mais consistencia — nao e ilusao.
             E o sinal mais honesto que voce tem. O dia do VLT vai acontecer de
             qualquer forma. A pergunta e se voce vai estar na sala."
CTA:        "Chega de vender abaixo do meu potencial →"
Nota:       "As vagas sao limitadas. O proximo lote e mais caro."
```

---

## 5. Padrao Tecnico Obrigatorio

### 5.1 Wrapper e GHL Full-Bleed

```html
<body>
<div class="vlt-page">
  <!-- todo o conteudo -->
</div>
<script> ... </script>
</body>
```

```css
:where(body *):has(.vlt-page){
  max-width:100%!important;
  width:100%!important;
  padding-left:0!important;
  padding-right:0!important;
  margin-left:0!important;
  margin-right:0!important;
}
```

### 5.2 Container de Conteudo

```css
.vlt-page .container{
  width:100%;
  max-width:1140px;
  margin:0 auto;
  padding:0 22px;
}
```

### 5.3 Isolamento de CSS

Prefixar TODAS as classes com `.vlt-page`:

```css
.vlt-page .section   { ... }
.vlt-page .container { ... }
.vlt-page .btn       { ... }
.vlt-page .hero      { ... }
/* etc. */
```

### 5.4 Fontes

```html
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@400;600;700;800&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet" />
```
- Headings: `'Sora', sans-serif`
- Body: `'Inter', system-ui, -apple-system, sans-serif`

### 5.5 Checklist GHL

- [ ] Todo conteudo dentro de `<div class="vlt-page">`
- [ ] Regra `:where(body *):has(.vlt-page)` no CSS
- [ ] Classes genericas prefixadas com `.vlt-page`
- [ ] `.vlt-page .container` com `max-width:1140px` + `margin:0 auto` + `padding:0 22px`
- [ ] Sem `100vw` nem `margin: calc(50% - 50vw)`
- [ ] Validar no **Preview/publicado**, nunca no editor
- [ ] No Tatica Leads: Section/Row/Column com padding 0 e largura Full

> Referencia: `VLT/guia/GUIA_HTML_FullWidth_TaticaLeads.md`

---

## 6. Componentes JavaScript

Copiar do VOICER e adaptar IDs/classes para VLT:

```javascript
// 1. Countdown timer — contagem regressiva ate a data do evento
// 2. FAQ accordion — abrir/fechar perguntas (classe .faq-q / .faq-item.open)
// 3. Scroll reveal — IntersectionObserver (classe .reveal → .in)
// 4. Secao oculta — data-reveal="id-da-secao" (remove .vlt-hidden)
// 5. Modal formulario — data-open-form / data-close
// 6. Header shadow on scroll — muda background do header
```

---

## 7. Dados Globais do IFC (reutilizar)

| Item | Valor |
|---|---|
| WhatsApp geral | `https://wa.me/message/6XCIYAQHJXSGP1` |
| WhatsApp VLT | `https://wa.me/message/6XCIYAQHJXSGP1?text=Quero%20saber%20sobre%20o%20VLT` |
| Instagram | `https://www.instagram.com/eusou.felipecastro/` |
| YouTube | `https://www.youtube.com/@eusou.felipecastro` |
| Email | `contato@institutofelipecastro.com.br` |
| Sede | Araraquara - SP - Brasil |
| Copyright | `© 2026 IFC — Instituto Felipe Castro. Todos os direitos reservados.` |

---

## 8. Depoimentos Padrao

Os mesmos 3 depoentes usados no ecossistema:

| Nome | Cargo | Foto CDN |
|---|---|---|
| Thais Leonel | Dona da Agencia WSI Digital | `https://assets.cdn.filesafe.space/VrEgg6CoAE8kU4AthR7m/media/6a1f806d7303598210540876.png` |
| Maderli Marcola | Dona da Liliantex Moda Masculina | `https://assets.cdn.filesafe.space/VrEgg6CoAE8kU4AthR7m/media/6a1f806dbce897da752738f0.png` |
| Adailton Silva | Dono do Ebenezer Buffet | `https://assets.cdn.filesafe.space/VrEgg6CoAE8kU4AthR7m/media/6a1f806d6103bdfedd96a05b.png` |

> Idealmente, coletar depoimentos especificos de vendas/lideranca para o VLT.

---

## 9. Integracoes (Tatica Leads)

```html
<!-- Embed inline (secao oculta) -->
<iframe
  src="https://api.taticaleads.com.br/widget/form/[ID-DO-FORM-VLT]"
  style="width:100%;height:600px;border:none;border-radius:8px"
  data-form-name="VLT - CAPTACAO LP"
  title="VLT - CAPTACAO LP">
</iframe>
<script src="https://api.taticaleads.com.br/js/form_embed.js"></script>
```

> O ID do formulario deve ser criado no Tatica Leads e substituido em `[ID-DO-FORM-VLT]`.

---

## 10. Convencoes de Arquivos

| Convencao | Valor |
|---|---|
| Diretorio | `Pages/VLT/` |
| Arquivo principal | `index.html` |
| Backup | `index_backup_AAAAMMDD_HHMMSS.html` |
| Logo | `VLT/logo/Logo_VLT.png` |
| Imagens | `VLT/images/` |
| Guia GHL | `VLT/guia/GUIA_HTML_FullWidth_TaticaLeads.md` |
| Modelagem | `VLT/modelagem/modelagem-vlt.md` (este arquivo) |

---

## 11. Pendencias — O que e necessario para iniciar a construcao

| # | Item | Status | Observacao |
|---|---|---|---|
| 1 | **Cor dominante do logo VLT** | PENDENTE | Abrir `Logo_VLT.png` e extrair hex |
| 2 | **Tema visual** (escuro ou claro) | PENDENTE | Sugestao: escuro (padrao LPs de imersao) |
| 3 | **Pilares reais da imersao** (4 temas) | PENDENTE | Sugestoes neste doc — validar com Felipe |
| 4 | **Etapas do metodo** (3-5 passos) | PENDENTE | Sugestoes neste doc — validar com Felipe |
| 5 | **Data e local do evento** | PENDENTE | Dia, mes, cidade |
| 6 | **Horario** (inicio/encerramento) | PENDENTE | Padrao IFC: 08h-20h |
| 7 | **Precos e lotes** (3 lotes) | PENDENTE | Valores de cada lote |
| 8 | **Copy aprovado ou livre** | PENDENTE | Sugestoes de copy neste doc |
| 9 | **Foto do Felipe Castro** | PARCIAL | Pode usar a mesma do O6S/VOICER |
| 10 | **Imagem hero** | PENDENTE | Foto do evento ou conceitual |
| 11 | **ID do formulario TaticaLeads** | PENDENTE | Criar no Tatica Leads |
| 12 | **Depoimentos especificos** | PENDENTE | Idealmente de vendas/lideranca |
| 13 | **Ferramentas e tecnicas ensinadas** | PENDENTE | Sugestoes neste doc — validar |
| 14 | **FAQ especifico** | PENDENTE | Adaptar do O6S/VOICER |

---

## 12. Fluxo de Construcao Recomendado

1. Resolver pendencias 1-3 (cor, tema, pilares) — minimo para iniciar
2. Criar `VLT/index.html` usando VOICER como template base
3. Substituir wrapper `.vcr-page` por `.vlt-page`
4. Trocar paleta verde por paleta do VLT
5. Adaptar todo o conteudo (copy, pilares, titulos)
6. Inserir logo VLT no header e footer
7. Ajustar countdown para data do evento
8. Criar formulario no Tatica Leads e inserir ID
9. Testar no preview do Tatica Leads (GHL)
10. Publicar

---

*Documento de modelagem — VLT (Vendas e Lideranca Training) — Instituto Felipe Castro*
*Gerado em: 2026-08-19*
