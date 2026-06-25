# Restaurante La Cuestuca — sitio web (single page)

## Estructura
```
la-cuestuca/
├── index.html              # Toda la página (HTML + CSS + JS, un solo archivo)
├── assets/
│   ├── logo.png             # Logo original (fondo blanco, de referencia)
│   ├── logo-mark.png        # Icono del logo, recortado y SIN fondo, en tinta oscura (usado en el menú/cabecera)
│   ├── logo-mark-light.png  # Mismo icono pero en crema, para fondos oscuros (usado en el pie de página)
│   ├── logo-full.png        # Logo completo (icono + texto), sin fondo, tinta oscura
│   └── logo-full-light.png  # Logo completo, sin fondo, en crema — por si lo necesitas sobre fondo oscuro
└── vercel.json               # Configuración de despliegue
```

## Subir a Vercel (sin tocar terminal)
1. Entra en https://vercel.com y crea una cuenta (puede ser con Google o GitHub).
2. Pulsa **"Add New… → Project"**.
3. Elige **"Deploy without Git"** (o arrastra esta carpeta entera a la zona de "Import" si te lo ofrece).
4. Arrastra la carpeta `la-cuestuca` completa (o sube los 3 elementos: `index.html`, `assets/`, `vercel.json`).
5. Pulsa **Deploy**. En menos de un minuto te dará una URL tipo `la-cuestuca.vercel.app`.

## Subir a Vercel (con terminal, más rápido)
```bash
cd la-cuestuca
npx vercel        # primera vez, sigue las preguntas
npx vercel --prod # para publicarlo en la URL definitiva
```

## Antes de publicarlo en serio, pendiente:
- **Fotos reales**: el diseño usa ilustraciones de línea en lugar de fotos (no he podido descargar las fotos de la ficha de Google por derechos de autor). Sustituye los huecos del hero y de "Especialidades" por fotos reales de los platos y del local — mejoran muchísimo el SEO local y la conversión. Guárdalas en `assets/` (ej. `cachopo.jpg`, `terraza.jpg`) y referencia esas rutas en `index.html`.
- **Dominio propio**: si compráis un dominio (ej. `restaurantelacuestuca.es`), cambia las URLs `https://www.restaurantelacuestuca.es/...` que aparecen en las etiquetas `<meta>` y en el JSON-LD por el dominio real, y conéctalo desde el panel de Vercel ("Settings → Domains").
- **Google Business Profile**: enlaza la web desde tu perfil de Google Business y viceversa (botón "Ver opiniones en Google" ya apunta a una búsqueda genérica; puedes cambiarlo por el enlace directo a tu ficha).
- **Imagen para redes (og-image.jpg)**: añade una foto horizontal (1200×630px) en `assets/og-image.jpg` para que se vea bien al compartir el enlace en WhatsApp/Facebook.

## Qué incluye ya para el SEO
- Título y meta descripción con "Comillas" y "Cantabria".
- Datos estructurados `Restaurant` (Schema.org) con dirección, teléfono, horario, valoración y especialidades — ayuda a aparecer mejor en Google y en el Mapa.
- Mapa embebido con la dirección real.
- Enlaces de "Cómo llegar" y "Llamar" listos para usar desde el móvil.
