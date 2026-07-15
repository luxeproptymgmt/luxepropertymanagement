# Luxe Property Management — Sitio Web

Sitio web de una sola página (one-page) para una empresa de administración y consultoría de Airbnb de lujo en Puerto Rico. Construido en HTML, CSS y JavaScript puro (sin frameworks ni build step), listo para desplegar en **GitHub Pages**.

---

## 🚀 Despliegue en GitHub Pages (paso a paso)

1. **Crea un repositorio** en GitHub (por ejemplo `luxe-website`).
2. **Sube todos los archivos** de esta carpeta a la raíz del repositorio (incluyendo la carpeta `assets/` y el archivo oculto `.nojekyll`).
3. En GitHub, ve a **Settings → Pages**.
4. En **Source**, elige **GitHub Actions** (recomendado — ya incluye el workflow en `.github/workflows/deploy.yml`).
   - *Alternativa:* elige **Deploy from a branch → main → / (root)**.
5. Espera 1–2 minutos. Tu sitio estará disponible en `https://TU-USUARIO.github.io/TU-REPO/`.

### Dominio personalizado (opcional)
1. Renombra `CNAME.example` a `CNAME` y escribe dentro tu dominio (ej. `luxepropmanagement.com`).
2. En tu proveedor de DNS, apunta el dominio a GitHub Pages.
3. En **Settings → Pages → Custom domain**, ingresa tu dominio y activa **Enforce HTTPS**.

---

## ✅ Configuración necesaria ANTES de publicar

Reemplaza estos marcadores de posición con tus datos reales:

| Qué | Dónde | Buscar y reemplazar |
|-----|-------|---------------------|
| **Formspree** | `index.html` | `YOUR_FORM_ID` → tu ID de Formspree (ver abajo) |
| **Dominio** | `index.html`, `sitemap.xml`, `robots.txt` | `luxepropmanagement.com` → tu dominio real |
| **Teléfono** | `index.html` | `17875550100` y `(787) 555-0100` |
| **Correo** | `index.html` | `luxeproptymgmt@gmail.com` |
| **Redes sociales** | `index.html` (footer) | enlaces de Instagram / Facebook |
| **Fotos de propiedades** | `index.html` | URLs de `images.unsplash.com` → tus fotos reales |
| **Retrato del equipo** | `index.html` (sección "Compromiso") | foto real del equipo |
| **Cifras de confianza** | `index.html` (sección Testimonios) | métricas reales (marcadas como "cifras de muestra") |
| **Testimonios** | `index.html` | reseñas reales de tus propietarios |

### Configurar Formspree (formulario de contacto)
1. Crea una cuenta gratuita en [formspree.io](https://formspree.io).
2. Crea un nuevo formulario y copia su **endpoint** (algo como `https://formspree.io/f/abcdwxyz`).
3. En `index.html`, busca `https://formspree.io/f/YOUR_FORM_ID` y reemplaza `YOUR_FORM_ID` por tu ID.
4. El formulario envía los datos por AJAX y muestra un mensaje de éxito sin recargar la página. Incluye un campo *honeypot* anti-spam.

---

## 📁 Estructura del proyecto

```
.
├── index.html              # Sitio principal
├── 404.html                # Página de error personalizada
├── site.webmanifest        # Manifiesto PWA (íconos, colores)
├── robots.txt              # Instrucciones para buscadores
├── sitemap.xml             # Mapa del sitio para SEO
├── .nojekyll               # Desactiva el procesamiento Jekyll de GitHub
├── CNAME.example           # Plantilla para dominio personalizado
├── assets/
│   ├── favicon.svg         # Favicon vectorial
│   ├── favicon-16.png      # Favicon 16px
│   ├── favicon-32.png      # Favicon 32px
│   ├── apple-touch-icon.png# Ícono para iOS (180px)
│   ├── icon-192.png        # Ícono PWA 192px
│   ├── icon-512.png        # Ícono PWA 512px
│   ├── og-image.svg        # Fuente editable de la imagen social
│   └── og-image.jpg        # Imagen Open Graph (1200×630)
└── .github/workflows/
    └── deploy.yml          # Despliegue automático en cada push
```

---

## 🔍 Características técnicas

- **SEO:** title y meta optimizados, Open Graph, Twitter Cards, hreflang, geolocalización, sitemap y datos estructurados JSON-LD (LocalBusiness, FAQPage, WebSite, BreadcrumbList).
- **Rendimiento:** carga diferida (*lazy loading*) de imágenes de fondo, `preconnect` a CDNs, fuentes con `display=swap`, sin dependencias pesadas.
- **Accesibilidad:** enlace "saltar al contenido", roles ARIA, textos alternativos, navegación por teclado con anillos de foco visibles, soporte de `prefers-reduced-motion`.
- **Seguridad:** Content-Security-Policy, `X-Content-Type-Options`, política de *referrer*, enlaces externos con `rel="noopener"`, honeypot anti-spam.
- **Sin build step:** HTML/CSS/JS puro. No requiere Node, npm ni compilación.

---

## 🧪 Probar localmente

Como es un sitio estático, basta con abrir `index.html` en el navegador. Para una prueba más fiel (rutas absolutas, formulario), usa un servidor local:

```bash
# Python 3
python3 -m http.server 8000
# luego abre http://localhost:8000
```

---

## ✏️ Validar datos estructurados

Antes de publicar, valida el JSON-LD en:
- [Google Rich Results Test](https://search.google.com/test/rich-results)
- [Schema.org Validator](https://validator.schema.org/)

Pega la URL ya publicada o el contenido del `<head>`.

---

© 2026 Luxe Property Management. Todos los derechos reservados.
