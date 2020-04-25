Arquitectura
 
Diego Alejandro Roldan Parrado 47412

Yonalid Martinez Chiquillo 56202

Andres Beltran 83724
______________________________________________________________________________



# lab05 : Unidad de suma, resta, multiplicaci�n, divisi�n y visualizaci�n BCD
## Introducci�n


Para este paquete de trabajo, deben estar inscrito en un grupo y clonar la informaci�n del siguiente link [WP05](https://classroom.github.com/g/dHrBou9a). Una vez aceptado el repositorio debe descargarlo en su computador, para ello debe clonar el mismo. Si no sabe c�mo hacerlo revise la metodolog�a de trabajo, donde se explica el proceso

Las documentaci�n deben estar diligencia en el archivo README.md del repositorio clonado.

Una vez clone el repositorio, realice lo siguiente:


## descipci�n 
La unidad aritm�tica, es tal que cuenta con componentes para realizar operaciones aritm�ticas. cada operaci�n aritm�tica es ejecutada acuerdo al c�digo de la operaci�n. 

Como ejercicio acad�mico, se propone construye una unidad con 4 operaciones aritm�ticas: suma, resta, multiplicaci�n y divisi�n.  de igual manera, el resultados se visualiza en los display de siete segmentos. El flujo de datos y la selecci�n de la operaci�n se realiza acorde a la se�al opcode, y segun la siguiente tabla:


opcode | operacion enteros positivos
00| suma
01| resta 
10|  multiplicacion
11| division

Por lo tanto, la unidad debe contar con:

1. Los dos puertos de entrada A y B. cada uno de  3 bits.
2. La se�al `opcode` de dos bits, para configurar la operaci�n que se realiza con los datos de `portA` y `portB`.
3. La a visualizaci�n de unidad debe tener las salidas de los 4�nodos, `An`  y las 7 se�ales de los cÃƒÂ¡todos, `sseg`.
4. Para las FSM  y las visualizaciÃƒÂ³n din�mica, se debe incluir la se�al de `clk` de entrada.
5. la se�al de reset del sistema

## Diagrama de caja negra

Seg�n las especificaciones anteriormente descrita, la caja funcional de la unidad aritmetica propuesta es:

![caja negra](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab06_Unidad_aritmetica/doc/cajanegra.png)


## Diagrama estructural

![estructural](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab06_Unidad_aritmetica/doc/diagraEstructural.png)

El diagrama estructural, se soporta en los componentes desarrollados en los anteriores laboratorios. De esta manera,  tanto el sumador, el multiplicador  y el Display, son tomados de los lab2, lab5 y lab4  respectivamente. Adicional a la estructura de cada operaciÃƒÂ³n se encuentra el decodificador  y el multiplexador.

## Entregables

1. Definir el diagrama estructurar interno de cada bloque funcionar 
2. Descargar la estructura propuesta de la  Unidad AritmÃƒÂ©tica del paquete de trabajo [WP05](https://classroom.github.com/g/dHrBou9a) Este proyecto cuenta con el archivo `alu.v` y, tiene la carpeta `src` que cuenta con las 5 carpetas de cada componente.
3. Implementar `alu.v` en la FPGA, y  comprobar el funcionamiento  de la suma la multiplicaciÃƒÂ³n y la visualizaciÃƒÂ³n
4. Incluir el  HDL para le divisor  realizado en el ejercicio anterior, en la carpeta `src/divisor`  y, adicione los archivos e instanciar el bloque divisor.
5. DiseÃƒÂ±ar el bloque restador, adicionar dicho bloque a la respectiva carpeta e instanciar el modulo en `alu.v`.
6. Realizar el testbench del bloque alu.
7. implementar el sistema completo en la FPGA remota
8. hacer la documentaciÃƒÂ³n respectiva en el archivo README
  
SOLUCION LAB5 
________________________________________________________________________________________________________________________________

Imagen de como usar la FPGA

![WhatsApp Image 2020-04-23 at 10 14 38 PM](https://user-images.githubusercontent.com/62714712/80264470-df03c900-8659-11ea-8aa1-e4b25b8c0d1c.jpeg)

Se toman los 10 switch, y se dividen en dos;
De ahÃ­ parte todas las operaciones, cuando no le doy operaciÃ³n, el me muestra los nÃºmeros de los switch 


![partiendo](https://user-images.githubusercontent.com/62714712/80264739-b0d2b900-865a-11ea-8f49-cd794126ad26.png)

La unidad aritmÃ©tica, es tal que cuenta con componentes para realizar operaciones aritmÃ©ticas. cada operaciÃ³n aritmÃ©tica es ejecutada acuerdo al cÃ³digo de la operaciÃ³n.

Opcode:Las posibles operaciones arimeticas que se pueden ejecutar en la ALU.


![TABLA](https://user-images.githubusercontent.com/62714712/80263655-ebd2ed80-8656-11ea-9d18-427c406b2630.png)

![principio](https://user-images.githubusercontent.com/62714712/80266493-da431300-8661-11ea-9c98-7519a86c875a.png)

Este codigo lo utilizamos para colocar los numeros que le ingresamos.
Se llama la funcion y en ella se le envia informacion, en este caso la informacion que recibe es:
A= 5bits
B= 5 bits
Como estÃ¡n en base hexadecimal (16), lo que se realiza es una conversiÃ³n 
Ej: 10110 =22
Los primero 4 se toman normal 0110 =6
El 5 bit se multiplica por 16; si el 5 bit es 1 obtendremos 16 sino serÃ¡ 0. En este caso tenemos 0001=16
Despues de ello sumamos y obtenemos
16+6 =22
El mismo ejercicio se realiza con el numero b, pero este al final se multiplica por 100, si tomamos el ejemplo anterior tendriamos 22*100=2200
B=2200

Y lo que realizamos al final es sumar los dos para obtener un solo numero
RTA=a+b ; 
RTA=2200+22 
RTA = 2222
Y este es el proceso de acomodar los bits de entrada en el display

![display](https://user-images.githubusercontent.com/62714712/80266890-f942a480-8663-11ea-8bef-2df349c65351.png)

Este el código que genera toda la segmentación de binario a digital
Como los bloques que tienen internos de operaciones básicas, realizan el proceso como si fuera digital, aunque internamente sea en binario. Realizamos el siguiente proceso

Si tenemos 2356 sabemos que tenemos 2000+300+50+6 y eso es lo que realiza el código, la separación por unidades quitando los ceros respectivamente
Tenemos:
Primera salida=2356/1000 = 2 después de ello realizamos módulo de división  y es
Variable=2356%1000= 356; lo que realiza esta operación es que me da el residuo de la división
Segunda salida=Variable/100= 356/100= 3, para ir dando las salidas a cada display
Variable=variable%100=356%100=56; seguimos descomponiendo nuestro numero
Tercera salida=variable/10= 56/10= 5; obtenemos las decenas para el display;
Cuarta salida=variable%10= 56%10=6 y con esto ya obtenemos nuestra unidad para los display


________________________________________________________________________________________________________________________________

Diagrama Estructural de la SUMA.


![Sumador](https://user-images.githubusercontent.com/62714712/80239337-ac3fdd80-8625-11ea-9c20-ee2d953edb7e.png)



Diagrama De Flujo

![Proceso de soporte tÃƒÂ©cnico](https://user-images.githubusercontent.com/62714712/80242997-f330d180-862b-11ea-860f-2cba9749ed28.png)

Se activan los display automaticamente  y los swich de la parte superiror e inferior son los que me van arrojar un valor a los display dicho valor va ser tomado por el boton B0 y va realizar una suma para realizar la suma implementamos la linea siguiente 


     if (op1==1)
			RTA = BCD1+BCD;
   
Simulacion de la Suma en Labsland

![suma](https://user-images.githubusercontent.com/62714712/80264594-41f56000-865a-11ea-91bc-5d2c65b4f091.png)


RESTA:

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

MULTIPLICACION

Descripci�n de la caja negra 


![multiplicador 1](https://user-images.githubusercontent.com/62735033/80259075-5c274200-864a-11ea-86d6-7213e712b1ae.png)

Descripci�n funcional

![descripcion multiplicador](https://user-images.githubusercontent.com/62735033/80259868-2edb9380-864c-11ea-8324-6246cf336cdd.png)

Simulacion de la multiplicaci�n en Labsland

![imagen 2](https://user-images.githubusercontent.com/62735033/80266526-f9da3b80-8661-11ea-93be-6161af097d6d.png)


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


______________________________________________________________________________________________________________________________


CODIGO FINAL.


    module BCDtoSSeg (V_SW,G_HEX0,G_HEX1,G_HEX2,G_HEX3,V_BT);

    input wire [9:0] V_SW;
    input wire [3:0] V_BT;
    output wire [6:0] G_HEX0;
    output wire [6:0] G_HEX1;
    output wire [6:0] G_HEX2;
    output wire [6:0] G_HEX3;
 
    reg [6:0] SSeg;
    reg [6:0] SSeg1;
    reg [6:0] SSeg2;
    reg [6:0] SSeg3;
    wire [4:0] BCD;
    wire [4:0] BCD1;
    //reg op1;
    //reg op2;
    //reg op3;
    //reg op4;
    reg [3:0] NM1;
    reg [3:0] NM2;
    reg [3:0] NM3;
    reg [3:0] NM4;
    reg [15:0] RTA;
    reg [15:0] RTA1;
    
    
    assign BCD = V_SW[4:0];
    assign BCD1 = V_SW[9:5];
    assign G_HEX0 = SSeg;
    assign G_HEX1 = SSeg1;
    assign G_HEX2 = SSeg2;
    assign G_HEX3 = SSeg3;
    assign op1 = V_BT[0];
    assign op2 = V_BT[1];
    assign op3 = V_BT[2];
    assign op4 = V_BT[3];

    // BCD= b00001111 and V_SW;


    task info;
      input [4:0] a;
      input [4:0] b;
    begin
      RTA = a[3:0];
      RTA = RTA+(16*a[4]);
      RTA1 = b[3:0];
      RTA1 = RTA1+(16*b[4]);
      RTA1 =RTA1*100;
      RTA =RTA1+RTA;
      
    end
    endtask




    always @ ( * ) begin

     if (op1==1)
			RTA = BCD1+BCD;
	else if (op2==1)
	        if(BCD1>BCD)
			RTA = BCD1-BCD;
			else
			RTA= 1000+(BCD-BCD1);
		
	else if (op3==1)
	        if (BCD==0)
			RTA =0;
			else 
			RTA=BCD1/BCD;
			
			
	else if (op4==1)
			RTA = BCD1*BCD;
			
			
		else 
			info(BCD,BCD1);
		//	RTA=RTA<<8;
		//	RTA=RTA | BCD;
		
		
			/*NM4=RTA[15:12];
			NM3=RTA[11:8];
			NM2=RTA[7:4];
			NM1=RTA[3:0];*/
			
	
			
			
			
	    
	    NM4=RTA/1000;
	    RTA=RTA%1000;
        NM3=RTA/100;
        RTA=RTA%100;
        NM2=RTA/10;
        NM1=RTA%10;;
	
    
 

     case (NM1)
      4'b0000: SSeg = 7'b1000000; // "0"  
	 4'b0001: SSeg = 7'b1111001; // "1" 
	4'b0010: SSeg = 7'b0100100; // "2" 
	4'b0011: SSeg = 7'b0110000; // "3" 
	4'b0100: SSeg = 7'b0011001; // "4" 
	4'b0101: SSeg = 7'b0010010; // "5" 
	4'b0110: SSeg = 7'b0000010; // "6" 
	4'b0111: SSeg = 7'b1111000; // "7" 
	4'b1000: SSeg = 7'b0000000; // "8"  
 	4'b1001: SSeg = 7'b0010000; // "9" 
    4'ha: SSeg = 7'b0001000;  
    4'hb: SSeg = 7'b0000011;
    4'hc: SSeg = 7'b1000110;
     4'hd: SSeg = 7'b0100001;
     4'he: SSeg = 7'b0000110;
    4'hf: SSeg = 7'b0001110;
    default:
    SSeg = 0;
    endcase
  
  
  
    case (NM2)
    4'b0000: SSeg1 = 7'b1000000; // "0"  
	4'b0001: SSeg1 = 7'b1111001; // "1" 
	4'b0010: SSeg1 = 7'b0100100; // "2" 
	4'b0011: SSeg1 = 7'b0110000; // "3" 
	4'b0100: SSeg1 = 7'b0011001; // "4" 
	4'b0101: SSeg1 = 7'b0010010; // "5" 
	4'b0110: SSeg1 = 7'b0000010; // "6" 
	4'b0111: SSeg1 = 7'b1111000; // "7" 
	4'b1000: SSeg1 = 7'b0000000; // "8"  
	4'b1001: SSeg1 = 7'b0010000; // "9" 
    4'ha: SSeg1 = 7'b0001000;  
    4'hb: SSeg1 = 7'b0000011;
    4'hc: SSeg1 = 7'b1000110;
    4'hd: SSeg1 = 7'b0100001;
    4'he: SSeg1 = 7'b0000110;
    4'hf: SSeg1 = 7'b0001110;
     default:
    SSeg1 = 0;
    endcase
  
    case (NM3)
    4'b0000: SSeg2 = 7'b1000000; // "0"  
	4'b0001: SSeg2 = 7'b1111001; // "1" 
	4'b0010: SSeg2 = 7'b0100100; // "2" 
	4'b0011: SSeg2 = 7'b0110000; // "3" 
	4'b0100: SSeg2 = 7'b0011001; // "4" 
	4'b0101: SSeg2 = 7'b0010010; // "5" 
	4'b0110: SSeg2 = 7'b0000010; // "6" 
	4'b0111: SSeg2 = 7'b1111000; // "7" 
	4'b1000: SSeg2 = 7'b0000000; // "8"  
	4'b1001: SSeg2 = 7'b0010000; // "9" 
    4'ha: SSeg2 = 7'b0001000;  
    4'hb: SSeg2 = 7'b0000011;
    4'hc: SSeg2 = 7'b1000110;
    4'hd: SSeg2 = 7'b0100001;
    4'he: SSeg2 = 7'b0000110;
    4'hf: SSeg2 = 7'b0001110;
    default:
    SSeg2 = 0;
    endcase
  
    case (NM4)
    4'b0000: SSeg3 = 7'b1000000; // "0"  
	 4'b0001: SSeg3 = 7'b1111001; // "1" 
	4'b0010: SSeg3 = 7'b0100100; // "2" 
	4'b0011: SSeg3 = 7'b0110000; // "3" 
	4'b0100: SSeg3 = 7'b0011001; // "4" 
	4'b0101: SSeg3 = 7'b0010010; // "5" 
	4'b0110: SSeg3 = 7'b0000010; // "6" 
	4'b0111: SSeg3 = 7'b1111000; // "7" 
	4'b1000: SSeg3 = 7'b0000000; // "8"  
	4'b1001: SSeg3 = 7'b0010000; // "9" 
    4'ha: SSeg3 = 7'b0001000;  
    4'hb: SSeg3 = 7'b0000011;
    4'hc: SSeg3 = 7'b1000110;
    4'hd: SSeg3 = 7'b0100001;
    4'he: SSeg3 = 7'b0000110;
    4'hf: SSeg3 = 7'b0001110;
     default:    SSeg3 = 0;
    endcase
  
     end





     endmodule


