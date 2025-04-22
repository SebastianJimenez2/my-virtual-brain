Lenguaje muy usado en el mundo de ==software embebido==, es decir, en la programación de microcontroladores que están en dispositivos de nuestras casas.
# Entorno de desarrollo
Antes se compilaba el código de la siguiente forma
```C++
gcc -o main_es main_es.c
```

>[!Note]
>Un entorno de desarrollo integrado (IDE) permite compilar, ejecutar y depurar un programa utilizando una interfaz gráfica. En este curso usaremos CodeBoard, que es un IDE en línea y que además ya está embebido en nuestro curso, por lo que no tendremos que instalar nada para poder usarlo.
# Anatomía de un programa en C++
## Cabecera
>[!Note]
>El preprocesador es el encargado de realizar la edición, es decir elimina partes innecesarias del programa y también añade instrucciones extras mediante las conocidas con el nombre de directivas del preprocesador.
### Directiva `#include`
Se usa para importar herramientas desarrolladas o predefinidas por otro creador.
```C++
#include -nombre_archivo-

#include "nombre_archivo"
```

>[!Note]
>`stdio.h` es una librería que significa standard input/output en donde se encuentran todas las funciones básicas como `print()`
### Directiva `#define`
Permite ingresar tus propias variables o constantes, para utilizarlas durante todo el desarrollo del programa.
```C++
#define nombre valor
```
Para usar las variables definidas se usa `%tipo_de_dato` dentro del `print()` y al final, seguido de una coma se pone el orden de las variables según su llamado
```C++
#include <stdio.h>
#define PRECIO 2,50

print("Hola, %f", PRECIO);
```
## Función principal
```C++
#include
#define

...

int main() { 

	...
	
	//instrucciones

	...
	
	return 0;	
}
```

>[!Note]
>Es importante que no cambiemos el nombre de la función principal debido a que el programa siempre buscara el nombre main() y en caso de no encontrarlo presentara un error de ejecución.

# Entrañas de un programa en C++
## Tipos de datos
### char[]
- Utilizado para declarar una cadena de caracteres
### int
- Utilizado para declarar un número entero
### float o double
- Utilizado para declarar un número con cifras decimales (DOUBLE permite definir un número de mayor precisión que un FLOAT)
## Variables
Es en donde se almacena un valor o dato que puede ser cambiado, de ahí el nombre: variable.
```C++
tipo_dato nombre = valor;
```
## Operadores aritméticos
| OPERADOR | SIGNIFICADO       | SINTAXIS |
| -------- | ----------------- | -------- |
| +        | Suma              | a + b    |
| -        | Resta             | a - b    |
| *        | Multiplicación    | a * b    |
| /        | División          | a / b    |
| %        | Módulo / Residuo  | a % b    |
| ++       | Suma +1 variable  | a++      |
| --       | Resta -1 variable | a--      |
## Operadores relacionales
| OPERADOR | SIGNIFICADO     | SINTAXIS |
| -------- | --------------- | -------- |
| ==       | Igual a         | a == b   |
| !=       | Distinto a      | a != b   |
| >        | Mayor que       | a > b    |
| <        | Menor que       | a < b    |
| >=       | Mayor igual que | a >= b   |
| <=       | Menor igual que | a <= b   |
## Operadores lógicos
| AND | OR  | NOT |
| --- | --- | --- |
| &   | \|  | !   |
![[Pasted image 20250422110004.png]]
# Diagnóstico de un programa
Para diagnosticar un programa se hace <mark style="background: #BBFABBA6;">depuración</mark>
## Tipos de mensajes de error
- **Errores de sintaxis:** En este caso la compilación se detendrá y el programa no podrá ser ejecutado.
- **Advertencias de código sospechoso:** Estos no detienen la compilación , pero podrían generar errores durante la ejecución del programa.
# Interactuando con el usuario
## Mostrando datos
Se sabe que un dato de salida es todo lo que el usuario puede ver en pantalla. Dentro del lenguaje C los comandos que permiten enviar los datos a pantalla son **puts()** y **printf()** (estos comandos están disponibles dentro de la librería **stdio.h**)
### puts()
La sentencia puts( ) permite solamente imprimir una cadena de caracteres, pero no otro tipo de variables como enteros, flotantes o dobles.
### printf()
Permite imprimir datos en pantalla, con la diferencia que este comando sí permite imprimir valores de otros tipos, como enteros, caracteres, cadenas de caracteres, flotantes, etc.
- `%d` => imprimir enteros.
- `%f` => imprimir flotantes.
- `%c` => imprimir caracteres.
Además, también se puede hacer uso de secuencias de escape
* `\n` => salto de línea
* `\t` => tabulaciones
## Recibiendo datos
Al tocar la pantalla para seleccionar, o al ingresar desde un teclado un dato, se está enviando información conocida como <mark style="background: #FFB8EBA6;">datos de entrada.</mark>
### gets()
La sentencia **gets()** nos permite leer en forma de cadena los datos que el usuario ha ingresado a través del teclado. Solo lee datos <mark style="background: #D2B3FFA6;">EN FORMA DE CADENA, TODO LO TRANSFORMA A TEXTO.</mark>
```C++
char pedido [20]

gets( pedido )
```
### scanf()
La sintaxis de **scanf()** requiere al menos de dos argumentos, es decir, escribiremos la palabra clave **scanf()** acompañada de paréntesis y dentro de los paréntesis colocaremos una cadena de control donde estructuraremos el formato del dato que vamos a leer, y separado con comas colocaremos la dirección de la variable o variables en donde se guardarán los datos que vamos a leer.
```C++
scanf( "cadena de control", direccion variables);
```
# Personalización y definición de datos
## Modificadores de formato
Los modificadores de formato de lenguaje C son utilizados para dar un formato a los datos de salida en una impresión, es decir, nos permiten personalizar la forma en como un dato de salida se mostrará en pantalla controlando aspectos como: 
* ancho que se usará para la impresión
* justificación del dato dentro del ancho disponible y, 
* precisión de los datos en caso de tener cifras decimales.
## Especificadores de formato
Un especificador de formato no es más que la forma de decirle al compilador, qué tipo de dato hay en una variable, ya sea de entrada o salida.
## Sintaxis
```C++
% [marcas][ancho][.precisión] tipo
```
Donde:
- El símbolo porcentaje y el campo tipo representan un <mark style="background: #ADCCFFA6;">especificador de formato.</mark>
- Los campos: marca, ancho y precisión representan los <mark style="background: #D2B3FFA6;">modificadores de formato.</mark>
>[!Important]
>En el campo <mark style="background: #FFB8EBA6;">marcas</mark> podemos colocar el símbolo menos [ - ] si queremos que el dato se justifique a la izquierda , cero [ 0 ] para que todos los espacios libres del ancho asignado se llenen con ceros , caso contrario si no se coloca nada , el dato por defecto se justificará a la derecha.
>El campo <mark style="background: #FFB8EBA6;">ancho</mark> nos permitirá definir el número de espacios que se usará para imprimir el dato, colocando un número entero.
>El campo <mark style="background: #FFB8EBA6;">precisión</mark> nos permitirá definir el número de decimales que se imprimirán de un número , aquí colocaremos un punto y un número entero que indicará el número de decimales.
# Condicionales
## if-else
Esta instrucción evalúa la expresión lógica dentro del IF; en caso de ser verdadera se ejecutara la acción declarada dentro del IF, en caso de que la expresión sea falsa se ejecutará el "caso contrario" ELSE siempre y cuando esté declarado, en caso de que el ELSE no esté declarado el programa no hará nada.
```C++
if ( expresión_lógica ){

//Instrucciones si es verdadera

}

else {

//Instrucciones si es falsa

}
```
### Anidamiento
Ahora luego del `ELSE` (o para ser estrictos dentro del `ELSE`) se añade un nuevo bloque `IF`. Dentro del segundo `IF`, evidentemente, irá una expresión lógica o condición diferente a la primera y finalmente, el segundo bloque `ELSE` que se ejecutará en caso de que no se cumpla ninguna de las dos condiciones anteriores.
```C++
if ( expresión_lógica ){

//Acción;

}

else if ( expresión ){

//Acción;

}

else {

//Acción;

}
```
Otra forma de hacerlo es:
```C++
if ( expresión_lógica ){

//Acción;

  if ( expresión ){

  //Acción;

  }

}

else {

//Acción;

}
```
>[!Note]
>Observar que una vez definido un condicional simple, se puede colocar un nuevo bloque `IF`, dentro del `IF`, por su puesto con su respectiva expresión lógica. Aunque en este ejemplo, solo se ha incluido un `IF`, también podría ir su respectivo `ELSE`.
## switch
La sentencia `if-else` presenta un problema y es que a medida que requiramos ir realizando la selección de múltiples opciones requeriríamos de mas sentencias `if-else` para cada una haciendo que nuestro código sea mas difícil de leer. Su sintaxis se observa de la siguiente forma:
```C++
switch (opcion){
	case etiqueta:
		//sentencia
		break;
	
	case etiqueta2:
		//sentencia
		break;
		
	default;
}
```
Como podemos observar la estructura se divide en 3 partes: variable de control, los casos, y un método por defecto.
Hay que mencionar que los casos tendrán una serie de instrucciones o sentencias las cuales se verán delimitadas por un símbolo de dos puntos y al final por la palabra "break;", encaso de que el caso y la variable de control tengan el mismo valor el código que este limita será ejecutado.
# Bucles
## for
Cumple el mismo objetivo de repetir una acción al igual que los otros bucles, sin embargo, su diferencia principal radica en que previamente a su uso conoceremos la cantidad de veces que el bucle va a repetirse.
```C++
for ( Inicialización ; Condición de Iteración ; Incremento ) {

  //Bloque de Iteración a repetir si se cumple la condición

}
```
En donde:
- **Inicialización:** en esta sección es donde se inicializa una variable con un valor, esta debe ser de carácter entero (int), y usualmente suele iniciar en 0.
- **Condición de Iteración:** en esta sección empleamos la variable inicializada con otra variable en una expresión lógica la cual dependiendo si es verdadera o falsa nos permitirá continuar con el bucle.
- **Incremento:** en esta sección es donde nuestra variable inicializada ira cambiando de valor después de cada bucle, esto usando operadores aritméticos.

>[!Important]
>Para romper un bucle o la ejecución del código abruptamente, se debe usar la palabra reservada <mark style="background: #FF5582A6;">break.</mark>
## Anidamiento for
```C++
for ( Inicialización ; Condición de Iteración ; Incremento )

{

  //Instrucciones lazo externo

  for ( Inicialización ; Condición de Iteración ; Incremento )

  {

    //Instrucciones lazo externo

  }

  //Instrucciones lazo externo

}
```
# Bucles infinitos
Se elimina la condición que limita el número de repeticiones. Y ahora que el lazo no sabe cuándo detenerse, simplemente se repite indefinidamente.
```C++
for (  ;  ;  ) {

  //Sentencias a repetir indefinidamente

}
```
**Ejemplo práctico:**
```C++
for(  ;  ;  ) {

  printf("Menú McDonalds, elija su hamburguesa\n");

  printf("1. Hamburguesa con queso\n");

  printf("2. Hamburguesa con tocino\n");

  printf("3. Hamburguesa doble\n");

  printf("4. Salir\n");

  printf("Opción: \n");

  int boton;

  scanf("%d", &boton)

  if(boton == 4) break;

}
```
>[!Important]
>Es mejor usar la condicional switch antes que un for infinito.

