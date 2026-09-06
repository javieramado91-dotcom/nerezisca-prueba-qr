# NEREZISCA — prueba de impresión QR en NIIMBOT B1

Página de una sola pantalla que imprime un sticker con un código QR
**directamente desde el navegador** en una impresora NIIMBOT B1, sin usar la
aplicación nativa de la impresora.

Es un banco de pruebas: sirve para verificar el eslabón físico entre un
producto y el sistema.

## Cómo usarla

Abrila desde el enlace de GitHub Pages, prendé la B1 y tocá el botón.

**Requisitos:**

- **Chrome o Edge**, en PC o Android. Firefox y Safari no tienen Web Bluetooth.
- **iPhone y iPad no funcionan.** iOS no implementa Web Bluetooth (Chrome en iOS
  usa Safari por dentro, así que tampoco sirve).
- La página tiene que estar servida por **HTTPS**. Descargar el archivo y abrirlo
  como `file://` no funciona: el navegador bloquea el Bluetooth.

## Qué hay adentro

Un solo archivo, sin dependencias externas ni CDN:

- Generador de códigos QR propio (ISO/IEC 18004, Reed-Solomon sobre GF(256),
  modo byte/UTF-8).
- [niimbluelib](https://github.com/MultiMote/niimbluelib) de MultiMote (MIT),
  que implementa el protocolo de NIIMBOT sobre Web Bluetooth.

El sticker se dibuja a **203 dpi exactos** (la resolución de la B1, cabezal de
384 px = 48 mm imprimibles) y se binariza a blanco y negro puro. El módulo del QR
se fuerza a un número entero de píxeles: si cae en decimales, el código se
deforma y deja de leerse.

## Licencia de terceros

niimbluelib se distribuye bajo licencia MIT. Ver
https://github.com/MultiMote/niimbluelib
