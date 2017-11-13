Poligonos de Secciones y Circuitos
----------------------------------

Para poner en mapas datos más agregados (por circuito o sección
electoral) se requieren los *polígonos* o puntos que los representan.

Secciones electorales
~~~~~~~~~~~~~~~~~~~~~

La secciones electorales (depratamentos) tienen una definición clara y
están disponibles desde el
`GeoPortal <https://datosestadistica.cba.gov.ar/organization/geoportal>`__
de la Provincia de Córdoba.

.. figure:: /img/geoportal.png

El GeoPortal incluye muchos datos útiles, en este caso tienen `una
sección <https://datosestadistica.cba.gov.ar/dataset/provincia-mapas-capas-y-tablas>`__
que inluye (entre otros datos útiles) los *poligonos* de los
departamentos de la Provincia.

El formato usado en general por el GeoPortal es el SHP
(`*shapefile* <https://es.wikipedia.org/wiki/Shapefile>`__). Este
formato es usado en ambientes técnicos y todavía no compatible con otras
herramientas más simples de este curso.

Los departamentos de Córdoba en SHP pueden descargarse desde
`aquí <https://datosestadistica.cba.gov.ar/dataset/6b0e69cb-71c4-4064-82ac-69d8aab6c7b3/resource/2d99c688-f49f-4391-b8a4-e0bfd8bf91c2/download/capa-provincial-cordoba-division-censal-departamentos-2010-shp.zip>`__. Con una `copia local aquí <https://avdata99.github.io/curso-datos-elecciones-generales-legislativas-2017/datos-a-usar/geo/capa-provincial-cordoba-division-censal-departamentos-2010-shp.zip>`__

.. figure:: /img/geoportal-poligonos.png
   :alt: geoportal-poligonos

En `el portal de Gobierno Abierto de la Ciudad de Córdoba <https://gobiernoabierto.cordoba.gob.ar/data/datos-abiertos/categoria/datos-geograficos-y-mapas/departamentos-de-la-provincia-de-cordoba/214>`__ se replica este datos y se agrega un mapa online y otros formatos más fáciles de reulizar.

.. figure:: /img/departamentos-cordoba-portal-muni.png
   :alt: departamentos-cordoba-portal-muni
   :target: https://gobiernoabierto.cordoba.gob.ar/data/datos-abiertos/categoria/datos-geograficos-y-mapas/departamentos-de-la-provincia-de-cordoba/214

Los archivos CSV con WKT pueden ser difíciles de editar con planillas de cálculo simples. Para esto es útil usar versiones que asumiendo alguna perdida de calidad en los datos son versiones simplificadas y fáciles de manipular. Para este curso se ha dispuesto `una versión simplificada <https://avdata99.github.io/curso-datos-elecciones-generales-legislativas-2017/datos-a-usar/geo/departamentos-poligonos-simplificado-WKT.csv>`__ de los polígonos de los departamentos de la Provincia de Córdoba.

Circuitos electorales
~~~~~~~~~~~~~~~~~~~~~

Los circuitos electorales de la provincia de Córdoba al parecer no están
disponibles en formatos de polígonos en su totalidad.

La Ciudad de Córdoba publica los polígonos de sus circuitos electorales
(Córdoba es a la vez sección/departamento y una ciudad). Pueden verse y
descargarse `aquí <https://gobiernoabierto.cordoba.gob.ar/data/datos-abiertos/categoria/legislacion/seccionales-y-circuitos-electorales/212>`__.

A diferencia de la provincia incluye un mapa online y múltiples formatos
más simples de reutilizar por audiencias no especializadas.

La realidad del resto de la provincia de Córdoba es compleja. Más del
80% del territorio provincia no pertenece a ningún municipio y los
territorios que si pertenecen se encuentran en disputas actualmente.

`Ver más info <https://andresvazquez.com.ar/blog/los-municipios-de-cordoba-no-existen/>`__

.. figure:: /img/radios-municipales-cordoba.png

El recurso más aproximado que aparece son los puntos de *localidades
censales* de 2010 que se encuentra en el mismo GeoPortal de la Provincia
de Córdoba: `SHP Localidades Censales 2010 <https://datosestadistica.cba.gov.ar/dataset/provincia-mapas-capas-y-tablas>`__. Dejamos una `copia local <https://avdata99.github.io/curso-datos-elecciones-generales-legislativas-2017/datos-a-usar/geo/capa-provincial-cordoba-localidades-censales-2010-shp.zip>`__ en este repositorio.

El problema con este recurso es que las *localidades censales* son más
parecidas a una lista de asentamientos humanos que no diferencia las
delimitaciones de ciudades o circuitos electorales.
