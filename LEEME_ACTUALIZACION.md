# Actualización del reporte de práctica 01

Conserva Just the Docs, paleta verde, mascota y estructura GitHub Pages del repositorio recibido. Se modificó la copia proporcionada; este ZIP no efectúa un push a GitHub.

## Publicar en el repositorio existente

Extraer y copiar **el contenido** de `repositorio_equipo_tortuga-main` dentro de la raíz del repositorio, aceptando reemplazos. No subir la carpeta contenedora como una subcarpeta. Hacer commit y push a la rama que usa GitHub Pages. En Settings → Pages conservar Deploy from a branch, rama correspondiente y /(root). Revisar que Actions finalice correctamente.

La configuración conserva `url: https://alfredo-merida.github.io/` y `baseurl: /repositorio_equipo_tortuga`. Si se usa otro propietario o nombre, ajustar ambos. No agregar `.nojekyll`: se requiere Jekyll para el tema y las rutas Liquid.

El visor WebGL no usa CDN ni bibliotecas remotas. Carga STL por fetch, por lo que requiere servidor HTTP (GitHub Pages o `python -m http.server 8000` para abrir `viewer.html`). Abrir `file://` no permite cargar geometrías. El servidor Python sirve el visor, pero no compila las páginas Markdown/Liquid; la página completa requiere Jekyll/GitHub Pages.

## Cambios

- Práctica de brazos separada del proyecto de tortuga suave, cuyo contenido se conserva.
- Fotografía real, esquemas SVG editables, 17 STL, cotas envolventes y láminas de referencia.
- Visor WebGL con pieza individual y despiece en cuadrícula; no se afirma un ensamble CAD no recibido.
- Firmware original recuperado, conexiones manual/remoto y vista demostrativa del panel web.
- 31 criterios trazados, con faltantes explícitos y registros CSV para resultados reales.
- Reparación de imágenes inexistentes, enlaces relativos y datos de equipo inconsistentes.

## Límites de validación

No se realizó fabricación, ensayo físico, compilación Arduino ni compilación Jekyll en este entorno. Ver `VALIDACION.md` para las comprobaciones realmente realizadas. No hay evidencias suficientes para afirmar cumplimiento total de la rúbrica.

## Licencias

EEZYbotARM: daGHIZmo, CC Attribution-NonCommercial según licencia original incluida. Las referencias de terceros mantienen sus condiciones; el pie CC BY 4.0 cubre solo documentación del equipo.
