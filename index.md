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


</style>

<!-- _class: lead -->
<!-- _footer: Photo by Mark Neal on Unsplash -->
![bg contrast:80% grayscale](images/first-bg.jpg)

# <!-- fit --> Pensando<br>em CSS

---

<!-- _class: invert -->

# Mito 1

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

![bg contain right](images/subgrid-full.png)

```css
li {
  display: flex;
  flex-direction: column;
}

li button {
  margin-top: auto;
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

![bg contain right](images/subgrid-ie.png)

```css
li {
  display: flex;
  flex-direction: column;
}

li button {
  margin-top: auto;
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
# 🙅 Mito 1 🙅

Pode usar praticamente tudo desde que se garanta que o seu site/app continua funcional quando não há suporte

---

<!-- _class: invert -->
# Mito 2

Você precisa brigar com o browser

---

<iframe
  height="700"
  style="width: 100%;"
  scrolling="no"
  title="Fallback de grid"
  src="https://codepen.io/vhfmag/embed/PowoMGq?height=500&theme-id=dark&default-tab=css,result"
  frameborder="no"
  allowtransparency="true"
  allowfullscreen="true"
>
  See the Pen <a href='https://codepen.io/vhfmag/pen/PowoMGq'>Fallback de grid</a> by Victor Magalhães (<a href='https://codepen.io/vhfmag'>@vhfmag</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

---

![bg grayscale](images/robot.jpg)

<!-- _color: white -->
# <!-- fit --> O browser é mais esperto que você

<!-- _footer: Photo by Franck V. on Unsplash -->