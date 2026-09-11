# RoxCraft-dev — Web

Sitio web público de **RoxCraft-dev**, desarrollador Android independiente.

## Repositorio

- **Remoto:** `roxcraft-dev/web` (organización `roxcraft-dev`).
- **Dominio:** `roxcraft.dev`, servido por GitHub Pages desde la rama `main`.
  El fichero `CNAME` de la raíz contiene el dominio: **no se debe borrar ni renombrar**,
  o el dominio personalizado deja de resolver.

### Regla de ramas (importante)

**Nunca commitear ni pushear directamente a `main`.** `main` es la rama publicada:
todo lo que entra ahí sale en producción de forma inmediata. El trabajo se hace
siempre en ramas de tipo `feat/...` o `fix/...`, y es rodri quien decide cuándo
se integra en `main`.

## Estructura

Sitio estático, sin build ni dependencias. Se abre directamente en el navegador.

- `index.html` — página principal: cabecera, sección *Proyectos* y pie.
- `nexosleeptimer/index.html` — página de la app Nexo Sleep Timer, servida en
  `roxcraft.dev/nexosleeptimer/`. Se llega a ella desde la tarjeta de la app en
  la sección *Proyectos* de la home.
- `nexosleeptimer/privacy-policy.html` — política de privacidad de Nexo Sleep
  Timer, bilingüe español / inglés.
- `nexosleeptimer/capturas/` — capturas de pantalla de la app, numeradas por el
  orden en que aparecen en la sección *Capturas* de su página.
- `nexosleeptimer/logo.svg` — logo de la app, portado de
  `ic_launcher_foreground.xml` del proyecto Android. Se usa como favicon de las
  dos páginas de Nexo Sleep Timer. La home **no lleva favicon** a propósito:
  RoxCraft-dev todavía no tiene logo propio de desarrollador, y el de una app
  concreta no representa al sitio entero.
- `privacy-policy.html` — **fichero temporal.** No contiene la política: es solo
  una redirección (`meta refresh`) hacia `nexosleeptimer/privacy-policy.html`,
  que es donde vive el documento desde que se creó la página de la app. Existe
  para no romper la URL antigua `roxcraft.dev/privacy-policy.html`, que puede
  estar declarada en la ficha de Google Play o enlazada desde dentro de la app.
  **Pendiente:** una vez confirmado en Play Console que la ficha apunta a la URL
  nueva, este fichero se borra.
- `CNAME` — dominio personalizado de GitHub Pages.

Los enlaces entre páginas del sitio son **relativos** (`nexosleeptimer/index.html`,
`../index.html`), nunca absolutos con barra inicial (`/nexosleeptimer/`): así el
sitio se puede probar en local abriendo el HTML directamente con `file://`, sin
levantar un servidor.

Las maquetas y borradores de diseño (`*.dc.html`, `*-maqueta.html`,
`support.js`) están en `.gitignore` y no forman parte del sitio publicado.

## Criterios de diseño

- **Modo oscuro permanente** en la home y en las páginas de app. No hay tema
  claro ni conmutador de tema; no añadir bloques
  `@media (prefers-color-scheme: light)`.
- **Excepción:** la política de privacidad conserva a propósito su paleta clara y
  serif propia (fondo `#fbfaf7`, acento `#2f6f5e`). Es un documento legal con
  identidad propia: **no unificar sus colores con los de la home.**
- Paleta base: fondo `#121316`, texto `#F2F1EE`, texto secundario `#8B8E94`,
  bordes `rgba(255,255,255,.09)`, acento de marca `#7C83FF` y acento secundario
  `#B07CFF`. Los dos acentos son los del logo de Nexo.
- Tipografías (Google Fonts): `Space Grotesk` para títulos, `Inter` para texto,
  `Outfit` en las tarjetas de proyecto y `JetBrains Mono` para etiquetas en
  versalitas (eyebrows, badges).
- CSS embebido en cada página mediante variables en `:root`. No hay hoja externa.
- Contenido en español.

## Estado del contenido

Los literales actuales de la sección *Proyectos* son provisionales y se
revisarán más adelante.

De la familia **Nexo**, solo **Nexo Mouse & Keyboard Bluetooth** figura como
*Próximamente*. **Nexo Sleep Timer** ya está publicada en Google Play
(`com.roxcraft.nexosleeptimer`) y tiene página propia.

### Pendientes

- Borrar `privacy-policy.html` de la raíz cuando Play Console apunte a la URL
  nueva de la política (ver *Estructura*).
- La home no tiene favicon: falta un logo de RoxCraft-dev como desarrollador,
  distinto del de cualquier app concreta.
