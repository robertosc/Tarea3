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

## Parte 3



## Parte 4: Curvas de mejor ajuste para las funciones de densidad marginales

Para esta sección se utilizó la función definida para retornar la ecuación gaussiana evaluada en un dominio deseado y con los parámetros mu y sigma para el caso. Puesto que se desea obtener una curva continua se debe utilizar un vector con bastantes puntos para obtener mayor precisión, utilizando la librería numpy y su función linspace se generó un espacio entre (5, 15) para X y (5, 25) para Y. Una vez se tienen las imágenes de la curva gaussiana se puede graficar con matplotlib.

<img src="../master/images/curvax.png">


<img src="../master/images/curvay.png">
