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

El modelo `LightGBM` fue mejor por muy poco que el modelo `CatBoost`, donde podemo ver que el valor **ROC AUC es de 0.93** con la base de datos de prueba, lo cual nos dice que a pesar de haber desequilibrio en nuestro `target`, el modelo puede predecir de manera muy eficiente la tasa de cancelación de clientes por sitinguir bien entre los verdaderos postivos y los falsos potivos, también, tenemos un valor de `Exactitud` del 0.88, que es alto debido al desequilibrio de clases, más un valor de `F1` de 0.76, que si bien no es alto, aún así nos dice que el modelo tienen un valor aceptable de Precission y Recall.


