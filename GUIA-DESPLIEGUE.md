# 🚀 Guía de Despliegue — `agency.4homehq.com`

Este paquete contiene todo lo necesario para publicar la página de **4HOME Agency** en el subdominio `agency.4homehq.com`.

---

## 📁 Archivos del Bundle

- [`index.html`](file:///c:/box4home/mi-negocio/agency/index.html) — Landing page B2B principal con wizard interactivo y precios en EUR.
- [`privacidad.html`](file:///c:/box4home/mi-negocio/agency/privacidad.html) — Aviso de privacidad legal.
- [`hero-bg.jpg`](file:///c:/box4home/mi-negocio/agency/hero-bg.jpg) — Fondo optimizado de cabecera.
- [`logo-dark.png`](file:///c:/box4home/mi-negocio/agency/logo-dark.png) — Logotipo de marca.
- [`favicon.png`](file:///c:/box4home/mi-negocio/agency/favicon.png) — Favicon para navegador.
- [`vercel.json`](file:///c:/box4home/mi-negocio/agency/vercel.json) — Configuración de encabezados de seguridad y URLs limpias.

---

## 🛠️ Opción A: Despliegue con Vercel CLI (Recomendado / Inmediato)

1. Abre la terminal en esta carpeta:
   ```bash
   cd c:\box4home\mi-negocio\agency
   ```
2. Ejecuta el comando de despliegue a producción:
   ```bash
   npx vercel --prod
   ```
3. En el panel de control de Vercel del proyecto creado:
   - Ve a **Settings** > **Domains**.
   - Añade el dominio: `agency.4homehq.com`.

---

## 🌐 Configuración DNS en tu Proveedor de Dominio (Cloudflare / Namecheap / Hostinger / GoDaddy)

Añade el siguiente registro DNS en la zona de `4homehq.com`:

| Tipo | Nombre (Host) | Valor (Target) | TTL | Proxy (Cloudflare) |
| :--- | :--- | :--- | :--- | :--- |
| **CNAME** | `agency` | `cname.vercel-dns.com` | Automático | DNS Only (Gris) o Proxied |

---

## 🔗 Endpoint de Captura de Leads

El formulario de calificación wizard envía los leads automáticamente a:
- **URL:** `https://app.4homehq.com/api/agency-leads` (o fallback a `/api/leads`)
- **Angle ID:** `A400`
- **Source:** `agency_4homehq`
- **Campos:** Nombre, Email, Empresa, WhatsApp, Tipo de Solución, Rango Presupuestario y Notas.
