# Sweet Crush

## Desafío numero 1 aprendiendo c++


## Autor
* Guillermo Alejandro Castillo Rueda



## Contextualización del Problema

Realizaremos una interfas grafica del juego **Sweet Crush**, el cual contará con **6 fichas diferentes** que interactúan en un tablero. El juego consiste en alinear de forma vertical u horizontal 3 o más fichas de la misma clase. Cuando estas se alinean, se eliminan y las demás fichas caen por gravedad para continuar el juego.

### Empaquetado de Memoria (Bitwise)

Cada ficha es representada mediante **3 bits**, empaquetando todo el tablero dentro de un arreglo dinámico continuo de bytes (unsigned char*).

<img width="1600" height="1382" alt="004f09dc-e2cb-4cc5-aa75-662e620705fa" src="https://github.com/user-attachments/assets/d6337e39-8049-41b1-8502-08c1ff789496" />



## Análisis del problema

Lo vamos a plantear de la siguiente forma: cómo optimizar y aprovechar de forma eficiente la memoria RAM y cómo empaquetar los 3 bits, ya que estamos trabajando dentro de los 8 bits que tiene el char.

Como tenemos que trabajar con 3 bits y lo mínimo es 1 byte, que es igual a 8 bits, el reto es organizar una secuencia lineal con los bits. Si usáramos un char entero para cada ficha, estaríamos perdiendo 5 bits por cada casilla, lo cual no es eficiente. Por eso, el problema principal es empaquetar esos 3 bits dentro de los 8 que tiene el char sin que se pierda la secuencia. 

Esto se organizaría dentro de un arreglo dinámico para que sea consecutivo y poder hacer uso de todos los espacios de memoria. Al trabajar de esta forma continua, se presentan los "casos frontera", donde una misma ficha queda repartida entre el final de un byte y el inicio del siguiente como pasa con la ficha C o la F. Para resolver esto y saber exactamente en qué bit y byte está cada ficha, necesitamos aplicar fórmulas de posicionamiento y operaciones de bits.



<img width="1083" height="1600" alt="066d3714-684a-462f-bdb3-ad8aa14449cc" src="https://github.com/user-attachments/assets/54357e16-5c09-44c6-8430-325d5398a425" />

