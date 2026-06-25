# Turnio

Landing comercial + demo del sistema de turnos **Turnio**: sistema de turnos online a medida para profesionales de la salud.

## Estructura

```
Turnio/
├── index.html   ← Landing comercial (página principal)
├── demo.html    ← Demo interactiva embebida en la landing (vista paciente + admin)
└── README.md
```

Ambos archivos son **100% estáticos**: no requieren backend, base de datos ni build. Solo HTML + CSS + JS vanilla. La demo guarda los turnos en `localStorage` del navegador del visitante.

## Probar en local

Cualquier servidor estático sirve. Algunas opciones:

**Con Python (viene preinstalado en muchos sistemas)**
```bash
cd Turnio
python -m http.server 8080
# abrir http://localhost:8080
```

**Con Node**
```bash
npx serve Turnio
```

**Sin servidor**: abrir `index.html` directamente con doble clic también funciona (el iframe de la demo va a renderizar bien porque es path relativo).

## Deploy a producción

Al ser estático, hostea gratis en cualquiera de estas plataformas. **Recomendado: Vercel** (tarda 2 minutos).

### Opción 1 — Vercel (recomendado)

1. Subir esta carpeta a un repo de GitHub (`turnio-landing` o similar).
2. Entrar a [vercel.com](https://vercel.com), conectar GitHub.
3. "Import Project" → elegir el repo.
4. Sin configuración: Vercel detecta que es estático y lo deploya.
5. Configurar dominio custom (ej: `turnio.app`) desde Vercel → Domains.

### Opción 2 — Netlify

1. Subir la carpeta a GitHub.
2. [app.netlify.com](https://app.netlify.com) → "Add new site" → "Import from Git".
3. Build command: dejar vacío. Publish directory: `/`.
4. Deploy.

### Opción 3 — Cloudflare Pages

1. Subir a GitHub.
2. [pages.cloudflare.com](https://pages.cloudflare.com) → conectar repo.
3. Sin build command. Output directory: `/`.

### Opción 4 — GitHub Pages

1. En settings del repo: Pages → Source: `main`, folder: `/ (root)`.
2. La landing queda en `https://USUARIO.github.io/turnio-landing/`.

## Antes de publicar — checklist

- [ ] Cambiar el link `https://ROMI-URL-DE-PRODUCCION.com` en `index.html` por la URL real del sistema de Romi (línea ~1199, está marcado con `<!-- TODO -->`).
- [ ] Verificar que el WhatsApp `3492 276388` y el mail `gfabrivelazquez@gmail.com` estén correctos (aparecen en varios lugares).
- [ ] Si querés cambiar el nombre del producto, hacer find-and-replace de `Turnio` en ambos archivos.
- [ ] Opcionalmente reemplazar el dominio placeholder `turnio.app/demo` que se muestra en la barra estilo navegador de la demo (en `index.html`, búsqueda: `turnio.app/demo`).

## Personalización rápida

| Qué cambiar | Dónde |
|---|---|
| Nombre del producto | Find-replace `Turnio` en `index.html` y `demo.html` |
| Color de marca (rosa) | `index.html` → `:root { --pink: #ec4899 }` |
| Color navy | `index.html` → `:root { --navy: #0a1535 }` |
| Tipografía | Link de Google Fonts al inicio + `font-family` |
| Precio | Sección `<section id="precio">` |
| Comparativa vs Docturno | Sección `<section id="comparativa">` |
| Features paciente / admin | Secciones `<section id="funciones">` y `.features-admin` |
| Testimonio Dra. Gigón | Sección `<section id="caso">` |
| WhatsApp y mail | Buscar `wa.me/543492276388` y `gfabrivelazquez@gmail.com` |

## Contacto

Fabri Velázquez — WhatsApp 3492 276388 — gfabrivelazquez@gmail.com
