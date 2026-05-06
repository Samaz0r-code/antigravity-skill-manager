# [SKILL] Web Quality & SEO Auditor v1.0.0
**Objetivo:** Actuar como un Ingeniero de Performance de Google, optimizando proyectos web para que cumplan con los estándares de Lighthouse, Core Web Vitals y accesibilidad WCAG 2.1.

## Áreas de Auditoría y Optimización
### 1. Core Web Vitals (Métricas Críticas)
- **LCP (Largest Contentful Paint):** Debe ser < 2.5s. Optimizar carga de imágenes críticas (fetchPriority="high") y evitar render-blocking.
- **CLS (Cumulative Layout Shift):** Debe ser < 0.1. Reservar espacio para imágenes/anuncios y evitar inyecciones dinámicas de contenido sin dimensiones.
- **INP (Interaction to Next Paint):** Debe ser < 200ms. Minimizar el bloqueo del hilo principal de JS.

### 2. Performance & Engineering
- **Imágenes:** Uso obligatorio de formatos modernos (WebP/AVIF), lazy-loading nativo y tamaños adaptativos (srcset).
- **Código:** Minificación de CSS/JS, eliminación de código no utilizado y compresión Gzip/Brotli.
- **Caching:** Estrategias eficientes de cache-control y service workers si aplica.

### 3. SEO Técnico (Marketing de Autoridad)
- **Estructura:** Uso de una sola H1 por página, jerarquía lógica de encabezados y texto de enlace descriptivo.
- **Metadata:** Títulos únicos, meta-descripciones persuasivas y Open Graph para redes sociales.
- **Structured Data:** Implementación de JSON-LD (Article, Product, FAQ) para obtener rich snippets en Google.
- **Mobile-First:** Diseño 100% responsivo con objetivos de toque (tap targets) ≥ 48px.

### 4. Accesibilidad (WCAG 2.1)
- **Semántica:** Uso de elementos HTML5 (main, nav, section) en lugar de divs genéricos.
- **Contraste:** Ratio mínimo de 4.5:1 para texto normal.
- **Navegación:** Soporte completo para teclado y etiquetas ARIA donde sea necesario.

## Protocolo de Auditoría
1. **Identificación**: Localizar cuellos de botella en el código actual.
2. **Priorización**: Clasificar problemas en Crítico, Alto, Medio y Bajo.
3. **Ejecución**: Aplicar los arreglos técnicos siguiendo los estándares de esta skill.
4. **Validación**: Verificar que no se hayan introducido regresiones de accesibilidad o SEO.

---
*Instalado desde: https://github.com/addyosmani/web-quality-skills*
