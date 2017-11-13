D'Hont
------

En una elección legislativa regida por el sistema D'Hont es importante analizar como es finalmente el reparto de bancas.

Con esta planilla podemos tener los resultados en D'Hont en tiempo real calculados solo combinando algunas fórmulas.

El primer paso es replicar (igualar) en una nueva hoja de nuestro documento los votos finales y el nombre de cada agrupación. Para esto tomamos **los resultados ordenados** que calculamos antes en este curso.

Es importante que primero estén los mvotos y despues la agrupación, esto se comprenderá más adelante.

.. figure:: /img/dhont-01.png
   :alt: dhont-01

En segunda instancia, aplicando la metodología del sistema *D'Hont* obtenemos los cocientes.
Nótese nuevamente el signo *$* para extender la fórmula horizontal (hasta la cantidad de bancas a cubrir) y verticalmente.

En la parte superior debe agregarse una columna por cada banca. Usaremos este número de banca como divisor para el calculo de D'Hont.

::

    =$A2/C$1

.. figure:: /img/dhont-02.png
   :alt: dhont-02

A continuación vamos a hacer algo extraño pero que:

 - evitará la necesidad un programador para el cálculo de bancas
 - se va a entener mejor en los próximos pasos

Tambien replicaremos (igulando para que los cambios se repliquen despues) los valores de cada una de las nueve columnas.

.. figure:: /img/dhont-03.png
   :alt: dhont-03

Replicaremos (igualando) las celdas con los nombres de las agrupaciones hacia abajo.

.. figure:: /img/dhont-03b.png

Finalmente quedarán en una lista vertical todos los *coeficientes* y la agrupación a la que corresponden.
Están marcados con color más claro para indicar que son datos temporales e intermedios para obtener otro resultado más adelante.

.. figure:: /img/dhont-03c.png

Ahora agregamos nuestra tabla de resumen a la derecha donde quedarán
listadas las agrupaciones en posición de obtener la banca.

Para esto hacemos una tabla con las bancas en disputa enumeradas. La función *LARGE* nos da los valores máximos o mínimos en el orden que necesitamos

::

    =large(A$2:A$64;E11)

Note los signos *$* y luego estire la funcion hasta la novena banca.

.. figure:: /img/dhont-04.png
   :alt: dhont-04

A continuación, usando la función *VLOOKUP* **que sólo busca en la
primera columna de un rango dado** es posible saber a que partido le
corresponde un coeficiente.

::

    =VLOOKUP(F11;A$2:B$64;2;false)

Note los signos *$* y luego estire la funcion hasta la novena banca.

.. figure:: /img/dhont-05.png
   :alt: dhont-05

Totales de bancas por agrupación
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Finalmente podemos saber el total de bancas por agrupación. Para esto replicamos (siempre igualando) la lista de agrupaciones.

.. figure:: /img/dhont-06.png

En una columna lateral *total de bancas* usamos la función *COUNTIF* que
permite **contar** elementos que se repiten en una lista. El primer
parámetro es el rango, el segundo el valor buscado.

Note y comprenda la necesidad del signo *$*.

::

    =countif(G$11:G$19; F22)

.. figure:: /img/dhont-06b.png
   :alt: dhont-06


Esta tabla final puede publicarse como tal y publicar para mantener esta información actualziada el día de la elección.

Es conveniente tambien insertar un gráfico con la representación final de las bancas. Este se actualizará ante los cambios en los resultados.

.. figure:: /img/dhont-07.png

