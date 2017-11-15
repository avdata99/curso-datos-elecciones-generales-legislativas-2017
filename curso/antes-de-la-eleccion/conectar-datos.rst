Conectar datos de planillas distintas
-------------------------------------

El análisis se vuelve interesantes cuando los acumulados por circuitos
de diferentes elecciones (vía cartas marinas en el caso de Córdoba) pueden reunirse en un solo
documento.

En este caso estamos trabajando con la carta marina 2017 y tenemos a mano, en formato reutilizable la `carta marina 2007 en excel <https://avdata99.github.io/curso-datos-elecciones-generales-legislativas-2017/datos-a-usar/carta-marina/electoral-2007-cordoba-marina.xls>`_

Esta aparecía solo buscando en Google *"carta marina filetype:xls"*. Al momento de escribir estas líneas el portal de estadísticas de la provincia se rehizo completo y el link desapareció. En este repositorio se guardo una copia. **Es otro ejemplo más de la necesisdad de mantener réplicas de los datos, nunca sabemos hasta cuando estarán online**.

Si bien `existe un analisis detallado en este sentido <https://gobiernoabierto.cordoba.gob.ar/data/datos-abiertos/categoria/sociedad/electores-por-circuito-en-la-provincia-de-cordoba/216>`__ es interesante conocer la forma en que puede realizarse.

Podemos colocar nuestras planillas de electores por
circuitos en una hoja de nuestra planilla y la de
2007 en otra hoja.

A ambas hojas las ordenamos por códigos de sección y códigos de circuito
(de modo que queden ordenadas por circuito dentro de cada *sección*).

**La existencia de códigos únicos de Circuitos y Secciones nos allana el
camino**. Es importante exigir este tipo de identificadores para los
gobiernos que liberan datos.

De esta forma ambas planillas estaran muy similares, cercanas a la
posibilidad de unirse. Si bien la función VLOOKUP podría resolver mejor este caso (porque existe una clave única*) lo cierto es que en la mayoría de los casos esto no existe.

Este ejercicio esta pensado para resolver casos  

Una forma simple de hacerlo es copiar una de las dos planillas completas
junto a la otra en columnas libres de modo que conformen una sola
planilla.

Conviene a continuación ordenar las columnas con los nombres de los
códigos o nombres de circuitos de modo que queden contiguas.

La comparación a continuación es manual y simple. Si existieran nuevos
circuitos simplemente deberán insertarse celdas para que la planilla
quede *alineada*.

.. figure:: /img/tablas-unidas.png


Finalmente en cada *fila* de la planilla debe quedar información relativa a un circuito electoral. De esta forma podrá verse cuales fueron los circuitos que mas crecieron o decrecieron, los que aparecieron y los que ya no están más.