# Robot_epson
Integrantes

Juan Pablo Ortiz Mendoza, Theylor Amaya

# Software Epson RC+ 7.0
 Se instala el software de la compaia epson para realizar la capacitancion con simulacion de los robot Scara, en este caso el T6

 Al crear el proyecto queda el siguiente resultado
 ![mov1](https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/2c7415df-f3c4-42f4-8549-87e7cb1cc289)

 Este es el resultado de la interfaz.

 Se procede a programar los tres puntos iniciales llamados Origen, Eje y y Ejex como se muestra acontinuación

 ![puntos](https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/c23736ca-a1a7-49f5-b936-a0a0a771f948)

 Con estos puntos se realiza el primer movimient0o con el siguiente codigo como se practicó en la capacitación
´´´
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
´´´

 

