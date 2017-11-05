Procesar CSV para Geolocalizar
==============================

Nótese que una de las columnas incluye más de un dato. Esto es un
*error* (que a veces podemos suponer intencional) que dificulta el análisis de datos. La
columna *Escuela* incluye:

* El nombre de la escuela
* La dirección de la escuela
* En algunos casos el barrio

Google Sheets (la planilla de cálculo incluida en Google Drive) incluye una herramienta para estos casos. Excel y LibreOffice ofrecen posibilidades similares en este sentido.

Como vamos a procesar la columna *Escuela* no es mala idea **hacer una
copia** de ella para referencias futuras en la medición de la efectividad
de los procesos que vamos a usar. Para esto debe insertarse una columna y colocar ahi la replica de los datos.

Hacemos un click en el encabezado de la columna *Escuela* para
seleccionarla. En el menú *datos* elegimos la opción *dividir texto en
columnas*. Nos ofrecera como *separador* predeterminado la coma.

.. figure:: /img/dividir-texto-en-col.png
   :alt: dividir


Nosotros cambiamos eso por un separador *personalizado*. Elegimos " - " (espacio, guión, espacio) que es el que detectamosmirando los datos.

**Analizar detenidamente como se divide un texto en caracteres**.

Al hacer esta división se **pisarán** los datos que estén a la derecha de la columna *recortada*. Revisar el espacio que necesita (e insertar las columnas que se necesiten) y realizar el recorte sin pérdida de datos. 

Preparar los datos para geolocalizar
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Las herramientas para geolocalizar son variadas y pueden requerir los datos de base de diferentes formas. Es por esto que conviene tener los datos completos.

Agregar en la planilla de cálculo las columnas *Ciudad*, *Provincia* y
*Pais*. A la columna Ciudad igualarla a la columna. Si bien no siembre
es necesario la provincia y el país ya que algunos entornos de
geolocalización permiten especificarlo nunca está de más.

La columna Ciudad no es tan facil de llenar. En Córdoba los circuitos
son localidades. Esto ayuda en general salvo en la Ciudad de Córdoba
donde los circuitos electorales tienen nombres no formales vinculados
algunas veces al barrio pero no son útiles a los fines de la
geolocalización. Todas las escuelas de la seccional 1, sin importar el
circuito, deben decir Córdoba en la columna *Ciudad*.

En definitiva, la columna *Ciudad* debe decir *Córdoba* para la
seccional *"Capital"* y copiar la columna *Circuito Nombre* en todos los
otros casos. Esto se puede programar con la función:

::

    =if(B2="CAPITAL";"Córdoba";D2)

Para algunos sitios se requiere que todos los datos de una
geolocalización este en una sola columna. Es util por esto agregar una
columna más al final que se llame por ejemplo *Geo* y que agrupe a las
columnas - Direccion - Ciudad - Provincia - País (separadas por comas).

::

    =CONCATENATE(F2;", ";H2;", ";I2;", ";J2)

Descargar esta planilla como CSV (menú *Archivo*, opción *descargar como* => CSV) para llevar a alguna plataforma de geolozalización.

Geolocalizando con Google MyMaps
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Con `Google MyMpas <https://www.google.com/maps/d/>`__ se pueden
construir mapas gráficamente en un entorno
colaborativo es interesante (con la misma lógica que Google Drive).

Al igual que Fusion Tables permite GeoLocalización automática sin
coordenadas y solo con datos de texto. La geolocalización aparenta ser
bastante más rápida que Fusion Tables.

Finalmente queda así: `Ver mapa <https://drive.google.com/open?id=17s7amCm2daY6BW5mj9ILNMhrsiU&usp=sharing>`__

.. figure:: /img/mapa-google-mymaps.png
   :alt: mymaps

**Pros**: 

* Permite iconos variados según algún campo.
* La edición colaborativa es muy interesante.
* Permite múltiples capas de datos geográficos.

**Problemas**:

* No permite exportar coordenadas.

Geolocalizando en CartoDB
~~~~~~~~~~~~~~~~~~~~~~~~~

Carto genera mapas más elegantes y mucho más potentes a la hora de dar
estilos por valores de la tabla. Permite trabajar gratis con un límite
interesante en general pero mas limitado en lo que hace a la geo
referenciación. Teniendo las coordenadas (que aún no tenemos ni pudimos
exportar de las otras dos plataformas) es la solución mas completa para
visualizar mapas de este tipo.

Finalmente queda así: `Ver
mapa <https://hudson.carto.com/builder/170fae5b-d302-4482-aa4d-13b67df9209b/embed>`__

.. figure:: /img/mapa-carto.png
   :alt: carto

**Pros**:

* Amplias posibilidades para dar estilos a los puntos segun variables.
* Si ya se cuentan con las coordenadas es muy potente.
* Permite múltiples capas de datos geográficos.

**Problemas**:

* Servicio de Geolocalización pago. Límite gratuito muy bajo.
* La geolocalización funcionó muy pobremente a pesar del límite.

Geolocalizar con el API de Google sin ser desarrollador
-------------------------------------------------------

Una solución intermedia es usar un script (similar a los macros de Excel) en Google Sheets que permite hasta 1000 Geolocalizaciones por día. Es muy útil y funciona. Más info `aquí <https://www.datavizforall.org/transform/geocode/>`__.

Este metodo es un pequeño programa que se puede anexar a cualquier planilla de Google Drive. Para agregarlo desde el menú *Herramientas* se elige *Editor de secuencia de comandos* y se copia el texto del archivo geolocalizar.gs del `repositorio de la Municipalidad de Córdoba <https://github.com/ModernizacionMuniCBA/muni-google-util-app-scripts/tree/master/geolocalizar%20desde%20direccion>`__.

Puede copiarse directamente desde `aquí <https://raw.githubusercontent.com/ModernizacionMuniCBA/muni-google-util-app-scripts/master/geolocalizar%20desde%20direccion/geolocalizar.gs>`__.

Una vez grabado, aparecerá un nuevo menú en la planilla de Google.

Para usar este nuevo menú se requieren cinco columnas en blanco a la derecha de la que incluye nuestro campo completo (direccion, ciudad, provincia, país) ya que este programa completará en esos espacios. Además de la latitud y la longitud se entregan algunos datos útiles más.

.. figure:: /img/google-sheets-geocoder-census-geographies.gif
   :alt: gf

La efectividad no es excelente pero es bastante buena. En los casos en que no es exacta, lo indica. De esta forma se puede entonces pasar por un proceso manual solo para los casos en los que sea necesario.
Finalemente de esta forma se pudieron obtener la gran mayoría de las geolocalizaciones. `CSV FINAL CON COORDENADAS <https://avdata99.github.io/curso-datos-elecciones-generales-legislativas-2017/datos-a-usar/carta-marina/escuelas-elecciones-2017-cordoba-PARA-MAPA-CON-COORDS.csv>`__.

Antes de descargar el archivo asegurarse de usar la configuración regional de *Estados Unidos* ya que CartoDB *prefiere* los numeros con separación decimal de punto. Para esto en la planilla de Google Drive se va al menú *Archivo* -> *Configuración del documento*.
Es importante conocer cuales son las diferencias en la configuraciones regionales ya que son motivo de numerosos dolores de cabeza.

Ahora Carto no requiere interferir la geolocalizazión y detecta a la
primera las columnas que representan las coordenadas. Con este archivo
se puede hacer un nuevo mapa en Carto con resultados muy superiores.

Finalmente queda así: `Ver
mapa <https://hudson.carto.com/builder/9f30c071-f758-4286-b408-8f8fa2db5c10/embed>`__.

.. figure:: /img/carto2-ok.png
   :alt: Mapa OK carto

Código para embeber:

::

    <iframe width="100%" height="520" 
        frameborder="0" 
        src="https://hudson.carto.com/builder/9f30c071-f758-4286-b408-8f8fa2db5c10/embed" 
        allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen>
    </iframe>

Usar este CSV con latitud y longitud incluida agiliza la carga en Google
MyMaps o cualquier otra plataforma ya que no será necesario mapear las
direcciones.

Geolocalizar direcciones es complejo
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para desarrolladores se recomiendan usar los webservices de Google u
OpenStreetMaps con scripts que gradualmente releven los datos
necesarios.

Otra posibilidad con mayor complejidad técnica es seguir los pasos que describió Manuel Aristarán para cruzar estos datos con la base de datos de escuelas argentinas realizada en 2013. Con esta aplicación `Donde voto? <https://github.com/jazzido/dondevoto>`__ es posible hacer match entre los nombres de las escuelas oficiales y los establecimientos de una carta marina. Si bien no es perfecto supera la efectividad en la geolocalización de otros métodos.

En base a este trabajo quedo disponible tambien `otro resumen de datos de las escuelas argentinas <https://github.com/avdata99/escuelas-argentinas>`__ con mapas incluidos.
