# Sharp Interactive · Enlaces

Página de enlaces de Sharp Interactive, el semillero de IDED en la UPB. Es la que abre el QR de los stickers: pre-inscripción, PDF informativo e Instagram.

Es un sitio estático (HTML, CSS y un poco de JavaScript, sin instalar nada) publicado con GitHub Pages.

Dirección actual: https://organicbrownkid.github.io/sharp-interactive/

## Cambiar un enlace

1. Abre `index.html` en GitHub y pulsa el lápiz (*Edit this file*).
2. Busca el botón y cambia solo lo que va dentro de `href="..."`.
3. Pulsa *Commit changes*. La página se actualiza sola en 1 o 2 minutos.

Si un botón lleva `href="#pendiente"`, se ve apagado y dice "Próximamente". Al poner la dirección real se activa solo.

## Cambiar el PDF

Sube el nuevo archivo a `assets/` con el mismo nombre: `sharp-interactive-estudiantes.pdf`. Así no hay que tocar el código y los enlaces que ya se compartieron siguen funcionando.

## Pasar la página al GitHub de Sharp

Hay dos caminos. Escoge uno.

**A. Transferir este repositorio** (conserva el historial)
1. En este repo: *Settings → General → Danger Zone → Transfer ownership*, y escribe la cuenta u organización de Sharp.
2. Alguien con permisos en la cuenta de Sharp acepta la transferencia.
3. En el repo ya transferido: *Settings → Pages → Branch: `main`, carpeta `/ (root)` → Save*.

**B. Subir el ZIP** (empezar de cero)
1. En la cuenta de Sharp: *New repository*, público, sin README.
2. *uploading an existing file*: arrastra todo el contenido del ZIP descomprimido (no la carpeta, lo de adentro) y pulsa *Commit changes*.
3. *Settings → Pages → Branch: `main`, carpeta `/ (root)` → Save*.

Consejo: si el repositorio se llama exactamente `<cuenta>.github.io` (por ejemplo `sharp-interactive.github.io`), la página queda en `https://<cuenta>.github.io/`, sin subcarpeta.

### Ojo con el QR de los stickers

Los stickers apuntan a `https://organicbrownkid.github.io/sharp-interactive/`, y GitHub Pages **no redirige** cuando un repositorio cambia de dueño.

- **Camino B:** el QR sigue funcionando porque la página original no se mueve. Para no tener que editar las dos copias, convierte la original en una redirección con el código de abajo.
- **Camino A:** la dirección vieja deja de funcionar al transferir. Justo después, crea en la cuenta vieja un repo con el mismo nombre (`sharp-interactive`), activa Pages y deja solo este `index.html`, cambiando `NUEVA-DIRECCION`:

```html
<!doctype html>
<meta charset="utf-8">
<title>Sharp Interactive</title>
<meta http-equiv="refresh" content="0; url=https://NUEVA-DIRECCION/">
<link rel="canonical" href="https://NUEVA-DIRECCION/">
<a href="https://NUEVA-DIRECCION/">Sharp Interactive se mudó. Toca aquí.</a>
```

Cuando cambie la dirección, actualiza también las dos líneas `og:url` y `og:image` al inicio de `index.html` (son las que arman la vista previa al compartir el enlace por WhatsApp).

## Archivos

- `index.html`: la página completa, con estilos y animaciones.
- `assets/logo-*.webp`: las tres partes del logo, sacadas del PSD de la marca. Van separadas para animarlas.
- `assets/sharp-interactive-estudiantes.pdf`: el PDF informativo para estudiantes.
- `favicon.png`, `apple-touch-icon.png`, `og-image.png`: ícono de la pestaña, ícono del celular e imagen para compartir.

## Sobre el diseño

Sigue el manual de marca de Sharp: colores `#051a1e`, `#242f2d`, `#253e2d`, `#79d056` y `#fcfe60`, nada redondo, alto contraste, líneas finas para diagramar y degradados muy suaves.

- **Fuentes:** el logo es imagen (Jersey Sharp no está disponible para web). Los textos usan [Saira](https://fonts.google.com/specimen/Saira) en lugar de TT Mussels, que es de pago. Si el equipo tiene la licencia web de TT Mussels, se cambia en la línea de Google Fonts y en `font-family`.
- **Animación:** el fondo de líneas es SVG y las esquirlas triangulares se dibujan con WebGL, así que se ven nítidas en cualquier pantalla. Si el celular tiene activado "reducir movimiento", la página se queda quieta.
- **Íconos:** dibujados a mano con esquinas rectas. El de Instagram es el oficial de [Bootstrap Icons](https://icons.getbootstrap.com/) (licencia MIT).
