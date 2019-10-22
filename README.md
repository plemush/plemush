#Mantenimiento presctiptivo de antenas de telecomunicaciones

##Entrega 1 proyecto aplicación CC6204 - Deep Learning, 2019

### Pablo Lemus

1.  Descripción del problema

El servicio que ofrece una empresa de telecomunicaciones depende del funcionamiento de sus antenas de transmisión, por lo que se deben realizar sus mantenciones respectivas para asegurar la calidad del servicio.
Sin embargo, para planificar un mejor uso de los recursos y disminuir los costos operacionales de realizar mantenciones (mover a los teams, repuestos necesarios, etc.) es que busco realizar un modelo de predicción de fallas de las antenas.

El input del modelo correpsonden a mediciones de estatus de cada antena  (cerca de 130 variables) que se registran cada una hora.

Dado que busco mejorar la forma de utilizar los recursos de mantención de las antenas, el output corresponde a la predicción de la probabilidad de que falle la antena al día siguiente con los datos obtenidos en el día hasta las 23:00 horas.

2. Descripción detallada de la métrica 

Las medidas que se usarán en este caso para determinar la calidad de predicción de la red son el valor del AUC (curva ROC) y el valor del test KS.

* Área bajo al Curva ROC o AUC:

En la Teoría de detección de señales, una curva ROC (acrónimo de Receiver Operating Characteristic, o Característica Operativa del Receptor) es una representación gráfica de la sensibilidad frente a la especificidad para un sistema clasificador binario según se varía el umbral de discriminación. Otra interpretación de este gráfico es la representación de la razón o ratio de verdaderos positivos (en el eje y del gráfico) frente a la razón o ratio de falsos positivos (en el eje x del gráfico) también según se varía el umbral de discriminación.

Cada resultado de predicción o instancia de la matriz de confusión representa un punto en el espacio ROC.

A modo de guía para interpretar las curvas ROC se han establecido los siguientes intervalos para los valores de AUC:

[0.5]: Es como lanzar una moneda.

[0.5, 0.6): Test malo.

[0.6, 0.75): Test regular.

[0.75, 0.9): Test bueno.

[0.9, 0.97): Test muy bueno.

[0.97, 1): Test excelente.

Utilizaré esta medida debido a que permite medir el riesgo de cada antena según su probabilidad de falla para cada día y tomar decisiones enfocadas en aquellas antenas más riesgosas. Además es la unidad de medida que actualmente utiliza la compañía para comparar los resultados de sus modelos predictivos.

Actualmente, usan otro modelo de Machine Learning para realizar sus predicciones, pero este tiene un valor de 0,67, por lo que se busca obtener un valor AUC mayor al valor actual ya que significaría una mejora en su predicción.

3. Descripción de los datos de entrenamiento

Como ya indiqué anteriormente, los datos corresponden a registros de estatus de funcionamiento de un conjunto de antenas (con aproximadamente 130 variables) realizados por la compañía de telecomunicaciones. Son cerca de 24.000 registros, de los cuales aproximadamente el 2% corresponde a casos positivos (casos de falla).

Lamentablemente por motivos de confidencialidad con la empresa, no puedo entregar más información al respecto de los datos obtenidos.

4. Descripción inicial de una arquitectura de Deep Learning

Dado que modelaré el problema en base a series de tiempo de los datos registrados, la literatura recomienda utilizar una arquitectura de Redes Neuronales Recurrentes. Y en particular pienso utilizar una red LTSM (Long Short Term Memory).

![Diagrama de red LTSM](LSTM_2.JPG)




5. Repositorio de código

https://github.com/plemush/plemush