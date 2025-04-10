### ¿Qué es una estructura?
El medio de almacenamiento en el cual va a ingresarse valores de diferentes datos

### ¿Qué son datos?
Son los pensamientos o letras de una recopilación de información, puede ser cualitativa o cuantitativa..
Un dato al combinarse con otro produce información

### ¿Qué es una estructura de datos?
Es simplemente una colección de datos que se caracteriza por su organización y operaciones que se pueden realizar sobre ellas.

Las estructuras de datos nos permiten hacer
	- Manipulación de los datos
	- Almacenamiento de datos
	- Ordenar los datos

### Operaciones básicas
Adicionar datos
Recorrer datos
Buscar datos
Eliminar datos

### Importancia
Al organizar los datos en una estructura la eficiencia con la que se maneja es mas eficaz al momento de su ejecución:
	- Eficiencia
	- Estructura, son estructuralmente ricas para procesamiento de datos
	- Simples en su estructura de datos

### Clasificación de las Estructuras de Datos
**Primitivas.-** Palabras reservadas de un lenguaje de programación
Un tipo primitivo está predefinido por el lenguaje y se nombre con una palabra clave reservada.
	- char
	- double
	- int
	- float
	- Boolean
**No primitivas.-** Son aquellas que son compuestas en su estructura.
	- *Lineales*, se caracterizan por poseer el principio adyacente, es decir, están almacenadas contiguamente entre ellas
		- Pilas
		- Listas
		- Colas
		- Arreglos
	- *No lineales*, se caracterizan por no poseer el principio adyacente, es decir están almacenadas contiguamente entre ellas
		- Árboles
		- Grafos
		
**Estáticas.-** Tiene un numero fijo de elementos que queda determinado en la declaración al comienzo del programa.
	- Arreglos
	- Matrices
	
### ¿Que se entiende por algoritmo?
Es un método o un proceso, un conjunto de instrucciones utilizadas para resolver un problema específico.

> Desde un punto de vista más formal y riguroso: Es un conjunto ordenado de pasos o instrucciones ejecutables

Para esto se usa un [[Pseudocódigo]]
El diseño de un algortimo para ser implementado debe ser fácil de entender, codificar y depurar

### Diagrama de flujo
No es lo mismo un diagrama de flujo a un algoritmo.

Un diagrama de flujo, es una representacion grafica de un proceso. Cada paso del proceso se representa por un símbolo diferente que contiene una breve descripción de la etapa de proceso.

### Propiedades de los algoritmos
1. Un algoritmo tiene un inicio
2. Existe una especificación precisa de la entrada
3. Especificación precisa de cada instrucción
4. Etapas bien definidas y concretas
5. Numero finito de pasos
6. Un algoritmo debe terminar

### Programa
Un programa de computadora es una representación concreta de un algoritmo en un lenguaje de programación
	- Que sea facil de entender, codificar y depurar
	- Que consiga la mayor eficiencia para los recursos de la computador.

## Tipos abstractos de datos ([[TAD]])
Es un tipo de dato definido por el programador se denomina tipo abstracto de datos ([[TAD]]) para diferenciarlo del tipo fundamental (predefinido) de datos.

En esencia, un tipo abstracto es un tipo de dato que consta de datos (estructuras de datos propias) y operaciones que se pueden realizar sobre ellos.

***Ventajas***
	1. Mejoran la conceptualizacion y hacen más caro y comprensible el código
	2. Hacen que el sistema sea más robusto
	3. Reducen el tiempo de compilación
	4. Permiten modificar la implementación sin que afecte al interfaz público
	5. Facilitan la extensibilidad
	6. Recogen mejor la semántica del tipo

### [[Clase]] y [[Objeto]]
Son los elementos clave sobre los que se articula la POO.

### Visibilidad de los Miembros de una [[Clase]]
Un principio fundamental en programación orientada a objetos es la ocultación de la información que significa que a determinados datos no se puede acceder a diferencia de los públicos.

```
class Nombre_Class {
	private (se accede dentro de la misma clase)
	protected (se accede de otras clases como de las interna)
	public (se accede por cualquier lado)
}
```

### Constructor
Un constructor es un método que se ejecuta automáticamente cuando se crea un objeto de una clase. Sirve para inicializar los miembros de la clase.

> ***El constructor tiene el mismo nombre que la clase y tiene parámetros***

Argumento son los datos que envías.

### Contructor por defecto
Es un constructor que no tiene parámetros. Normalmente inicializa los miembros dato de la clase con valores por defecto.

### Constructor sobrecargado
Son bastante frecuentes y proporcionan diferentes alternativas para inicializar objetos

### Estructura de una clase
1. Paquete
2. Imports
3. Declaración de la clase
4. Variables
5. Constructores
6. Métodos

## Arreglos
Arreglo es una secuencia de datos con un número fijo de componentes, todos del mismo tipo.

### **Arreglo unidimensional:** 
Un arreglo unidimensional es finito, homogéneo y ordenado. Una sola dimensión. Cada componente del arreglo se puede acceder mediante un índice. La dimensión se maneja por un par de corchetes "[]"

#### **¿Para que sirven los arreglos?**
Nos sirven para manejar de fomra sencilla y directa conjuntos de datos del mimso tipo.

#### **¿Cómo se puede ver a un arreglo?**
Un arreglo se puede ver como un conjunto de espacios finitos donde se almacenan elementos todos del mismo tipo

Las partes en los arreglos:
* ***Componentes***, valores que se almacenan en cada casilla
* ***Índices***, Cuántos elementos tendrá el arreglo

Un arreglo unidimensional se define según **Cairo** de la siguiente manera:
```
ident_arreglo = ARREGLO [líminf...límsup] DE TIPO
```
* *líminf...límsup*, es el tipo de los índices así como el número de elementos.
* *Tipo*, es el tipo de dato para todos los componentes del arreglo.

Número total de componentes = lim sup - lim inf + 1

#### Declaración de Arreglos
La declaración de un arreglo se lo realiza de forma similar a otros tipos de datos, especificando que es un arreglo, utilizando corchete.
```
TipoDeDato Arreglo[]
```

#### Creación de un Arreglo
La creación de un arreglo se hace de la siguiente forma utilizando el operado new:
```
Tipo nombre_del_arreglo[] = new Tipo[número de elementos]
```

#### Declaración e inicialización
Para declarar e inicializar un arreglo unidimensional se tiene la siguiente sintaxis:
```
TipoDeDato nombre[] = {val1, val2, ..., valn}
```

#### Operaciones con Arreglos Unidimensionales
Podemos clasificar a las operaciones en las que intervienen arreglos de la siguiente manera:
* [[Lectura]] / [[Escritura]]
* [[Asignación]]
* [[Actualización]]: [[Inserción]], [[Elimincación]], modificación
* Ordenación
* Busqueda

### Arreglos Bidimensionales
* Se los conoce tamién como matrices
* Es un conjunto de datos de un mismo tipo que están almacenados en arreglos de dos dimiensiones
* Tiene una cantidad de filas y columnas
* Al igual que los arreglos unidimensionales los índices comienzas a partir de 0 o 1 y se indican entre corchetes
* *Representación gráfica:*
![[Representación Gráfica.png]]

#### Características
* Almacena elementos del mismo tipo.
* Tamaño fijo (mxn).
* Cada espacio se referencia con índices.
* El primer índice refiere a las filas.
* El segundo índice refiera a las columnas.
* Es un arreglo bidimensional de mxn sus índices irán de 0 a m-1 para las filas y de 0 a n-1 para las columnas.

#### Declaración 
Se declara con la siguiente sintaxis:
```
id_arreglo = ARREGLO[liminf..limsup][liminf...limsup] de TIPO
```

NTC = (limsup - liminf + 1) x (limsup - liminf + 1)

#### Creación de arreglo bidimensional
```
tipoDeDato nombre[][] = new tipoDeDato[m][n]
```
* m es la cantidad de fila
* n es la cantidad de columnas

```
String nombres[][] = new String[3][2]
```

#### Lectura
```
Repetir i desde 1 hasta 10
	Repetir con j desde 1 hasta 5
		Leer Matriz[][]
	fin
fin

Para  i = 1 y j = 1 --> 1, 1
	  i = 1 y j = 2 --> 1, 2
```

#### Escritura
```
Repetir i desde 1 hasta 10
	Repetir con j desde 1 hasta 5
		Escribir Matriz[][]
	fin
fin

Para i = 1 y j = 1 --> 1, 1
	 i = 1 y j = 2 --> 1, 2
```

#### Asignación
```
Depende del número de componentes involucrados

Repetir i desde 1 hasta 10
	Repetir j desde 1 hasta 5
		Matriz <-- 0
	fin
fin

Para i = 1 y j = 1 --> M[1][1] = 0
	 i = 1 y j = 2 --> M[1][2] = 0
```

### Ejemplo
![[Código Bidimensional.png]]

### Arreglos multidimensionales
Los arreglos multidimensionales tienen N dimensiones, las dimensiones se manejan por medio de corchetes, dentro de los que se escriben los valores de cada dimensión.

Como una coleccion de n componentes por ejemplo:
k1 * k2 * k3... * kn elementos

En donde para hacer referencia a cada componente se utilizará para n índices uno para cada dimensión

Definición segun ***CAIRO*** de un arreglo multidimensional:
```
A = ARREGLO[LI1...LS1, LI2...LS2, LI3...LS3, LIn...LSn] de TIPO
```

***¿Conociendo la definicion de un arreglo multidimensional como se realiza el calculo del NTC?***
- NTC = (LS1 - LI1 + 1) x (LS2 - LI2 + 1) x ... x (LSn - LIn + 1)

#### Operación de Inserción
Escribir un algoritmo que nos permita ingresar e imprimir los valores en un arreglo tridimensional A de 2, 4, 2
```
1. A = ARREGLO[1...2, 1...4, 1...2] de TIPO
2. Repetir i desde 1 hasta 2
	Repetir j desde 1 hasta 4
		Repetir k desde 1 hasta 2
			Escribir A[i, j, k]
		fin
	fin
   fin
3. Repetir i desde 1 hasta 2
	Repetir j desde 1 hasta 4
		Repetir k desde 1 hasta 2
			Leer A[i, j, k]
		fin
	fin
   fin
```

#### Ejemplos donde se aplican Arreglos Multidimensionales
Una florícola lleva un registro del total producido mensualmente por tipo de flores; La florícola conta de 6 tipos de flores y la información se ha registrado a lo largo de los últimos 4 años
```
FLORICOLA = ARREGLO[1...6][1...12][1...4] de TIPO REAL
NTC = (6 - 1 + 1) x (12 - 1 + 1) x (4 - 1 + 1)
NTC = 288
```

**a)** El total mensual de cada tipo de flor duranre el primer año.
```
1. Inicio
2. F = A[1...6, 1...12, 1...4]
3. Repetir con i de 1 hasta 6
	   Repetir con j de 1 hasta 12
			Escribir A[i, j, 1]
		fin
	fin
	
```

**b)** El total de produccion durante el segundo año
```
1. Inicio
2. F = A[1...6, 1...12, 1...4]
3. Repetir con i de 1 hasta 6
	   Repetir con j de 1 hasta 12
			Hacer S <-- S + A[i, j, 2]
		fin
	fin
4. Imprimir S	
```

**c)** El total de la producción del tercer tipo de flor a lo largo del último año
```
1. Inicio
2. F = A[1...6, 1...12, 1...4]
3. Repetir con j de 1 hasta 12
	   Hacer S <-- S + F[3, j, 4]
   fin
5. Imprimir S	
```

#### Código
![[Código Multidimensional.png]]

### [[EDA]] Tipo Pila
Una pila representa un estructura lineal de datos en que se puede agregar o quitar elementos únicamente por uno de los dos extremos

En consecuencia, los elementos de una pila se eliminan en el orden inverso al que se insertaron. Se manejan con la lógica LIFO.

Se define formalmente como una colección ordenada de elementos a los cuales solo se puede acceder por un único lugar o extremo de la pila.
Este extremo se conoce generalmente como tope o cima.

##### ¿Qué aplicaciones utilizan los Pilas?
* **Editores de texto**, en el botón de deshacer cuando se cancela las operaciones de edición recientes y restablece el estado anterior del documento. La secuencia de operaciones recientes se mantiene en una pila.
* Los **navegadores** permiten habitualmente volver hacia atrás en la secuencia de páginas visitadas. Las direcciones de los sitios visitados se almacenan en una pila.

##### ¿Cómo se representan las pilas?
**No son estructuras fundamentales de datos**; es decir, no están definidas como tales en los lenguajes de programación.

Para su representación requieren de otras EDs, como:
* Arreglos
* Listas

Al utilizar un array para contener los elementos de la pila hay que tener en cuenta que **el tamaño de la pila no puede exceder el número de elementos del array,** y la condición pila llena será significativa para el diseño.

Se debe definir un **tamaño máximo** de la pila, así como una variable auxiliar a la que se denomina **TOPE**.

### Tipos de Pila
|Tipo|Descripción|
|---|---|
|**Pila llena.**|  Tope = Máximo|
|**Pila semillena.**| Tope < Máximo|
|**Pila vacía**.| Tope == 0|

**Representación Gráfica:**
![[Pilas.png]]

##### ¿Qué consideraciones se tiene si se trabaja con arreglos?
* Al utilizar arreglos para implementar pilas se tiene la limitación de que se debe reservar espacio de memoria con anticipación, característica propia de arreglos
* Una vez dado un máximo de capacidad a la pila no es posible insertar un número de elementos mayor al máximo establecido
* Si la pila estuviera llena y se inserta un nuevo elemento, se producirá un erro conocido como desbordamiento -overflow-

##### Posibles soluciones
* Consiste en definir pilas de gran tamaño, pero esto resulta ineficiencia y costoso si solo se utilizarán algunos elementos. No siempre es viable saber con exactitud el número de elementos a tratar, y siempre existe la posibilidad de que ocurra un error de desbordamiento.
* Consiste en usar espacios compartidos de memoria para la implementación de pilas.

#### Operaciones
Para el caso de las pilas, las operaciones básicas que se pueden llevar a cabo son:
* Insertar (push)
* Eliminar (pop)
y las operaciones auxiliares
* Pila vacía
* Pila llena 

```
Pila vacia (pila, tope, B)
{Tope <-- entero, B <-- boolean}

1. Si (tope = 0) entones {
	   Hacer B <-- V
   } Sino {
	   Hacer B <-- F
   }
```

```
Pila llena (pila, tope, max, B)
{Tope <-- entero, B <-- boolean}

1. Si (tope = max) entones {
	   Hacer B <-- V
   } Sino {
	   Hacer B <-- F
   }
```

```
Insertar Pila (pila, tope, max, DATO)
{Tope <-- entero, DATO <-- entero}

1. Llamar Pila-Llena con PILA, TOPE, MAX, B
2. Si (B = V) entonces {
	   Escribir "Desbordamiento de pila llena"
   } sino {
	   Hacer TOPE <-- TOPE + 1
	   Pila[TOPE] <-- DATO
   }
```

```
Quitar Pila (pila, tope, DATO)
{Tope <-- entero, DATO <-- entero}

1. Llamar Pila-vacía con PILA, TOPE, B
2. Si (B = V) entonces {
	   Escribir "Subdesbordamiento"
   } sino {
	   DATO <-- PILA[TOPE]
	   TOPE <-- TOPE - 1
   }
```

#### Aplicaciones de Pilas
* Llamadas a subprogramas
* Recursividad
* Tratamiento de operaciones aritméticas

![[Programas.png]]

#### Prioridad de operadores
|Operadores|Proprodad Dentro Pila|Prioridad Fuera Pila|
|---|---|---|
|^|3|4|
|x, /|2|2|
|+,-|1|1|
|(|0|5|
### Algoritmo de pasos de notación infija a postfija (completo)
![[Infijo a postfijo.png]]

##### Ejemplo
![[Ejercicio infijo a postfijo.png]]

### Algoritmo de pasos de notación infija a postfija (reducido)
![[Infijo a postfijo corto.png]]


### EDA Tipo Cola
Constituye una estructura lineal de datos en la que los nuevos elementos se introducen por un extremo y los ya existentes se eliminan por otro

> Debido a la característica que tienen las colas reciben el nombre de estructuras FIFO

##### Definición en Programación
Las colas, no existen como estructura de datos estándar en los lenguajes de programación. Se representan median el uso de:
* Arreglos
* Listas
Es importante definir un tamaño máximo para la cola y dos variables auxiliares.

##### Operaciones 
Las operaciones básicas que pueden efectuarse son:
* Insertar un elemento en la cola
* Eliminar un elemento de la cola

##### Algoritmos para las operaciones básicas
**Cola Vacía**
```
Cola vacía (COLA, Frente (f), Final (F), B <variable para determinar si la estructura está llena o vacía>)
1.  Si (P = 0 y F = 0) entonces
		B <-- V
    sino
		B <-- F
    Fin Si
```

**Cola llena**
```
Cola llena (COLA, F, B, MAX)
1.  Si (F = MAX) entonces
		B <-- V
    sino
		B <-- F
    Fin Si
```

**Insertar**
```
Insertar (COLA, Frente (f), Final (F), DATO, MAX)
1.  Si (F < MAX) entonces
		Hacer F <-- F + 1 y COLA[F] <-- DATO
	    Si (F = 1)
			Hacer f <-- 1
	    Fin Si
	sino 
		Escribir "Desbordamiento"
	Fin si
```

**Eliminación**
```
Cola vacía (COLA, Frente (f), Final (F), DATO)
1.  Si (f != 0) entonces
		Hacer DATO <-- COLA[f]
	    Si (f = F) entonces
		    F <-- 0 y F <-- 0
		Sino
			f <-- f + 1
		Fin Si
	sino
		Escribir "subdesbordamiento"
    Fin Si
```

### Tipos de cola
#### Colas circulares
Constituye una estructura de datos lineal en el cual el siguiente elementos del último en realidad es el primero. De esta forma se utiliza de manera más eficiente la memoria de la computadora. Si se quiere insertar datos, se da la vuelta. El frente siempre permite eliminar.

##### Insertar
```
Intertar ColaCircular (Cola, MAX, f, Fin, D)
MAX <-- int
f, F <-- posición CC; D <-- elemento afín

1.  Si (f = 1 && F = MAX || F + 1 = f)
		Escribir "desbordamiento"
    SiNo
		Si (f = 0)
			F <-- 0
			f <-- 0
			Cola[F] <-- D
		SiNo
			Si(MAX = F + 1)
				F <-- 1
				Cola[F] <-- D
			SiNo
				F <-- F + 1
				Cola[F] <-- D
			FinSi
		FinSi
	FinSi
```

##### Eliminar
```
Eliminar ColaCircular (Cola, MAX, f, Fin, D)
MAX <-- int
f, F <-- posición CC; D <-- elemento afín

1.  Si (f = 0)
		Escribir "subdesbordamiento"
    SiNo
		Si (f = F)
			D <-- Cola[f]
			f <-- 0
			F <-- 0
		SiNo
			Si(MAX = f)
				D <-- Cola[f]
				f <-- 1
			SiNo
				D <-- Cola[f]
				f <-- f + 1
			FinSi
		FinSi
	FinSi
```

##### Ejemplo de inserción / eliminación
Sea A una cola circular de 8 elementos. Inicialmente la cola está vacía (INIVIO=FIN=0). Especifique el estado de la estructura de datos luego de realizar cada una de las siguientes operaciones:
* Insertar los elemento A,B,C,D,E,F,G,H
* Eliminar A
* Eliminar B
* Insertar I
* *¿Con cuántos elementos quedó el ARREGLO?*
	* 7 elementos
* *¿Hubo algún caso de error?*
	* NO

#### Doble Cola
Una bicola es un conjunto ordenado de elementos, al que se puede añadir o quitar elementos desde cualquier extremo del mismo. El acceso a la bicola está permitido desde cualquier extremo. Se puede afirmar que una bicola es una cola bidireccional

##### Variantes de la bicola
Existen dos variantes:
* **Doble cola con entrada restringida**. La inserción se hace solo por el final
* **Doble cola con entrada restringida.** La inserción se hace por ambos lados
![[Pasted image 20220607080735.png]]

##### Eliminar bicola entrada restringida
```
Eliminar Bicola (Bicola, MAX, f, Fin, D)
MAX <-- int
f, F <-- posición CC; D <-- elemento afín

1.  Si (f = 0 && F = 0)
		Escribir "subdesbordamiento"
    SiNo
		Si (F = MAX)
			D <-- Bicola[F]
			F <-- F - 1
		SiNo
			Si(f >= 1)
				D <-- Bicola[f]
			SiNo
				Si (f = F)
					f <-- 0; F <-- 0
				SiNo
					Hacer f <-- f + 1
				FinSi
			FinSi
		FinSi
	FinSi
```
#### Basada en prioridad
Constituye una estructura de datos en donde los elementos son ordenados siguiendo un criterio. El orden de los elementos de la cola de prioridad de Java depende de la prioridad de los elementos. El elemento con mayor prioridad se moverá al principio de la cola.
```
1.  Si `fin = MAX`
		escribir **"Desbordamiento, la cola está llena"** y salir.
	FinSi

	Si `fin = 0`, 
		insertar `Elemento` en `Cola[1]` y actualizar `fin`.
	SiNo:
		Buscar la **posición correcta** para insertar `Elemento` manteniendo el orden.
		Mover los elementos hacia la derecha para hacer espacio.
		Insertar `Elemento` en su posición correcta.
	FinSi
	Incrementar 
Fin`.
``` 



# PASA LO DE LAS DIAPOSITIVAS DE RECURSIVIDAD AQUÍ, PORFA

La recursividad es un tópico muy importante que es examinado frecuentemente en cursos que estudian la resolución de algoritmos y estructuras de datos

En matemáticas existen numerosas funciones que tienen carácter recursivo, de igual modo en la vida ordinaria.

La recursividad de manera general es un concepto muy amplio con muchas variantes y difícil de precisar con pocas palabras, LA recursividad aparece en numerosas actividades de la vida diaria.

```java
metodo 1 (...){
	...
}

Indirecta:
metodo 2 (...){
	...
	metodo1(); //llamada al metodo1
	...
}

Directa:
metodo 1 (...){
	...
	metodo1(...); //se llama asimismo
	...
}
```

#### Importancia
En toda actividad recursiva de un problema siempre se deben establecer dos pasos diferentes y muy importantes
- El paso básico
- El paso recursivo 

#### Consideraciones
* Una función no recursiva a pesar de parece más sencilla y más frecuente no puede dar solución a todos los problemas planteados
- Una función recursiva en cambio da in programa más sencillo y más elegante. Además hay muchos problemas cuas respuestas se plantean de forma recursiva.

Recursividad
``` java
Factorial Número
	 -> 1            si n = 0 o n = 1; 
n! -|  
	 -> n*(n-1)!     si (n > 1)

1.  Si (n=0 o n=1){
		Hacer Factorial <-- 1
	SiNo
		Hacer Factorial <-- n * factorial(n-1)
	FinSi

2.  Hacer x <-- 1
	Mientras (n > 0) repetir
		Hacer x <-- n * x && n <-- n - 1
	FinMientras
3.	Imprimir x
```

```java
Fibonacci
	   -> F(0) = 0; F(1) = 1 
F(n) -|  
	   -> F(n) =  F(n - 1) + F(n - 2)     si (n > 1)

1.  Si (n = 0 o n =1 ){
		Hacer F(n) <-- n
	SiNo
		Hacer F(n) <-- F(n-1) * F(n-2)
	FinSi
****
2.  Si (n = 0 || n = 1)
		Hacer x <-- n
	SiNo
		Hacer y <-- 0, z <-- 1 e i <--2
	FinSi
3.  Mientras (i <-- n) repetir
		Hacer x <-- z + y; y <-- z; z <-- x; i <-- i + 1
    FinMientras
4.	Imprimir x
```

```java
Potencia(a, b)
	      -> n 
P(a, b) -|  
	      -> a * P(a, b-1)

1.  Si (b = 1)
		Hacer Potencia <-- a
	SiNo
		Hacer Potencia <-- a * Potencia(a, b - 1)
	FinSi
```

F
eS UN TIÓ DE ESTRUCTURA LINEAL Y DINAMICA DE DATOS
* lINEAL, PORQUE A CADA ELEMENTO SLE PUEDE SEGUIR SOLO OTRO ELEMENTO
* dINAMICA, PORQUE SE PUEDE MANEJAR LA MEMORIA DE MANERA FELXIBLE, SIN NECESIDAD DE RESERVAR ESPACIO CON ANTELACION

P s apuntador del nodo D

#### Listas simplemente ligadas
Una lista simplemente ligada constituye una coleccion de elementos llamdos generalmente nodos
Un tipo especial de lista simplemente ligada es la lista vacía

La referencia null se utiliza, normalmente, en dos situaciones:
* a
* *

¿Qué operaciones se trabaja con una lista simplemente ligada?
* Recorrido 
```Java
1. Q <-- P
2. Mientras (Q != null)
	1. Imprimir Q^.INFO
	2. Hacer Q <-- Q^.LIGA
3. Fin Mientras
```
* Inserción
```Java
InsertarInicio (P, D)
Q tipo puntero
INFOR, LIGA
1. Crear (Q)
2. Hacer Q^.INFOR <-- D, Q^.LIGA <--P
	1. P <--Q
```
* Borrado
* Búsqueda

```Java
Crear InicioLista
	P, Q tipo puntero
	INFO, LIGA tipo apuntador
	1. Crear(P)
		1. Leer P^.INFO
		2. Hacer P^.LIGA <-- null
		3. Leer OPCION
	2. Mientras (OPCION=1)
		1. Crear(Q)
		2. Leer Q^.INFO
		3. Hacer Q^.LIGA <-- P && P <-- Q
		4. Escribir "Desea continuar? s/n"
		5. Leer OPCION
	3. Fin mientras
Fin InicioLista
```

```Java
Crear FinalLista
	P, Q, T tipo puntero
	INFO, LIGA tipo apuntador
	1. Crear(P)
		1. Leer P^.INFO
		2. Hacer P^.LIGA <-- null && T <-- P
		3. Escribir "Desea ingresar mas nodos? s/n"
		4. Leer OPCION
	2. Mientras (OPCION=1)
		1. Crear(Q)
		2. Leer Q^.INFO
		3. Hacer Q^.LIGA <-- null && T^.LIGA <-- Q && T <-- Q
		4. Escribir "Desea continuar? s/n"
		5. Leer OPCION
	3. Fin mientras
Fin FinalLista
```

### Lista doblemente enlazadas
Conjunto de datos ordenados en el cual cada nodo apunta al nodo siguiente y el ultimo nodo a punta al primero

![[Lista Circular.png]]

Dentro de las listas circulares es importante mencionar que no existe un nodo que apunta a NULL

Las operaciones que se pueden realizar con estas listas son las siguientes:
* Crear nodo en la lista
* Buscar o localizar elementos
* Eliminar elementos
* Recorrer a través de la lista


```Java
Inicio InsertarNodoCircular()
	P, Q, T <-- tipo apuntador
	INFO, LIFA <-- Campos del nodo
	1. Si (P^.LIGA != null)
		1. Hacer T <-- P && T <-- T^.LIGA
		2. Mientras (T^.LIGA != P)
			1. T <-- T^.LIGA
		3. FinMientras
		4. Crear(Q)
		5. Leer Q^.INFO
		6. Hacer Q^.LIGA <-- T^.LIGA
			1. T^.LIGA <-- Q && T <-- Q
	2. SiNo
		1. Crear(P)
		2. Leer P^.INFO
		3. Hacer P^.LIGA <-- P
	3. FinSi
Fin InsertarNodoCircular()
```

```Java
Inicio CrearNodoFinal()
	Definir P, Q, T INFO, LIGA, OPC
	1. Crear(P) 
	2. Leer P^.INFO
	3. Hacer P^.LIGA <-- P
	4. Hacer Q <-- P
	5. Imprimir "Desea continuar? s/n"
	6. Leer OPC
	7. Mientras (OPC = 1)
		1. Crear (T)
		2. Leer T^.INFO
		3. Hacer Q^.LIGA <-- T
		4. Hacer Q <-- T
		5. Imprimir "Mas nodos? s/n"
		6. Leer OPC
	8. FinMientras
Fin CrearNodoFinal()
```

```Java
Inicio EliminarNodoCircular()
	P, Q, T
	INFO, LIGA
	1. Hacer Q <-- P
	2. Hacer P <-- Q^.LIGA
	3. Mientras (P^.LIGA != P)
		1. Hacer T <-- P
		2. Hacer T <-- T^.LIGA
			1. Si (T^.LIGA = Q)
				1. Quitar(Q)
				2. Hacer T^.LIGA <-- P
			3. FinSi
	4. FinMientras
Fin EliminarNodoCircular()
```

```Java
Inicio RecorrerNodoCircular()
	P, Q, T
	INFO, LIGA
	1. Si (P^.LIGA != null)
		1. Hacer Q <-- P
		2. Escribir Q^.INFO
		3. Hacer Q <-- Q^.LIGA
		4. Mientras (Q^.LIGA != P^.LIGA)
			1. Escribir Q^.INFO
			2. Hacer Q <-- Q^.LIGA
		3. FinMientras
	4. SiNo
		1. Escribir "Lista vacía XD UwU"
	2. FinSi
Fin RecorrerNodoCircular()
```

## Árboles
---
Son las estructura de datos NO lineales y dinámicas de datos más importantes del área de la computación

Los árboles balanceados son la estructura de datos más eficiente para trabajar con la memoria principal interna del procesador, mientras que los árboles 

Un árbol se puede definir como una estructura jerárquica aplicada sobre una colección de elementos u objetos llamados nodos. Consta de un conjunto finito de elementos, denominados nodos, y un conjunto finito de líneas dirigidas denominadas ramas, que conectan los nodos.

**Aplicaciones**
* Fórmulas matemáticas
* Registrar historias de un campeonato de tenis
* Construir un árbol genealógico
* Enumerar los capítulos

**Características**
1. Todo árbol diferente de vacío tiene un único nodo denominado raíz
2. Un nodo X es descendiente (hijo) directo de un nodo Y
3. Un nodo X es antesesor (padre) de un nodo Y
4. Todos los nodos que son descendientes directos, hijos de un mismo nodo padre son hermanos
5. Todo nodo que no tiene ramificaciones se conocen como nodos terminales
6. Las ramificaciones de un nodo hijo se llama nodo interior
7. El grado es el número de descendiente directos de un nodo
8. Joyanes empieza con nivel 0, Cairo con nivel 1
9. La altura es el máximo número de niveles de un nodo

#### Longitud de camino interno y externo 
**Longitud de camino externo**
![[Longitud de Camino Interno.png]]
i --> nivel del árbol
n --> altura
ni --> n nodos en ese nivel

**Medida de Longitud de camino interno**
```
=> MLCI = LCI / n
```

**Ejemplo:**
![[LCI ejemplo.png]]

**Longitud de camino externo**
![[Longitud de Camino Externo.png]]
nei --> nodos especiales
i --> nivel del arbol

**Medida de Longitud de camino interno**
```
=> MLCI = LCE / n
```

#### **Árboles binarios**
Cada nodo puede tener como máximo dos subárboles que se distinguen entre sí como el subárbol izquierdo y el subárbol derecho, según si ubicación con respecto al nodo raíz.

**Árboles binarios distintos:** Son diferentes sus estructuras, nodos y arcos
![[Árboles distintos.png]]
**Árboles binarios similares:** Las estructuras son idénticas solamente la información que contiene sus nodos difiere entre sí.
![[Árboles similares.png]]
**Árboles binarios equivalentes:** Su estructura es similar y además contienen la misma información
![[Árboles equivalentes.png]]
**Árboles binarios completos:** Todos sus nodos excepto los del último tienen dos hijos: el subárbol izquierdo y el subárbol derecho.
![[Árboles completos.png]]
```
número de nodos =  2^h - 1
```

### **Operaciones Básicas**
##### **Creación de Árbol Binario**
```Java
Inicio crear_nodos_AB(AP)
	INFO de tipo caracter
	IZQ, DER de tipo puntero
	OPC de tipo carácter
	O de tipo enlace
	1. Crear(AP)
	2. Leer AP^.INFO
	3. Escribir "¿Existe nodo por izquierda? s/n"
	4. Leer OPC
	5. Si (OPC = s)
		1. Crear(O)
		2. Hacer AP^.IZQ <-- O
		3. Regresar crear_nodos_AB() con AP^.IZQ
	4. Si no
		1. Hacer AP^.IZQ <-- null
	2. FinSi
	3. Escribir "¿Existen nodos por derecha? s/n"
	4. Leer OPC
	5. Si (OPC = s)
		1. Crear(O)
		2. Hacer AP^.DER <-- O
		3. Regresar crear_nodos_AB() con AP^.DER
	4. Si no
		1. Hacer AP^.DER <-- null
	2. FinSi
Fin crear_nodos_AB()
```

##### **Recorrido**
***
=> *Recorrido en Pre-orden*
- Visitar la raíz
- Recorrer Subárbol IZQ
- Recorrer Subárbol DER

Ejemplo:
![[Recorrido en pre-orden.png]]
Pre-orden: ABDECFG

```Java
Inicio preorden(AP)
	INFO de tipo caracter
	IZQ, DER de tipo enlace
	1. Si(AP != null)
		1. Visitar AP --> {Escribir NODO^.INFO}
		2. Regresar preorden() con AP^.IZQ
		3. Regresar preorden() con AP^.DER
	4. Fin si
Fin preorden(AP)
```
***
=> *Recorrido en in-orden*
* Recorrer Subárbol IZQ
- Visitar la raíz
- Recorrer Subárbol DER

Ejemplo:
![[Recorrido en in-orden.png]]
In-orden: CBDAHFIEG

```Java
Inicio inorden(AP)
	INFO de tipo caracter
	IZQ, DER de tipo puntero
	1. Si(AP != null)
		1. Regresar inorden() con AP^.IZQ
		2. Visitar AP --> {Escribir NODO^.INFO}
		3. Regresar inorden() con AP^.DER
	4. Fin si
Fin inorden(AP)
```
***
=> *Recorrido en Post-orden*
* Recorrer Subárbol IZQ
- Recorrer Subárbol DER
- Visitar la raíz

Ejemplo:
![[Recorrido en post-orden.png]]
Post-orden: DEBHIFGCA

```Java
Inicio postorden(AP)
	INFO de tipo dato
	IZQ, DER de tipo enlace
	1. Si(AP != null)
		1. Regresar postorden() con AP^.IZQ
		2. Regresar postorden() con AP^.DER
		3. Visitar AP --> {Escribir NODO^.INFO}
	4. Fin si
Fin postorden(AP)
```

## **Arboles binarios de búsqueda**
Es un tipo especial de árbol, cuya característica principal es que la información que se almacena en los nodos cuida mantener cierto orden.

#### **Operaciones básicas**
Es una estructura de datos sobre la cual se pueden realizar eficientemente las operaciones de búsqueda, inserción y eliminación. Por ejemplo, árbol binario de búsqueda se encuentra representado de la siguiente manera:
![[ABB.png]]
En la parte derecha hay números mayores y en la izquierda mayores.

Las tres operaciones se basan en un sencillo esquema de búsqueda: si el árbol T está vacío, el elementó buscado X no se encuentra en el mismo.

En caso contrario, se pueden dar tres casos:
* clave(x) = clave(raíz(t)) => el elemento ha sido encontrado
* clave(x) < clave(raíz(t)) => se repite la búsqueda en el subárbol izquierdo
* clave(x) > clave(raíz(t)) => se repite la búsqueda en el subárbol derecho

##### **Búsqueda**
La operación de búsqueda en un árbol binario de búsqueda es mucho más eficiente que en un árbol binario general. Para buscar se sigue lo siguiente:
1. Entrar por la raíz.
2. Si el número a buscar es mayor a la raíz, se toma el lado derecho.
3. Se vuelve a una raíz y se repite la comparación, si la nueva raíz es mayor al número a buscar, va tomar él subárbol izquierdo.

```Java
Inicio busquedaABB(I, P)
	INFO, IZQ, DER del nodo
	P de tipo puntero {apunta a la raíz}
	1. Si(INFO < P^.INFO)
		   Si(P^.IZQ = NULL)
			   Escribir "La info no se encontró"
		   Si no
			   Regresar a busquedaABB() con P^.IZQ, INFO
		   Fin Si
	2. Si no, Si(INFO > P^.INFO)
		   Si(P^.DER = NULL)
			   Escribir "La info no se ha encontrado"
		   Si no
			   Regresar a busquedaABB() con P^.DER, INFO
		   Fin Si
	3. Fin Si
Fin busquedaABB(I, P)
```

##### **Inserción**
```Java
Inicio insertarABB(I, P)
	INFO, IZQ, DER del nodo
	P de tipo enlace
	I tipo entero
	1. Si(INFO < P^.INFO)
		   Si(P^.IZQ = NULL)
			   Crear(Q)
			   Hacer Q^.IZQ <-- null
			   Q^.DER <-- null, Q^.INFO <-- I
			   P^.IZQ <-- Q
		   Si no
			   Regresar a insertarABB() con P^.IZQ, INFO
		   Fin Si
	2. Si no, Si(INFO > P^.INFO)
		   Si(P^.DER = NULL)
			   Crear(Q)
			   Hacer Q^.IZQ <-- null
			   Q^.DER <-- null, Q^.INFO <-- I
			   P^.DER <-- Q
		   Si no
			   Regresar a insertarABB() con P^.DER, INFO
		   Fin Si
	3. Fin Si
Fin insertarABB(I, P)
```

##### **Eliminación** 
```Java
Inicio eliminarABB(102, P)
	INFO, IZQ, DER del nodo
	P de tipo enlace
	I tipo entero
	1. Si (P != null)
		   Si(102 < P^.INFO)
			   Regresar eliminarABB() con P^.IZQ, 102
		   SiNo
			   Si(102 > P^.INFO)
				   Regresar eliminarABB con P^.DER, 102
			   SiNo
				   Hacer O <-- P
				   Si(O^.IZQ = null && O^.DER = null)
					   Hacer P^.DER <-- null
				   FinSi
			   FinSi
	   SiNo
		   Escribir "No hay datos en el arbol"
	   FinSi
Fin eliminarABB(I, P)
```

#### **Características**
* Los valores almacenados en el subárbol izquierda de T deben ser menores o iguales a la información guardada en el nodo T (raíz).
* Si se hace un recorrido en in-orden la impresión de los datos se dará de manera ascendente.
---
## **Árboles Balanceados (AVL Adelson Velskii y Landis)**
Con el objeto de mantener una eficiencia en la operación de búsqueda surgen los árboles balanceados.

La característica principal es la de realizar reacomodos o balanceos luego de realizar operaciones básicas (búsqueda, inserción, eliminación) de elementos dentro de un árbol.

**Definición formal**. Se define como un Árbol Binario de Búsqueda, en el cuál se debe cumplir la siguiente condición: para todo nodo T del árbol la altura de los subárboles izquierdo y derecho no deben diferir en más de una unidad.

```Java
h = 0 --> vacío
h = 1 --> 1 nodo

Kh = Kh1 + 1 + Kh-2
Donde,
	- K = número de nodos A
	- n = altura

Si h = 5
K5 = K4 + 1 + K3
	K4 = K2 + 1 + K1
		K3 = K2 + 1 + K1
			K2 = K1 + 1 + K0
				K1 = 1
				K0 = 0
			K2 = 2
		K3 = 4
	K4 = 7
K5 = 12 nodos
```

```
1. La ramas (RI) y (RD) tienen misma altura
	1. Insertar 1 elemento RI
		HRI > HRD
	2. Insertar 1 eleneto RD
		HRD > HRI

2. Las ramas (RI) y (RD) tienen altura diferente 
	1. HRI < HRD
		1. Insertar 1 elemento RI
			HRI = HRD
		2. Insertr 1 elemento RD
			Rompe criterio equilibrio
	2. HRI > HRD
		1. Insertar 1 elemento RI
			Rompe equilibrio
		2. Insertar 1 elemento RD
			HRD = HRI
```

En los árboles AVL surge el concepto de Factor de Equilibrio que ayuda a determinar si existe o no equilibrio en un árbol binario de búsqueda, el cual se distingue con la siguiente formula:
```Pascal
FE = altura subárbol derecho - altura subárbol izquierdo

Significado del resultado:
	- (-1) cargado a la izquierda
	- (0) equilibrado
	- (1) cargado a la derecha
```
* Valores que pueden tomar el FE son -1, 0, 1 (equilibrio)
* Valores que NO pueden tomar el FE son -2, 2 (no equilibrado)

![[Fórmula FE árboles AVL.png]]

```Java
DeFinición LA
	ENLACE = 1 nodo
	NODO = REGISTRO
		IZQ de tipo ENLACE
		DER de tipo ENLACE
		INFO de tipo DATO
		FE: {-1, 0, 1}
Fin
```

##### **Reestructuración del Árbol Balanceado**
**Operaciones Auxiliares**
```
Rotar los Nodos
								    -> DD
			-> Simple (2 nodos) ---|
		   |					    -> II
Rotación --|
		   |					       -> DI
			-> Compuesta (3 nodos) ---|
								       -> ID
```

**Inserción**
```Java
Inicio InsertarAVL(P, DATO)
	P, Q, P1 de tipo APUNTADOR
	IZQ, DER, IND campos del NODO
	1. Si(P != null)
		Si(42 < P^.INF)
			Regresar InsertarAVL(P^.I, 42)
		Sino
			Si(42 > P^.INF)
				Regresar InsertarAVL(P^.D, 42)
			Fin Si
		Fin Si
	2. Sino
		Crear(Q)
		Hacer Q^.INF <-- 42
		Hacer Q^.IZQ <-- null
		Hacer Q^.DER <-- null
		Hacer P1^.DER <-- Q
		Calcular Q^.FE
		Hacer Q^.FE <-- 0
		{Calcular P1^.FE ==> P1^.FE = 1 - 0 = 1}
		Hacer P1^.FE <-- 1
		{Calcular P^.FE ==> P1^.FE = 2}
		Hacer P^.FE <-- 2
		//Rotacion
		Si (P^.FE = 2)
			Hacer Q^.IZQ <-- P1
			Hacer Q^.DER <-- P
			{Recalcular FE}
		FinSi
	3. FinSi
Fin InsertarAVL()
```

## Árboles B
Son una generalización de los árboles AVL. Representan un método para almacenar y recuperar información en medios externos.

**Un grupo de nodos va a recibir el nombre de páginas**, en donde se almacena la información de un grupo de nodos y se identifica por medio de una clave/llave

Se dice que cada página de un árbol B de orden (grado) d, con tiene como 2d claves como máximo.

Si un árbol es de orden 2
* d = 2
* La página tiene como máximo 2d = 2(2) = 4 nodos
* La página tiene como mínimo d = 2 nodos

**Sus hijos**
- Como máximo tiene 2d + 1 hijos
- Como mínimo tiene d + 1 hijos

La página raíz puede contener como:
- min --> 1 dato
- máx --> 2d datos

Por temas de espaciado en cada nodo se almacena un dato.

![[Estructura Árbol B.png]]

#### Operaciones básicas
##### Búsqueda Árbol B
Es una generalización de los árboles binarios de búsqueda. Como principio se debe tener localizada la página en la que se va a buscar la clave
```Java
x --> clave a buscar
cl --> clave

Inicio Busqueda()
	1. Ubicar la pagina en memoria sobre la cual se va a trabajar
		Si (pagina != null)
			Avanzar paso 2
		Sino
			Avanzar paso 3
	2. Se debe verificar si la clave buscada esta en la pagina. Si m es pequeno se usa una busqueda secuencial o binaria
		Si (clave encontrada en pagina)
			Escribir "Dato encontrado!"
		SiNo
			Si (datoABuscar < clave1)
				Localizar pagina cero
			Si (cli < datoABuscar < clave max)
				Localizar pagina i
			Si (datoABuscar > clave max)
				Localizar pagina max
			FinSi
		FinSi
		Regresar paso 1
	3. Escribir "Fracaso"
Fin Busqueda()
```

##### Inserción Árbol B
```Java
Inicio Inserción()
	1. Se debe localizar la página en donde se va a insertar el dato, tal que no altere las propiedades del árbol
	2. Si (m < 2d)
		Insertar la clave en el lugar correspondiente.
	    Si No
		    La página se divide en don y se distribuyen las (m + 1) claves equitativamente. 
		    La clave del medio sube a la página antecesora.
	    Fin Si
Fin Inserción()

Donde:
	- m, número máximo de elementos de la página
```

##### Eliminación Árbol B
Consiste en quitar una árbol sin violar las condiciones básicas 
* m < d
* m > 2d
Donde m, es el numero de claves en la pagina
```Java
1. Si clave a eliminar está en la pagina hoja, se suprime.
	1.1. Si (m >= d)
			Termina la operacion de borrado
		 Si No
			Bajar clave adyacente de la pagina antecesora y sustituir por clave por las que se encuentra mas a la derecha en el subárbol izquierdo o mas a la izquierda en en subárbol derecho con el fin de que m siga siendo >= que d
			Si no es lo anterior posible, por las m paginas, se debe fusionar las paginas que son descendientes directas de la calve que se baja
	1.2. Fin Si
2. Fin Si
3. Si la clave a eliminar no está en la página hoja
	3.1. Se debe sustituir por la clave que se encuentra más a la izuuierda en el subarbol derecho o por la clave que se encuentra más a la derecha en el subárbol izquierdo
	3.2. Si (m >= d)
			Termina la operación de borrado
		 Sino
			 Se baja la clave adyacente de la página antecesora y fusionar las páginas que son descendientes directas de dicha clave.
	3.3. Fin Si
4. Fin Si
```

![[Eliminación Árbol B.png]]

![[Eliminación Árbol B (2).png]]


## Ordenación y búsqueda
**Ordenar**, reagrupar o reorganizar datos en una secuencia especifica.
**Buscar**, recuperar de información normalmente sobre elementos ordenados.

Formalmente: Sea A una lista de N elementos $A_1$; $A_2$; $A_3$...$A_n$
Ascendentes $A_1$<=$A_2$<=$A_3$ ... $A_n$
Descendentes $A_n$>=$A_1$>=$A_2$>=$A_3$>+$A_n-1$

Ordenación interna
Ordenación de Arreglos se denomina también ordenación interna ya que los elementos se encuentran en la memoria principal

Arreglos unidimensionales



