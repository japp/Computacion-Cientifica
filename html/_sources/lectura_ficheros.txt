Lectura y escritura de ficheros 
===============================

Muy a menudo tenemos datos de un cálculo o medidas de un experimento en un fichero de texto. Para poder manipular estos datos debemos aprender a leerlos como números o arrays para poder analizarlos. Igualmente, el resultado de un cálculo o un análisis es necesario volcarlo a un fichero de texto en lugar de mostrarlo por pantalla para conservar el resultado. Esto es especialmente necesario cuando los resultados son *arrays* largos o cuando tenemos que procesar gran cantidad de números de ficheros generados automáticament. Vamos a ver cómo leer y escribir ficheros de texto con Python.

Creando un fichero sencillo
---------------------------

El primer paso para manipular un fichero, ya sea para crearlo, leerlo o escribir en él es crear una **instancia** a ese fichero; una instancia es una llamada o referencia, en este caso a un fichero, a la que se le asigna un nombre. Esto consiste simplemente en "abrir" el fichero en modo de lectura, escritura, para añadir o una combinación de estos, según lo que necesitemos:

.. sourcecode:: ipython

   In [48]: fichero_leer = open('mi_fichero.txt', 'r')         
   In [48]: fichero_escribir = open('mi_fichero.txt', 'w')  
   In [48]: fichero_escribir = open('mi_fichero.txt', 'a')   
   In [48]: fichero_leer = open('mi_fichero.txt', 'rw')

En los ejemplos anteriores se ha abierto un fichero de varias maneras posibles, donde hemos indicado en el primer parámetro el nombre del fichero y el segundo el **modo de apertura**:

.. sourcecode:: text

  'r'  -> Abre el fichero mi_fichero.txt para leer (debe existir)
  'w'  -> Abre el fichero mi_fichero.txt para escribir. Si no 
           existe lo crea y si existe sobrescribe el contenido.
  'a'  -> Abre el fichero mi_fichero.txt para añadir. Si no 
           existe lo crea y si existe continua escribiendo en al final del fichero.
  'rw' -> Abre el fichero mi_fichero.txt para leer y escribir


Vamos a crear un fichero y escribir algo en él. Lo primero es abrir el fichero en modo escritura:

.. sourcecode:: ipython

   In [49]: fs = open('prueba.txt', 'w')
   In [50]: type(fs)
   Out[50]: <type 'file'>

aquí la variable **fs** es una instancia o llamada al fichero. A partir de ahora cualquier operación que se haga al fichero se hace a esta instancia **fs** y no el nombre del fichero en sí. Escribamos ahora algo de contenido, para esto se emplea el método **write()** a la instancia del fichero:

.. sourcecode:: ipython

   In [51]: fs.write('Hola, estoy escribiendo un texto a un fichero')
   In [52]: fs.write('Y esta es otra linea')
   In [53]: fs.write( str(exp(10)) )
   In [54]: fs.close()                # Cerramos el fichero

Al teminar de trabajar con el fichero debemos cerrarlo con el método **close()**, es aquí cuando realmente se escribe el fichero y no hay que olvidar cerrarlo siempre al terminar de trabajar con él. Una vez cerrado se abrir con un editor de textos como Kate o gEdit. Veremos que cada orden de escritura se ha hecho consecutivamente y no línea a línea. Si queremos añadir líneas nuevas debemos ponerlas explícitamente con ``\\n`` que el código ASCII para una nueva línea:

.. sourcecode:: ipython

   In [55]: fs = open('prueba.txt', 'a')
   In [56]: fs.write("\n\n")                      # Dejo dos lineas en blanco
   In [57]: fs.write("Esta es una linea nueva\n")   
   In [58]: fs.write("Y esta es otra linea\n")   
   In [59]: fs.close()


De igual manera podemos usar un bucle **for** para escribir una lista de datos:

.. sourcecode:: ipython

   In [61]: fsalida = open('datos.txt', 'w')
   In [62]: for i in arange(100.):
      ....:     fsalida.write('%d  %10.4f\n' % (i, exp(i)))     # Escribe usando 10 caracteres en total,
   In [63]: fsalida.close()                                     # con 4 decimales


Lectura de ficheros
-------------------

Ahora podemos leer este fichero de datos u otro similar que ya exista. Una vez abierto el fichero para lectura, podemos crear una lista vacía para cada columna de datos y luego con un bucle leerlo línea por línea separando cada una en columnas con el método **split()**. Veámoslo con un ejemplo; queremos leer el fichero "datos.txt" acabamos de crear antes. Contiene 100 filas con dos columnas, la primera un número y la segunda su exponencial. Lo podríamos hacer de esta forma:

.. sourcecode:: ipython

   In [69]: fdatos = open('datos.txt', 'r')   #  Abrimos el fichero "datos.txt" para lectura
   In [70]: x_datos = []
   In [71]: y_datos = []
   In [73]: for linea in fdatos:
      ....:     x, y = linea.split()           # Se separa cada línea en columnas
      ....:     x_datos.append(float(x))       # Añado el elemento x a la lista x_datos
      ....:     y_datos.append(float(y))       # Añado el elemento y a la lista y_datos
      ....:     
      ....:     

   In [75]: fdatos.close()

   In [77]: type(x_datos)
   Out[77]: <type 'list'>

   In [78]: len(x_datos)
   Out[78]: 100

   In [79]: x_datos, y_datos = array(x_datos), array(y_datos)

   In [80]: type(x_datos)
   Out[80]: <type 'numpy.ndarray'>

   In [81]: x_datos.shape
   Out[81]: (100,)


Ahora que tenemos todos los datos en arrays los podemos manipular como tales. Recuerda que **split()** separa por defecto por espacios, si queremos separar por comas u otro caracter debemos incluirlo como parámetro: **split(',')**.

Lectura y escritura con Numpy
-----------------------------

Una manera alternativa de guardar y leer arrays es usando los métodos **savetxt()** y **loadtxt()** de **numpy**, que guardan y leen ficheros de texto con **una línea por columna**.

.. sourcecode:: ipython

   # Guardamos en el fichero "datos2.txt" (creándolo) dos columnas 
   # que contienen los arrays x_datos e y_datos
   savetxt("datos2.txt", (x_datos, y_datos))
   
   # Leemos el fichero que acabamos de crear y  
   # almacenamos los arrays en x e y
   x, y = loadtxt("datos2.txt")


Consulta la ayuda de la función leadtxt() de **numpy** para conocer otras opciones de lectura como seleccionar columnas determinadas, usar distintos delimitadores de columnas, etc.


Ejercicios
----------

#. En el fichero *datos_2col.txt* hay dos columnas de datos. Calcular la raíz cuadrada de los valores de la primera columna y el cubo de la segunda y escribirlos a un nuevo fichero de dos columnas, pero solo para las entradas cuyos valores de la segunda columna de datos original sean mayor o igual a 0.5. 

#. El fichero *datos_4col.txt* contiene cuatro columnas de datos. Escribir un fichero de datos con cuatro columnas que incluya el número de entrada (empezando por 1), el promedio entre las dos primeras columnas, el promedio entre las dos últimas y la diferencia entre ambas medias. 


