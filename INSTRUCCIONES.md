# Cómo poner la web en marcha

## 0. Instalar (una sola vez)
- **Quarto**: https://quarto.org/docs/get-started/
- **Git**: https://git-scm.com/downloads
- **VS Code** + extensión **Quarto** (buscar "Quarto" en Extensiones).

## 1. Rellenar el marcador que queda
GitHub (vgarcica) y ORCID ya están puestos. Bluesky está desactivado. Para activarlo, en `index.qmd` quita las líneas `<!--` y `-->` que rodean el enlace y cambia `TU_USUARIO_BLUESKY` por tu handle (p. ej. `vgarcica.bsky.social`).

## 2. CV en PDF
Ya está en `files/CV_Victor_Garcia_Carrasco.pdf`. Para actualizarlo, sustituye ese archivo.

## 3. Ver la web en tu ordenador
En VS Code, abre la terminal (Ver → Terminal) y escribe:

    quarto preview

Se abre en el navegador y se recarga sola cada vez que guardas un archivo. Para pararla: Ctrl+C.

## 4. Crear el repositorio en GitHub
En github.com → New repository:
- Nombre: **exactamente** `vgarcica.github.io`
- Public
- Sin README ni .gitignore (vacío)

## 5. Subir el código
En la terminal de VS Code, dentro de la carpeta:

    git init
    git add .
    git commit -m "First version"
    git branch -M main
    git remote add origin https://github.com/vgarcica/vgarcica.github.io.git
    git push -u origin main

La primera vez, VS Code te pedirá iniciar sesión en GitHub desde el navegador.

## 6. Publicar
    quarto publish gh-pages

Responde "Y". Quarto genera la web y la sube a la rama `gh-pages`.

## 7. Activar GitHub Pages (una sola vez)
En el repositorio: Settings → Pages → Source: "Deploy from a branch" → Branch: `gh-pages`, carpeta `/ (root)` → Save.

En 1-2 minutos la web estará en `https://vgarcica.github.io`.

## Para actualizar más adelante
1. Edita los `.qmd` y comprueba con `quarto preview`.
2. Guarda el código:

       git add .
       git commit -m "Describe el cambio"
       git push

3. Publica: `quarto publish gh-pages`

## Dónde está cada cosa
- `index.qmd`: portada (foto, bio, enlaces)
- `projects.qmd`: proyectos
- `research.qmd`: tesis, informe y publicaciones
- `teaching.qmd`: docencia
- `cv.qmd`: CV resumido y botón de descarga
- `styles.scss`: colores y tipografía
- `_quarto.yml`: menú y configuración
