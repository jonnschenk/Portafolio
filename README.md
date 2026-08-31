# Portafolio

Portafolio personal de **Jonathan Ramírez**, diseñado y desarrollado de forma íntegra (diseño UI/UX + front-end) para mostrar proyectos, habilidades y experiencia como desarrollador.

🔗 Demo: [jonnschenk.github.io/Portafolio](https://jonnschenk.github.io/Portafolio/)

## Características

- Diseño responsive, propio y adaptado a mobile/desktop.
- Navegación con menú hamburguesa para pantallas pequeñas.
- Sección de proyectos destacados con detalle individual (ej. proyecto **ALCOBA**).
- Sección "Sobre mí" con enfoque en pensamiento analítico, desarrollo y diseño con propósito.
- Sección de tecnologías/herramientas.
- Descarga directa de CV en PDF.
- Enlaces de contacto (email, GitHub, LinkedIn).

## Tecnologías utilizadas

- **HTML5**
- **SCSS** compilado a CSS3 (diseño propio, sin frameworks en el sitio principal)
- **JavaScript** (interacción del menú de navegación)
- **SCSS**, **Bootstrap 5** y **AOS** (usados en el proyecto destacado ALCOBA)

## Estructura del proyecto

```
Portafolio/
├── index.html          # Página principal
├── pages/               # Páginas internas (about, proyectos, detalle de proyecto)
├── scss/                 # Fuente de los estilos, organizada por página (ver abajo)
├── css/                 # CSS compilado (lo que consumen los .html, no se edita a mano)
├── js/                  # Scripts (navegación)
├── images/              # Recursos gráficos
└── archivos/             # CV descargable (PDF)
```

### Estilos (SCSS)

Los estilos viven en `scss/` y se compilan a `css/`. Cada archivo compilado mantiene su
nombre y ruta (`css/base.css`, `css/styles.css`, `css/about.css`), así que los `<link>` en
los `.html` no cambian.

```
scss/
├── _mixins.scss           # @include tablet { } / @include desktop { } (breakpoints 768px/1024px)
├── base.scss              # -> css/base.css   (reset, variables, header/nav, botones, footer — global)
├── about.scss              # -> css/about.css  (usado solo por pages/about.html)
└── styles.scss             # -> css/styles.css (usado por index.html, proyectos.html y detalle de proyecto)
    └── pages/
        ├── _shared-sections.scss  (.section-card / .section-heading)
        ├── _hero.scss              (hero + collage de index.html)
        ├── _projects.scss          (grid de proyectos: preview en index + listado en proyectos.html)
        ├── _about-teaser.scss      (teaser "Sobre mí" de index.html)
        ├── _tools.scss             (sección tecnologías de index.html)
        ├── _contact.scss           (sección contacto de index.html)
        └── _project-detail.scss    (páginas proyecto-*.html)
```

Cada archivo de `pages/` incluye sus propios ajustes responsive junto a la regla base
(usando los mixins `tablet`/`desktop`), en vez de agruparlos todos al final del archivo.

Para editar estilos: modifica el `.scss` correspondiente y recompila con:

```bash
npm run build:css   # compila una vez
npm run watch:css   # recompila automáticamente al guardar
```

No edites los archivos en `css/` directamente — se sobrescriben en cada build.

## Cómo verlo localmente

1. Clona el repositorio:
   ```bash
   git clone https://github.com/jonnschenk/Portafolio_JR.git
   ```
2. Instala las dependencias (necesarias solo para compilar SCSS):
   ```bash
   npm install
   npm run build:css
   ```
3. Abre `index.html` en tu navegador (o usa una extensión tipo Live Server).

## Autor

Jonathan M. Ramírez

- Email: [jonathanrott.dev@gmail.com](mailto:jonathanrott.dev@gmail.com)
- GitHub: [github.com/jonnschenk](https://github.com/jonnschenk)
- LinkedIn: [linkedin.com/in/jonathan-ramírez](https://www.linkedin.com/in/jonathan-ramírez-2b0043246/)

---

© 2026 Jonathan Ramírez.
