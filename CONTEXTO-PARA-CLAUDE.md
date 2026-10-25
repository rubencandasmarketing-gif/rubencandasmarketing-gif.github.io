# Contexto para Claude — rubencandas.com

> Este fichero es solo para trabajar en el repositorio. **No se sube a Raiola**
> (si se subiera, quedaria publico y revelaria la ruta de la carpeta oculta).

## Como esta hecha la web

- HTML estatico, una pagina por fichero en la raiz. Sin build, sin includes:
  cada pagina lleva su propio `<style>`, cabecera y pie copiados.
- Tipografias: Roboto Slab (titulos), Manrope (texto), Caveat (detalles a mano).
- Colores (`:root`): `--ink #101f1c`, `--teal #5bbdb5`, `--teal-deep #2f8f86`,
  `--teal-ink #20746a`, `--paper #f5f2ea`, `--paper-2 #eae5d8`, `--bolt #e8402f`.
- Publicacion: subida manual a Raiola (Apache, `.htaccess`). GitHub es copia de
  seguridad; hacer push NO publica nada.
- Formularios: Formspree por `fetch` (AJAX). Sin `_next` (la redireccion propia
  de Formspree es de pago). Honeypot `_gotcha`. `_subject` se compone con JS.

## Tu Campaña Lista (carpeta oculta `/tucampanalista/`)

Servicio de anuncios en Instagram/Facebook para distribuidores independientes
de nutricion y bienestar.

- `tucampanalista/index.html` — formulario de alta. Formspree
  `https://formspree.io/f/xgaonnwk`. Asunto: "Nueva alta Tu Campaña Lista · {nombre}".
  Campos condicionales (`data-cond`) visibles si falla el JS. Mensajes de
  validacion en espanol por JS. Si el envio falla, muestra el WhatsApp 664 290 852.
- `tucampanalista/gracias.html` — destino tras un envio correcto (redireccion por JS).
  Boton a `https://wa.me/34664290852`.
- `tucampanalista/condiciones.html` — condiciones en version corta (precios destacados y 7 tarjetas: servicio, pago, gasto en Meta, baja, resultados, normas de Meta, datos). El detalle del servicio va en el PDF que se envia por WhatsApp; no ampliar esta pagina.
- `tucampanalista/.htaccess` — `X-Robots-Tag: noindex, nofollow` para toda la carpeta.

Extras del formulario: barra de progreso (preguntas obligatorias), borrador en
`localStorage` (`tcl-alta-borrador`, se borra al enviar bien), errores en rojo
solo tras intentar enviar, `?ref=Nombre` rellena "¿Quien te ha hablado...?",
el usuario de Instagram se limpia si pegan el enlace del perfil.

Requisitos de ocultacion (mantenerlos en cualquier pagina nueva de la carpeta):
`<meta name="robots" content="noindex, nofollow">`, fuera de `sitemap.xml`,
**sin** `Disallow` en `robots.txt` y ningun enlace desde el resto de la web.
Las rutas a recursos van con `../` (logo, favicons, legales).

La politica de privacidad incluye desde el 13-10-2026 la finalidad de alta de
clientes y la comunicacion por telefono/WhatsApp.

### Pendiente

- Guia de alta (misma carpeta).
- Instrucciones de grabacion del video (misma carpeta).
- El repositorio de GitHub es publico: la rama `feat/tucampanalista-alta` no se
  ha subido para no revelar la carpeta. Hacer el repo privado antes de subirla.

Decision (25-10-2026): los contactos de los anuncios NO se envian por email. Cada cliente los revisa a diario en Meta Business Suite. Por eso se quito del formulario la pregunta `recepcion_contactos`.
