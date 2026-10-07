# Mesa · Inventario de restaurante

Página adaptable a celular para agregar productos, registrar entradas y salidas, consultar existencias, mostrar alertas de stock bajo y descargar o importar respaldos JSON.

## Archivos

- `index.html`: página completa; incluye estilos y funciones. No requiere instalación ni compilación.
- `.nojekyll`: permite publicar los archivos como sitio estático.
- `inventario-vacio.json`: respaldo opcional con inventario vacío. Puedes cargarlo mediante «Importar JSON». La página no escribe sobre este archivo automáticamente.

## Publicar en GitHub Pages

1. Crea un repositorio público en GitHub, por ejemplo `inventario-restaurante`.
2. Descomprime el ZIP y sube los archivos de esta carpeta directamente a la raíz del repositorio, mediante «Add file» → «Upload files». No subas únicamente el ZIP ni dejes `index.html` dentro de una subcarpeta. Incluye `.nojekyll` si el explorador lo muestra.
3. Guarda la carga con «Commit changes».
4. Abre «Settings» → «Pages».
5. En «Build and deployment» → «Source», elige «Deploy from a branch».
6. Selecciona la rama `main` (o la rama donde subiste los archivos), la carpeta `/(root)` y pulsa «Save».
7. Espera a que termine la publicación. En esa misma pantalla, GitHub mostrará el enlace del sitio.

Si usaste el nombre de repositorio sugerido, el enlace normalmente tendrá esta estructura: `https://TU-USUARIO.github.io/inventario-restaurante/`. Sustituye TU-USUARIO por tu usuario real. Abre ese enlace desde el celular.

Guía oficial: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Cómo funciona el guardado

Los productos y movimientos se guardan como JSON en el almacenamiento local del navegador. GitHub Pages publica la página, pero no sincroniza el inventario entre teléfonos, computadores ni navegadores y no modifica archivos del repositorio.

Para trasladar tus datos de la versión local a la publicada:

1. En la página que ya usabas, pulsa «Descargar JSON».
2. Abre el enlace publicado e importa ese respaldo con «Importar JSON».
3. Revisa los productos después de importarlos. La importación reemplaza el inventario de ese navegador; no combina inventarios.

Conserva respaldos periódicos: borrar datos del navegador puede eliminar el inventario local. La navegación privada puede borrar los datos al cerrar la sesión. Evita usar varias pestañas a la vez para editar el inventario.

Para compartir cambios automáticamente entre varios dispositivos se necesita añadir almacenamiento en un servidor o una base de datos; esta versión todavía no lo incluye.

## Inventario desde cero y unidades

Esta edición empieza sin productos y utiliza un espacio nuevo del navegador para no cargar los ejemplos anteriores. Los datos de la edición anterior no se eliminan automáticamente; puedes recuperarlos importando un respaldo.

Pulsa «＋ Nuevo producto» para registrar nombre, código único, unidad, cantidad inicial y mínimo de alerta. Las unidades disponibles son arrobas, kilos, litros, unidades y cajas. Todas las medidas permiten hasta tres decimales, con coma o punto (por ejemplo, 2,5 unidades). No hay conversiones automáticas entre medidas.

Para actualizar un repositorio existente, reemplaza `index.html` y `README.md` con estos archivos y conserva `.nojekyll`. Puedes quitar del repositorio el antiguo `inventario-ejemplo.json`, si lo subiste; la página no lo utiliza. No necesitas volver a configurar Pages si ya estaba activo. Espera a que termine la publicación y recarga el enlace.

## Editar y eliminar

Cada producto tiene botones «Editar» y «Eliminar». Puedes cambiar nombre, código, medida, cantidad disponible y mínimo de alerta. Los ajustes de cantidad quedan en el historial. Al cambiar de medida, escribe manualmente las existencias en la nueva medida: no se realiza conversión automática. Los movimientos anteriores conservan su nombre y medida originales.

Eliminar requiere confirmación y retira el producto de la vista del inventario; su registro se conserva archivado en el respaldo JSON para mantener el historial. El botón «Vaciar inventario» sí borra todo el inventario e historial después de confirmar. Los productos archivados conservan su código: para un producto nuevo, usa otro código.

Esta actualización conserva el mismo almacenamiento del navegador que la edición anterior. Antes de actualizar, descarga un respaldo JSON.

## Presentación o contenido

Al crear o editar un producto puedes agregar una descripción opcional de hasta 160 caracteres, por ejemplo «Cada caja trae 12 botellas de 1 litro». Aparece en su tarjeta y se conserva en los respaldos JSON. Es una nota informativa: no convierte cajas en unidades ni cambia cantidades automáticamente. Los respaldos anteriores, sin esta descripción, siguen siendo compatibles.
