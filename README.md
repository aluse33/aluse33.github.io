# Mi web académica (Quarto)

Una web personal al estilo de https://www.uv.es/beneito/, hecha con [Quarto](https://quarto.org).
En la portada, la plantilla `trestles` pone la foto y los enlaces a la izquierda y el texto a la derecha.

## Estructura

```
_quarto.yml          ← configuración: título, menú, pie, tema
styles.scss          ← estilos (fuente Lato, botones, línea vertical)
index.qmd            ← portada (about / trestles)
research.qmd         ← working papers y publicaciones
projects.qmd         ← listado automático de todo lo que haya en projects/
projects/<nombre>/index.qmd   ← cada proyecto o notebook es una carpeta
teaching.qmd, media.qmd
files/               ← foto, CV.pdf, papers, favicon (se copian tal cual)
docs/                ← la web ya generada (lo que se publica)
```

## Puesta en marcha

1. Instala Quarto: https://quarto.org/docs/get-started/ (en RStudio ya viene incluido).
2. Abre una terminal en esta carpeta y ejecuta:
   ```
   quarto preview
   ```
   La web se abre en el navegador y se recarga cada vez que guardas un archivo.
3. Busca y sustituye `TU NOMBRE`, `Tu Nombre`, `TU-USUARIO` y el resto de textos de ejemplo.
4. Sustituye `files/profile.svg` por tu foto, por ejemplo `files/profile.jpg`, y cambia
   `image:` en `index.qmd`. Sustituye también `files/CV.pdf` por tu CV, con el mismo nombre.

## Cosas útiles

- **Otra plantilla de portada.** Cambia `template: trestles` por `jolla`, `solana`, `marquee` o `broadside`.
- **Iconos.** Se usan los nombres de https://icons.getbootstrap.com (`linkedin`, `github`, `envelope`…).
- **Añadir un proyecto.** Copia la carpeta `projects/piaac-primeros-pasos`, cambia el título, la fecha y las categorías, y aparecerá solo en *Projects*.
- **Ejecutar código.** Un bloque ```` ```{r} ````, ```` ```{python} ```` o ```` ```{stata} ````
  (este último con `nbstata`) se ejecuta al renderizar. Con `freeze: auto` solo se vuelve a
  ejecutar cuando cambias ese archivo, así que la web se puede reconstruir sin tener los datos.
- **Datos de PIAAC.** El `.gitignore` ya excluye `data/`, `*.dta` y `*.sav` para que no subas microdatos al repositorio.

## Publicar gratis en GitHub Pages

1. Crea un repositorio en GitHub, por ejemplo `mi-web`, y sube esta carpeta.
2. Ejecuta `quarto render`, que regenera `docs/`, y haz commit + push.
3. En GitHub ve a *Settings → Pages → Deploy from a branch*, elige `main` y la carpeta `/docs`.
4. La web quedará en `https://TU-USUARIO.github.io/mi-web`. Pon esa dirección en `site-url` dentro de `_quarto.yml`.

Para un servidor de la universidad, sube el contenido de `docs/` por FTP o SFTP.
