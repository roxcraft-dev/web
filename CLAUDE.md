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
- `privacy-policy.html` — política de privacidad de Nexo Sleep Timer. Enlazada
  desde la tarjeta de la app en la sección *Proyectos*.
- `CNAME` — dominio personalizado de GitHub Pages.

Las maquetas y borradores de diseño (`*.dc.html`, `support.js`) están en
`.gitignore` y no forman parte del sitio publicado.

## Criterios de diseño

- **Modo oscuro permanente.** El sitio no tiene tema claro ni conmutador de tema.
  No añadir bloques `@media (prefers-color-scheme: light)`.
- Paleta base: fondo `#121316`, texto `#F2F1EE`, texto secundario `#8B8E94`,
  bordes `rgba(255,255,255,.09)`, acento de marca `#7C83FF`.
- Tipografías (Google Fonts): `Space Grotesk` para títulos, `Inter` para texto,
  `Outfit` en las tarjetas de proyecto y `JetBrains Mono` para etiquetas en
  versalitas (eyebrows, badges).
- CSS embebido en cada página mediante variables en `:root`. No hay hoja externa.
- Contenido en español.

## Estado del contenido

Los literales actuales de la sección *Proyectos* son provisionales y se
revisarán más adelante. Las apps de la familia **Nexo** figuran como
*Próximamente*.
