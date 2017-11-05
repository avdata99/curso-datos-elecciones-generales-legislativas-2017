Procesar la carta marina Córdoba 2015
-------------------------------------

Una búsqueda en Google dará con una lista de `recursos en el poder
judicial de Nación sobre
CORDOBA <https://www.pjn.gov.ar/cne/secelec/secciones/otros/otros_view.php?oID=674&dID=4>`__.
Hay de todas las provincias. Lamentablemente son PDFs difíciles de
procesar en general.


Tip de búsqueda
~~~~~~~~~~~~~~~

Si se busca *"Carta Marina" Córdoba* y se agrega además

* *filetype:pdf*: Solo archivos PDF
* *filetype:csv*: Solo archivos CSV
* *filetype:xls*: Solo archivos de Excel
* *site:gov.ar*: Solo sitios de Gobierno en Argentina (sumar además el nuevo gob.ar)

los resultados cambian sensiblemente. Google no sabe que tipo de
archivos buscamos y si solo queremos algunos sitios específicamente (en
este caso, datos oficiales de gobierno).

Allí se encuentra la `Carta Marina Córdoba 2017 en
PDF <https://www.pjn.gov.ar/cne/secelec/document/otros/4-CartaMarina08092017.pdf>`__.

.. figure:: /img/carta-marina-pdf.png
   :alt: carta

Una vez descargado se debe abrir con `Tabula
PDF <http://tabula.technology/>`__. Este producto libre y gratuito
permite pasar tablas a formatos reutilizables de datos.

Como primera prueba se puede seleccionar directamente una parte de la
tabla para analizar si el resultado es útil.

.. figure:: /img/marcando-zona-en-tabula.png
   :alt: marca

Luego del proceso se ven los resultados pasados a una tabla de datos
reutilizable.

.. figure:: /img/primer-intento-tabula.png
   :alt: intento

Se ve que no tomo correctamente las celdas como uno podría imaginar. Se
requiere que cada dato esté en una celda individual. El que construyo el
PDF no lo hizo construyendo una tabla ordenadamente sino que dejo varias
líneas de texto en cada *celda*.

Como prueba adicional se puede usar el detector automático de tablas en
Tabula y ver los resultados.

.. figure:: /img/prueba-2-tabula.png
   :alt: prueba2

Como se ve, la falla es la misma. Este PDF no es procesable de manera que entregue resultados listos para usar. En estos casos las opciones son:

* Si el PDF no es muy largo, tomar estos resultados (o copiar el texto del PDF y pasarlos a un editor de texto) para limpiarlos a mano. 
* Si el PDF es muy largo se puede contar con la colaboración de algún programador que procese automáticamente y obtenga el resultado deseado.
* Si se tienen contactos con algún partido político o con funcionarios de la junta electoral se puede solicitar una versión más amigable (Excel, CSV o similares). 

A los fines de usar Tabula en casos efectivos pueden tomarse dos ejemplos relacionados en casos donde el PDF sí se puede transformar: 

* `NÓMINA DE AUTORIDADES DE MESA -ELECCIONES BALOTAJE 2015 <https://www.pjn.gov.ar/cne/secelec/document/otros/4-04_web_am181115_20h40m.pdf>`__
* `Integración de Alianzas 2015 <https://www.pjn.gov.ar/cne/secelec/document/otros/4-INTEGRACION%20DE%20ALIANZAS%202015%20ELECCIONES%20PASO.pdf>`__


Archivo final
^^^^^^^^^^^^^

Finalmente puede descargarse el archivo CSV para comenzar a trabajar desde `aquí <https://avdata99.github.io/curso-datos-elecciones-generales-legislativas-2017/datos-a-usar/carta-marina/escuelas-elecciones-2017-cordoba-BASE.csv>`__.

