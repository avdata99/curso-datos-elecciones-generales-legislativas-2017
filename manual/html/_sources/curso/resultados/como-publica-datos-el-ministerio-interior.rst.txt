Datos el Ministerio del Interior 
================================

Para 2017 (al igual que 2015) los interesados pueden recibir datos de la
elección durante el día de la misma y posteriormente. Estos datos se
entregan en formatos reutilizables.

Si desean formar parte del grupo que recibe esta información técnica es
necesario manifestarlo por email a Yanina Sandra Martinez
ymartinez@mininterior.gob.ar. Esta es la forma que el Ministerio del
Interior provee esta información.

Para las elecciones 2017 todos estos datos se compartieron vía email: `muestra 2017 <https://avdata99.github.io/datos-indra-dia-eleccion-paso-2017-AR/generales-2017/Elecciones%20legislativas%202017.html>`__ 
(`version PASO <https://github.com/avdata99/datos-indra-dia-eleccion-paso-2017-AR/blob/master/info-previa-DINE.md>`__).

.. figure:: /img/muestra-mininterior-explicacion.png
   :alt: Datos informados por el ministerio del interior

El documento indica cuales y en que formatos están los documentos. El proceso a continuación es el uso de estos datos para construir resumenes y visualizaciones útiles.

Datos incluidos
~~~~~~~~~~~~~~~

Para procesar estos daton abrimos una planilla de cálculo nueva de Google Drive en donde vamos a ir colocando copia de cada tabla.

Tipos de elección
^^^^^^^^^^^^^^^^^

El primer dato es la lista de códigos para los cargos electivos. No esta en un CSV, es un texto suelto. Copiamos el texto y lo pegamos en la planilla.

.. figure:: /img/dato-texto-01-indra.png
   :alt: dato-texto-01-indra

Luego seleccionamos las celdas con texto y usamos la funcionalidad de *Dividir texto en columnas* (en el menú *datos*) con el separador " = " (espacio, signo igual, espacio). Además le agregamos encabezado a las
columnas.

.. figure:: /img/dato-texto-02-indra.png
   :alt: dato-texto-02-indra

Se incluyen dos archivos de interés para analizar la elección. Uno es estático y el segundo cambia cada 5 minutos e incluye los resultados parciales la noche de entrega de resultados. 

El archivo estático se llama `generales_00.tar.gz <https://github.com/avdata99/curso-datos-elecciones-generales-legislativas-2017/blob/master/datos-a-usar/descargados-mininterior-elecciones-generales/generales_00.tar.gz?raw=true>`__

Este incluye datos que no varían durante la elección:

Ámbitos electorales
^^^^^^^^^^^^^^^^^^^

`Ámbitos <https://github.com/avdata99/curso-datos-elecciones-generales-legislativas-2017/blob/master/datos-a-usar/descargados-mininterior-elecciones-generales/generales_00/ambitos_00.csv?raw=true>`__: Lista de las secciones electorales. Vale destacar que en cuanto a las zonas las elecciones nacionales se dividen en distrito (provincias) + seccion (departamentos) + circuito (ciudades en general).

El alcance máximo de estos datos son las secciones electorales (en Córdoba, Departamentos). La lista de estos departamentos esta en el archivo

Tip: ¿Notó que separa los campos con *punto y coma*? Es para comodidad de los usaurios de *Excel* que por defecto usar punto y coma en lugar de la coma estandar. 

Agrupaciones
^^^^^^^^^^^^

`Agrupaciones <https://github.com/avdata99/curso-datos-elecciones-generales-legislativas-2017/blob/master/datos-a-usar/descargados-mininterior-elecciones-generales/generales_00/agrupaciones_00.csv?raw=true>`__: Alianzas y partidos políticos que participan de la elección.

.. figure:: /img/listas.png
   :alt: listas

**Nota para todos los datos:** El código 999 se refiere a totales provinciales.

Allí el texto se podrá mostrar tal cual es. Lo copiamos y pegamos en una
**hoja nueva** de nuestra planilla de drive. Será necesario nuevamente
*dividir el texto en columnas*. Esta vez el separador es el punto y
coma.

Hay que agregar los nombres de las columnas (en la fila 1): Provincia, Sección y Nombre Sección.
Aquí uno puede *adivinar* que Córdoba es la número 4, este dato nos va a servir para los datos a continuación.

Totales
^^^^^^^

Hay un archivo de totales por cada provincia. Con *totales* se refiere a datos generales de cada departamento, a los votos generales (positivos, válidos, en blanco, etc), no a los votos que recibió cada lista.
En este caso, el de Córdoba es `totales_04.csv <https://github.com/avdata99/curso-datos-elecciones-generales-legislativas-2017/blob/master/datos-a-usar/descargados-mininterior-elecciones-generales/DATOS_41776329/totales_04.csv?raw=true>`__.

::

   3;04;001;03254;03232;09932;01109206;00797369;07237;01101751;09933;00777601;09752;00006138;00077;00013242;00166;00000388;00005;10;23;00;25;
   3;04;002;00163;00163;10000;00051517;00038500;07473;00051517;10000;00037288;09685;00000449;00117;00000734;00191;00000029;00008;10;23;01;50;
   3;04;003;00653;00650;09954;00222858;00162228;07313;00221827;09954;00157832;09729;00001335;00082;00002975;00183;00000086;00005;10;22;23;00;
   3;04;004;00159;00157;09874;00049041;00033097;06830;00048456;09881;00032018;09674;00000540;00163;00000527;00159;00000012;00004;10;22;23;30;
   3;04;005;00090;00088;09778;00028383;00019971;07197;00027748;09776;00019476;09752;00000304;00152;00000184;00092;00000007;00004;10;22;22;10;

Según el documento se indica que los campos (nombres de las columnas):

+-----------------------------------------------+------------+
| DESCRIPCIÓN                                   | LONGITUD   |
+===============================================+============+
| Código de elección                            | 1          |
+-----------------------------------------------+------------+
| Código de provincia                           | 2          |
+-----------------------------------------------+------------+
| Código de comuna                              | 3          |
+-----------------------------------------------+------------+
| Total de mesas                                | 5          |
+-----------------------------------------------+------------+
| Mesas escrutadas                              | 5          |
+-----------------------------------------------+------------+
| Porcentaje de mesas escrutadas                | 5          |
+-----------------------------------------------+------------+
| Electores                                     | 8          |
+-----------------------------------------------+------------+
| Total de votantes                             | 8          |
+-----------------------------------------------+------------+
| Participación sobre escrutado                 | 5          |
+-----------------------------------------------+------------+
| Electores escrutados                          | 8          |
+-----------------------------------------------+------------+
| Porcentaje de electores escrutados            | 5          |
+-----------------------------------------------+------------+
| Votos positivos                               | 8          |
+-----------------------------------------------+------------+
| Porcentaje de votos positivos                 | 5          |
+-----------------------------------------------+------------+
| Votos en blanco                               | 8          |
+-----------------------------------------------+------------+
| Porcentaje de votos en blanco                 | 5          |
+-----------------------------------------------+------------+
| Votos nulos                                   | 8          |
+-----------------------------------------------+------------+
| Porcentaje de votos nulos                     | 5          |
+-----------------------------------------------+------------+
| Votos recurridos, impugnados y comando        | 8          |
+-----------------------------------------------+------------+
| Porcentaje de votos recurridos e impugnados   | 5          |
+-----------------------------------------------+------------+
| Mes                                           | 2          |
+-----------------------------------------------+------------+
| Día                                           | 2          |
+-----------------------------------------------+------------+
| Hora                                          | 2          |
+-----------------------------------------------+------------+
| Minuto                                        | 2          |
+-----------------------------------------------+------------+

La *Longitud* es la cantidad de caractares (letras) que el campo de la
tabla podrá tener. Es un método que usaban nuestros **ancestros** para
optimizar el espacio en disco de los datos.

Tip: Una forma fácil de usar estos datos como titulos de las columnas es
copiar la tabla, pegarla Google Drive, volver a copiarla y hacer el
pegado especial que se llama *Pegado con transposición de datos*. Esto
transforma filas en columnas.

Debería verse así:

.. figure:: /img/totales-04-indra.png
   :alt: totales-04-indra

Totales por agrupaciones
^^^^^^^^^^^^^^^^^^^^^^^^

Esta lista si incluye los totales de cada lista junto a las agrupaciones
que compiten en internas. A los fines de conservar todos estos datos en
una sola tabla simple se agregan al final tres columnas todas las veces
que sean necesarias para mostrar las agrupaciones internas que compiten
dentro de cada lista.

Muestra de los datos::

   3;04;001;10;23;00;25;0502;00374100;04811;
   3;04;001;10;23;00;25;0578;00192897;02481;
   3;04;001;10;23;00;25;0543;00077474;00996;
   3;04;001;10;23;00;25;0217;00046604;00599;
   3;04;001;10;23;00;25;0503;00036652;00471;
   3;04;001;10;23;00;25;0201;00031016;00399;
   3;04;001;10;23;00;25;0567;00018858;00243;

Descripción de los datos

+---------------+------------+
| DESCRIPCIÓN   | LONGITUD   |
+===============+============+
| Código de     | 1          |
| elección      |            |
+---------------+------------+
| Código de     | 2          |
| provincia     |            |
+---------------+------------+
| Código de     | 3          |
| sección/      |            |
| comuna        |            |
+---------------+------------+
| Mes           | 2          |
+---------------+------------+
| Día           | 2          |
+---------------+------------+
| Hora          | 2          |
+---------------+------------+
| Minuto        | 2          |
+---------------+------------+
| Código de la  | 4          |
| agrupación    |            |
| política      |            |
+---------------+------------+
| Votos a la    | 8          |
| agrupación    |            |
| política      |            |
+---------------+------------+
| Porcentaje de | 5          |
| votos a la    |            |
| agrupación    |            |
| política      |            |
+---------------+------------+

Haciendo el mismo proceso con el archivo de `totales por listas para Córdoba <https://github.com/avdata99/curso-datos-elecciones-generales-legislativas-2017/blob/master/datos-a-usar/descargados-mininterior-elecciones-generales/DATOS_41776329/totalesagrupaciones_04.csv?raw=true>`__
se debe llegar a esta lista:

.. figure:: /img/totales-listas-04-indra.png
   :alt: totales-listas-04-indra


