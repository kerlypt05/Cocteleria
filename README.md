# Fundamentos de Coctelería · UBU

Versión publicada para GitHub Pages con:

- **nuevo login visual** basado en la propuesta elegida por el docente;
- **presentación interactiva cifrada**;
- **galería cifrada** con 35 miniaturas;
- **animaciones de diapositivas reactivadas por defecto**.

## Publicación

Sube a la raíz del repositorio estos archivos:

- `index.html`
- `galeria.html`
- `.nojekyll`
- `README.md`

Después activa GitHub Pages desde `Settings → Pages → Deploy from a branch → main → /(root)`.

## Nota técnica sobre las animaciones

La presentación original incluía una lógica de accesibilidad que desactivaba el movimiento si el navegador o el sistema operativo informaban `prefers-reduced-motion: reduce`, o si se había guardado la preferencia local `cocteleria-movimiento = no`.

En esta versión **las animaciones quedan activas por defecto** para conservar las transiciones de gráficos, esquemas y cambios de escena. Solo se desactivarán si el usuario las apaga explícitamente desde la propia presentación.
