Analizando los datos del ministerio del interior
------------------------------------------------

Luego de procesar los datos de la elección es el momento de ordenar estos datos y visualizarlos.

Resultados totales provincia por lista
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Como primer análisis vamos a ver y ordenar los datos totales por provincia.

La lista de totales por agrupación representa los votos a todas las agrupaciones desagregado por sección electoral pero tiene un **detalle o falla**. Si se suma la columna de votos el total resultante es **el doble de los votos reales**. Esto se debe a que la tabla al final tiene la sección 999 que representa el total provincial. Esto no esta bien visto en el mundo de las bases de datos, duplicar información que podría obtenerse simplemente sumando los departamentos no es útil. 

Podemos ver estos datos haciendo un filtro (menú *Datos* opción *Filtro*) para ver solo la *Sección* 999 (que representa totales provinciales) puede verse así:

.. figure:: /img/viz-resultado-provincial-por-listas.png


Para separar estos datos hacemos una nueva hoja en la planilla de cálculo y *linkeamos* estos datos. Sabemos que la planilla subida siempre tendrá la misma cantidad de filas por lo que podemos en este nueva hoja usar el signo *=* para vincular estas celdas con el contenido de la tabla original.

Esto es particularmente útil si esperamos actualizar (pisando los datos) de la primera hoja cada 5 o 10 minutos. **Nuestra idea es desarrollar resultados, análisis y visualizaciones que se actualicen automáticamente cada vez que actualicemos datos en la hoja original**.

La nueva hoja podrá verse así.

.. figure:: /img/viz-resultado-provincial-por-listas2.png

En la hoja de totales podemos ver una de las columnas que incluye el porcentaje de la agrupación, este número
viene sin decimales.
Parece una mala idea esta forma de publicación por dos motivos:

 - Es un dato que podemos calcular nosotros simplemente dividiendo los votos de cada agrupación por el total de votos.
 - Por que necesitaríamos dividirlo por 100 para saber el porcentaje real.

Es por esto que agregamos una columna extra al final con la formula que corresponde.

La fórmula es:

::

    =I2/sum(I2:I8) * 100

Nótese que podemos hacer fórmulas que incluyan operaciones matemáticas simples y funciones en la misma celda.

Esa formula puede estirarse para completar hasta el final. Analizar la
necesidad de los signos *$* en las fórmulas.

.. figure:: /img/viz-resultado-provincial-por-listas-02.png
   :alt: viz-resultado-provincial-por-listas-02

Lo que necesitamos a continuación son los nombres de las agrupaciones.
Si bien podemos hacerlo a mano es bueno conectarlo a la lista accesoria
con los nombres de las agrupaciones incluidas.

La función *VLOOKUP* (Vertical Lookup) permite dado un código devolver
datos relacionados a ese mismo código en otra tabla. En este caso
tenemos el código de la agrupación y en una tabla accesoria dos datos
(nombre y descripción) de la agrupación.

La formula para la primera fila.

::

    =VLOOKUP(H2;agrupaciones!A$2:B$158;2;FALSE)

**Nótese** nuevamente la necesidad del signo *$*.

Debe quedar así:

.. figure:: /img/viz-resultado-provincial-por-listas-03.png
   :alt: viz-resultado-provincial-por-listas-03

Es necesario ordenar estos datos según la cantidad de votos que irá
cambiando durante el día de la elección. Para es útil la función *sort*.

Debajo de la lista anterior podemos poner la fórmula:

::

    =SORT(H2:L8;2;false)

.. figure :: /img/ordenando-resultados.png


La función SORT lleva 3 parámetros (6 si fueramos a ordenar por una segunda columna luego de la primera). El primer parámetro es el rango de celdas a ordenar. El segundo es el número de orden de la columna que vamos a tener como referencia para ordenar y finalmente el tercero es solo TRUE o FALSE según se haga un orden ascendente o no.

Se generará automáticamente una nueva lista con los datos ordenados.
Estos se actualizarán automáticamente cuando los datos cambien.

Prueba
~~~~~~

Si cambiamos manualmente los resultados totales (sección 999) en la hoja inicial veremos como esta lista final
se reordena convenientemente.

Esta tabla de resultados ordenados es un ejemplo de dato de interés para publciar como gráfico tipo tabla en algún sitio web.

Visualizar
~~~~~~~~~~

Con las herramientas usadas para publicar y visualizar
planillas es posible publicar en tiempo real esta tabla y un gráfico.

.. figure:: /img/viz-resultados-01.png
   :alt: viz-resultados-01

Probar en la lista original de resultados y ver como se reordena la lista y se actualizan los gráficos. 



