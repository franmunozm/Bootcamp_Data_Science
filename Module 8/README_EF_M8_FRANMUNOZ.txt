PREDICCIÓN DE NATALIDAD SEGÚN FACTORES SOCIOECONÓMICOS 

Desarrollo de un modelo basado en redes neuronales para predecir la tasa de natalidad en distintos países. Se cuenta con un dataset que incluye información socioeconómica como el PIB per cápita, el acceso a servicios de salud, el nivel de educación, la tasa de empleo femenino, edad de maternidad, urbanización y la tasa de natalidad que es la variable objetivo. 
Se diseñó, entrenó y evaluó una red neuronal que permite predecir la tasa de natalidad de manera precisa, analizando el impacto de diferentes variables en la predicción. 


# Análisis de resultados y reflexión final

Basándose en la exploración de datos, el diseño del modelo, su entrenamiento y optimización, se pueden extraer las siguientes conclusiones:


## Variables más influyentes

Considerando tanto el análisis de correlación lineal inicial como el rendimiento del modelo entrenado y optimizado, las variables que parecen tener una mayor influencia en la predicción de la tasa de natalidad son:

*   PIB per cápita: Como observamos en la matriz de correlación, existe una fuerte relación negativa con la tasa de natalidad. Esto sugiere que en países con mayor desarrollo económico, la tasa de natalidad tiende a ser menor.
*   Otras variables del dataset que presentan una correlación baja, son Tasa_Empleo_Femenino (0.242), 'Edad_Maternidad' (-0.300) y 'Urbanizacion' (0.205). Tanto la Tasa_Empleo_Femenino como la Urbanización tienen una correlación positiva, es decir la tasa de natalidad aumenta a medida de que estas variables lo hagan. Y en el caso de la Edad_Maternidad la correlación es negativa por lo que a mayor edad de maternidad menor tasa de natalidad.
Las variables 'Acceso_Salud' (0.076) y 'Nivel_Educativo' (-0.124), tienen una correlación prácticamente nula, por lo que no afectan la predicción en este caso.
Es importante recordar que la red neuronal puede haber identificado relaciones no lineales entre las variables que no son evidentes en un simple análisis de correlación lineal.


## Relación con tendencias demográficas globales

Los hallazgos parecen alinearse con algunas tendencias demográficas globales conocidas, como la transición demográfica, donde las tasas de natalidad tienden a disminuir a medida que los países se desarrollan socioeconómicamente. Por lo que países con un PIB per cápita más alto, mayor tasa de empleo femenino y urbanización tienden a tener una tasa de natalidad más baja.


## Propuestas de mejora y ajustes futuros

Para futuras iteraciones de este modelo, se podrían considerar las siguientes mejoras:

*   Explorar más a fondo la influencia de variables: Aunque la correlación lineal da una pista, se podrían emplear otras técnicas para entender mejor cómo cada variable impacta la predicción en el modelo no lineal.
*   Probar arquitecturas de red neuronal más complejas: Experimentar con un mayor número de capas, diferentes tipos de capas (aunque para este problema de regresión simple, capas densas son apropiadas) o un mayor rango de unidades en las capas ocultas durante la sintonización de hiperparámetros.
*   Optimizar aún más los hiperparámetros: Ejecutar Keras Tuner por más `max_trials` o `executions_per_trial`, o probar otros tuners como `BayesianOptimization`.
*   Considerar la inclusión de más datos: Un dataset más amplio y diverso podría mejorar la capacidad de generalización del modelo.


Este ejercicio ha permitido diseñar, entrenar y evaluar un modelo de red neuronal para predecir la tasa de natalidad, así como reflexionar sobre la importancia de distintos factores socioeconómicos en este fenómeno.