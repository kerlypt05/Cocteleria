# Fundamentos de Coctelería · UBU

Versión publicada para GitHub Pages con:

- **acceso rediseñado** sobre la fotografía de barra a sangre completa, con el formulario acotado en tarjeta;
- **presentación interactiva cifrada** (`index.html`);
- **galería cifrada** con 35 miniaturas (`galeria.html`);
- **animaciones de diapositivas activas por defecto**.

## Publicación

Sube a la raíz del repositorio estos archivos:

- `index.html`
- `galeria.html`
- `hero.jpg`
- `hero-mobile.jpg`
- `.nojekyll`
- `README.md`

Después activa GitHub Pages desde `Settings → Pages → Deploy from a branch → main → /(root)`.

> Las dos imágenes `hero*.jpg` deben estar en la misma carpeta que los HTML. Si faltan, el acceso
> sigue funcionando: la vista cae automáticamente a un fondo degradado oscuro.

## La vista de acceso

- **Una sola imagen de fondo.** `hero.jpg` (1672 × 941) ocupa toda la pantalla en escritorio y
  `hero-mobile.jpg` es un recorte vertical para móvil, servido con `<picture>` según el ancho.
- **Tarjeta acotada.** El formulario vive en un panel de ancho fijo (≈430 px) situado sobre la zona
  oscura central-derecha de la fotografía, de modo que el bartender queda a la izquierda y el
  bodegón de cócteles a la derecha sin quedar tapados.
- **Sin accesos anexos.** La vista no enlaza a otras páginas: la clave es la única vía de entrada.
  El cierre de sesión sigue disponible añadiendo `?salir` a la dirección.
- **Texto neutro.** No se menciona ninguna titulación concreta, porque el material se imparte
  también al grupo de Tecnología de los Alimentos.

### Funciones del formulario

| Función | Detalle |
|---|---|
| Aviso de Bloq Mayús | Se muestra mientras la tecla está activada, causa habitual de fallo |
| Mostrar / ocultar clave | Botón con icono de ojo y estado `aria-pressed` |
| Estado de verificación | El botón se bloquea y muestra un indicador giratorio durante el descifrado |
| Errores accesibles | `role="alert"` con `aria-live`, más una vibración breve de la tarjeta |
| Gestores de contraseñas | `autocomplete="current-password"` conservado |
| Foco automático | Solo en escritorio, para no abrir el teclado en móvil |
| Movimiento reducido | Se respeta `prefers-reduced-motion` |

## Cifrado

Cada página incrusta su propio documento cifrado con **AES-GCM 256** y clave derivada por
**PBKDF2-SHA256 con 600 000 iteraciones**. El rediseño de la vista de acceso **no modifica ni el
objeto cifrado ni la clave**: el bloque `const D={…}` se conserva byte a byte respecto a la versión
anterior.

## Nota técnica sobre las animaciones

La presentación original incluía una lógica de accesibilidad que desactivaba el movimiento si el
navegador o el sistema operativo informaban `prefers-reduced-motion: reduce`, o si se había guardado
la preferencia local `cocteleria-movimiento = no`.

En esta versión **las animaciones quedan activas por defecto** para conservar las transiciones de
gráficos, esquemas y cambios de escena. Solo se desactivarán si el usuario las apaga explícitamente
desde la propia presentación.
