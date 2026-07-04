# CV — Adrián Martínez Fuentes

Currículum web personal, estático y bilingüe (ES/EN), sin dependencias ni build step.

**🔗 Demo:** [amfuentes-dev.vercel.app](https://amfuentes-dev.vercel.app)

## Características

- **Bilingüe (ES/EN)**: toggle de idioma en la esquina superior derecha que reescribe el `textContent` de todos los elementos marcados con `data-es` / `data-en`, sin recargar la página.
- **Sin dependencias**: HTML + CSS + un puñado de líneas de JavaScript vanilla. Sin frameworks, sin bundlers, sin `node_modules`.
- **Responsive**: layout de una sola columna que se adapta a móvil (breakpoint en 560px).
- **Imprimible**: hoja de estilos `@media print` dedicada para generar un PDF limpio directamente desde el navegador (Ctrl+P).
- **Tema oscuro** por defecto, con paleta de acento configurable vía variables CSS.

## Estructura

```
.
├── index.html   # Contenido y estructura (una sola página, todas las secciones)
├── styles.css   # Estilos, variables de tema y media queries
├── favicon.ico
└── Curriculum-Vitae-ES.pdf   # CV en PDF (fuente de la información del sitio)
```

## Desarrollo local

No requiere instalación. Basta con abrir `index.html` en el navegador, o servirlo con cualquier servidor estático:

```bash
python -m http.server 8000
# o
npx serve
```

## Actualizar contenido

Todo el contenido vive en `index.html`, organizado en `<section>` (Sobre Mí, Habilidades, Experiencia, Formación, Honores y Premios, Proyectos, Idiomas, Certificaciones).

Para que un texto sea traducible, añade los atributos `data-es` y `data-en` al elemento con el texto en cada idioma; el script de `setLang()` se encarga del resto:

```html
<span data-es="Texto en español" data-en="Text in English">Texto en español</span>
```

El contenido del sitio debe mantenerse sincronizado con `Curriculum-Vitae-ES.pdf`, que es la fuente de referencia.

## Despliegue

Sitio estático: cualquier hosting de archivos estáticos (Vercel, GitHub Pages, Netlify...) sirve directamente `index.html` sin configuración adicional.
