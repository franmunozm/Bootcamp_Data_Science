ANÁLISIS DE MOVIMIENTOS MIGRATORIOS CON SPARK

Estudio de las tendencias de migración humana en el siglo XXI utilizando Big Data. Para ello, se trabajará con un conjunto de datos que contiene información sobre migraciones entre distintos países, sus causas y el impacto socioeconómico en las regiones de origen y destino.

Objetivos de la actividad fueron:

* Aplicar conceptos de Big Data utilizando Apache Spark y PySpark.
* Explorar y transformar datos con RDDs y DataFrames.
* Realizar consultas con Spark SQL.
* Implementar modelos de aprendizaje automático con MLlib.

Resumen de los Hallazgos:

* La carga y exploración inicial de datos cargó exitosamente el archivo migraciones.csv en un DataFrame de Spark, mostrando las primeras 20 filas, el esquema (incluyendo tipos de datos string y long), y estadísticas descriptivas para columnas numéricas como Año y Cantidad.
* El procesamiento de datos con RDDs y DataFrames incluyó filtrar migraciones posteriores a 2017 usando un RDD (resultando en 2 migraciones), filtrar el DataFrame por razones 'Económica' (encontrando 2 migraciones de este tipo), calcular el promedio del 'PIB_Destino' para migraciones económicas ($48000.0), y ordenar el DataFrame por 'Año'.
* El DataFrame ordenado se guardó exitosamente en un archivo Parquet llamado "migraciones_ordenadas.parquet".
* El registro del DataFrame como una vista temporal de SQL llamada "migraciones" permitió realizar consultas SQL.
* Las consultas SQL identificaron exitosamente los países de origen y destino más frecuentes y analizaron las razones de migración por país de origen después de corregir un ParseException al encerrar el nombre de la columna Razón entre acentos graves.
* Para la aplicación de MLlib, la columna 'Razón' se convirtió en una etiqueta numérica utilizando StringIndexer para la clasificación multiclase.
* Se creó un pipeline que incluyó VectorAssembler, StandardScaler y LogisticRegression.
* El modelo fue entrenado y evaluado, resultando en una precisión (accuracy) de 0.0 en el conjunto de prueba, lo que indica que el modelo no fue capaz de predecir correctamente el resultado en esta división específica de los datos de prueba.

Ideas o Próximos Pasos:

* La baja precisión (0.0) del modelo de regresión logística sugiere que las características y el modelo actuales no son suficientes para predecir la razón de migración con este pequeño conjunto de datos. Es necesaria una mayor investigación en ingeniería de características, explorar diferentes algoritmos de clasificación, o adquirir un conjunto de datos más grande y representativo para mejorar el rendimiento predictivo.
* El uso exitoso de RDDs y DataFrames/Spark SQL resalta la flexibilidad de Spark para la manipulación y consulta de datos. Para conjuntos de datos más grandes, los beneficios de rendimiento de DataFrames y Spark SQL serían más pronunciados.