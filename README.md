# Robot_epson
Integrantes

Juan Pablo Ortiz Mendoza, Theylor Amaya

# Software Epson RC+ 7.0
 Se instala el software de la compaia epson para realizar la capacitancion con simulacion de los robot Scara, en este caso el T6

 Al crear el proyecto queda el siguiente resultado
 ![mov1](https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/2c7415df-f3c4-42f4-8549-87e7cb1cc289)

 Este es el resultado de la interfaz.
## Movimiento 1
Inicialmente se establece la posicion home con las siguientes coordenadas

![grafik](https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/00adab86-1106-47c1-9bd1-d7768308fcb6)

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

## Movimiento 3

Ahora se da paso al movimiento 3 donde debera moverse por las cuadricula siguiendo un movimiento continuo, si moverse en diagonales, para esto se creo un bucle for con condicionales if que crea este tipo de movimiento, como se muestra acontinuación. Es importante aclarar que para el movimiento 2 y 3 se utilizo una velocidad de 100%

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
		If i < 4 Then
			Jump Pallet(1, i)
		ElseIf i < 7 Then
			Jump Pallet(1, i)
		Else
			Jump Pallet(1, 16 - i)
		EndIf
	Next
Home
Fend
```

Con este codigo se obtiene el siguiente movimiento

https://github.com/JuanPabloOrt/Robot_epson/assets/144562439/0e6141a7-b11b-41f7-b7d9-afab29cd8ed6

## Conclusiones

Con el robot Scara T6 es posible realizar movimientos en cuadriculas respecto a puntos definidos previamente  con todos los parametros conocidos de la robotica como aceleracion, velocidad estandar, y permite que se creen codigos segun el cambio de los movimientos que se deseen.




