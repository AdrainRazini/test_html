# Exemplos Modernos de Iframes

Este README reúne vários tipos de iframes modernos, responsivos e seguros, prontos para uso em qualquer projeto web.

---

## 1) Iframe Responsivo com `aspect-ratio`


<div style="width:100%; max-width:1200px; margin:0 auto;">
  <div style="aspect-ratio:16/9; width:100%; position:relative; overflow:hidden; border-radius:8px;">
    <iframe
      src="https://adrian-liard.vercel.app/"
      title="Meu site - Demo"
      style="position:absolute; inset:0; width:100%; height:100%; border:0;"
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"
      allowfullscreen>
    </iframe>
  </div>
</div>


---

## 2) Iframe com `loading="lazy"`

```html
<iframe
  src="https://adrian-liard.vercel.app/"
  title="Demo lazy"
  width="800"
  height="450"
  loading="lazy"
  style="border:1px solid #ddd; border-radius:6px;">
</iframe>
```

---

## 3) Iframe Sandboxed

```html
<iframe
  srcdoc="<p>Conteúdo isolado, sem scripts.</p>"
  title="Sandbox demo"
  style="width:100%; height:200px; border-radius:6px;"
  sandbox>
</iframe>

<iframe
  src="https://adrian-liard.vercel.app/some-widget"
  sandbox="allow-scripts allow-same-origin"
  title="Widget confiável"
  style="width:100%; height:400px; border:0;">
</iframe>
```

---

## 4) Iframe com `srcdoc`

```html
<iframe
  srcdoc='<!doctype html><meta charset="utf-8"><style>body{font-family:system-ui;padding:10px}</style><h3>Preview</h3><p>Conteúdo via <code>srcdoc</code>.</p>'
  title="Srcdoc demo"
  style="width:100%; height:240px; border-radius:6px;"
  sandbox="allow-scripts">
</iframe>
```

---

## 5) Comunicação via `postMessage`

**Parent:**

```js
const iframe = document.getElementById('myIframe');
iframe.contentWindow.postMessage({ type: 'hello', payload: 42 }, 'https://adrian-liard.vercel.app');

window.addEventListener('message', (e) => {
  if (e.origin !== 'https://adrian-liard.vercel.app') return;
  console.log('Mensagem do iframe:', e.data);
});
```

**Iframe:**

```js
window.parent.postMessage({ type: 'ready' }, 'https://seu-site.com');
```

---

## 6) Iframe Carregado Sob Demanda

```html
<div class="iframe-placeholder" style="height:360px; background:#f5f5f5; display:flex; align-items:center; justify-content:center;">
  <button id="loadFrame">Carregar conteúdo</button>
</div>

<script>
const btn = document.getElementById('loadFrame');
btn.addEventListener('click', () => {
  const wrapper = btn.parentElement;
  const iframe = document.createElement('iframe');
  iframe.src = 'https://adrian-liard.vercel.app/';
  iframe.loading = 'lazy';
  iframe.style.width = '100%';
  iframe.style.height = '100%';
  iframe.style.border = '0';
  wrapper.replaceWith(iframe);
});
</script>
```

---

## 7) Iframe YouTube Sem Cookies

```html
<iframe width="560" height="315"
  src="https://www.youtube-nocookie.com/embed/VIDEO_ID"
  title="YouTube privacy embed"
  loading="lazy"
  allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>
```

---

# Boas Práticas

* Use `loading="lazy"` para melhorar desempenho.
* Use `aspect-ratio` para responsividade sem JS.
* Utilize `sandbox` para isolamento de segurança.
* Para comunicação cross-origin, sempre valide `event.origin`.
* Evite colocar conteúdo crítico de SEO dentro de iframes.

---

Pronto! Se quiser, posso gerar também uma versão completa como página HTML (`index.html`).
