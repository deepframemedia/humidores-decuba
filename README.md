# DECUBA — Humidores de Cuba
### Rediseño Web · Landing Page + About Us

Rediseño completo de [humidoresdecuba.com](https://humidoresdecuba.com) — tienda artesanal de humidores de madera cubana fundada en 1995 en Pinar del Río, Cuba. Proyecto desarrollado con HTML/CSS/JS puro, sin frameworks ni dependencias externas.

---

## Archivos

| Archivo | Descripción |
|---------|-------------|
| `index.html` | Landing page principal — hero, productos, taller, galería, carrito |
| `about.html` | Página de historia — timeline, premios, fundador, presencia global |

---

## Stack técnico

- **HTML5** semántico con roles ARIA
- **CSS3** con custom properties (design tokens), Grid, Flexbox, `position: sticky`, `IntersectionObserver`
- **JavaScript** vanilla — sin dependencias externas
- **Fuentes:** Google Fonts — Playfair Display + Cormorant Garamond
- **Imágenes:** servidas directamente desde `humidoresdecuba.com/wp-content/uploads/`

---

## Sistema de diseño

### Paleta de colores

| Token | Hex | Uso |
|-------|-----|-----|
| `--bg` | `#0D0A07` | Fondo principal |
| `--surface` | `#1A1008` | Superficies / cards |
| `--tobacco` | `#3D1F0A` | Secciones cálidas |
| `--gold` | `#C9A84C` | Acento principal |
| `--gold-light` | `#E8C97A` | Acento hover / precios |
| `--cream` | `#F5ECD7` | Texto principal |
| `--cream-dim` | `rgba(245,236,215,0.55)` | Texto secundario |

### Tipografía

| Variable | Fuente | Uso |
|----------|--------|-----|
| `--font-display` | Playfair Display | Headlines, títulos, botones |
| `--font-body` | Cormorant Garamond | Cuerpo de texto, subtítulos |

---

## Secciones — index.html

### Navbar
- Sticky + transparente sobre el hero, oscurece al hacer scroll (`scrollY > 60`)
- Logo "DE CUBA" en Playfair Display dorado
- Links: Colección · Taller · Historia · Contacto
- Icono de carrito con contador animado (badge con efecto bump)

### Hero
- Full viewport height (`100vh`)
- Imagen real de textura de madera cedro desde la web original
- Tipografía display en 3 niveles: eyebrow · headline · subtítulo
- Animaciones de entrada escalonadas (CSS `@keyframes fadeUp`)
- Indicador de scroll animado

### Producto Destacado
- Grid asimétrico 1:1 con `gap: 8rem`
- Imagen del humidor con hover zoom
- Badge circular dorado (edición limitada)
- Specs en grid 2x2 con separadores dorados

### Nuestro Taller
- **Columna izquierda sticky** (`position: sticky; top: 7rem`) — año 1995 + cita del fundador
- Columna derecha: texto real de DECUBA + estadísticas reales
- Galería full-width de 4 fotos en fila (grid 4 columnas)
- **Lightbox** al hacer clic: navegación ←→, ESC para cerrar, teclado soportado

### Colección de Productos
- Grid 3 columnas responsive
- 6 productos con imágenes reales del sitio
- Datos en `data-attributes` por card: imagen, colección, nombre, descripción, material, capacidad, acabado, origen
- Botón **"Ver Detalles"** → abre modal
- Botón **"+"** → añade directo al carrito con feedback visual
- Botón **"Ver toda la Colección"** al pie, enlaza a `humidoresdecuba.com/tienda/`

### Modal de Producto
- Overlay con blur de fondo
- Grid imagen + info
- Specs en 4 campos
- Botón "Añadir al carrito" con animación de ítem volando al icono del carrito
- Cierre por: botón ×, click fuera, tecla ESC

### Banner CTA
- Imagen de lifestyle (puro + cognac) con overlay oscuro
- Headline + subtítulo + dos CTAs

### Footer
- Grid 4 columnas: marca · colección · la marca · contacto
- Datos de contacto reales
- Iconos sociales SVG

### WhatsApp flotante
- Botón verde fijo `bottom: 2rem; right: 2rem`
- Animación pulse continua (`@keyframes waPulse`)
- Enlace directo con mensaje pre-escrito

---

## Secciones — about.html

### Hero
- 70vh con imagen de madera rústica
- Overlay degradado hacia abajo
- Headline: "Rescatando el arte de dos tradiciones"

### Sobre DECUBA (Intro)
- Grid 2 columnas: texto + imagen del taller
- Lead en Playfair Display italic
- Descripción real: ebanistería + tabaco, cedro cubano (*Cedrela Odorata*), Pinar del Río

### Misión & Visión
- Dos cards con borde dorado
- Textos literales de la web oficial de DECUBA

### Estadísticas

| Cifra | Dato |
|-------|------|
| 30+ años | Experiencia artesanal |
| 3.000+ | Piezas únicas creadas |
| 147 | Puntos Casa del Habano abastecidos |
| 75+ | Países con presencia |
| 70+ | Eventos internacionales |

### Timeline (9 hitos)

| Año | Hito |
|-----|------|
| 1995 | Fundación por Jorge Luis Milán Domínguez |
| 2000 | Primeras exportaciones · presencia en 75+ países |
| 2002 | Licencia oficial Habanos S.A. · Habanos Collection 3.000 piezas |
| 2008 | Premio Artesanía Artística — FCBC |
| 2013–2015 | Premio Mejor Exportador — Ferias Internacionales |
| 2018 | Premio Categoría de Producto |
| 2020 | Actor clave en sustitución de importaciones |
| 2023 | Reconocimiento Medioambiental — CITMA |
| 2024 | Mejor Stand Design — Festival del Habano XXIV |

### Premios
Grid 3x2 con los 6 reconocimientos oficiales

### Presencia Global
- 4 items: países · Casas del Habano · licencia Habanos S.A. · eventos
- Fondo con imagen lifestyle semitransparente

### Fundador
- Jorge Luis Milán Domínguez — biografía y filosofía reales
- Quote en overlay dorado sobre imagen

---

## Animaciones

| Nombre | Trigger | Descripción |
|--------|---------|-------------|
| `fadeUp` | CSS load | Hero eyebrow, title, subtitle |
| `reveal` | IntersectionObserver | Todas las secciones al entrar en viewport |
| `scrollPulse` | CSS loop | Indicador de scroll en hero |
| `modalIn` | JS class `.open` | Entrada del modal (scale + fadeUp) |
| `flyArc` | JS click carrito | Ítem volando del modal al icono del carrito |
| `cartBump` | JS addToCart | Efecto bump en el contador del carrito |
| `waPulse` | CSS loop | Pulse continuo del botón WhatsApp |
| `waPulse` | CSS loop | Pulse continuo del botón WhatsApp |
| Lightbox | JS click | Fade-in del overlay de galería |

---

## Imágenes utilizadas

Todas servidas desde `https://humidoresdecuba.com/wp-content/uploads/`

| Archivo | Uso |
|---------|-----|
| `rich-wood-grain-texture-with-dynamic-light-shadow-play.jpg` | Hero background |
| `rough-old-wooden-retro-background-...png` | Hero about.html |
| `Group-1171275008.png` | Producto destacado (featured) |
| `Group-1171275007.png` | Card producto 1 |
| `Group-1171275009-2.png` | Card producto 2 |
| `Group-1171275009-3.png` | Card producto 3 |
| `1000114547-01-scaled.jpeg` | Card producto 4 |
| `1000114553-01-1-scaled.jpeg` | Card producto 5 |
| `1000114539-01-1.png` | Card producto 6 |
| `473089192_...n.jpg` | Galería taller / Intro about |
| `472964171_...n.jpg` | Galería taller |
| `473115984_...n.jpg` | Galería taller |
| `WhatsApp-Image-2026-02-18-at-2.42.03-AM.jpeg` | Galería taller |
| `WhatsApp-Image-2026-02-18-at-2.44.29-AM-1.png` | Foto fundador about |
| `burning-cigar-in-ashtray-and-cognac-...png` | Banner CTA / Reach about |
| `pexels-ian-panelo-32796580-scaled.jpg` | Disponible para uso futuro |

---

## Datos de contacto reales (DECUBA)

| Campo | Valor |
|-------|-------|
| Email | humidoresdecuba@gmail.com |
| Email alt. | milandc2020@gmail.com |
| Teléfono | +53 50 993 108 |
| Teléfono alt. | +53 48 758866 |
| WhatsApp | [wa.me/5350993108](https://wa.me/5350993108) |
| Dirección | Cuba, Pinar del Río, Reparto Cuba Libre, Pascual Martí No. 197 |
| Web original | [humidoresdecuba.com](https://humidoresdecuba.com) |

---

## Workflow Git

```bash
# Subir cambios
git add .
git commit -m "descripción del cambio"
git push

# Ver historial
git log --oneline
```

**Repositorio:** [github.com/deepframemedia/humidores-decuba](https://github.com/deepframemedia/humidores-decuba)

---

## Pendientes / Ideas futuras

- [ ] Página de producto individual por humidor
- [ ] Integración real con WooCommerce o sistema de pedidos
- [ ] Formulario de contacto funcional
- [ ] Versión en inglés (mercado internacional)
- [ ] Optimización de imágenes (WebP local, lazy loading mejorado)
- [ ] Animaciones de scroll más elaboradas (GSAP)
- [ ] Página de encargos personalizados

---

*Desarrollado con Claude Code — Anthropic*
