# Guia — HTML full-width dentro do Tática Leads

> Como colar uma landing page em HTML/CSS dentro do Tática Leads (elemento **Custom HTML/Javascript**) **sem aparecer borda lateral** e mantendo o conteúdo organizado (centralizado, não colado nas bordas).

---

## 1. O problema (o que acontecia)

Ao colar o HTML no Tática Leads, aparecia uma **moldura/borda escura uniforme nos 4 lados** da página. Causas reais (em ordem de importância):

1. **O Tática Leads envolve seu código em camadas próprias** — `Section › Row › Column › Custom Code`. A **Row/Container do Tática Leads tem uma largura máxima centralizada** que **os toggles "Full width" da interface nem sempre removem**. É a principal causa da borda lateral.
2. **Colisão de nomes de classe.** Se o seu CSS usa classes genéricas (`.container`, `.section`, `.row`, `.btn`…), elas **batem com as classes internas do Tática Leads** e bagunçam o layout (foi o que causou o efeito "passou demais", estourando a largura).
3. **Confusão com o editor.** O *canvas do editor* do Tática Leads **sempre** mostra a página dentro de uma área de trabalho com margens — isso **não é** a página real. **Sempre validar no Preview / publicado**, nunca no editor.
4. **Imagem quebrada no preview** = caminho relativo (`Files/banner.jpeg`) ainda não hospedado. Não tem a ver com layout; some quando os arquivos forem subidos.

---

## 2. A solução (o que resolve de vez)

São **3 regras de CSS** dentro do `<style>` do seu HTML + **1 wrapper** no `<body>`.

### 2.1 Envolver TODO o conteúdo num wrapper único

Logo depois de `<body>` abra, e antes do `<script>` feche:

```html
<body>
<div class="o6s-page">   <!-- abre o wrapper -->

  ... todo o conteúdo (topbar, header, sections, footer, mobile-cta) ...

</div>                    <!-- fecha o wrapper -->
<script> ... </script>
</body>
```

> Use um nome **único** para o wrapper (ex.: `o6s-page`, `lp-xyz`). **Nunca** `page`, `wrapper`, `container`.

### 2.2 Forçar as camadas do Tática Leads a full-width (a regra-chave)

```css
/* Tática Leads FULL-BLEED: força as camadas (Section/Row/Column/Container) que
   envolvem ESTE bloco a ocuparem 100% da largura, sem max-width nem
   padding lateral. Afeta SÓ os ancestrais do wrapper — não mexe no
   resto da página do Tática Leads. */
:where(body *):has(.o6s-page){
  max-width:100% !important;
  width:100% !important;
  padding-left:0 !important;
  padding-right:0 !important;
  margin-left:0 !important;
  margin-right:0 !important;
}
```

- `:has(.o6s-page)` seleciona **só os elementos do Tática Leads que contêm o seu bloco** (Section, Row, Column…). Não afeta nada fora dali.
- Usa `width:100%` (e **não** `100vw`) → **nunca estoura nem cria rolagem horizontal**.
- O `100vw` + `margin-left:calc(50% - 50vw)` (truque clássico de "breakout") **NÃO funcionou bem aqui** porque o container do Tática Leads já é largo: estourava ("passou demais"). **Evitar `100vw` dentro do Tática Leads.**

### 2.3 Isolar TODO o CSS no wrapper (evita colisão com o Tática Leads)

Prefixe as regras de **classes genéricas** com `.o6s-page` para elas só valerem dentro do seu bloco:

```css
.o6s-page .container { ... }   /* em vez de  .container { ... } */
.o6s-page .section   { ... }   /* em vez de  .section   { ... } */
```

> Faça isso pelo menos para `.container`, `.section`, `.row`, `.col`, `.btn` e qualquer outro nome genérico. O ideal é **prefixar tudo** ou usar nomes únicos desde o começo.

### 2.4 Conteúdo centralizado (organizado, não colado nas bordas)

Fundo full-width, mas **o conteúdo continua centralizado** com respiro lateral:

```css
.o6s-page .container{
  width:100%;
  max-width:1140px;     /* largura do conteúdo; ajuste se quiser */
  margin:0 auto;        /* centraliza */
  padding:0 22px;       /* respiro lateral (gutter) */
}
```

- **Fundos/seções** ocupam a tela toda → some a borda.
- **Texto/conteúdo** fica centralizado e legível → não cola nas bordas.
- Para mudar a "largura do miolo": altere `max-width` (ex.: `1240px` mais largo, `1040px` mais estreito).

---

## 3. Checklist rápido (copiar e seguir)

- [ ] Todo o conteúdo dentro de um `<div class="NOME-UNICO">`.
- [ ] Regra `:where(body *):has(.NOME-UNICO){ width/max-width:100% !important; padding/margin lateral:0 !important }`.
- [ ] CSS isolado: classes genéricas prefixadas com `.NOME-UNICO`.
- [ ] `.NOME-UNICO .container` com `max-width` + `margin:0 auto` + `padding:0 22px`.
- [ ] **NÃO** usar `100vw` nem `margin:calc(50% - 50vw)` dentro do Tática Leads.
- [ ] Validar **no Preview/publicado**, nunca no editor.
- [ ] No Tática Leads, deixar Section/Row/Column com **padding 0** e largura **Full** (ajuda, mas o CSS acima já garante).

---

## 4. Ajustes finos no painel do Tática Leads (opcional, complementa o CSS)

Pelo painel (aba **Styles** de cada camada), de fora pra dentro:

| Camada | Ajuste |
|---|---|
| **Section** | Padding = 0; largura Full |
| **Row** | Full Width ativado; Margin/Padding = 0; gutter/column gap = 0 |
| **Column** | Padding = 0 |
| **Custom Code** | Margin = 0 / Padding = 0 / Width = auto |

> Mesmo sem mexer aqui, o CSS da seção 2 já resolve. Estes ajustes são "cinto e suspensório".

---

## 5. Observações importantes

- **`:has()`** é suportado por todos os navegadores modernos (Chrome, Safari, Firefox, Edge atuais). Sem problema em 2025+.
- **Espaço só no topo** (acima da barra superior)? É `padding-top` da Section do Tática Leads. Some zerando o padding vertical da Section no painel, ou adicione `padding-top:0 !important` ao seletor `:has()` da seção 2.2.
- **Imagem não aparece no preview**? Caminho relativo (`Files/...`) ainda não hospedado. Suba os arquivos ou use URL absoluta. Não é problema de layout.
- **Sempre faça backup** do `.html` antes de grandes alterações (padrão: `nome_backup_AAAAMMDD_HHMMSS.html`).

---

*Referência interna · O6S — Instituto Felipe Castro · Pages/O6S/Files*
