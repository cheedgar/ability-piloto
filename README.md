# Ability V6.3 — PWA piloto para Android e iOS

## Objetivo
Distribuir la aplicación mediante HTTPS, instalarla en pantalla de inicio y mantener el generador de licencias V6.1 sin cambios.

## Contenido
- `index.html`: copia de Ability V6.1 con solo metadatos PWA y registro opcional del service worker.
- `manifest.webmanifest`: información de instalación.
- `sw.js`: caché básico para uso sin conexión después de la primera carga.
- `icon-192.png`, `icon-512.png`: iconos provisionales (letra A).

## Publicación sencilla (GitHub Pages)
1. Crea un repositorio NUEVO, preferentemente dedicado a la versión piloto. **Atención: GitHub Pages publica los archivos de forma pública incluso si el repositorio es privado en ciertas modalidades; no publiques secretos ni datos reales de clientes.**
2. Sube el CONTENIDO de esta carpeta a la raíz del repositorio, no el ZIP sin extraer.
3. Settings > Pages > Build and deployment > Deploy from a branch > main > /(root) > Save.
4. Abre la URL HTTPS indicada en Pages (normalmente https://USUARIO.github.io/REPOSITORIO/).
5. iPhone: abre en Safari > Compartir > Añadir a pantalla de inicio. Android: Chrome > menú > Instalar aplicación o Añadir a pantalla principal.
6. En cada dispositivo, copia el identificador, genera su clave con el generador V6.1 y prueba activación y persistencia tras cerrar y reabrir.

## Limitaciones y seguridad
- **NO es una app publicada en App Store/Google Play**. Es una PWA web instalable.
- El identificador es de una instalación/perfil de navegador, **NO un identificador físico seguro del teléfono**. Puede cambiar al borrar datos o al instalar en otro perfil.
- El algoritmo de licencia y su secreto están en el HTML; por tanto un tercero puede estudiarlos. NO es adecuado para cobrar con garantías contra copias ni para impedir activaciones repetidas. Para venta real se requiere servidor de activaciones con validación y revocación.
- La PWA y Safari pueden usar almacenamiento separado. Activar primero en Safari y luego instalar podría requerir nueva clave.
- No se garantiza conservación de datos ante limpieza del navegador, eliminación de la PWA o restricciones de almacenamiento iOS. Usar exportación/importación JSON como respaldo.
- Pruebas pendientes: iPhone real, Android real, exportación/importación, imágenes, WhatsApp, cotizaciones y reinstalación.
- Para clientes reales, la aplicación administrativa pública no ofrece autenticación ni aislamiento de cuentas: NO almacenar datos sensibles sin evaluación adicional.
