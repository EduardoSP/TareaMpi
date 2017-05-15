# TareaMpi
1210076 Multiplicación matriz vector Mpi

La función distributereceive consiste en tres partes:

La primera parte envia cada fila para que realice una tarea(TAGTAREA)y se le asigna un proceso(se controla con la variable procesoActual)

La segunda parte recibe los resultados de los procesos.

Para la tercera parte como ya no hay filas que procesar se le envía un mensaje a cada proceso para que sean detenidos, en este mensaje se utiliza la variable TAGPARAR.


La función receive.

En la función receive se recibe el vector b del maestro(rank=0) utilizando el TAGVECTOR.

Se utiliza la variable detener para controlar el procesamiento. Hasta que no se reciba el TAGPARAR en el Stat.MPI_TAG. se seguirá ejecutando la función. Si no se recibe el TAGPARAR entonces siginifica que se está recibiendo filas del maestro y se debe realizar la operación para que el resultado de un trabajador se envíe al maestro.
Cuando el maestro envá el TAGPARAR entonces se detiene el procesamiento y se envía un mensaje para de que se detuvo al maestro para que se imprima por pantalla "no hay mas filas a procesar". 
