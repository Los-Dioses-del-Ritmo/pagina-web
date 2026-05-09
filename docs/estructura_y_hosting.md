# Estructura del repositorio y Hosting (GitHub Pages)

Este repositorio contiene un sitio web estático. La carpeta principal que sirve el contenido web es la carpeta `public/`.

## Resumen

- Tipo: sitio estático (HTML, CSS, assets)
- Carpeta principal de entrega: `public/`
- Hosting actual: GitHub Pages (configuración del repositorio)

## Estructura importante (carpeta `public/`)

- `index.html` — página principal
- `styles.css` — estilos globales
- `assets/` — recursos (imágenes, documentos)
- Páginas HTML adicionales: `biografia.html`, `comunidad.html`, `contacto.html`, `enlaces.html`, `galeria.html`, `musica.html`, `noticias.html`, `shop.html`, `shows.html`, `videos.html`, `trayectoria.html`, `identidad.html`, `fundacion.html`, `estrategia.html`, `skeleton.html`

Dentro de `public/assets/` hay subcarpetas como `img/` y `docs/` donde se almacenan imágenes y documentos usados por las páginas.

## Cómo publicar en GitHub Pages

Hay varias opciones para publicar este contenido en GitHub Pages:

### Opción A — Usar la carpeta `docs/` (rápida, sin CI)
1. Copiar el contenido de `public/` a una carpeta `docs/` en el root del repositorio.
2. Commit y push a la rama principal (`main` o `master`).
3. En GitHub: Settings → Pages → Source: `main` branch / `docs` folder.

Comandos de ejemplo (PowerShell o terminal compatible):

```
mkdir docs
cp -r public/* docs/    # en PowerShell `cp -r` funciona; en Windows también puede usarse robocopy
git add docs
git commit -m "Publicar sitio estático en carpeta docs/"
git push
```

### Opción B — Publicar en la rama `gh-pages` (sin mover archivos)
Esto publica directamente el contenido de `public/` en la rama `gh-pages`:

```
git subtree push --prefix public origin gh-pages
```

O alternativamente usar `gh-pages` (paquete npm) o una GitHub Action para automatizar despliegues.

### Opción C — GitHub Actions (recomendado para despliegues automáticos)
Usar una acción como `peaceiris/actions-gh-pages` para desplegar `public/` a `gh-pages` tras cada push o build. Esto es útil si añades un pipeline o paso de build.

## Consideraciones

- Si quieres un dominio personalizado, añade un archivo `CNAME` con el dominio en la raíz publicado.
- Verifica que las rutas de los recursos (imagenes, CSS, JS) sean relativas o apunten correctamente cuando publiques desde una carpeta distinta.
- Si actualizas fotos o assets, recuerda limpiar la caché del navegador o cambiar nombres/versiones para forzar la recarga.

## Dónde editar

- Contenido de las páginas: editar los archivos HTML en `public/`.
- Recursos: `public/assets/`.

Si necesitas, puedo añadir un workflow de GitHub Actions de ejemplo para automatizar el despliegue desde `public/` a `gh-pages`.
