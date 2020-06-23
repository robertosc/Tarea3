# Tarea3: Variable aleatoria múltiple

## Parte 1: modelo probabilístico para las funciones de densidad marginales de X y Y

Se tiene una serie de datos de una variable aleatoria para los cuales se desea conocer su función de densidad marginal probabilística. Puesto que en este caso se cuenta con un fenómeno discreto, esta se obtiene mediante de la sumatoria de los valores en las fila de X y las columnas de Y. Una vez realizados estos cálculos, se grafican los resultados en un histograma.

![](../master/images/densx.png)

![](../master/images/densy.png)

Los histogramas mostrados en las figuras previas se asemejan a una curva de distribución normal, por lo tanto este será el la curva de ajusta que se buscará obtener en esta sección. Para ello se define una función que retorna un la ecuación gaussiana.


## Parte 2: función de densidad conjunta

En este caso la función de densidad conjunta se obtiene de manera analítica utilizando los resultados obtenidos de la curva de mejor ajuste de la parte 1, se obtuvo el valor de sigma y mu para la distribución de X y de Y. Por medio de la función de scipy  curve_fit se obtuvo lo siguiente:

![](../master/images/datos.png)

Asumiendo que los datos son independientes entre sí mismos, se tiene que la función de densidad marginal conjunta se puede obtener de la siguiente manera.

![](../master/images/ec1.png)

Utilizando los datos obtenidos de mu y sigma se obtiene las ecuaciones de la PMF para la variable aleatoria X y Y, estas vienen dadas por
![](../master/images/ec2.png)

De modo que la función de densidad conjunta se modela por la siguiente ecuación
![](../master/images/ec3.png)
