# Baratio - Réplica de asesoriaenergetica

Réplica estática (HTML/CSS/JS) del sitio https://baratio.es/, lista para abrir en Cursor.

## Cómo usarlo

1. Copia el contenido de esta carpeta dentro de tu carpeta `asesoriaenergetica` en el Escritorio (sustituye el README.md que ya tenías, o fusiónalos).
2. Abre `index.html` directamente en el navegador, o mejor, usa un servidor local (en Cursor: extensión "Live Server", clic derecho sobre `index.html` → "Open with Live Server"). Esto evita problemas de rutas relativas y de CORS con las fuentes/CDNs.
3. Sube los cambios a GitHub con `git add . && git commit -m "Réplica web Baratio" && git push`.

## Qué incluye

- `index.html` — estructura completa: cabecera, hero con formulario, franja de contacto, servicios, sección "quiénes somos", sección presupuesto, sección "trabaja con nosotros", testimonios, footer y modal de privacidad.
- `css/style.css` — todo el CSS propio del tema (colores, tipografías, layout, botones, tarjetas de testimonios, responsive).
- `css/pe-icon-7-stroke.css` — fuente de iconos del tema original (no se usa visualmente en esta página, pero se mantiene por fidelidad).
- `js/custom.js` — scroll suave entre secciones, menú con resaltado de sección activa (One Page Nav), modal de política de privacidad, y el formulario de contacto.
- `js/jquery.nav.js` y `js/jquery.scrollTo-min.js` — plugins originales del tema para el scroll y la navegación.
- `images/` — placeholders generados (logo, ilustraciones, iconos de servicios, fondos) para que el diseño no se rompa mientras no tengas los archivos reales.

Bootstrap 4.1.3, Animate.css, FontAwesome 5 y Magnific Popup se cargan vía CDN (son librerías públicas estándar; no hace falta tenerlas en local).

## Pendiente / limitaciones importantes

**El formulario "¿Quieres ahorrar? Te llamamos" NO envía datos a ningún sitio real.** El original usa reCAPTCHA v3 y un backend PHP propio (`formularios/llamada.php`) que no tenemos. Ahora mismo el formulario solo simula el envío (muestra el mensaje de éxito) para conservar el comportamiento visual. Para que funcione de verdad necesitas:
- Un backend propio (PHP, Node, lo que prefieras) que reciba el POST y envíe el email/lo guarde en una base de datos, o
- Un servicio externo tipo Formspree, Web3Forms o similar, cambiando la lógica en `js/custom.js`.

**Las imágenes son placeholders genéricos** (logo, ilustraciones, iconos), generados con los colores de marca (#1a5a9e). Sustitúyelos en la carpeta `images/` por los archivos reales de Baratio cuando los tengas, manteniendo los mismos nombres de archivo para que no haya que tocar el HTML.

**Las páginas enlazadas no existen todavía**: `presupuesto.html`, `empleo.html`, `aviso-legal.html`, `privacidad.html`, `politica-de-cookies.html`. Los enlaces del menú y botones apuntan a ellas pero darán 404 hasta que las crees.
