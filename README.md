# Fundamentos de Coctelería · UBU

Sitio web docente del Grado en Ciencias Gastronómicas, Universidad de Burgos. Material de clase de Prof. Kerly Palacios.

**Dirección prevista cuando se active GitHub Pages:** https://kerlypt05.github.io/Cocteleria/

## Estructura de publicación

- `index.html`: presentación interactiva cifrada con 35 diapositivas, imágenes, PDF de fichas técnicas y evaluación, simulaciones y controles de la clase.
- `galeria.html`: galería cifrada con 35 miniaturas; permite abrir una diapositiva concreta.
- `.nojekyll`: archivo de configuración para servir el sitio estático.

**Pendiente:** cargar los dos HTML de publicación en la raíz de la rama `main`. Están en el paquete `Cocteleria_GitHubPages_PUBLICAR.zip` generado a partir del material docente original. No subas el ZIP original con las fuentes sin cifrar.

Después, en GitHub, abrir **Settings → Pages → Build and deployment**; seleccionar **Deploy from a branch** → **main** → **/(root)** → **Save**. La dirección prevista se activará cuando GitHub Pages termine el despliegue.

## Acceso

El acceso usa **AES-256-GCM**, con una clave derivada por **PBKDF2-SHA256 (600 000 iteraciones)**. No se guarda la contraseña en el repositorio. Las páginas cifradas son autocontenidas: imágenes, miniaturas y PDF están integrados en el contenido protegido. El navegador recuerda la clave durante la sesión de la pestaña, salvo al cerrar sesión.

**Seguridad real:** este método cifra el contenido estático, pero no identifica a cada estudiante, no impide capturas o redistribución del material por quienes conozcan la clave y no sustituye el control de acceso de un servidor privado. Para revocar usuarios individualmente se necesitaría autenticación gestionada por servidor.

## Edición y actualización

Las fuentes editables se mantienen **fuera** de GitHub público. Al modificar el material, hay que regenerar el HTML autónomo y cifrarlo de nuevo mediante el script local de mantenimiento. No subas `src/`, `assets/`, `vistas/` ni el HTML original sin cifrar al repositorio público.

