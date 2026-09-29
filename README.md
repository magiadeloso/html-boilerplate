# HTML Boilerplate

Plantilla `index.html` base para proyectos web. Este documento explica **por qué** existe cada etiqueta.

> Los valores (`example.com`, `styles.css`, `font.woff2`, colores, etc.) son marcadores: reemplázalos. Elimina lo que tu sitio no use (feeds, búsqueda, manifest).

## Estructura base

| Etiqueta | Por qué |
|---|---|
| `<!doctype html>` | Declara HTML5 y evita el *quirks mode*, para que el navegador renderice según el estándar. |
| `<html lang="es">` | Declara el idioma (etiqueta RFC 5646). Lo usan lectores de pantalla (pronunciación), traductores automáticos y el motor tipográfico (guionado, comillas). Cámbialo según tu contenido. |

## `<head>`: esencial

| Etiqueta | Por qué |
|---|---|
| `<meta charset="UTF-8">` | UTF-8 es la única codificación válida en HTML5. Va primero (dentro de los primeros 1024 bytes) para que el contenido siguiente no se corrompa. |
| `<meta name="viewport" content="width=device-width">` | Hace que los móviles rendericen al ancho del dispositivo en lugar de simular un escritorio reducido. Base del diseño responsive. |
| `<meta name="text-scale" content="scale">` | Permite que el texto siga la escala de texto del sistema (accesibilidad). Tu CSS debe usar unidades relativas para no romper el layout. |
| `<title>` | Obligatorio. Se muestra en pestañas, marcadores y resultados de búsqueda. Formato recomendado: página primero, sitio después. |

## `<head>`: recursos

| Etiqueta | Por qué |
|---|---|
| `<link rel="stylesheet">` | Cargar CSS desde el HTML evita las cascadas de `@import`, donde un CSS debe procesarse antes de descubrir el siguiente. |
| `<link rel="preload" as="font" ... crossorigin>` | Descarga la fuente crítica pronto, evitando parpadeos de texto. `crossorigin` es obligatorio para fuentes aunque sean del mismo origen. WOFF2 es el formato más ligero y soportado. |

## `<head>`: SEO y redes sociales

| Etiqueta | Por qué |
|---|---|
| `<meta name="description">` | Resumen para buscadores. Ya no siempre se muestra, pero sigue siendo señal útil. |
| `og:title` | Título para embeds (Open Graph). Sin el nombre del sitio porque las plataformas lo muestran aparte (`og:site_name`). |
| `og:description` | Descripción para redes y chats; conviene que sea breve y atractiva, distinta de la del SEO. |
| `og:image` (+ `alt`, `type`, `width`, `height`) | Imagen del embed. 1200×630 funciona en casi todas las plataformas; WebP equilibra compresión y soporte. Declarar tamaño y tipo evita que la plataforma tenga que descargarla para calcularlos. El `alt` no lo soportan todas, pero es buena práctica. |
| `<link rel="canonical">` + `og:url` | Indican la URL oficial de la página para evitar contenido duplicado (parámetros, variantes) y concentrar el posicionamiento. |
| `og:site_name` | Nombre del sitio junto al título en los embeds. |
| `<meta name="author">` | Autoría de la página; informativo, no obligatorio. |

## `<head>`: apariencia

| Etiqueta | Por qué |
|---|---|
| `<link rel="icon" type="image/svg+xml">` | Favicon SVG: escala a cualquier tamaño, admite modo claro/oscuro y evita generar múltiples PNG. |
| `<meta name="color-scheme" content="light dark">` | Declara soporte de ambos temas, de modo que el navegador use fondos/controles oscuros desde el inicio y evite el destello blanco antes de cargar el CSS. |
| `<meta name="theme-color" media="...">` | Colorea la barra del navegador (Android Chrome, PWA). El `media` permite un color distinto por tema. |

## `<head>`: descubrimiento e integración

| Etiqueta | Por qué |
|---|---|
| `<link rel="alternate" type="application/rss+xml">` / `feed+json` | Autodescubrimiento de feeds: lectores y navegadores detectan la suscripción automáticamente. |
| `<link rel="search" type="application/opensearchdescription+xml">` | Expone la búsqueda del sitio al navegador (buscar desde la barra de direcciones). |
| `<link rel="manifest">` | Manifiesto PWA: nombre, iconos y comportamiento al instalar la web en la pantalla de inicio. |

## `<body>`

| Etiqueta | Por qué |
|---|---|
| `<header><nav></nav></header>` | Estructura semántica para la cabecera y la navegación principal; los lectores de pantalla pueden saltar entre regiones. |
| `<main id="main">` | Contenido principal único de la página. El `id` permite enlaces "saltar al contenido" para teclado y lectores de pantalla. |
| `<footer id="footer">` | Metadatos del sitio, enlaces secundarios y avisos legales. El `id` permite un ancla "ir al pie". |

## Notas

- Las etiquetas Open Graph usan `property`; el resto usa `name`.
- Este `index.html` está en español (`lang="es"`); el original está en inglés.
