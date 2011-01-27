Ejercicios de arrays y ficheros
===============================


#. Crear un programa que resuelva la ecuación de segundo grado :math:`ax^2 + bx + c = 0` para cualquier valor de *a*, *b* y *c* comprobando el valor del descriminante :math:`\Delta = b^2 - 4ac`. 

#. La media aritmética, pesada y geométrica de una serie de números se definen respectivamente como

   .. math::

      \bar{x} = \frac{1}{n}\cdot \sum_{i=1}^n{x_i}, \hspace{1cm} \bar{x} = \frac{\sum_{i=1}^n{w_i \cdot x_i}}{\sum_{i=1}^n {w_i}}, \hspace{1cm} \bar{x} =  \prod_{i=1}^n{x_i}  

   Calcular estos valores para la lista de números 34.4, 30.1, 29.8, 33.5, 30.9, 31.1 y pesos 0.9, 0.79, 0.84, 0.6, 0.88, 0.78.

#. Cree un programa que calcule la desviación estándar de los números en un array, es decir, calcular:

   .. math::

      s = \sqrt{\frac{1}{N-1} \sum_{i=1}^N (x_i - \overline{x})^2}.

#. Usando la función randint de numpy.random, genere una lista de 30 números enteros. Calcule la media y desviación estándar entre grupos de 5 en 5 poniendo los resultados en arrays, es decir, obtener un array con las medias y otro con las desviaciones estándar, que serán de longtud 30/5. Crear un fichero con tres columnas que contenga el número de línea, la media y la desviación estándar.

#. La función **arctan2** del módulo math o de numpy permite calcular el arcotangente de (y,x) medido en radianes, lo que permite mantener la información sobre los cuadrantes. El valor medio de *n* ángulos se puede realizar con la siguente ecuación:

   .. math::
 
      M \theta = \operatorname{arctan2}\left(\frac{1}{n}\cdot\sum_{j=1}^n \sin\theta_j, \frac{1}{n}\cdot\sum_{j=1}^n \cos\theta_j\right)

   Calcule el valor medio de los ángulos 12.3, 10.1, 11.9, 12.4, 10.4 y 10.9.

#. Calcule en un *array* los valores que toma la función seno cociente :math:`sen(\theta)/\theta` para valores de :math:`\theta` entre -45º y 45º a intervalos de 0.1º. Escriba el resultado en un fichero que incluya en una columna el ángulo  :math:`\theta` en grados y en otra el valor de seno cociente correspondiente.

#. En el fichero *datos_2col.txt* hay dos columnas de datos. Calcular la raíz cuadrada de los valores de la primera columna y el cubo de la segunda y escribirlos a un nuevo fichero de dos columnas, pero solo para las entradas cuyos valores de la segunda columna de datos original sean mayor o igual a 0.5. 

#. El fichero *datos_4col.txt* contiene cuatro columnas de datos. Escribir un fichero de datos con cuatro columnas que incluya el número de entrada (empezando por 1), el promedio entre las dos primeras columnas, el promedio entre las dos últimas y la diferencia entre ambas medias. 



