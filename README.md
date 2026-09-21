# Paneles productivos del Chaco

Visualizaciones interactivas sobre apicultura y ganadería caprina en la provincia del Chaco,
con detalle departamental, elaboradas a partir de fuentes públicas oficiales.

Cada panel es un archivo HTML autocontenido: los datos y las geometrías están embebidos,
no requiere servidor, dependencias ni conexión a internet.

## Contenido

### `panel-apicola.html`

- **Panorama por provincia** — productores, apiarios y colmenas de las 23 provincias,
  en medidas nominales y relativas.
- **Chaco por departamento** — mapa coroplético de los 25 departamentos con selector de
  variable, tabla ordenable y barra temporal con tres cortes (2022-05-11, 2025-06-25,
  2026-03-17).
- **Exportaciones de miel** — NCM 04090000 por país de destino para 2012, 2025 y 2026
  (enero–agosto), estacionalidad mensual, comparación del precio implícito de Estados
  Unidos contra el resto de los destinos, y origen provincial según la serie OPEX.

### `panel-caprinos.html`

- **Chaco por departamento** — mapa coroplético al corte 31-03-2026 con trece variables
  seleccionables, incluidos tamaño medio de establecimiento e indicadores por habitante.
- **Distribución por estrato de tamaño** — participación del stock según tamaño de majada
  para las cuatro provincias publicadas.
- **Evolución 2008–2026** — serie anual provincial, participación de Chaco en el total
  nacional y ranking provincial por año.

## Fuentes

| Dato | Organismo |
|---|---|
| Apiarios y colmenas por departamento | RENAPA — MAGyP / datos.gob.ar |
| Existencias caprinas | SENASA / Dirección Nacional de Ganadería |
| Exportaciones NCM 04090000 | INDEC / ARCA |
| Origen provincial de las exportaciones (OPEX) | INDEC |
| Población por departamento y apertura urbano/rural | Censo 2022, INDEC (Redatam, variable `URP`) |
| Geometrías departamentales | Instituto Geográfico Nacional (WFS `ign:departamento`) |

## Notas metodológicas

Las limitaciones de cada fuente están señaladas dentro de los paneles. Las principales:

- **Serie apícola departamental.** El DataStore de CKAN no conserva histórico: sobrescribe
  el archivo en cada actualización. Los cortes anteriores a 2026 provienen de capturas del
  Internet Archive, por lo que la serie tiene intervalos irregulares y permite comparar
  niveles, no describir trayectorias.
- **Consistencia entre bases apícolas.** La base provincial y la departamental se publican
  con distinta fecha de corte; sus totales no son comparables entre sí.
- **Desglose caprino por categoría en 2026.** Las columnas `cabra` y `cabrito` presentan
  valores compatibles con un intercambio respecto de los años anteriores. El total no se
  ve afectado y es la variable recomendada para comparación intertemporal. Los valores se
  publican tal como figuran en la fuente, sin corrección.
- **Exportaciones.** Las estadísticas de comercio exterior se publican por país de destino,
  no por provincia de origen; no existe una cifra oficial de miel exportada por Chaco. En
  2025 y 2026 una parte de los registros está alcanzada por el secreto estadístico y se
  agrupa bajo el destino «Confidencial».
- **Estratos de tamaño caprino.** Miden participación del stock de animales, no de
  establecimientos, y sólo existen a nivel provincial.
- **Denominadores poblacionales.** Corresponden a población en viviendas particulares
  (1.124.603 personas en Chaco), un 1,6% por debajo del total censal, que incluye viviendas
  colectivas. La población rural (108.159 personas, 9,6%) suma las categorías rural agrupada
  y rural dispersa de la variable `URP`.

## Uso

Abrir cualquiera de los archivos HTML en un navegador. Los paneles incluyen modo claro y
oscuro, y se adaptan a pantallas de escritorio y móviles.
