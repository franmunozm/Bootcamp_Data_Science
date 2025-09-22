# **ANÁLISIS DE PREFERENCIAS MUSICALES A NIVEL GLOBAL**



Realización de análisis sobre las preferencias musicales en distintos países mediante la aplicación de técnicas de aprendizaje de máquina no supervisado para extraer patrones de escucha y agrupar países según sus similitudes en consumo musical.

Se realizo lo siguiente:

\* Aplicación de clusterización para encontrar grupos de países con patrones de escucha similares (Kmeans, Clustering Jerárquico, DBScan).

\* Utilización de reducción de dimensionalidad para visualizar la estructura de los datos (PCA y t-SNE).

\* Evaluación de diferentes algoritmos y justificacion de ventajas y desventajas.

\* Interpretación de los resultados en un contexto cultural y social.



## **RESULTADOS**



### *Comparación de Métodos de Clusterización*



Los métodos utilizados para la clusterización fueron Kmeans, clustering jerárquico y DBSCAN. Las principales diferencias para estos 3 algoritmos son:



\*   K-Means forma agrupaciones esféricas mediante la búsqueda de centros de agrupación (centroides) y requiere que se especifique de antemano el número de agrupaciones (K).

\*   La Clusterización Jerárquica construye un árbol de agrupaciones, ya sea mediante la fusión (aglomerativa) o la división (divisiva), y ofrece un dendrograma para visualizar las relaciones.

\*   DBSCAN se basa en la densidad, identifica automáticamente agrupaciones de forma arbitraria y gestiona el ruido etiquetando los valores atípicos por separado, pero requiere un ajuste cuidadoso de sus parámetros (ε y MinPts).



En este caso, fue más fácil utilizar el Kmeans, debido a que el parámetro K fue encontrado por medio del método del codo y el coeficiente de silueta. Lo que lo hace más simple y certero que los otros modelos.



### *Comparación de PCA y t-SNE*



##### *PCA:*



\*   Para la visualización con los 2 componentes principales usando PCA la data se distribuye en la gráfica de manera de que al utilizar los colores para los paises desde Kmeans (con k=4), agrupa los países en 4 clusters descritos a continuación:





     | Cluster 0 | Cluster 1            | Cluster 2   | Cluster 3   |

 PCA | Corea     | EEUU-México-Alemania | Rusia-Chile | Italia-Japón|





Esa distribución es la misma obtenida con Kmeans usando k=4 y con el Clustering Jerárquico utilizando el método 'Ward'





##### *t-SNE:*



\*   En el caso de t-SNE, la visualización del modelo en 2D, se generó variando el parámetro de 'perplexity' considerando los números entre 1 y 7. En las gráficas obtenidas se aprecia que los países a medida que el valor de 'perplexity' aumenta se separan espacialmente de manera que no se logra apreciar alguna agrupación entre ellos. Al revés, con perplexity=1, se generan 3 grupos muy marcados donde los puntos están casi uno sobre otros, pero con perplexity 2 o 3 los países se dispersan muy similar a lo obtenido con PCA, pudiendo identificarse 4 clusters (los mismos que se obtuvieron con PCA) pero dispersos de manera diferente en la gráfica.



**En general, si comparamos el PCA con las primeras 2 componentes y el t-SNE usando perplexity=2 o 3, ambos modelos de visualización para este dataset resultaron bastante similares. No se aprecian mayores diferencias entre la información que entrega uno con respecto al otro, por lo que no se puede afirmar que uno sea mejor que el otro. Esto puede deberse a que el dataset utilizado es pequeño y por lo mismo hace difícil tratar de modelar cualquier comportamiento con tan poca información**





# **Conclusiones**



La agrupación que más se repitió, fue la siguiente





        | Cluster 0 | Cluster 1            | Cluster 2   | Cluster 3   |

 Países | Corea     | EEUU-México-Alemania | Rusia-Chile | Italia-Japón|



Según esto se entiende que Corea es un país que no tiene mucho en común con otro de los países del set de datos. También se puede observar que las agrupaciones que los algoritmos hicieron no necesariamente consideraron similitudes geográficas, por ejemplo en distintos algoritmos se generó el cluster que contiene a Italia-Japón y el de Chile-Rusia y esos pares de países no se parecen mucho culturalmente y tampoco están cerca geográficamente.



Considerando las tendencias actuales donde el Pop, Hip-Hop y Electrónica son de los estilos de música más escuchado, la clusterización agrupó países como Japón e Italia que tienen una alta preferencia a escuchar música Hip-Hop y Electrónica. Pero además de esa similitud con el consumo de estilos de música actual no hay otra.

