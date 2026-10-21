# Web de Foso

Web estática alojada en Cloudflare Pages: portada, privacidad, borrado de cuenta
y la página de los enlaces de invitación a ligas (`/liga/ABC-123`).

Sin compilación ni dependencias: lo que hay en esta carpeta es lo que se publica.

## Publicar

1. Sube esta carpeta a un repositorio de GitHub (por ejemplo `foso-web`).
2. Cloudflare → Workers y Pages → Crear → Pages → Conectar con Git → elige el repositorio.
3. Configuración de compilación: **ninguna** (framework «None», comando vacío, carpeta de salida `/`).
4. Cada cambio que se sube a la rama `main` se publica solo.

## Antes de publicar

- Si el dominio no acaba siendo `foso.pages.dev`, cambia `og:url` y `og:image` en `index.html`.
- Pon esa dirección como `webUrl` en `assets/config.json` de la app y como *Site URL* en Supabase.

## Estructura

- `index.html` — portada con una pregunta de prueba jugable
- `privacidad.html`, `borrar-cuenta.html` — páginas legales (las piden Google Play y App Store)
- `liga.html` — destino de `/liga/*` (ver `_redirects`)
- `tv/` — modo tele (Plató) compilado desde la app con `publicar_web.sh`; `/sala/CODIGO` lleva a unirse desde el móvil
- `404.html` — página no encontrada
- `_headers` — cabeceras de seguridad y caché
- `assets/` — estilos, fuentes (Bricolage Grotesque y Geist, licencia OFL, servidas desde la propia web), iconos e imagen para compartir
