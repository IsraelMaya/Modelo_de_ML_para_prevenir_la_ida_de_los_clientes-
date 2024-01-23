## Predecir clientes que se pueden ir para retenerlos con promociones 

Al operador de telecomunicaciones Interconnect le gustaría poder pronosticar su tasa de cancelación de clientes, por lo que necesita un **modelo que tenga un ROC-AUC ≥ 0.88**. Si se descubre que un usuario o usuaria planea irse, se le ofrecerán códigos promocionales y opciones de planes especiales. El equipo de marketing de Interconnect ha recopilado algunos de los datos personales de sus clientes, incluyendo información sobre sus planes y contratos.

## Tabla de conteidos del proyecto

* [1 Incialización](#Capítulo_1)
* [2 Exploración datos iniciales](#Capítulo_2)
    * [2.1 Preparación de los datos](#Sección_2_1)
* [3 Validación de modelos](#Capítulo_3)
    * [3.1 División y codificación de los datos](#Sección_3_1)
    * [3.2 LogisticRegression](#Sección_3_2)
    * [3.3 DecisionTreeClassifier](#Sección_3_3)
    * [3.4 RandomForestClassifier](#Sección_3_4)
    * [3.5 LightGBM](#Sección_3_5)
    * [3.6 CatBoost](#Sección_3_6)
* [4 Conclusión](#Capítulo_4)


## Librerías Utilizadas

`pandas`
`numpy`
`seaborn` 
`matplotlib.pyplot`
`sklearn`
`lightgbm`
`catboost`

## Resultados

El modelo `LightGBM` fue mejor por muy poco que el modelo `CatBoost`, donde podemo ver que el valor **ROC AUC es de 0.93** con la base de datos de prueba, lo cual nos dice que a pesar de haber desequilibrio en nuestro `target`, el modelo puede predecir de manera muy eficiente la tasa de cancelación de clientes por distinguir bien entre los verdaderos positivos y los falsos positivos, también, tenemos un valor de `Exactitud` del 0.88, que es alto debido al desequilibrio de clases, más un valor de `F1` de 0.76, que si bien no es alto, aún así nos dice que el modelo tienen un valor aceptable de Precission y Recall.

Se muestra a continuación los resultados de los modelos utilizados y el valor de sus metricas tanto en la base de datos de entrenamiento como de pruebas:

**LogisticRegressor**

|  Métrica | Train  |Test   |
| ------------ | ------------ | ------------ |
|Exactitud |  0.81 | 0.81|
|    F1        |  0.59 | 0.59|
|   PR         | 0.68 | 0.67|
|ROC AUC  |   0.86 | 0.85|

 **DecisionTreeClassifier**

 |  Métrica | Train  |Test   |
| ------------ | ------------ | ------------ |
|Exactitud |  0.96 | 0.82|
|F1 |   0.91 | 0.66|
|PR |   0.98 | 0.62|
|ROC AUC |    0.99 | 0.80|

**RandomForestClassifier**

|  Métrica | Train  |Test   |
| ------------ | ------------ | ------------ |
|Exactitud |  0.86 | 0.82|
|F1 |   0.71 | 0.62|
|PR |   0.85 | 0.76|
|ROC AUC |    0.93 | 0.88|   
    
**LightGBM Regressor**

|  Métrica | Train  |Test   |
| ------------ | ------------ | ------------ |
|Exactitud |  0.96 | 0.90|
|F1 |   0.92 | 0.79|
|PR |   0.98 | 0.89|
|ROC AUC |    0.99 | 0.93|   

**CatBoost Regressor**

|  Métrica | Train  |Test   |
| ------------ | ------------ | ------------ |
|Exactitud |  0.94 | 0.88|
|F1 |   0.88 | 0.76|
|PR |   0.96 | 0.88|
|ROC AUC |    0.98 | 0.93|  

