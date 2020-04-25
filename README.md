Arquitectura
 
Diego Alejandro RoldÃ¡n Parrado 47412

Yonalid Martinez Chiquillo 56202

Andres Beltran 83724
______________________________________________________________________________



# lab05 : Unidad de suma, resta, multiplicaciÃ³n, divisiÃ³n y visualizaciÃ³n BCD
## IntroducciÃ³n


Para este paquete de trabajo, deben estar inscrito en un grupo y clonar la informaciÃ³n del siguiente link [WP05](https://classroom.github.com/g/dHrBou9a). Una vez aceptado el repositorio debe descargarlo en su computador, para ello debe clonar el mismo. Si no sabe cÃ³mo hacerlo revise la metodologÃ­a de trabajo, donde se explica el proceso

Las documentaciÃ³n deben estar diligencia en el archivo README.md del repositorio clonado.

Una vez clone el repositorio, realice lo siguiente:


## descipciÃ³n 
La unidad aritmÃ©tica, es tal que cuenta con componentes para realizar operaciones aritmÃ©ticas. cada operaciÃ³n aritmÃ©tica es ejecutada acuerdo al cÃ³digo de la operaciÃ³n. 

Como ejercicio acadÃ©mico, se propone construye una unidad con 4 operaciones aritmÃ©ticas: suma, resta, multiplicaciÃ³n y divisiÃ³n.  de igual manera, el resultados se visualiza en los display de siete segmentos. El flujo de datos y la selecciÃ³n de la operaciÃ³n se realiza acorde a la seÃ±al opcode, y segun la siguiente tabla:


opcode | operaciÃ³n  enteros positivos
00| suma
01| resta 
10|  multiplicaciÃ³n
11| divisiÃ³n 

Por lo tanto, la unidad debe contar con:

1. Los dos puertos de entrada A y B. cada uno de  3 bits.
2. La seÃ±al `opcode` de dos bits, para configurar la operaciÃ³n que se realiza con los datos de `portA` y `portB`.
3. La a visualizaciÃ³n de unidad debe tener las salidas de los 4 Ã¡nodos, `An`  y las 7 seÃ±ales de los cÃ¡todos, `sseg`.
4. Para las FSM  y las visualizaciÃ³n dinÃ¡mica, se debe incluir la seÃ±al de `clk` de entrada.
5. la seÃ±al de reset del sistema

## Diagrama de caja negra

SegÃºn las especificaciones anteriormente descrita, la caja funcional de la unidad aritmÃ©tica propuesta es:

![caja negra](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab06_Unidad_aritmetica/doc/cajanegra.png)


## Diagrama estructural

![estructural](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab06_Unidad_aritmetica/doc/diagraEstructural.png)

El diagrama estructural, se soporta en los componentes desarrollados en los anteriores laboratorios. De esta manera,  tanto el sumador, el multiplicador  y el Display, son tomados de los lab2, lab5 y lab4  respectivamente. Adicional a la estructura de cada operaciÃ³n se encuentra el decodificador  y el multiplexador.

## Entregables

1. Definir el diagrama estructurar interno de cada bloque funcionar 
2. Descargar la estructura propuesta de la  Unidad AritmÃ©tica del paquete de trabajo [WP05](https://classroom.github.com/g/dHrBou9a) Este proyecto cuenta con el archivo `alu.v` y, tiene la carpeta `src` que cuenta con las 5 carpetas de cada componente.
3. Implementar `alu.v` en la FPGA, y  comprobar el funcionamiento  de la suma la multiplicaciÃ³n y la visualizaciÃ³n
4. Incluir el  HDL para le divisor  realizado en el ejercicio anterior, en la carpeta `src/divisor`  y, adicione los archivos e instanciar el bloque divisor.
5. DiseÃ±ar el bloque restador, adicionar dicho bloque a la respectiva carpeta e instanciar el modulo en `alu.v`.
6. Realizar el testbench del bloque alu.
7. implementar el sistema completo en la FPGA remota
8. hacer la documentaciÃ³n respectiva en el archivo README
  
SOLUCION LAB5 
________________________________________________________________________________________________________________________________

Imagen de como usar la FPGA

![WhatsApp Image 2020-04-23 at 10 14 38 PM](https://user-images.githubusercontent.com/62714712/80264470-df03c900-8659-11ea-8aa1-e4b25b8c0d1c.jpeg)

Se toman los 10 switch, y se dividen en dos;
De ahí parte todas las operaciones, cuando no le doy operación, el me muestra los números de los switch 


![partiendo](https://user-images.githubusercontent.com/62714712/80264739-b0d2b900-865a-11ea-8f49-cd794126ad26.png)

La unidad aritmética, es tal que cuenta con componentes para realizar operaciones aritméticas. cada operación aritmética es ejecutada acuerdo al código de la operación.

Opcode:Las posibles operaciones arimeticas que se pueden ejecutar en la ALU.


![TABLA](https://user-images.githubusercontent.com/62714712/80263655-ebd2ed80-8656-11ea-9d18-427c406b2630.png)

![principio](https://user-images.githubusercontent.com/62714712/80266493-da431300-8661-11ea-9c98-7519a86c875a.png)

Este código lo utilizamos para colocar los números que le ingresamos.
Se llama la función y en ella se le envía información, en este caso la información que recibe es:
A= 5bits
B= 5 bits
Como están en base hexadecimal (16), lo que se realiza es una conversión 
Ej: 10110 =22
Los primero 4 se toman normal 0110 =6
El 5 bit se multiplica por 16; si el 5 bit es 1 obtendremos 16 sino será 0. En este caso tenemos 0001=16
Después de ello sumamos y obtenemos
16+6 =22
El mismo ejercicio se realiza con el numero b, pero este al final se multiplica por 100, si tomamos el ejemplo anterior tendríamos 22*100=2200
B=2200

Y lo que realizamos al final es sumar los dos para obtener un solo número
RTA=a+b ; 
RTA=2200+22 
RTA = 2222
Y este es el proceso de acomodar los bits de entrada en el display

________________________________________________________________________________________________________________________________

Diagrama Estructural de la SUMA.


![Sumador](https://user-images.githubusercontent.com/62714712/80239337-ac3fdd80-8625-11ea-9c20-ee2d953edb7e.png)



Diagrama De Flujo

![Proceso de soporte tÃ©cnico](https://user-images.githubusercontent.com/62714712/80242997-f330d180-862b-11ea-860f-2cba9749ed28.png)

Se activan los display automaticamente  y los swich de la parte superiror e inferior son los que me van arrojar un valor a los display dicho valor va ser tomado por el boton B0 y va realizar una suma para realizar la suma implementamos la linea siguiente 


     if (op1==1)
			RTA = BCD1+BCD;
   
Simulacion de la Suma en Labsland

![suma](https://user-images.githubusercontent.com/62714712/80264594-41f56000-865a-11ea-91bc-5d2c65b4f091.png)


Resta:

La resta se toma usando las dos botoneras cada vez que activamos un swich dependiendo de la posicion nos va arrojar un valor que se va ver reflejado en el display teniendo estos valores el boton B1 es el responsable de realizar la resta la implementacion se realizo con la linea de codigo siguiente.

Valores ingresados 

![digitos](https://user-images.githubusercontent.com/62714712/80266649-a5838b80-8662-11ea-94d2-dc20df0e55fe.png)

if (op2==1)
	        if(BCD1>BCD)
			RTA = BCD1-BCD;
			else
			RTA= 1000+(BCD-BCD1);
			
   Resultado: 
   
   
   ![resta](https://user-images.githubusercontent.com/62714712/80266267-93085280-8660-11ea-87cd-b0357635db41.png)


   
_______________________________________________________________________________________________________________________________

Multiplicación 

Descripción de la caja negra 

La caja funcional o caja negra tiene como entradas multiplicando y el multiplicador (A y B), señales de m bits cada una. la salida es el resultado de la multiplicación PP (Bus de 2m Bits). Además, la señal de reloj (CLOCK), entrada. Las señales INIT y DONE, entrada y salida, se utilizan para iniciar el proceso de multiplicación e indicar que el resultado está a disponible respectivamente

![multiplicador 1](https://user-images.githubusercontent.com/62735033/80259075-5c274200-864a-11ea-86d6-7213e712b1ae.png)

Descripción funcional

![descripcion multiplicador](https://user-images.githubusercontent.com/62735033/80259868-2edb9380-864c-11ea-8324-6246cf336cdd.png)


________________________________________________________________________________________________________________________________

DIVISION:

Para activar la division usamos la siguiente linea

assign op3 = V_BT[2]; eso quiere que la division se activa cuando pulsamos el Boton 2

Para realizar la division usamos la siguiente lineas

if (op3==1)
	        if (BCD==0)
			RTA =0;
			else 
			RTA=BCD1/BCD;
			


Valores ingresados.


![division](https://user-images.githubusercontent.com/62714712/80266711-ea0f2700-8662-11ea-9e60-522c27074aeb.png)


Resultado:

![divisionresul](https://user-images.githubusercontent.com/62714712/80266712-ebd8ea80-8662-11ea-9cec-4ddc695a6af2.png)




