D'Hont
------

Luego de `ordenar los datos de la
elección <analizar-datos-ministerio-interior-e-Indra.md>`__ es el
momento de ordenar estos datos y visualizarlos.

| Podemos tener los resultados en D'Hont en tiempo real calculados solo
  combinando fórmulas de Google Drive.
| El primer paso es replicar (igualar) en una nueva hoja de nuestro
  documento los votos finales y el nombre de cada agrupación:

.. figure:: /img/dhont-01.png
   :alt: dhont-01

   dhont-01

| En segunda instancia, aplicando la metodología del sistema *D'Hont*
  obtenemos los cocientes.
| Nótese nuevamente el signo *$* para extender la fórmula horizontal
  (hasta la cantidad de bancas a cubrir) y verticalmente.

::

    =$A2/C$1

.. figure:: /img/dhont-02.png
   :alt: dhont-02

   dhont-02

A continuación vamos a hacer algo extraño pero que: - evitar necesitar
un programador para el cálculo - se va a entener mejor en los próximos
pasos

| Replicaremos (igualando) las celdas con los nombres de las
  agrupaciones 9 veces hacia abajo.
| Tambien replicaremos (igualndo) los valores de cada una de las nueve
  columnas.

Se verá así (los colores no son necesarios, solo explicativos).

.. figure:: /img/dhont-03.png
   :alt: dhont-03

   dhont-03

Ahora agregamos nuestra tabla de resumen a la derecha donde quedarán
listadas las agrupaciones en posición de obtener la banca.

La función *LARGE* nos da los valores máximos o mínimos en el orden que
necesitamos

::

    =large(A$2:A$100;L2)

Note los signos *$* y luego estire la funcion hasta la novena banca.

.. figure:: /img/dhont-04.png
   :alt: dhont-04

   dhont-04

A continuación, usando la función *LOOKUP* **que sólo busca en la
primera columna de un rango dado** es posible saber a que partido le
corresponde un coeficiente.

::

    =VLOOKUP(M2-0;A$2:B$100;2;FALSE)

Note los signos *$* y luego estire la funcion hasta la novena banca.

.. figure:: /img/dhont-05.png
   :alt: dhont-05

   dhont-05

Totales de bancas por agrupación
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Finalmente podemos saber el total de bancas por agrupación podemos en
una hoja nueva. Para esto replicamos (siempre igualando) la lista de
agrupaciones en una columna.

En una columna lateral *total de bancas* usamos la función *COUNTIF* que
permite **contar** elementos que se repiten en una lista. El primer
parámetro es el rango, el segundo el valor buscado.

Note y comprenda la necesidad del signo *$*.

::

    =countif(N$2:N$10;M14)

.. figure:: /img/dhont-06.png
   :alt: dhont-06

   dhont-06
