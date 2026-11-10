# MusicStore

Sitio estático inicial para catálogo de beats, drumkits y servicios.

## Probar
Abrí `index.html` en un navegador moderno. Desde **Panel admin** podés crear/editar productos, arrastrar portada, MP3 y archivo RAR/ZIP, elegir precios, marcar gratis y configurar redes/colores.

## Importante: qué funciona y qué falta
- El catálogo, reproductor de muestras, panel de edición, arrastrar archivos y tema funcionan en el navegador.
- Desde el panel admin también podés editar tu correo de contacto; aparece como botón de email para que te escriban.
- Los productos y archivos quedan guardados localmente en el navegador que los cargó (IndexedDB/localStorage). No se sincronizan entre dispositivos ni visitantes. Para una tienda pública real se necesita backend + almacenamiento privado.
- Los botones de compra piden correo. El pago solo redirige si cargás un enlace HTTPS de Checkout Pro válido para ese producto.
- No se simula la verificación del pago. Para mostrar “Pago verificado” y entregar archivos automáticamente hay que crear una preferencia de Mercado Pago en un servidor, recibir y validar su webhook, consultar el pago a la API desde el servidor y recién entonces habilitar una descarga privada y enviar el email.
- Nunca publiques el Access Token de Mercado Pago, contraseñas ni claves en el código del sitio.
- Los formularios no envían correos por sí solos; el envío automático necesita un servicio backend/email.
- No uses una transferencia a CVU como señal automática de pago verificado: la web no puede comprobarla sin una integración bancaria/proveedor apropiada.

## Publicar en GitHub Pages
1. Creá un repositorio nuevo en GitHub.
2. Subí `index.html` y este `README.md` a la raíz.
3. En **Settings → Pages**, elegí desplegar desde la rama `main`, carpeta `/ (root)`.
4. GitHub Pages mostrará la URL pública cuando termine el despliegue.

Para un catálogo con ventas reales, agregá backend, base de datos, almacenamiento de archivos, autenticación del administrador y Mercado Pago Checkout Pro + webhook antes de anunciarlo como tienda operativa.
