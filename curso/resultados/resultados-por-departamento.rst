Resultados por departamento
---------------------------

Para conocer más en detalle podemos analizar los resultados por departamento.
Para esto seleccionamos de la hoja de totales por departamento **casi** todas las filas. Excluimos las de la sección 999 (que son totales provinciales) y generamos una tabla dinámica.

En el menú *datos* elegimos la opción *tabla dinámica*

En esta definimos como *filas* a las secciones y como columnas a las *agrupaciones*.
Como *valores* elegimos los votos (con la función sumar que viene predeterminada). 

.. figure:: /img/tabla-dinamica-resultados-por-depratamento.png

De esta forma tenemos aquí un resumen de los resultados en todos los departamentos para todas las agrupaciones. 
Si bien el resumen es correcto esta codificado. Los departamentos y las agrupación tienen solo un código. Para resolver esto tenemos la función VLOOKUP que nos permitirá extraer los nombres de las hojas/tablas accesorias.

Lo más prolijo será resolver esto en una hoja nueva que tome los datos de esta *tabla dinámica* y los complemente con los nuevos datos

.. figure:: /img/resultados-por-depto-listo-para-viz.png

La forma es:
 - En la primera fila se iguala a la fila uno de la tabla dinámica (se dejan dos celdas libres al inicio)
 - La primera columna se igual contra la columna uno de la tabla dinámica (se dejan dos celdas libres al inicio)
 - La segunda fila se completa con la función VLOOKUP contra la tabla accesoria de agrupaciones. **CUIDADO** con el uso del signo $. En este caso deben *anclarse* las letras de la formula y no el número de fila. Esto es debido a que la función se va a *arrastrar* horizontalmente.
 - La segunda columna se completa con VLOOKUP contra la tabla accesoria de *ambitos* pero eligiendo **SOLAMENTE** las celdas del distrito 4 (Córdoba). 
 - Las celdas interiores se completan con los datos interiores de la tabla dinámica


Para hacer una visualización ahora tenemos textos faciles de comprender en lugar de códigos que no nos son familiares. Es por esto que dispusimos de esta forma donde las referencias de cada fila y columna están cerca de los datos. De esta forma el rango a definir para una visualización es más simple

.. figure:: /img/seleccion-resultados-por-depto-listo-para-viz.png

Con esta selección podemos insertar un gráfico de *columnas apiladas al 100%* para saber el desempeño de cada agrupación en cada uno de los 26 departamentos:

.. figure:: /img/viz-resultados-por-dapartamento.png

Este mismo gráfico de columnas apiladas simples perdería un poco de vista a los departamentos que tienen menos electores. Así se vería en modo simple:

.. figure:: /img/viz-resultados-por-dapartamento-apilado-simple.png

Otra forma de ver estos mismos datos es invertir la selección de filas y columnas (esto se puede invertir desde la edición del gráfico). De esta forma cada barra del gráfico es un partido (y no más un departamento). Dentro de cada barra los valores son los votos en un departamento específico.

.. figure:: /img/viz-resultados-por-agrupacion-apilado-100.png 

**Nota:** Al tener todos los datos conectados entonces a la tabla de resultados iniciales al cambiar datos en ese origen esta tabla y sus visualizaciones se actualizarán automáticamente en esta planilla y en todos los sitios webs donde estén publciados.
