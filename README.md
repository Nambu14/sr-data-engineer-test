# Sr. Data Engineer Programming Test

Suponga que se presenta la necesidad de ingestar archivos planos de distintos aplicativos origen, realizarles pequeñas transformaciones (mayoritariamente de formato) y guardarlo en formato Apache Parquet en HDFS.

Dada esta necesidad se pide generar una solución utilizando Pyspark o Spark Scala que contemple las siguientes características:

1.- Debe tener la flexibilidad suficiente para procesar archivos de texto ancho fijo y delimitados.

2.- Como input debe tomar un archivo de configuración que contenga los siguientes parámetros:

	a.- El path de origen del archivo a ser ingestado;
	b.- El path destino donde se escribirá ese archivo;
	c.- La metadata necesaria para procesar el archivo crudo (e.g. delimitador, header, columnas, anchos de columnas);
	d.- La metadata necesaria para generar el archivo en parquet que crea necesarias (e.g. particiones, cantidad de archivos, compresión);
	e.- Permitir el agregado de columnas al data frame con valores predefinidos.
	
Se solicita que lo desarrollado sea capaz de ser ejecutado en cualquier computadora de forma local, de ser posible, con la menor cantidad de dependencias.

### Sets de prueba
Se proveen dos archivos para realizar *pruebas*.

nyse_2012.csv, delimitado por comas, con cabecera. El parquet de salida debe estar particionado por una columna extra, llamada partition_date y cuyo valor viene dado por parámetro.

nyse_2012_ts.csv, de ancho fijo, sin cabecera y con las siguientes longitudes de columnas:

|columna|tipo de dato|longitud|
| ------------- | ------------- | ------------- |
|stock|string|6|
|transaction_date|timestamp|24|
|open_price|float|7|
|close_price|float|7|
|max_price|float|7|
|min_price|float|7|
|variation|float|7|

El parquet de salida debe estar particionado por la columna stock.


Pregunta:
Qué peculiaridades tiene el modo de escritura Overwrite, en data frames particionados, para versiones de Spark previas a 2.3? Qué cambió a partir de dicha versión?

### Criterios de evaluación
Tener en cuenta:
* Calidad del código desarrollado.
* Mantenibilidad.
* Claridad y facilidad de entendimiento.
* Performance y escalabilidad.
* Pragmatismo.

(Los criterios de evaluación son guías para brindar mayor claridad al candidato en términos de cómo su trabajo será calificado, esta evaluación se centrará en dichos conceptos pero no necesariamente se limitará a los mismos)
