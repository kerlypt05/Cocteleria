# Fundamentos de Coctelería · UBU

Repositorio público preparado para GitHub Pages: **HTML cifrado**, sin archivos fuente en claro.

- `index.html`: puerta de acceso y presentación interactiva de 35 diapositivas con sus imágenes, esquemas, PDF de fichas y controles integrados.
- `galeria.html`: puerta de acceso y galería con miniaturas autocontenidas. Sus enlaces abren la presentación en la diapositiva seleccionada.
- `.nojekyll`: desactiva Jekyll en GitHub Pages.

**Publicación:** en GitHub → Settings → Pages → Build and deployment → Deploy from a branch → `main` → `/(root)` → Save.

**Dirección prevista:** https://kerlypt05.github.io/Cocteleria/

**Acceso:** clave distribuida mediante el canal docente. No la guardes en el repositorio ni en su historial de commits. Las páginas usan AES-256-GCM y PBKDF2-SHA256 con 600 000 iteraciones. La contraseña no se almacena en el repositorio. La sesión solo utiliza sessionStorage del navegador, que puede permanecer abierto durante toda la sesión de la pestaña.

**Limitación:** es cifrado de material estático, no autenticación individual ni control de permisos, y quien conozca la clave puede obtener una copia del material. Para impedir la redistribución, revocar usuarios o restringir por cuenta se requiere servidor de autenticación/proxy y acceso privado a los contenidos.

**Mantenimiento:** conserva los archivos editables originales **fuera** del repositorio público. Para actualizar el material hay que reconstruir los HTML y volverlos a cifrar con la herramienta local. No publiques las fuentes sin cifrar junto a estas páginas.
