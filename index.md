---
theme: uncover
marp: true
paginate: true
autoScaling: true
---

<style>
section.lead h1, section.lead h2 {
  color: hsl(0, 0%, 100%);
}

section.lead h1 {
  text-align: left;
}

section.hipster-quote {
  color: white;
  justify-content: flex-end;
  padding-bottom: 1.5em;
}

section.two-col ul,
section.two-col ol,
section.two-col p {
  column-count: 2;
}

.iframe-wrapper {
  width: 100%;
  height: 700px;
  resize: both;
  overflow: scroll;
  margin: auto;
}

iframe {
  width: 100% !important;
  height: 100% !important;
}

</style>

<!-- _class: lead -->
<!-- _footer: Photo by Mark Neal on Unsplash -->
![bg contrast:80% grayscale](images/first-bg.jpg)

# <!-- fit --> Pensando<br>em CSS

---

<!-- _header: Parte 1 -->
<!-- _class: invert -->
<!-- _footer: Photo by Joanna Kosinska on Unsplash -->
# <!-- fit --> Mitos 🧙<br>vs<br>🕵 Fatos

![bg grayscale brightness:0.75](images/crystals.jpg)

---

<!-- _class: invert -->

# Mito 1 🧙

Só podemos usar o que todos os browsers a que damos suporte suportam

---

> Vixe, nem posso usar Grid por causa do IE 🤦

<!-- _footer: Photo by Jacob Rank on Unsplash -->
<!-- _class: hipster-quote -->
![bg grayscale](images/hipster.jpg)

---

![bg left](images/about.blank.png)

```js
async function* hispter(val) {
  while (isValid(val)) {
    yield val = await api(
      val?.toLowercase()
    );
  }
}
```

---

<!-- _header: Firefox 71 -->
<!-- _footer: https://codepen.io/vhfmag/pen/XWJJxry -->
![bg contain right](images/subgrid-full.png)

```css
ul {
  display: grid;
  grid-template-columns:
    1fr 1fr;
  grid-gap: 1em;
}

li {
  display: grid;
  grid-row: span 3;
  grid-template-rows:
    subgrid;
}
```

---

![](https://caniuse.bitsofco.de/image/css-grid.png)

---

![](https://caniuse.bitsofco.de/image/css-subgrid.png)

---

<!-- _header: Chrome 78 -->
<!-- _footer: https://codepen.io/vhfmag/pen/XWJJxry -->
![bg contain right](images/subgrid-chrome-nofallback.png)

```css
ul {
  display: grid;
  grid-template-columns:
    1fr 1fr;
  grid-gap: 1em;
}

li {
  display: grid;
  grid-row: span 3;
  grid-template-rows:
    subgrid;
}
```

---

<!-- _header: Chrome 78 -->
<!-- _footer: https://codepen.io/vhfmag/pen/XWJJxry -->
![bg contain right](images/subgrid-full.png)

```css
li {
  display: flex;
  flex-direction: column;
}

@supports (
  grid-template-rows: subgrid
) {
  li {
    display: grid;
    grid-row: span 3;
    grid-template-rows:
      subgrid;
  }
}
```

---

<!-- _header: IE 11 -->
<!-- _footer: https://codepen.io/vhfmag/pen/XWJJxry -->
![bg contain right](images/subgrid-ie.png)

```css
li {
  display: flex;
  flex-direction: column;
}

@supports (
  grid-template-rows: subgrid
) {
  li {
    display: grid;
    grid-row: span 3;
    grid-template-rows:
      subgrid;
  }
}
```

---

<!-- _class: invert -->
# Fato 1 🕵

Se pode usar praticamente tudo desde que se garanta que tudo continua funcional quando não há suporte

---

<!-- _class: invert -->
# Mito 2 🧙

Você precisa brigar com o browser

---

<iframe
  height="700"
  style="width: 100%;"
  scrolling="no"
  title="Fallback de grid"
  src="https://codepen.io/vhfmag/embed/PowoMGq?height=700&theme-id=dark&default-tab=result"
  frameborder="no"
  allowtransparency="true"
  allowfullscreen="true"
>
  See the Pen <a href='https://codepen.io/vhfmag/pen/PowoMGq'>Fallback de grid</a> by Victor Magalhães (<a href='https://codepen.io/vhfmag'>@vhfmag</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

---

![bg grayscale](images/robot.jpg)

<!-- _color: white -->
# <!-- fit --> O browser é mais<br>esperto que você

<!-- _footer: Photo by Franck V. on Unsplash -->

---

<iframe
  height="700"
  style="width: 100%; margin: auto"
  scrolling="no"
  title="Fallback de grid"
  src="https://codepen.io/brundolf/embed/gRaREv?height=700&theme-id=dark&default-tab=css,result"
  frameborder="no"
  allowtransparency="true"
  allowfullscreen="true"
>
  See the Pen <a href='https://codepen.io/brundolf/pen/gRaREv'>CSS is Awesome</a> by Brandon (<a href='https://codepen.io/brundolf'>@brundolf</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

---

<div class="iframe-wrapper">
  <iframe
    height="700"
    style="width: 100%;"
    scrolling="no"
    title="AEA 2018 — Teaser Card"
    src="https://codepen.io/jensimmons/embed/gezmMa?height=700&theme-id=dark&default-tab=result"
    frameborder="no"
    allowtransparency="true"
    allowfullscreen="true"
  >
    See the Pen <a href='https://codepen.io/jensimmons/pen/gezmMa'>AEA 2018 — Teaser Card</a> by Jen Simmons
    (<a href='https://codepen.io/jensimmons'>@jensimmons</a>) on <a href='https://codepen.io'>CodePen</a>.
  </iframe>
</div>

---

<!-- _class: invert -->
# Fato 2 🕵

O browser pode inferir layout adaptativos caso se use as ferramentas adequadas e um CSS que sugira ao invés de instruir

---

<!-- _header: Parte 1 -->
<!-- _class: invert -->
<!-- _footer: Photo by Mark Rasmuson on Unsplash -->
# <!-- fit --> Falando CSS

![bg grayscale blur:3px brightness:0.5](images/ancient-book.jpg)

---

<!-- _class: invert two-col -->
# Layouts

- Flow
- Flex
- Grid
- Multicoluna

---

# Flow

> I feel like, at this point, we are fish who are growing legs, and we’re climbing out onto land, and we’re having all these conversations about land and what land is and what it means to be on the land, but we also have to give a whole bunch of words and terms to the water, because now water’s actually a thing that’s different than land.
> — Jen Simmons ([@jensimmons](https://twitter.com/jensimmons/))

---

# Multicoluna

<style scoped>
  p {
    column-width: 20ch;
  }
</style>

Layout similar ao *flow* mas divido em colunas, típico do design gráfico. Existe desde o IE10 🤯

---

<div class="iframe-wrapper">
  <iframe
    height="700"
    style="width: 100%;"
    scrolling="no"
    title="Image Gallery — multicolumn layout (7/9)"
    src="https://codepen.io/jensimmons/embed/BKPGov?height=700&theme-id=dark&default-tab=result"
    frameborder="no"
    allowtransparency="true"
    allowfullscreen="true"
  >
    See the Pen <a href='https://codepen.io/jensimmons/pen/BKPGov'>AEA 2018 — Teaser Card</a> by Jen Simmons
    (<a href='https://codepen.io/jensimmons'>@jensimmons</a>) on <a href='https://codepen.io'>CodePen</a>.
  </iframe>
</div>

---

# Flex

O mais imitado 🤷

---

- Layout unidimensional (com wrap)
- Controle sobre crescimento e encolhimento
- Controle sobre alinhamento nas duas dimensões

---

# Grid

Apenas use. Você vai ver grid em tudo

---

- Layout bidimensional
- Nova unidade: `fr`
- Novos valores: `min-content`, `max-content`
- Novas funções: `repeat`, `minmax`, `fit-content`

---

<!-- _footer: Photo by viklundvisuals on Unsplash -->

<style scoped>
.grid-overlap {
  height: 85%;
  display: grid;
  grid-template-columns: 1fr 32ch 1fr;
  grid-template-rows: 300px 3em 1fr;
}

.grid-overlap * {
  margin: 0;
}

.grid-overlap :nth-child(1) {
  grid-row: 1 / 3;
  grid-column: 1 / -1;
  
}

.grid-overlap :nth-child(1) img {
  width: 100% !important;
  height: 100%;
  object-fit: cover;
}

.grid-overlap :nth-child(2) {
  padding: 0.5em;
  grid-row: 2 / 4;
  grid-column: 2;
  background-color: white;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
  border-radius: 4pt;
}
</style>

<div class="grid-overlap">

![w:500px](images/surf.jpg)

Venha pro nosso treino de surf e reprograme o seu DNA com nossas técnicas quânticas. Resultado garantido!

</div>

---

<div class="iframe-wrapper">
  <iframe
    height="700"
    style="width: 100%;"
    scrolling="no"
    title="Fallback de grid"
    src="https://codepen.io/vhfmag/embed/XWJJxry?height=700&theme-id=dark&default-tab=result"
    frameborder="no"
    allowtransparency="true"
    allowfullscreen="true"
  >
    See the Pen <a href='https://codepen.io/vhfmag/pen/XWJJxry'>Fallback de grid</a> by Victor Magalhães (<a href='https://codepen.io/vhfmag'>@vhfmag</a>) on <a href='https://codepen.io'>CodePen</a>.
  </iframe>
</div>

---

# Expressividade do CSS

---

<style scoped>
  blockquote {
    text-align: justify;
    text-align-last: left;
  }
</style>

> Paragraphs of text that are too long are difficult to follow, and paragraphs of text that are too thin are difficult to read. **Ideally, blocks of text should be roughly 70 characters wide**. Be sure to keep them at least between 50 and 120 characters wide.
> — [Página de tipografia do design system da Adobe](https://spectrum.adobe.com/page/typography/)

---

```css
p {
  width: 70ch; /* 🤷 */
}
```

---

**Tipografia fluida**
Ex: de 16 a 24px, de 400 a 600px de largura de tela

---

<div class="iframe-wrapper">
  <iframe
    height="700"
    style="width: 100%;"
    scrolling="no"
    title="Fallback de grid"
    src="https://codepen.io/vhfmag/embed/QWwbPVK?height=700&theme-id=dark&default-tab=result"
    frameborder="no"
    allowtransparency="true"
    allowfullscreen="true"
  >
    See the Pen <a href='https://codepen.io/vhfmag/pen/QWwbPVK'>Fallback de grid</a> by Victor Magalhães (<a href='https://codepen.io/vhfmag'>@vhfmag</a>) on <a href='https://codepen.io'>CodePen</a>.
  </iframe>
</div>

---

```css
body {
  font-size: 4vw;
}

@media (max-width: 400px) {
  body {
    font-size: 16px;
  }
}

@media (min-width: 600px) {
  body {
    font-size: 24px;
  }
}
```

---

```css
/* Safari 11.1+ & Chrome 79+ */
body {
  font-size: min(max(16px, 4vw), 24px);
}

/* Chrome 79+ */
body {
  font-size: clamp(16px, 4vw, 24px);
}
```
