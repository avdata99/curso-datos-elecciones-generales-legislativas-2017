Primeros ejercicios
-------------------

Con la finalidad de familiarizarse con la lógica de esta planilla de cálculo se realizarán las siguientes tareas sobre la planilla:

Ordenar 
^^^^^^^
Averiguar cual es el centro de votación con más electores

.. figure:: /img/ordenar-sheet.png

Total 
^^^^^

Calcular el total de electores en la Provincia de Córdoba. 
Se debe **usar siempre el signo = al inicio** para indicar que una celda contendrá un calculo o *función*
Aquí se introduce a las funciones, en este caso la función **SUM** (SUMA si se usa la versión en español de las funciones). Las funciones pueden usar (como en este caso) *rangos* además de celdas.

Las funciones pueden tener uno o más *parámetros* según su cometido. En este caso la función *SUM* solo requiere un parámetro, el rango de celdas a sumar.

Un rango se define por la celda de inicio y de final separadas por el signo de *dos puntos*. Ejemplos de rangos:

* A2:A9
* C3:F3 (puede ser horizontal)
* B15:C90 (puede tener mas de una fila o columna contenida) 

.. figure:: /img/sumar-sheet.png

Promedio de electores por escuela
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Calcular cual es el promedio de electores por centro de votación

.. figure:: /img/promedio-electores.png


Promedio de electores por mesa
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Agregar una columna que indique el *promedio* de electores por mesa. Para esto es necesario conocer como funciona una planilla de cálculo.
Cada *celda* puede usarse o llamarse desde *funciones* o calculos desde otras celdas. 
En este caso necesitamos dividir el total de electores (celda **I2** para el primer centro de votación) de cada centro por su total de mesas celda **F2**.

.. figure:: /img/eletores-por-mesa.png

Revisar la forma de *estirar* celdas calculadas para replicar un cálculo o función. 


Cantidad de escuelas con más de 5.000 electores
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Función::

   =COUNTIF(J2:J1212; ">5000")

La funcion COUNTIF (*contar si* se cumple alguna condición) tiene dos parámetros. La forma de escribir funciones es *= (signo igual)* seguido del nombre de la función. Luego entre paréntesis se colocan los parámetros. Estos son los insumos para que la función realice su tarea. En este caso son dos parámetros separados por punto y coma (podría ser coma según la *regionalización* elegida)

Filtrar
^^^^^^^

Es posible elegir cuales *filas* de esta tabla mirar definiendo *filtros* basados en cualquiera de las columnas. Por ejemplo uno podría mirar los centros de votación de un circuito electoral específico y hacer análisis más particulares.
Datos -> Filtro

Conclusiones
^^^^^^^^^^^^

Como se ve, el lenguaje de las planillas de cálculo esta enriquecido por funciones específicas que nos ayudan a obtener nueva información de los datos. Conocer la lógica de celdas de estas planillas y el alcance de las decenas de funciones existentes pueden permitir rápido y facil obtener información util de cualquier conjunto de datos.

La combinación de filtros, ordenamientos, funciones y visualizaciones debe permitirle al analista encontrar la información que busca.

Ejericicios opcionales
^^^^^^^^^^^^^^^^^^^^^^

* Buscar cuantas escuelas tienen la palabra *Sarmiento* incluida en su nombre.
* Pensar en algún análisis que pueda ser interesante basado en estos datos.
* Repetir los análisis hechos sobre la `Carta marina de 2015 <https://gobiernoabierto.cordoba.gob.ar/data/datos-abiertos/categoria/sociedad/cartas-marinas-electorales/213>`__ a modo de comparación.

