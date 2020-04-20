Arquitectura
 
Diego Alejandro Rold�n Parrado 47412
Yonalid Martinez Chiquillo 56202
______________________________________________________________________________



# lab05 : Unidad de suma, resta, multiplicaci�n, divisi�n y visualizaci�n BCD
## Introducci�n


Para este paquete de trabajo, deben estar inscrito en un grupo y clonar la informaci�n del siguiente link [WP05](https://classroom.github.com/g/dHrBou9a). Una vez aceptado el repositorio debe descargarlo en su computador, para ello debe clonar el mismo. Si no sabe c�mo hacerlo revise la metodolog�a de trabajo, donde se explica el proceso

Las documentaci�n deben estar diligencia en el archivo README.md del repositorio clonado.

Una vez clone el repositorio, realice lo siguiente:


## descipci�n 
La unidad aritm�tica, es tal que cuenta con componentes para realizar operaciones aritm�ticas. cada operaci�n aritm�tica es ejecutada acuerdo al c�digo de la operaci�n. 

Como ejercicio acad�mico, se propone construye una unidad con 4 operaciones aritm�ticas: suma, resta, multiplicaci�n y divisi�n.  de igual manera, el resultados se visualiza en los display de siete segmentos. El flujo de datos y la selecci�n de la operaci�n se realiza acorde a la se�al opcode, y segun la siguiente tabla:


opcode | operaci�n  enteros positivos
00| suma
01| resta 
10|  multiplicaci�n
11| divisi�n 

Por lo tanto, la unidad debe contar con:

1. Los dos puertos de entrada A y B. cada uno de  3 bits.
2. La se�al `opcode` de dos bits, para configurar la operaci�n que se realiza con los datos de `portA` y `portB`.
3. La a visualizaci�n de unidad debe tener las salidas de los 4 �nodos, `An`  y las 7 se�ales de los c�todos, `sseg`.
4. Para las FSM  y las visualizaci�n din�mica, se debe incluir la se�al de `clk` de entrada.
5. la se�al de reset del sistema

## Diagrama de caja negra

Seg�n las especificaciones anteriormente descrita, la caja funcional de la unidad aritm�tica propuesta es:

![caja negra](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab06_Unidad_aritmetica/doc/cajanegra.png)


## Diagrama estructural

![estructural](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab06_Unidad_aritmetica/doc/diagraEstructural.png)

El diagrama estructural, se soporta en los componentes desarrollados en los anteriores laboratorios. De esta manera,  tanto el sumador, el multiplicador  y el Display, son tomados de los lab2, lab5 y lab4  respectivamente. Adicional a la estructura de cada operaci�n se encuentra el decodificador  y el multiplexador.

## Entregables

1. Definir el diagrama estructurar interno de cada bloque funcionar 
2. Descargar la estructura propuesta de la  Unidad Aritm�tica del paquete de trabajo [WP05](https://classroom.github.com/g/dHrBou9a) Este proyecto cuenta con el archivo `alu.v` y, tiene la carpeta `src` que cuenta con las 5 carpetas de cada componente.
3. Implementar `alu.v` en la FPGA, y  comprobar el funcionamiento  de la suma la multiplicaci�n y la visualizaci�n
4. Incluir el  HDL para le divisor  realizado en el ejercicio anterior, en la carpeta `src/divisor`  y, adicione los archivos e instanciar el bloque divisor.
5. Dise�ar el bloque restador, adicionar dicho bloque a la respectiva carpeta e instanciar el modulo en `alu.v`.
6. Realizar el testbench del bloque alu.
7. implementar el sistema completo en la FPGA remota
8. hacer la documentaci�n respectiva en el archivo README
  

 
