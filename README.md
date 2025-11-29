LABORATORIO FINAL

Laboratorio Final, presentado por Laura Mosquera y Celeste Isaza.

PARTE 1:

CONSULTAR LA IMPLEMENTACION DEL REGRESOR LINEAL CON SKLEARN.
El regresor lineal con SKLEARN, funciona aplicando el método de mínimos cuadrados ordinarios (OLS). Esta es una técnica matemática que se usa para encontrar la mejor línea recta que se ajusta a un conjuntos de puntos.

Inicialmente supone un modelo de tipo:
image
donde w son los coeficientes y b es el bias o sesgo.

Luego, ajusta los coeficientes buscando la linea o hiperplano que mejor se ajuste a los datos.

Para encontrar esa línea, SKLEARN calcula los valores de w y b que minimizan la suma de los errores al cuadrado, así:

image
Finalmente, el modelo ya tendra los coeficientes y solo hará lo siguiente:
image
GRAFIQUE LOS COSTOS VS LAS EPOCHS.

image
Conclusión:

El MSE comienza alto y baja rápidamente en las primeras épocas, el modelo aprende rapidamente al inicio ajustando los pesos de forma efectiva.

PRESENTE LAS METRICAS DE REGRESION CON SU RESPECTIVA INTERPRETACION (R2, MSE, MAE...Y LAS QUE ESTAN ESPECIFICADAS EN EL NOTEBOOK).

R², mide la proporción de la variabilidad de la variable objetivo que el modelo logra explicar, basicamente dice qué tan bien el modelo explica los datos.

Rango:

0: no explica nada.

1: prefecto.

Negativo: peor que adivinar.

MAE (Error absoluto medio), es un promedio de cuánto se equivoca el modelo. Entre mas pequeño se a el valor que arroje, mejor.

Por ejemplo: sí dio 5, esto siginifica que el modelo se equivoca en promedio en 5 unidades.

Coeficiente de correlación de Pearson (r), mide qué tan linealmente relacionados están los valores reales y las predicciones.

Rango:

1: relación perfecta y positiva.

0: no hay relación.

–1: relación perfecta pero inversa.

Mientras más cerca esté de 1, mejor está prediciendo la tendencia.

MAPE (Error porcentual absoluto medio), es un promedio del error, pero en porcentaje. Entre más bajo sea el valor que arroja mejor.

Análisis de las metricas obtenidas en nuestro modelo

image
PARTE 2:

CONSULTAR LA IMPLEMENTACION DEL PERCEPTRON SIMPLE CON SKLEARN.
El perceptrón simple con SKLEARN es un modelo que toma varias entradas, las combina y decide si la salida es 0 o 1.

Este método funciona de la siguiente manera:

Cada entrada se multiplica por un “peso”. Luego se suman todas esas multiplicaciones y se añade un sesgo (bias).

La suma anterior pasa por una regla muy simple:

Si el resultado es mayor que un umbral: predice 1

Si es menor: predice 0

Cuando se equivoca, corrige los pesos.

Si predijo 1 y era 0: baja los pesos.

Si predijo 0 y era 1: sube los pesos.

GRAFIQUE LOS COSTOS VS LAS EPOCHS , QUE CONCLUSION PUEDE SACAR?.
image
Conclusiones:

El modelo no comete muchos errores: el costo se mantiene por debajo de 15 en todas las épocas, lo cual es bajo considerando que hay 150 muestras.

Hay fluctuaciones visibles: el número de errores sube y baja en distintas épocas, lo que indica que el modelo está ajustando su frontera de decisión constantemente.

No hay una tendencia clara de descenso sostenido, lo que sugiere que el modelo está reentrenándose desde cero en cada época

GRAFIQUE EL ACCURACY VS LAS EPOCHS, QUE CONCLUSION PUEDE SACAR?
image
Conclusiones:

Inicio (épocas 0–30): El accuracy comienza por debajo de 0.92, lo que indica que el modelo aún está aprendiendo y cometiendo errores significativos.

Rápido ascenso (épocas 30–60): Hay una mejora abrupta: el modelo aprende rápidamente a clasificar mejor y supera el 96% de precisión.

Estabilización (épocas 60–300): El accuracy se mantiene alto, entre 0.96 y 1.00, con pequeñas fluctuaciones. Esto sugiere que el modelo ha convergido y está generalizando bien.

PRESENTE LAS METRICAS DE CLASIFICACION CON SU RESPECTIVA INTERPRETACION (ACCURACY, F1-SCORE, MATRIZ DE CONFUSION, SENSIBILIDAD Y ESPECIFICIDAD).
Accuracy, esta metrica mide el porcentaje de predicciones correctas del modelo. Entre más grande sea el valor arrojaod, mejor.

F1-SCORE, esta métrica combina Precision y Recall en un solo valor. Sirve para ver si el modelo predice bien la clase 1 sin cometer muchos errores.

Siendo:

precisión = (aciertos en clase 1) ÷ (todas las predicciones de 1)

Alta precisión: cuando el modelo dice “es 1”, casi siempre es verdad.

Baja precisión: predice muchos falsos positivos.

Matriz de Confusión, esta es una tabla que muestra cuántos aciertos y errores tiene el modelo en cada clase:

TP: predijo 1 y era 1 (True Positive)

TN: predijo 0 y era 0 (True Negative)

FP: predijo 1 y era 0 (False Positive)

FN: predijo 0 y era 1 (False Negative)

La ventaja de esta métrica es que dice en qué se esta fallando, por ejemplo:

Muchos FN: está fallando al reconocer positivos.

Muchos FP: está dando falsos positivos.

Sensibilidad (Recall), esta nos indica qué tan bien detecta la clase positiva (1).

Sensibilidad alta: el modelo no deja escapar positivos.

Sensibilidad baja: pierde muchos casos reales de la clase 1.

Especificidad, esta indica qué tan bien detecta la clase negativa (0).

Especificidad alta: el modelo se equivoca poco con la clase 0.

Especificidad baja: da demasiados falsos positivos.

Análisis de las metricas obtenidas en nuestro modelo

image
POR QUÉ SON TAN DIFERENTES ESTAS METRICAS RESPECTO A LAS DE REGRESIÓN?
image
Son diferentes porque regresión predice números y clasificación predice categorías, así que necesitan métricas que midan cosas completamente distintas.
