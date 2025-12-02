# test_html
https://adrian-liard.vercel.app/


---
<!-- responsivo: container controla a altura via aspect-ratio -->
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
---
<iframe
  src="https://adrian-liard.vercel.app/"
  title="Demo lazy"
  width="800"
  height="450"
  loading="lazy"
  style="border:1px solid #ddd; border-radius:6px;">
</iframe>
---
---
<iframe
  srcdoc="<p>Conteúdo inline isolado — sem scripts</p>"
  title="Sandbox demo"
  style="width:100%; height:200px; border-radius:6px;"
  sandbox>
</iframe>

<!-- permitir scripts e same-origin (use com cautela) -->
<iframe
  src="https://adrian-liard.vercel.app/some-widget"
  sandbox="allow-scripts allow-same-origin"
  title="Widget confiável (com cautela)"
  style="width:100%; height:400px; border:0;">
</iframe>
---
---
<iframe
  srcdoc='
    <!doctype html>
    <meta charset="utf-8">
    <style>body{font-family:system-ui;padding:10px}</style>
    <h3>Preview rápido</h3>
    <p>Este HTML vem do atributo <code>srcdoc</code>.</p>
    <script>/*scripts opcionais*/</script>
  '
  title="Srcdoc demo"
  style="width:100%; height:240px; border-radius:6px;"
  sandbox="allow-scripts">
</iframe>
---
---

