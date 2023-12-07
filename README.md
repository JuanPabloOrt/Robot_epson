# Robot_epson
Integrantes

Juan Pablo Ortiz Mendoza, Theylor Amaya

# Software Epson RC+ 7.0
 Se instala el software de la compaia epson para realizar la capacitancion con simulacion de los robot Scara, en este caso el T6

 Al crear el proyecto queda el siguiente resultado
 ![mov1](https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/2c7415df-f3c4-42f4-8549-87e7cb1cc289)

 Este es el resultado de la interfaz.
## Movimiento 1
 Se procede a programar los tres puntos iniciales llamados Origen, Eje y y Ejex como se muestra acontinuación

 ![puntos](https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/c23736ca-a1a7-49f5-b936-a0a0a771f948)

 Con estos puntos se realiza el primer movimient0o con el siguiente codigo como se practicó en la capacitación
```
Function main
Motor On
Power Low

Accel 50, 50
Speed 50
Home
Do
	Call Movimiento1

Loop
	

Fend
Function Movimiento1
	Go Origen
	Go Ejex
	Go Ejey
	
Fend
```
Este codigo basicamente, inicxa el moto y da potencia baja al robot, luegoi acelera y desacelera al 50 % respectivamente, y va a una velocidad maxima del 50%. Se ubica en el home que tambien fue programado previamente, y se creó la función que invita a realizar el movimiento curvilineo entre los puntos Orige, Ejex y Ejey. Todo estro dentro de un ciclo infinito como se especifica es requerido.

dando como resultado el siguiente moviemiento


https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/1b35d9da-a108-4e91-a713-a974b5575888

## Movimiento 2
Para el movimiento se procede a crear un apllet, que basicamente es una rejilla, dandole 3 puntos, el stos son las esquinas, y la separacion basica entre cuadrilla, luego se le especifica la cantidad de espacions, con un recuadro 3x3, que el compilador interpreta creando la cuadricula equidistante.
 esto se logra con el siguiente codigo
```
Function main
Motor On
Power High
Integer i
Accel 50, 50
Speed 100
Home
Pallet 1, Origen, Ejey, Ejex, 3, 3
For i = 1 To 9
	Jump Pallet(1, i)
Next
Home
Fend
```
Al ejecutar este codigo, se opbtiene el movimiento 2 que se muestra acontinuación




https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/65e5147d-b2df-448e-9a85-e4e8caf4ba89

