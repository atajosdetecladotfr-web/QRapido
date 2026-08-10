# QRápido

Convierte usuario y contraseña en un código QR listo para escanear, en vez de digitarlos a mano.

**Todo ocurre en el navegador.** No hay backend, ni API externa, ni base de datos: las credenciales nunca salen del dispositivo de quien genera el código.

## Cómo funciona

1. La persona abre `index.html` (o el link de GitHub Pages) en su propio navegador.
2. Escribe su usuario y contraseña.
3. Al enviar el formulario, el QR se genera localmente en un `<canvas>` usando la librería vendorizada `qrcode.min.js`.
4. La imagen se descarga automáticamente como PNG y se abre el diálogo de impresión del navegador.

El contenido del QR es exactamente:

```
USUARIO\tCONTRASEÑA\n
```

(`\t` = tabulador, `\n` = enter — para autocompletar formularios de login al escanear con un lector configurado como teclado).

## Archivos

| Archivo | Qué es |
|---|---|
| `index.html` | Página completa: estructura, estilos y lógica |
| `qrcode.min.js` | Librería [`qrcode`](https://github.com/soldair/node-qrcode) de Ryan Day, empaquetada para navegador. Licencia MIT incluida en el propio archivo. |

## Publicar en GitHub Pages

1. Sube estos dos archivos a la raíz de un repositorio (o a una carpeta `docs/` — lo que configures en el paso 2).
2. En **Settings → Pages**, selecciona la rama y carpeta donde están los archivos, y guarda.
3. GitHub entrega la URL pública en unos minutos, con HTTPS automático.

## Seguridad

- No subas al repositorio capturas, imágenes QR o commits con credenciales reales.
- El nivel de corrección de errores del QR está en `H` (alto), para que tolere manchas o dobleces al imprimirse.
- Un QR generado aquí equivale a una contraseña impresa: no debe compartirse ni dejarse a la vista.

## Licencia

El código de este proyecto (`index.html`) se distribuye bajo licencia MIT — ver `LICENSE`.
`qrcode.min.js` mantiene su propia licencia MIT original (Ryan Day y colaboradores), incluida como comentario al inicio del archivo.
