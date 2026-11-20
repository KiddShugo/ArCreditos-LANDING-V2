# AR Créditos: sitio web

Sitio estático (HTML, CSS y JavaScript sin framework) publicado en GitHub Pages. No tiene servidor:
todo lo que hace el catálogo ocurre en el navegador del visitante.

## Qué se edita y dónde

| Para cambiar…                                    | Editar                                   |
|--------------------------------------------------|------------------------------------------|
| Número de WhatsApp y textos del mensaje          | `assets/js/config.js`                    |
| Productos, categorías y tipos                    | `assets/data/productos.js`               |
| Fotos de producto                                | `assets/img/productos/` (ver su LEEME)   |
| Textos de las secciones, zonas, preguntas        | `index.html`                             |
| Estilos del header / catálogo / resto            | `assets/css/header.css`, `catalogo.css`, `styles.css` |

Después de cambiar un `.css` o `.js`, subir el número `?v=` de ese archivo en `index.html` para que
los navegadores no usen la versión vieja guardada.

## Cómo está armado

- `assets/data/productos.js`: única fuente de datos del catálogo (112 productos). Cada producto tiene
  un `id` único y estable: no cambiarlo, porque la lista guardada del visitante lo usa.
- `assets/js/catalogo-core.js`: búsqueda, filtros y orden (sin interfaz).
- `assets/js/catalogo.js`: pestañas, buscador, tarjetas, "ver más" y detalle del producto.
- `assets/js/consulta.js`: lista de consulta (se guarda en el navegador con `localStorage`).
- `assets/js/whatsapp.js`: arma todos los enlaces y mensajes de WhatsApp.
- `assets/js/header.js`: header de dos niveles, desplegable de Productos y menú del teléfono.
- `assets/js/ilustraciones.js`: dibujos por tipo de producto, mientras no haya fotos.
- `assets/js/main.js`: animaciones de la página, mapa de zonas y preguntas frecuentes.
- `assets/system.css`, `assets/system.js`, `assets/motion`, `assets/layout`: sistema base de la landing original.

Desde la consola del navegador, `AR.cat.pendientes()` lista los productos con datos por confirmar.

## Lo que necesitaría un servidor (no está hecho)

- Guardar las consultas en una base de datos o mandarlas por mail: hoy se envían solo por WhatsApp.
- Que la lista de un visitante lo siga entre dispositivos: hoy vive en el navegador donde la armó.
- Precios, stock o disponibilidad en tiempo real: hoy se cargan a mano en `productos.js`.
- Un panel para que la empresa edite productos sin tocar archivos.
- Estadísticas de consultas (qué productos se consultan más): se puede sumar Google Analytics o similar.
