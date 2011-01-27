Ejercicios
==========

Cadenas de texto y control de flujo
-----------------------------------

#. Dada la frase "En un lugar de la mancha cuyo nombre no quiero acordarme"

    * ¿Cuantas letras tiene? y palabras?
    * Selecciona las 15 primeras letras. ¿Y las cinco primeras palabras?
    * ¿Cuántas letras tiene la última palabra?
    * Concatena (une) el primer tercio de la fase con el último tercio.

#. Calcula la edad media de una clase cuyos alumnos tienen edades de 18.3, 19.0, 17.9, 19.2, 18.5, 21.0 y 17.6 años.
#. Calcula el factorial de un número *n* cualquiera. Es decir, calcula:

   .. math::

      n!=\prod_{k=1}^n k\qquad\mbox{para }n\ge0


#. En una lista de números cualesquiera, encuentra el mayor.
#. La variación de temperatura de un objeto a temperatura :math:`T_0` en un ambiente a :math:`T_s` cambia de la siguiente manera:

   .. math::

      T =  T_s + (T_0 - T_s)e^{-kt}

   con :math:`t` en horas y *k* un parámetro que depende del líquido. Una lata de refresco a 5º queda en la guantera del coche a 40º. ¿Qué temperatura tendrá cada hora hasta pasadas 24 horas? Utiliza *k=0.45*. Encuentra las horas que tendría que estar para alcanzar la temperatura ambiente.

#. Calcular el valor de :math:`\pi` empleando la siguiente expresión:

   .. math::
     
      4 \sum^n_{k=1} \frac{(-1)^{k+1}}{2k - 1}


#. Haz un programa que calcule volumen de una esfera, cilindro o un cono. El programa debe pedir los datos necesarios según lo que se desea calcular. Define una función para cada figura geométrica.

#. Dada la lista de notas de los alumnos de una clase, decir quien ha sacado aprobado (más de 5), notable (más de 7), sobresaliente (más de 9) o ha suspendido.

            ===============    =======
            Alumno             Nota
            ===============    =======
            Miguel             6.7
            Maria              4.9
            Iballa             9.8
            Fran               5.0
            Luisa              6.7
            Ruyman             8.0
            Ana                6.2
            ===============    =======


Suponiendo que todos los nombres de chica terminan con "a" (lo que casualmente en este ejemplo es cierto), decir si cada uno es chico o chica. 

Funciones y arrays
------------------

#. En ocasiones tenemos datos de fecha y hora en formato año/mes/dia horas:minutos:segundos que nos conviene convertir a fracción de año para manipularlo. Cree una función que a partir de la fecha y hora dé la fracción de año con decimales, es decir, una función del tipo ``funcion(anho, mes, dia, horas, minutos, segundos)`` que dé como resultado un valor del tipo 2009.230456, suponiendo que un año tiene 365.25 días. 

#. Escriba una funcion que calcule el resto o módulo de una división.

#. Para el cálculo de la letra del DNI se calcula el módulo 23 del número, es decir, la división entera del número del DNI entre 23. El resultado será siempre un valor entre 0 y 22 y cada uno de ellos tiene asignado una letra según la siguiente tabla:


   ``0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22``

   ``T R W A G M Y F P D  X  B  N  J  Z  S  Q  V  H  L  C  K  E``


   Escriba un programa que calcule letra de cualquier DNI. El programa debe comprobar que la entrada tiene ocho dígitos.

#. Cree una función la cual para un array unidimensional de longitud n, haga el promedio de m elementos consecutivos. El resultado será otro array o lista de longitud n/m. La función sólo debe admitir valores enteros de m/n con una comprobación previa.

#. Calcule todos los números inferiores a 500 que son multiplos de 5 y 7.


#. Se llama sucesión de Fibonacci a la colección de ``n`` números para la que el primer elemento es cero, el segundo 1 y el resto es la suma de los dos anteriores. Por ejemplo, la sucesión para n=5 es (0, 1, 1, 2, 3). Crear un programa que calcule la lista de números para cualquier ``n``.

#. Para una lista de números como esta:

   nums = [23.4, 5.0, -12.3, 54.0, 3.0, -7, 64.5, 56.7, 23.3, 34.94, 5, 20., -3. , 13., 10, 9.0, -1]

   escriba un código que los añada a listas de números positivos, negativos y mayores o iguales a 10 según el caso. Un número puede estar en varias listas.

#. Sumar los cien primeros elementos de la serie :math:`\sum_{k=1}^n\frac{1}{k^2}`. Hacer un gráfico del valor que va tomando dicha suma hasta sumar esos cien elementos.

#. El producto de dos arrays bidimensionales de Numpy se hace hace elemento a elemento. Defina una función que calcule el producto matricial de dos arrays bidimensionales. 


Gráficos y cálculo numérico
---------------------------

#. El movimiento de oscilador amortiguado se puede expresar la siguiente manera:

	.. math::
		
		x = A_0 e^{-k\omega t} \cos{(\omega t + \delta)}
	

   Siendo :math:`A_0` la amplitud inicial, :math:`\omega` la fecuencia de oscilación y *k* el factor de amortiguamiento. Representar gráficamente el movimiento de un oscilador forzado de amplitud inicial de 10cm y frecuencia de 10 ciclos por segundo y :math:`\delta=\pi/8` con factores de amortiguamiento de 0.1, 0.4, 0.9 y 1.1.
	
   Para el gráfico correspondiente a *k=0.1* dibujar con líneas a trazos los valores máximos y mínimos del movimiento osciliatorio. Nótese correspondena las curvas para las que :math:`x=A_0` y :math:`x=-A_0`.

#. Calcular numéricamente las siguientes integrales
	
	.. math::
	
		2\pi \int_0^1 x^3 \sqrt{1 + 9x^4}~dx   ~~~~~~~~~~~~   \int_0^{2\pi}e^{-x} \sin{(10x)}~dx
	

#. Calcular numéricamente el área más pequeña comprendida entre un círculo :math:`x^2 + y^2 = 25` y la recta *x=3*.

#. Crear una función que calcule numéricamente la siguiente integral admitiendo parámetros de entrada *m* y *n*:

	.. math::
	
		2\pi \int_0^1 \frac{x^m - x^n}{\ln{x}} dx  = \ln{\frac{m+1}{n+1}} 

#. Resolver el sistema **AX=B** donde:

	.. math::
	
		\begin{array}{ccc} 
		\mathbf{A=}
		\left[
		\begin{array}{cccc} 
		1 & 3 & 5 & 7\\
		2 & -1 & 3 & 5\\
		0 & 0 & 2 & 5\\
		-2 & -6 & -6 & 1
		\end{array}
		\right] & y &
		\begin{array}{ccc} 
		\mathbf{B=}
		\left[
		\begin{array}{c} 
		1\\
		2 \\
		3\\
		4
		\end{array}
		\right]
		\end{array}
		\end{array}



