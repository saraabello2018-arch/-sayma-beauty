# Sayma Beauty — página original conectada a Supabase y Netlify

Esta entrega conserva el diseño original de Sayma Beauty e incorpora catálogo desde la base de datos, inicio de sesión de administrador por correo y contraseña, gestión de productos, pedidos, descuento del 5 % desde $150.000 COP, registro de pedidos y descuento transaccional del inventario. Al cancelar un pedido desde administración, las existencias se restauran una sola vez.

## Antes de publicar

1. En Supabase > SQL Editor, crea una consulta nueva y ejecuta TODO `supabase/schema.sql`. Este archivo es una migración para las tablas que ya creaste, no las borra.
2. En Supabase > Authentication > Users, crea un usuario con tu correo y una contraseña fuerte.
3. En Netlify, crea un sitio desplegando este proyecto desde un repositorio Git (las funciones de servidor no funcionan en un sitio estático subido solo como archivos).
4. En la configuración del sitio Netlify > Environment variables, agrega: `SUPABASE_URL` = URL de tu proyecto; `SUPABASE_SERVICE_ROLE_KEY` = clave `service_role` (solo en Netlify, nunca en archivos ni chats); `ADMIN_EMAILS` = correo exacto del usuario administrador de Supabase.
5. Después de desplegar, vuelve a ejecutar un deploy para que Netlify lea las variables.
6. `config.js` ya contiene la URL y la clave publicable de este proyecto. La clave publicable está diseñada para el navegador; no uses `service_role` allí.

## Limitaciones importantes

- La carga de foto de producto en esta primera conexión se hace pegando una URL pública de imagen. La carga directa desde el celular a almacenamiento en la nube requiere configurar Supabase Storage después.
- WhatsApp solo abre el mensaje preparado; el cliente debe tocar Enviar.
- No se ha configurado una pasarela de pago ni se cobran pagos automáticamente.
- No consideres la tienda lista para recibir ventas reales hasta probar un pedido de prueba y comprobar inventario, permisos y variables de Netlify.
