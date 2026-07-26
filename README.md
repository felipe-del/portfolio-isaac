# Portafolio Personal – Isaac Brenes

Sitio web estático construido con **Nuxt 3/4**, desarrollado para la tarea
"Sitio Web Personal Estático" del curso Arquitectura de Información
(Universidad Nacional).

## 🔗 Sitio publicado

> **Completar antes de subir al AulaVirtual:**
> `https://TU-SITIO.netlify.app`

## Páginas

| Ruta          | Archivo                     | Descripción                                   |
|---------------|------------------------------|------------------------------------------------|
| `/`           | `app/pages/index.vue`        | Inicio: presentación y resumen profesional      |
| `/sobre-mi`   | `app/pages/sobre-mi.vue`     | Experiencia laboral, formación y certificaciones|
| `/proyectos`  | `app/pages/proyectos.vue`    | Proyectos Full Stack destacados                 |
| `/blog`       | `app/pages/blog.vue`         | Artículos y bitácora técnica                    |
| `/contacto`   | `app/pages/contacto.vue`     | Formulario de contacto y otros canales          |

Layout compartido en `app/layouts/default.vue` (encabezado con navegación
tipo "pestañas de editor" + pie de página tipo barra de estado), usado por
todas las páginas mediante `<NuxtLayout>` en `app/app.vue`.

Cada página define su propio título y meta descripción con `useHead()`.

## Requisitos

- Node.js 18+
- npm

## Instalación y desarrollo local

```bash
npm install
npm run dev
```

Abre `http://localhost:3000`.

## Generar sitio estático

```bash
npm run generate
```

Nitro detecta automáticamente el entorno de destino: en tu máquina genera el
sitio en `.output/public`, pero al construir sobre la infraestructura de
Netlify (variable de entorno `NETLIFY`) lo genera en `dist`. El
`netlify.toml` de este proyecto ya está configurado para ese caso.

## Despliegue en Netlify

**Opción A — Arrastrar y soltar:**
1. Ejecuta `npm run generate` en tu máquina.
2. Entra a [app.netlify.com](https://app.netlify.com) → *Add new site* →
   *Deploy manually*.
3. Arrastra la carpeta `.output/public` generada (ese es el nombre cuando
   generas localmente, fuera del entorno de Netlify).

**Opción B — Desde un repositorio Git (recomendado):**
1. Sube este proyecto a GitHub/GitLab (sin `node_modules`, ver `.gitignore`).
2. En Netlify: *Add new site* → *Import an existing project*.
3. Build command: `npm run generate`
   Publish directory: `dist`
   (ya configurado en `netlify.toml`).

## Estructura del proyecto

```
portfolio-isaac/
├── app/
│   ├── app.vue                # Punto de entrada, monta el layout
│   ├── layouts/default.vue    # Header + footer compartidos
│   ├── pages/                 # Rutas automáticas de Nuxt
│   │   ├── index.vue
│   │   ├── sobre-mi.vue
│   │   ├── proyectos.vue
│   │   ├── blog.vue
│   │   └── contacto.vue
│   └── assets/css/main.css    # Tema visual (paleta, tipografías, estilos base)
├── public/                    # Estáticos (favicon, robots.txt)
├── nuxt.config.ts
└── netlify.toml
