Mapa de los resultados por departamento
---------------------------------------

Usando `la versión simplificada <https://avdata99.github.io/curso-datos-elecciones-generales-legislativas-2017/datos-a-usar/geo/departamentos-poligonos-simplificado-WKT.csv>`__ de los polígonos de los departamentos de la Provincia de Córdoba podemos hacer un mapa de resultados con diferentes temáticas.

Para esto copiamos el contenido de este archivo en una nueva hoja de nuestra planilla de trabajo. 

.. figure:: /img/wkt-deptos-en-drive.png

Lamentablemente **los identificadores que usa el GeoPortal de la Provincia de Córdoba no son iguales a los usados por el ministerio del interior**. Vale recordar la importancia de avanzar en códigos únicos para este tipo de datos que se utilizan en tantas oficinas de diferentes niveles del estado.

De todas formas podemos cruzar los datos vía el nombre del departamento. Usamos VLOOKUP para intentar esta mezcla. Funciona bastante bién salvo en los casos en los que los nombres están escritos de diferente forma.
El caso de las tildes de los nombres es uno:

.. figure:: /img/cruzar-wkt-con-resultados-via-nombre-depto.png

Se puede resolver simplemente modificando los nombres de los departamentos en esta nueva hoja para que coincidan con los usados en nuestros resultados.

Una vez hechas estas correcciones los datos están completos. Antes de llevar estos datos a Carto DB (u otroa plataforma similar) es necesario hacer que estos resultados tengan algún datos a graficar.

Ejemplo 1: Ganador por departamento
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Para obtener una columna con el *Ganador* hacemos tres pasos. Primero obtenemos el numero de votos del ganador de cada departamento con la función **max**:

.. figure:: /img/encontrar-ganador-depto-01.png

Luego agregamos una columna de ayuda para saber que distancia hay entre esta fila y una que tenga los nombres de los partidos ganadores. Colocamos para esto (como insumo de la función HLOOKUP) al final de la tabla una celda con copia de los nombres de los partidos.

.. figure:: /img/encontrar-ganador-depto-02.png

Finalmente con HLOOKUP (usando la *distancia* variable hasta el nombre del ganador) podemos saber quien es el *dueño* de los votos del ganador calculados para cada departamento.

.. figure:: /img/encontrar-ganador-depto-03.png

El mapa quedo `abierto y disponible <https://hudson.carto.com/builder/fa9229e7-e333-491a-bbeb-5e88485a72bf/embed>`__ para consulta.

.. figure:: /img/mapa-final-deptos-ganador.png

Ejemplo 2: Desempeño del FIT
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A los fines de tenes los datos en la misma planilla que tiene polígonos listos agregamos 7 nuevas columnas (una por cada partido). El titulo de cada columna es el *signo %* mas el nombre del partido.

Los datos porcentuales evitan la enorme distorción generada por la cantidad de electores existentes en cada departamento. Esta visualización esta pensada para conocer el desempeño de un partido en toda la provincia. lo mejor para este caso es saber el % de votos de un partido en cada departamento

.. figure:: /img/porcentajes-partido-depto.png

Luego calculamos los % de cada partido en cada fila-departamento
Préstese especial atención a los signos $ que permitiran estirar esta fórmula horizontal y verticalmente sin tenes que modificarse.

::
    
    =B2/sum($B2:$H2) * 100

Quedará así:

.. figure:: /img/porcentajes-partido-depto2.png

Este archivo debe descargarse en formato CSV (sólo la hoja actual de resultados) y llevarse a CARTO DB

.. figure:: /img/Desempeno-FIT.png

Este mapa puede usarse para armar mapas de cada uno de los partidos.

