Arquitectura
 
Diego Alejandro Roldán Parrado 47412

Yonalid Martinez Chiquillo 56202

Andres Beltran 83724
______________________________________________________________________________



# lab05 : Unidad de suma, resta, multiplicación, división y visualización BCD
## Introducción


Para este paquete de trabajo, deben estar inscrito en un grupo y clonar la información del siguiente link [WP05](https://classroom.github.com/g/dHrBou9a). Una vez aceptado el repositorio debe descargarlo en su computador, para ello debe clonar el mismo. Si no sabe cómo hacerlo revise la metodología de trabajo, donde se explica el proceso

Las documentación deben estar diligencia en el archivo README.md del repositorio clonado.

Una vez clone el repositorio, realice lo siguiente:


## descipción 
La unidad aritmética, es tal que cuenta con componentes para realizar operaciones aritméticas. cada operación aritmética es ejecutada acuerdo al código de la operación. 

Como ejercicio académico, se propone construye una unidad con 4 operaciones aritméticas: suma, resta, multiplicación y división.  de igual manera, el resultados se visualiza en los display de siete segmentos. El flujo de datos y la selección de la operación se realiza acorde a la señal opcode, y segun la siguiente tabla:


opcode | operación  enteros positivos
00| suma
01| resta 
10|  multiplicación
11| división 

Por lo tanto, la unidad debe contar con:

1. Los dos puertos de entrada A y B. cada uno de  3 bits.
2. La señal `opcode` de dos bits, para configurar la operación que se realiza con los datos de `portA` y `portB`.
3. La a visualización de unidad debe tener las salidas de los 4 ánodos, `An`  y las 7 señales de los cátodos, `sseg`.
4. Para las FSM  y las visualización dinámica, se debe incluir la señal de `clk` de entrada.
5. la señal de reset del sistema

## Diagrama de caja negra

Según las especificaciones anteriormente descrita, la caja funcional de la unidad aritmética propuesta es:

![caja negra](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab06_Unidad_aritmetica/doc/cajanegra.png)


## Diagrama estructural

![estructural](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab06_Unidad_aritmetica/doc/diagraEstructural.png)

El diagrama estructural, se soporta en los componentes desarrollados en los anteriores laboratorios. De esta manera,  tanto el sumador, el multiplicador  y el Display, son tomados de los lab2, lab5 y lab4  respectivamente. Adicional a la estructura de cada operación se encuentra el decodificador  y el multiplexador.

## Entregables

1. Definir el diagrama estructurar interno de cada bloque funcionar 
2. Descargar la estructura propuesta de la  Unidad Aritmética del paquete de trabajo [WP05](https://classroom.github.com/g/dHrBou9a) Este proyecto cuenta con el archivo `alu.v` y, tiene la carpeta `src` que cuenta con las 5 carpetas de cada componente.
3. Implementar `alu.v` en la FPGA, y  comprobar el funcionamiento  de la suma la multiplicación y la visualización
4. Incluir el  HDL para le divisor  realizado en el ejercicio anterior, en la carpeta `src/divisor`  y, adicione los archivos e instanciar el bloque divisor.
5. Diseñar el bloque restador, adicionar dicho bloque a la respectiva carpeta e instanciar el modulo en `alu.v`.
6. Realizar el testbench del bloque alu.
7. implementar el sistema completo en la FPGA remota
8. hacer la documentación respectiva en el archivo README
  
SOLUCION LAB5 
________________________________________________________________________________________________________________________________
Diagrama Estructural de la SUMA.

![Sumador](https://user-images.githubusercontent.com/62714712/80239337-ac3fdd80-8625-11ea-9c20-ee2d953edb7e.png)

Caja Negra de 3 bits

![sumador3](https://user-images.githubusercontent.com/62714712/80239725-5881c400-8626-11ea-8c2b-0549f57023b2.png)

Instanciamiento de 3 bits 

![sumador3bits](https://user-images.githubusercontent.com/62714712/80239338-acd87400-8625-11ea-9ad2-5c5185210bfc.png)

Diagrama De Flujo

![Proceso de soporte técnico](https://user-images.githubusercontent.com/62714712/80242997-f330d180-862b-11ea-860f-2cba9749ed28.png)

Multiplicaci�n 

Descripci�n de la caja negra 

La caja funcional o caja negra tiene como entradas multiplicando y el multiplicador�(A y B), se�ales de�m�bits cada una. la salida es el resultado de la multiplicaci�n�PP�(Bus de 2m Bits). Adem�s, la se�al de reloj (CLOCK), entrada. Las se�ales�INIT�y�DONE, entrada y salida, se utilizan para iniciar el proceso de multiplicaci�n e indicar que el resultado est� a disponible respectivamente

![multiplicador 1](https://user-images.githubusercontent.com/62735033/80259075-5c274200-864a-11ea-86d6-7213e712b1ae.png)

Descripci�n funcional

![descripcion multiplicador](https://user-images.githubusercontent.com/62735033/80259868-2edb9380-864c-11ea-8324-6246cf336cdd.png)




 
