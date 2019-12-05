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

(aka panaceia)

---

<!-- TODO -->

---

# Grid

<!-- TODO: headline -->

---

<!-- TODO -->
