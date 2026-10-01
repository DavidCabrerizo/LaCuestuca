# Restaurante La Cuestuca — Sitio Web v3

## Estructura de archivos

```
lacuestuca-v3/
├── index.html                    ← Página principal
├── aviso-legal.html              ← Aviso Legal (LSSI-CE art. 10)
├── politica-privacidad.html      ← Política de Privacidad (RGPD + LOPDGDD)
├── vercel.json                   ← Configuración de despliegue en Vercel
└── assets/
    ├── fonts/                    ← Fuentes autoalojadas (sin Google Fonts)
    │   ├── fraunces-500.woff2
    │   ├── fraunces-600.woff2
    │   ├── fraunces-900.woff2
    │   ├── inter-400.woff2
    │   ├── inter-500.woff2
    │   ├── inter-600.woff2
    │   ├── inter-700.woff2
    │   ├── spacemono-400.woff2
    │   └── spacemono-700.woff2
    ├── favicon.ico               ← Favicon clásico (pestaña navegador)
    ├── favicon-32.png            ← Favicon PNG 32×32
    ├── favicon-192.png           ← Favicon PNG 192×192 (Android)
    ├── apple-touch-icon.png      ← Icono iOS (añadir a pantalla inicio)
    ├── logo.png                  ← Logo original (fondo blanco, referencia)
    ├── logo-mark.png             ← Icono solo, sin fondo, tinta oscura
    ├── logo-mark-light.png       ← Icono solo, sin fondo, en crema
    ├── logo-full.png             ← Logo completo, sin fondo, tinta oscura
    └── logo-full-light.png       ← Logo completo, sin fondo, en crema
```

---

## Cómo subir a Vercel

### Opción A — Sin terminal (arrastrando)
1. Entra en https://vercel.com e inicia sesión.
2. Pulsa **Add New… → Project**.
3. Elige **Deploy without Git**.
4. Arrastra la carpeta `lacuestuca-v3` completa a la zona de subida.
5. Pulsa **Deploy**. En menos de un minuto tienes la URL activa.

### Opción B — Con terminal
```bash
cd lacuestuca-v3
npx vercel        # primera vez: sigue las preguntas
npx vercel --prod # para publicar en la URL definitiva
```

---

## Qué incluye y para qué sirve cada cambio

### ✅ Fuentes autoalojadas
Las fuentes Fraunces, Inter y Space Mono se sirven desde el propio servidor de Vercel, dentro de `assets/fonts/`. **Ya no se realiza ninguna conexión con Google Fonts**, lo que elimina la transferencia de IP del visitante a Google en cada carga de página (exigido por el RGPD desde la sentencia LG München I de enero de 2022).

### ✅ Google Maps con consentimiento previo
El mapa no se carga automáticamente. El visitante ve un aviso con un botón «Activar mapa». Solo al pulsarlo se establece la conexión con Google Maps. Si el usuario ya lo activó en una visita anterior, el mapa carga directamente (se guarda en localStorage del navegador, sin cookies). Cumple el estándar «two-click solution» recomendado por la AEPD.

### ✅ Precio con IVA
El rango de precios (20–30 €) incluye la indicación «IVA incl.», obligatoria en hostelería según el RD 3484/2000.

### ✅ Aviso Legal
Página en `/aviso-legal` con los datos del titular (nombre, NIF, domicilio y email), redactada según el artículo 10 de la LSSI-CE (Ley 34/2002). Accesible desde el pie de página.

### ✅ Política de Privacidad
Página en `/politica-privacidad` redactada según el RGPD (Reglamento UE 2016/679) y la LOPDGDD (LO 3/2018). Cubre: responsable del tratamiento, datos de navegación (IP), Google Maps bajo consentimiento, fuentes autoalojadas, ausencia de cookies propias y derechos del usuario (acceso, rectificación, supresión, portabilidad, oposición, limitación). Accesible desde el pie de página.

### ✅ Banner de alérgenos
Aviso visible en la parte superior de la página principal que invita a los comensales con alergias o intolerancias a comunicárselo al personal antes de pedir. Cumple con el Reglamento UE 1169/2011 sobre información alimentaria al consumidor.

---

## Estado legal tras esta versión

| Área                          | Estado     | Norma                        |
|-------------------------------|------------|------------------------------|
| Aviso Legal                   | ✅ Resuelto | LSSI-CE art. 10              |
| Política de Privacidad        | ✅ Resuelto | RGPD + LOPDGDD               |
| Google Fonts (IP a Google)    | ✅ Resuelto | RGPD                         |
| Google Maps sin consentimiento| ✅ Resuelto | RGPD art. 6 + guía AEPD      |
| Precio con IVA                | ✅ Resuelto | RD 3484/2000                 |
| Alérgenos                     | ✅ Resuelto | Reglamento UE 1169/2011      |
| Accesibilidad (WCAG 2.1 AA)   | ⚠️ Pendiente| RD 1112/2018                 |
| Canal derechos RGPD (email)   | ✅ Resuelto | RGPD art. 12–22              |

---

## Pendiente para el futuro

- **Dominio propio**: si se compra un dominio (`restaurantelacuestuca.es` o similar), actualizar las URLs en las etiquetas `<meta>` del `index.html` (og:url, og:image, canonical) y en el JSON-LD, y conectarlo desde el panel de Vercel en Settings → Domains.
- **Foto para redes (og-image.jpg)**: añadir una foto horizontal (1200×630 px) en `assets/og-image.jpg` para que el enlace se vea bien al compartirlo en WhatsApp o redes sociales.
- **Accesibilidad**: revisar contraste de textos con WebAIM Contrast Checker y añadir atributos `alt` más descriptivos en los iconos SVG de las especialidades.
- **Analítica**: si en el futuro se añade Google Analytics u otra herramienta, será necesario implementar un banner de cookies (CMP) como Cookiebot, Axeptio o Iubenda.
- **Revisión anual**: la Guía de Cookies de la AEPD se actualiza periódicamente. Se recomienda revisar el cumplimiento una vez al año.

---

## Datos del titular (para referencia interna)

Titular: Natalia Montes Suárez  
Domicilio fiscal: Calle Antonio López, bajo s/n, 39520 Comillas, Cantabria  
Email de contacto web: bareljubilado@gmail.com  
Teléfono restaurante: 942 72 04 95
