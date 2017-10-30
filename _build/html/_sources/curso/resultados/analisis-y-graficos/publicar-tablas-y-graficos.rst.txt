Publicar tablas y gráficos
--------------------------

Desde Google Drive
~~~~~~~~~~~~~~~~~~

Las planillas de cálculo locales (Excel o Open/LibreOffice) permiten
siempre hacer gráficos. Por su naturaleza on-line, las planillas en
Google Drive permiten además publicar el gráfico en una URL fija en
internet.

Esta característica nos permite tener gráficos listos para embeber en un
medio online muy rápido. Esto funciona no solo para gráficos sino que
incluye tablas de datos (útiles para mostrar junto a los datos).

Como ejemplo vamos a tomar `la planilla que acompaña este curso de
escuelas y electores por circuito
geolocalizada <../recursos/escuelas-elecciones-2015-cordoba-FINAL-CON-GEO.csv>`__.

| Vamos a *publicar* (tabla y gráficos) una lista de las 20 escuelas con
  más electores.
| Para esto ordenamos la planilla por *Electores* de mayor a menor.

.. figure:: /img/ordenando.png
   :alt: ord

   ord

Copiamos los primeros 20 centros de votación y los pegamos (pegar **solo
valores** ya que hay formulas que ya no son convenientes) en una nueva
hoja del documento.

.. figure:: /img/pegar-como-valores.png
   :alt: pegar-como-valores

   pegar-como-valores

Eliminar todas las columnas no necesarias para la publicación, volver a
dat formato. Esta hoja debe tener en el nombre algún indicador que note
que hay información publicada online ya que eliminarla o modificarla
hará que todo el contenido publicado se pierda o se modifique.

.. figure:: /img/tab-publicado.png
   :alt: tab-publicado

   tab-publicado

| Ahora se puede publicar inicialmente la tabla directamente (aunque el
  documento no sea de acceso público).
| Luego de marcar las celdas a publicar y presionar el boton *Insertar
  gráfico* se elige el tipo *Gráfico de tabala*.

.. figure:: /img/grafico-de-la-tabla.png
   :alt: grafico-de-la-tabla

   grafico-de-la-tabla

Finalmente conviene aislar este gráfico a una hoja nueva por prolijidad.

.. figure:: /img/mover-a-hoja-propia.png
   :alt: mover-a-hoja-propia

   mover-a-hoja-propia

... y publicar

.. figure:: /img/publicar-tabla.png
   :alt: publicar-tabla

   publicar-tabla

El `link
recibido <https://docs.google.com/spreadsheets/d/1CMHGvGB59HitcdHfdK_Uj6lU2G3_muC44L_pKoHNqOc/pubchart?oid=988967550&format=interactive>`__
ya está listo para embeberse e insertarse en un sitio web.

El recorrido de la seleccion de la tabla, la inserción del gráfico y la
publicación puede usarse para cualquier tipo de gráfico. Esto es potente
para complementar con múltiples gráficos una nota online.

Algunos ejemplo más:

Gráfico de barras

.. figure:: /img/grafico-barras.png
   :alt: grafico-barras

   grafico-barras

Sugerencia periodística sobre estos datos
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  Buscar el porque de la cantidad de electores muy superior en algunas
   escuelas.
-  Ver escuelas que más cambiaron de electores entres dos elecciones

Con DataStudio
~~~~~~~~~~~~~~

Con `DataStudio <https://datastudio.google.com>`__ de Google tambien es
posible conectar recursos de datos variados (archivos CSV, spreadsheets
de Google y muchos otros).

.. figure:: /img/barras-con-datastudio.png
   :alt: barras-con-datastudio

   barras-con-datastudio

DataStudio permite combinar fuentes de datos y trabajar un poco más
cómodamente que google Spreadsheets

.. figure:: /img/dispersion-escuelas.png
   :alt: dispersion-escuelas

   dispersion-escuelas

| Se puede ver online
  `aquí <https://datastudio.google.com/reporting/0B9saNutQ5ZYhZlpvYXQ2X1JIMVk/page/X7qG>`__.
| #### Pros y Contras Los gráficos de Google Spreadsheets son mejores
  para embeber, los de DataStudio son mejores para compartir como links
  externos.

Con Plot.ly
~~~~~~~~~~~

Plot.ly permite login con redes y es poco invasivo en cuanto a los
permisos.

Como diferencia de las anteriores permite exportar a HTML, esto hace
posible descargar el gráfico completo como contenido estático de modo de
usar esta visualización sin dependencia de la plataforma.

| `Ver diagrama de
  dispersion <export-plot-ly/escuelas-por-departamento.html>`__.
| |plot-ly-scatter|

| Plot.ly apunta a usuarios mas de perfíl estadístico. Además los
  gráficos por defecto tienen zoom, posibilidad de descarga en PNG y
  otros detalles interesantes.
| Por ejemplo este `\_Box Plot\_o \_diagrama de
  cajas <https://es.wikipedia.org/wiki/Diagrama_de_caja>`__ de los
  electores por Departamento (*Sección*):

| `Ver gráfico box
  plot <export-plot-ly/box-plot-electores-por-departamento.html>`__.
| |box-plot-ly|

| Pequeños detalles a destacar de plot.ly. - En los diagramas de cajas
  calcula automáticamente los *quartiles* (a diferencia de drive que
  pide estos valores).
| - En los `*diagramas de
  dispersion* <https://es.wikipedia.org/wiki/Diagrama_de_dispersi%C3%B3n>`__
  plot.ly no exige que ambos ejes sean numéricos. Podemos usar valores
  de texto y serán interpretados como *categorías*.

Otras formas a analizar
~~~~~~~~~~~~~~~~~~~~~~~

Usar App Script para hacer un sitio con D3 que consuma los datos de la
planilla:
`aquí <http://www.benlcollins.com/spreadsheets/d3-google-sheets/>`__

.. |plot-ly-scatter| image:: /img/ploy-ly-scatter.png
.. |box-plot-ly| image:: /img/box-plot-ly.png

