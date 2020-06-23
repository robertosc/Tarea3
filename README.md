# Tarea3: Variable aleatoria múltiple

## Parte 1: modelo probabilístico para las funciones de densidad marginales de X y Y

Se tiene una serie de datos de una variable aleatoria para los cuales se desea conocer su función de densidad marginal probabilística. Puesto que en este caso se cuenta con un fenómeno discreto, esta se obtiene mediante de la sumatoria de los valores en las fila de X y las columnas de Y, de modo que se obtiene la función probabilidad marginal en forma de un vector. Una vez realizados estos cálculos, se grafican los resultados en un histograma para cada una de las variables aleatorias.

![](../master/images/densx.png)

![](../master/images/densy.png)

Los histogramas mostrados en las figuras previas se asemejan a una curva de distribución normal, por lo tanto este será el la curva de ajusta que se buscará obtener en esta sección. Para ello se define una función que retorna un la ecuación gaussiana.


## Parte 2: función de densidad conjunta

En este caso la función de densidad conjunta se obtiene de manera analítica utilizando los resultados obtenidos de la curva de mejor ajuste de la parte 1, se obtuvo el valor de sigma y mu para la distribución de X y de Y. Por medio de la función de scipy  curve_fit se obtuvo lo siguiente:


<img src="../master/images/datos.png" width="80">

Asumiendo que los datos son independientes entre sí mismos, se tiene que la función de densidad marginal conjunta se puede obtener de la siguiente manera.

<img src="../master/images/ec1.png" width="200">

Utilizando los datos obtenidos de mu y sigma se obtiene las ecuaciones de la PMF para la variable aleatoria X y Y, estas vienen dadas por

<img src="../master/images/ec2.png" width="250">

De modo que la función de densidad conjunta se modela por la siguiente ecuación

<img src="../master/images/ec3.png" width="400">

## Parte 3: Parámetros de interés

Para los datos se pidió obtener una serie de parámetros para anaizar diferentes aspectos. El primero que se halló fue la correlación entre las variables aleatorias. Este dato no dice mucha información por sí mismo, sin embargo es muy útil para halar la similitud entre la variables aleatorias al obtener la covarianza. Si este parámetro es cero o muy cercano a cero, se puede asumir que no hay similitud entre las variables o bien, los datos son ortogonales. Este parámetro en forma discreta se calcula de la siguiente manera:

<img src="../master/images/ec4.png" width="300">

Para este cálculo se aprovechó la funcionalidad de la librería pandas, que permite multiplicar columnas entre sí. Puesto que se tenía un documento con los datos de la forma x,y,probabilidad, bastó con multiplicar estas columnas y luego obtener la sumatoria de la columna resultante. Se obtuvo el siguiente resultado:

<img src="../master/images/dato1.png" width="100">

Para saber si los datos están correlacionados se halló el valor esperado de cada variable aleatoria por separado, se sabe que si se cumple la siguiente relación, los datos no están correlacionados.

<img src="../master/images/ec5.png" width="150">

<img src="../master/images/dato2.png" width="150">

Puesto que ambos resultados son muy similares se puede asumir que los datos no están correlacionados. Este se puede confirmar con el dato de covarianza y el coeficiente de pearson. 

La covarianza no dice que tan similares son dos variables aleatorias, si el valor de la covarianza tiende a 0, se puede decir que las variables no están correlacionadas. La covarianza se obtiene por medio de la siguiente ecuación:

<img src="../master/images/ec6.png" width="300">

De modo que se obtuvo que

<img src="../master/images/dato3.png" width="100">

El coeficiente de pearson es otra medida de qué tan relacionados se encuentran los datos, sin embargo da más información. Este parámetro dice sí los datos tienen una distribución lineal. Cuando el coeficiente es cercano a 1, se tiene una distribución con pendiente positiva y si fuera cercano o igual a -1, la pendiente de la distribución es negativa. En este caso, se confirma lo mencionado previamente respecto a a la correlación.

<img src="../master/images/ec7.png" width="100">

<img src="../master/images/dato4.png" width="100">





## Parte 4: Curvas de mejor ajuste para las funciones de densidad marginales

Para esta sección se utilizó la función definida para retornar la ecuación gaussiana evaluada en un dominio deseado y con los parámetros mu y sigma para el caso. Puesto que se desea obtener una curva continua se debe utilizar un vector con bastantes puntos para obtener mayor precisión, utilizando la librería numpy y su función linspace se generó un espacio entre (5, 15) para X y (5, 25) para Y. Una vez se tienen las imágenes de la curva gaussiana se puede graficar con matplotlib.

<img src="../master/images/curvax.png">


<img src="../master/images/curvay.png">

El caso de la gráfica de la función de densidad marginal conjuta es más complejo puesto que se debe graficar en 3 dimensiones. Para este caso no basta con tener dos espacios lineales para cada variable aleatoria, se debe generar una matriz de coordenadas de X y Y. Se debe añadir una variable que contenga la función de densidad conjunta y se evalúe en los valores de X y Y de la matriz de coordenadas. Esto se grafica utilizando la función de matplotlib: mpl_toolkits.mplot3d.

<img src="../master/images/conju.png">

En la curva en 3 dimensiones previa se observa que se mantiene la forma de una curva gaussiana en los ejes x y y.
