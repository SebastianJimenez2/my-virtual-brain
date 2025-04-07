Lenguaje de alto nivel (entendible para el ser humano). Dispone de una buena optimización de código.
Se usan en diferentes campos.

IDE -> Entorno integrado de Desarrollo

---
# TIPOS DE DATOS
- string (str)
```python
"Hola mundo"
```
- integer (int)
```python
1, 2, 3
```
- floating (float)
```python
1.25, 1.36
```
- listas (list)
```python
[a, b, c]
 0  1  2
```
- diccionarios (dic)
```python
{'color':'rojo', 'arte':'cine'}
	clave --> color
	valor --> rojo
```
* tuples (tuple). Pueden ser de cualquier tipo de datos. Su orden es inmutable, su orden no se puede modificar nunca.
```python
('lun', mar, 'mier')
```
* sets (set). Arreglos con elementos únicos y no repetibles
```python
{'a', 'b', 'c'}
```
* booleanos (bool)
```python
true, false
```

---
# VARIABLES
Espacio de memoria al que se le pone un nombre y sirve para almacenar contenido.
# CONVERSIONES
* **Implícitas**.  Python convierte el tipo de datos en otros tipos de datos automáticamente.
* **Explícitas.** Nosotros somos los que especificamos a qué tipo de variable se va a convertir la variable.

# FORMATEAR CADENAS
* Función format
```python
print("Mi auto es {} y de matricula {}".format(color_auto, matricula))
```
* Cadenas literales
```python
print(f"Mi auto es {color_auto} y de matricula {matricula}")
```
# REDONDEO
```python
round(numero, decimales)
```

---
# MANIPULAR STRINGS
Secuencia de caracteres, los cuáles tiene una secuencia ordenada desde 0 hasta n.
#### index()
* Determinar la posición de un caracter.
* Devuelve la posición de un caracter específico.
```python
index(caracter, <desde donde>, <hasta donde>)
```

> La búsqueda es menor a, es decir que si se busca un caracter desde 5 hasta 10, los caracteres en las posiciones 5 y 10 no van a contar dentro de la búsqueda 
### Slicing
>Desde donde : hasta donde, pero sin incluirlo : saltos que va a realizar.
```python
palabra = "ABCDEFGHIJL"
palabra[5:10:2]
resultado => "FHJ"
	```
### Upper
```python
texto = "hola"
texto.upper()
resultado => HOLA
```
### Lower
```python
texto = "HOLA"
texto.lower()
resultado => hola
```
### Split
> Por defecto toma por separador los espacios, pero se le puede pasar como parámetro al separador que se desee.
```python
texto = "hola como estas"
texto.split()
resultado => ['hola', 'como', 'estas']
```
### Join
>Usa como 'unidor' a lo que se especifique antes de usar el método .join().
```python
texto = "hola"
texto1 = "como"
texto2 = "estas"
texto3 = " ".join([texto, texto1, texto2])
resultado => "hola como estas"
```
### Find
> Es igual a index, sin embargo, este método al no encontrar la palabra especificada devuelve -1 y no error.
```python
texto = "hola"
texto.find("l")
resultado => 2
```
### Replace
>Necesita dos parámetros: el texto que se desea reemplazar y por lo que se desea reemplazar.
```python
texto = "hola como estas"
texto.replace("o", "a")
resultado => hala cama estas
```

---
# PROPIEDADES DE LOS STRINGS
- Son **inmutables**, una vez que han sido construidos no puedes modificar su orden interno.
```python
nombre = "Carina"  
nombre[0] = "K"  
print(nombre)
resultado => TypeError
```
- Son **concatenables** y **multiplicables**.
```python
nombre = "Carina"  
print(nombre * 10)
resultado => CarinaCarinaCarinaCarinaCarinaCarinaCarinaCarinaCarinaCarina
```
- Son **multilineales**
```python
poema = """Juan,  
Este mundo es una  
maravilla"""
```
- **Verificar** si contiene
```python
poema = """Juan,  
Este mundo es una  
maravilla"""  
print("es" in poema)
print("es" not in poema)

resultado = true
resultado = false
```
- **Calculables** en su longitud
```python
palabra = "hola mundo"
print(len(palabra))

resultado => 10
```

---
# LISTAS
Secuencia ordenada de objetos. Puede estar compuesta por diferentes tipos de elementos a diferencia de otros lenguajes de programación.

> Listas anidadas. Una lista de listas.

Las listas son inmutables como los strings. Las funciones que se les puede implementar a las listas son similares y en su mayoría iguales a los de los strings:
### Agregar un elemento a una lista
```python
mi_lista = ['a', 'b', 'c']  
mi_lista3.append('beta')  

resultado => ['a', 'b', 'c', 'beta']
```
### Eliminar un elemento de una lista
>Si no se especifica nada dentro del método pop, Python eliminará siempre el último elemento. Además, al usar el método pop() la variable eliminada se puede guardar dentro de otra variable.
```python
mi_lista = ['a', 'b', 'c']  
mi_lista.pop()  

resultado => ['a', 'b']
```
### Ordenar a-z
>El método sort no devuelve nada, sino que trabaja sobre la lista, por lo que si se espera almacenar la lista ordenada dentro de una variable nueva usando sort() nos devolverá 'None'
```python
lista = ['g', 'o', 'm', 'c', 'b']  
lista.sort()  

resultado => ['b', 'c', 'g', 'm', 'o']
```
### Ordenar z-a
>Al igual que sort, no devuelve nada cuando se usa reverse
```python
lista = ['g', 'o', 'm', 'c', 'b']  
lista.reverse()  

resultado => ['o', 'm', 'g', 'c', 'b']
```
### Concatenar
```python
mi_lista = ['a', 'b', 'c']  
mi_lista2 = ['d', 'e', 'f']  
mi_lista3 = mi_lista + mi_lista2

resultado => ['a', 'b', 'c', 'd', 'e', 'f']
```
### Inmutabilidad
>A diferencia de los strings, si se puede cambiar un valor dentro de la lista esto se conoce como **inmutabilidad**.
```python
mi_lista = ['a', 'b', 'c']  
mi_lista2 = ['d', 'e', 'f']  

mi_lista3 = mi_lista + mi_lista2
mi_lista3[0] = 'alfa'

resultado => ['alfa', 'b', 'c', 'd', 'e', 'f']
```

---
# DICCIONARIOS
Es una colección de pares, en donde cada una de estas tiene una clave y un valor asociado a dicha clave. No tienen un índice, por lo que el orden es irrelevante para python. Para realizar la búsqueda se hace mediante su clave, no mediante su índice.
```python
mi_diccionario = {'clave':'valor'}
```

> Las claves deben ser únicas, a diferencia de los valores que si pueden duplicarse.
### Consultas
```python
cliente = {'nombre': 'Juan', 'apellido': 'Ramirez', 'peso': 60, 'talla': 1.72}  
consulta = cliente['apellido']

resultado => Ramirez
```
### Añadir elementos
```python
cliente = {'nombre': 'Juan', 'apellido': 'Ramirez', 'peso': 60, 'talla': 1.72} 
cliente['nacionalidad'] = 'ecuatoriano'

resultado => {'nombre': 'Juan', 'apellido': 'Ramirez', 'peso': 60, 'talla': 1.72, 'nacionalidad': 'ecuatoriano'} 
```
### Eliminar
```python
cliente = {'nombre': 'Juan', 'apellido': 'Ramirez', 'peso': 60, 'talla': 1.72}  
cliente.pop('nombre')

resultado => {'apellido': 'Ramirez', 'peso': 60, 'talla': 1.72} 
```
### Obtener claves
```python
cliente = {'nombre': 'Juan', 'apellido': 'Ramirez', 'peso': 60, 'talla': 1.72}  
cliente.keys()

resultado => dict_keys(['nombre', 'apellido', 'peso', 'talla'])
```
### Obtener valores
```python
cliente = {'nombre': 'Juan', 'apellido': 'Ramirez', 'peso': 60, 'talla': 1.72}  
cliente.values()

resultado => dict_values(['Juan', 'Ramirez', 60, 1.72])
```
### Obtener tuplas
```python
cliente = {'nombre': 'Juan', 'apellido': 'Ramirez', 'peso': 60, 'talla': 1.72}  
cliente.items()

resultado => dict_items([('nombre', 'Juan'), ('apellido', 'Ramirez'), ('peso', 60), ('talla', 1.72)])
```

---
# TUPLAS
- Ocupan menos espacio de memoria
- No pueden ser modificadas
### Obtener un valor de la tupla
```python
mi_tuple = (1, 2, 3, 4, 5)
print(mi_tuple[2])

resultado => 3
```
### Inmutable
```python
mi_tuple = (1, 2, 3, 4, 5)
mi_tuple[0] = 5

resultado => TypeError
```
### Tuplas anidadas
```python
mi_tuple = (1, 2, (10, 20), 4, 5)
print(mi_tuple[2][0])

resultado => 10
```
### Casteo
```python
mi_tuple = (1, 2, (10, 20), 4, 5)
list(mi_tuple)
```
### Extraer valores
>Para hacer este proceso es importante que se asignen la misma cantidad de valores que tiene la tupla, si se quieren asignar 3, entonces la tupla debe ser de longitud 3.
```python
t = (1, 2, 3)
x, y, z = t

print(x, y, z)
resultado => 1 2 3
```
### Longitud
```python
t = (1, 2, 3)
len(t)

resultado => 3
```
### Contar
>Permite contar la cantidad de apariciones de un item dentro de la tupla
```python
t = (1, 2, 3, 1)
t.count(1)

resultado => 2
```
### Index
```python
t = (1, 2, 3)
t.index(2)

resultado => 1
```

---
# SETS
Se pueden declarar de dos maneras
```python
set([<elementos>]) => admite solo un conjunto de elementos, por eso se encierra entre corcehtes.
{1,2,3,4}
```

Solo aceptan valores únicos, si se encuentran duplicados Python los descarta. Además, no se pueden agregar listas ni diccionarios en el conjunto de valores.

Los sets no tienen orden, por ende no se puede hacer ningun tipo de manipulacion con indices.
### Definir set
```python
mi_set = set([1, 2, 3, 4, 5])

otro_set = {1, 2, 3, 4, 5}
```
### Union de sets
```python
s1 = {1,2,3}
s2 = {3,4,5}

s3 = s1.union(s2)

resultado = {1, 2, 3, 4, 5}
```
### Agregar
```python
s1 = {1,2,3}
s1.add(4)
```
### Eliminar
```python
s1 = {1,2,3}
s1.remove(3)
s1.pop() => elimina un elemento aleatorio (lo puedes almacenar)
```
### Descartar
Funciona igual que remove, pero si descartas un elemento que no existe no da error.
```python
s1 = {1,2,3}
s1.discard(6)
```
### Limpiar
```python
s1 = {1,2,3}
s1.clear() => vacia al set
```

---
# Booleanos
Son variables que tienen dos valores: `true` y `false`, generalmente se usan para poder determinar si cierto tipo de acción/valor cumple con una condición en específico o no.

En este caso, podemos usar los diferentes operadores de comparación para obtener estas variables: (`==`, `!=`,  `<`, `>`, `<=`, `>=`)

---
# OPERADORES DE COMPARACIÓN

| Operador | Descripcion   |
| -------- | ------------- |
| =        | Asignación    |
| ==       | Comparación   |
| >=       | mayor o igual |
| <=       | menor o igual |
| !=       | distinto      |
| >        | mayor que     |
| <        | menor que     |

---
# OPERADORES LÓGICOS
| Operador | Descripción |
| -------- | ----------- |
| and      | y           |
| or       | o           |
| not      | no          |

---
# CONTROLES DE FLUJO

```python
if (condicion):
	do_something()
elif (condicion):
	do_something_else()
else:
	do_something_else_else()
```

---
# LOOPS
### FOR
```python
for <elemento> in <algo>:
	do_somethin()
```
### WHILE
```python
while condicion:
	do_something()
else:
	do_something_else()
```
### Palabras clave
| Palabra  | Descripción                                      |
| -------- | ------------------------------------------------ |
| break    | Detiene el proceso o loop que se este ejecutando |
| pass     | Pasar, saltarse un pedazo de código              |
| continue | Permite continuar con un loop                    |

---
# RANGO
```python
range(empieza, finaliza (sin contarlo), saltos)
```
# ENUMERADOR
>Devuelve una tupla (índice, item) de un arreglo.

```python
lista = ['apple', 'banana', 'cherry']  
  
for indice, item in enumerate(lista):  
    print(indice, item)

resultado:
0 apple
1 banana
2 cherry
```
# ZIP
Combina dos o más lista en una lista de tuplas
```python
nombres = ['Jose', 'Maria', 'Pedro']  
edades = [20,12,21]  
  
combinaciones = list(zip(nombres, edades))  
print(combinaciones)

resultado => [('Jose', 20), ('Maria', 12), ('Pedro', 21)]
```

>Si se unen listas que no son del mismo tamaño, se descartarán los valores de la lista más larga en comparación a la lista más corta.

# MIN y MAX
```python
menor = min(2,4,7,8,9,6,8)  
mayor = max(2,4,7,8,9,6,8)

resultado:
2
9
```
# RANDOM
### Randint
>Entrega un entero aleatorio entre el rango provisto.
```python
aleatorio = randint(1, 50)  
print(aleatorio)
```
### Uniform
>Entrega un número decimal aleatorio entre el rango definido, se puede limitar los decimales usando `round()`
```python
aleatorio = round(uniform(1, 50), 1)  
print(aleatorio)
```
### Random
>Entrega un número aleatorio entre 0 y 1
```python
aleatorio = random()
print(aleatorio)
```
### Choice
>Escoge un elemento de un arreglo
```python
colores = ['red', 'green', 'blue']  
aleatorio = choice(colores)  
print(aleatorio)
```
### Shuffle
>Re-ordena una lista proporcionada
```python
numeros = list(range(1, 11, 3))  
shuffle(numeros)  
print(numeros)
```
# MATCH
Es el `switch-case` de python, fue introducido en la version 3.10. Al ser agregado, Python quiso que su implementación destaque de los demás lenguajes de programación, por ende, hizo capaz que esta estructura sea capaz de **detectar** patrones en diccionarios
### Estructura base
```python
match <algo>
	case <algo>:
		do_something()
	case <algo_más>
		do_something_else()
	case _:
		do_something() #Caso para definir qué hacer en caso de que no se cumpla lo demás
```
### Patrones con diccionarios
Un diccionario es aquella estructura que posee una clave y un valor, con switch y case, podemos identificar patrones dentro de estos diccionarios para que el programa haga x o y cosa según sea el caso:
```python
#Se define un diccionario de clientes
cliente = {'nombre': 'Federico',  
           'edad': 45,  
           'ocupación': 'instructor'}  

#Se define un diccionario de películas
película = {'titulo': 'Matrix',  
            'ficha_técnica': {'protagonista': 'keanu reeves',  
                              'director': 'Lana y Lily'}}  

#Creamos un arrelgo con los diccionarios
elementos = [cliente, película, 'libro']  

#Procedemos a buscar patrones dentro del arreglo
for e in elementos:  
    match e:  
        case {'nombre': nombre,  
              'edad': edad,  
              'ocupación': ocupación}:  
            print('Es un cliente')  
            print(nombre, edad, ocupación)  
        case {'titulo': titulo,  
              'ficha_técnica': {'protagonista': protagonista,  
                                'director': director}}:  
            print("Es una película")  
            print(titulo, protagonista, director)  
        case _:  
            print("No sé qué es esto")
```
---
# FUNCIONES
Permiten crear bloques de código para reutilizar el código, no repetirlo constantemente.
### Métodos
Funciones pertenecientes un objeto que permiten manipularlos, analizarlos y ejecutar acciones. Son generadas por Python.
### Crear funciones
```Python
def nombre_función (parámetro_1 ... parámetro_N):
	# Cuerpo de la función (código)

# Para llamar a la función
nombre_función(parámetro_1 ... parámetro_N)
```
 >En Python los parámetros no necesitan ser definidos con su tipo, como en otros lenguajes de programación, es necesario únicamente el nombre y el compilador asumirá de qué tipo es. 

Para asignar un resultado a una función, se usa `return`, esto permite almacenar dentro de un variable el valor devuelto y poder usarlo a gusto del desarrollador.
```Python
def multiplicar(numero_1, numero_2):  
    return numero_1 * numero_2  
  
  
resultado = multiplicar(1, 2)  
print(resultado)

>>> 2
```
### Funciones Dinámicas
Consiste en hacer que las funciones devuelvan algo a partir de una lógica impartida, es decir, dentro de la función pueden existir estructuras que manipules los o el parámetro que la función requiere.
### Interacciones de Funciones
Consiste en usar los resultados de una función en otra función para que esta misma la use para sus propósitos pertinentes.
```Python
from random import *  
  
  
def lanzar_moneda():  
    resultados = ['Cara', 'Cruz']  
    return choice(resultados)  
  
  
def probar_suerte(resultado_lanzamiento, lista):  
    if resultado_lanzamiento == 'Cara':  
        print("La lista se autodestruirá")  
        lista.clear()  
        return lista  
    elif resultado_lanzamiento == 'Cruz':  
        print("La lista fue salvada")  
        return lista  
  
  
resultado_lanzamiento_método = lanzar_moneda()  
lista_números = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]  
probar_suerte(resultado_lanzamiento_método, lista_números)
```
# Argumentos
### Argumentos definidos
Sirve para cuando se requiere pasar varios valores a una función. Trabaja como una tupla
```Python
*args   #El término args es una convención, se podría usar cualquier nombre
		#siempre y cuando esté el *
```
**Ejemplo:**
```Python
def suma(*args):  
    return sum(args)
  
  
print(suma(5, 6, 5, 8, 5))
```
### Argumentos indefinidos
Trabaja como dsi fuesen diccionariosiccionarios 
```Python
**kwargs   #El término kwargs es una convención, se podría usar cualquiera 
		   #siempre y cuando esté el **
```
**Ejemplo:**
```Python
def suma(**kwargs):  
    for clave, valor in kwargs.items():  
        print(clave, valor)  
  
  
suma(x=1, y=2, z=3)
```

---
# Archivos
### Manipular archivos
- **Abrir un archivo**
```Python
mi_archivo = open('nombre_del_archivo')
```
>Lo que devuelve 'open' es los metadatos del archivo, no el archivo en sí.

>Si el archivo se encuentra a nivel de la clase en dónde se extrae no es necesario especificar la ruta

Para manipular el archivo, se pueden usar los métodos asociados a la variable que guardó el archivo.

* **Leer un archivo**
```Python
print(mi_archivo.read())
```
Si se quiere leer una sola línea se debe usar:
```Python
print(mi_archivo.readline())
```
>Este comando guarda un punto de lectura dentro del archivo, por lo que si se vuelve a llamar (desde otra variable) leerá la siguiente línea del archivo y no la misma una vez

Para eliminar el salto de línea entre la lectura de líneas se puede usar:
```Python
print(mi_archivo.readline().rstrip())
```

>Al leer una línea, lo que se tiene es un string, por lo que todo las operaciones con string son válidas en la variable que esté guardando la información.

Para leer más de una sola línea, se puede usar un bucle 'for', sin embargo está práctica no es lo mejor, por lo que existe el siguiente método para dicho caso:

```Python
print(mi_archivo.readlines())
```

- **Cerrar un archivo**

>Para ahorrar memoria en el ordenador, es importante cerrar el archivo que se está manipulando.

```Python
mi_archivo.close()
```
### Crear y escribir archivos
- **Modos de apertura**

| Clave | Descripción                          |
| ----- | ------------------------------------ |
| 'r'   | Solo lectura (modo por defecto)      |
| 'w'   | Solo escritura, resetea el archivo   |
| 'a'   | Solo escritura, al final del archivo |
- **Escribir en un archivo**
```Python
archivo = open('nombre_del_archivo', 'modo_de_apertura')
archivo.write('linea nueva')
archivo.close
```
>Si el archivo tiene contenido y se usa el tipo de apertura 'w' todo este contenido será eliminado y reemplazado por lo que se mande en el método 'write'.

```Python
archivo = open('nombre_del_archivo', 'modo_de_apertura')
archivo.writelines(['hola', 'mundo'])
archivo.close
```

>Este método lo que hace es mostrar en el archivo el arreglo que se lo pase concatenando las palabras, no escribe cada palabra en una línea diferente como se esperaría. Si se desea hacer eso, se puede seguir lo siguiente:

```Python
archivo = open('registro.txt', 'a')  
registro_ultima_sesion = ["Sebas", "20/04/2024", "08:17:32 hs", "Sin errores de carga"]  
for palabra in registro_ultima_sesion:  
    archivo.writelines(palabra + "\n")  
archivo.close()  
  
archivo = open('registro.txt')  
print(archivo.read())  
archivo.close()
```

>El modo de lectura 'a' se usa generalmente para hacer logs, ya que escribe en la siguiente línea del archivo sin modificar lo que existe ya en el mismo.
### Rutas y directorios
```Python
from pathlib import Path

base = Path.home()
guia = Path("arg1", "arg2")
```

>home() va a devolver la base del directorio en el que nos encontremos, se usa para establecer rutas globales: C:/USER/User1

>Los atributos que se le pasen a Path, forman una ruta, es decir, los concatena usando '/', esto sirve para extraer archivos usando rutas relativas.

Existen formas que optimizan la obtención de ciertos archivos dentro de un directorio, dado a que Path devuelve un objeto iterable, se podría hacer lo siguiente:
```Python
guia = Path("arg1", "arg2")

for txt in Path(guia).glob('*.txt'):  
    print(txt)
```

En este caso, se está diciendo que: todos los archivos txt (`*.txt`) que se encuentren dentro de la ruta `guia` se impriman en pantalla.

Por otro lado, si dentro de un directorio, se tiene otro directorio y dentro de este se encuentran archivos txt, se podría decir que se muestre en pantalla todos estos de la siguiente forma:
```Python
for txt in Path(guia).glob('**/*.txt'): # **/ significa "todos los directorios"
    print(txt)
```

La clase Path ofrece bastantes opciones para manejar rutas y directorios, por lo que, siempre se sugiere seguir la documentación: [Path.py](https://docs.python.org/3.10/library/pathlib.html?highlight=path#module-pathlib)
### Descomprimir y comprimir archivos
Para realizar esta acción se necesita importar el módulo `zipfile`
##### Comprimir
```Python
import zipfile

zip = zipfile.ZipFile(<.zip>, w)
zip.write(<archivo>) # Crea el archivo dentro del .zip comprimido

zip.close()
```
#### Descomprimir
```Python
import zipfile

zip = zipfile.ZipFile(<.zip_comprimido>, r)
zip.extractall() 

zip.close()
``` 
# Consola
Dentro de la consola, podemos limpiar la información que se presenta en la misma a medida que se ejecuta el programa. Siguiendo el siguiente método de la siguiente librería:
```Python
from os import system

# TODO: código

system('cls') # Para windows

# TODO: continuación del código
```
# os y shutil
- **Saber en que directorio estoy trabajando**
```Python
import os

os.getcwd()
```
- **Listar todos los archivos de un directorio**
```Python
import os

os.listdir()
```
- **Mover archivos**
```Python
import shutil

shutil.move(<archivo>, ruta)
```
- **Eliminar archivos**
```Python
import shutil
import os

os.unlink(<ruta>) # Eliminar un archivo
os.rmdir(<ruta>) # Elimina una carpeta

shutil.rmtree(<ruta>) # Elimina todo de una ruta
```

>Para eliminar archivos y que vayan a la papelera podemos instalar `pip install send2trash`

```Python
import send2trash

send2trash.send2trash(<archivo>)
```
- **Recorrer todos los directorios**
```Python
import os

os.walk(<ruta>) # Devuelve un generedor

for carpeta, subcarpetas, archivos in os.walk(<ruta>):
	print(f"En la carpeta: {carpeta} hay: ")
	for subcarpeta in subcarpetas:
		print(subcarpeta)
		
	for archivo in archivos:
		print(archivo)
```
>El orden de devolución de este método es: ruta (carpeta), subcarpetas y archivos
# Programación Orientado a Objetos
**Clase.** Conjunto de atributos y métodos.
**Objeto.** Instancia de una clase.
### Principios de la POO
- Herencia
- Polimorfismo
- Cohesión
- Abstracción
- Acoplamiento
- Encapsulamiento
### Crear una clase
```Python
class <NombreClase>:
	# Lógica de la clase
```
### Crear un objeto
```Python
nombreObjeto = NombreClase()
```

### Atributos
```Python
class Pájaro: 
	atributoDeClase = True
	
    def __init__(self, parámetro):
        self.atributo = parámetro
```
 - `__init__`. Se usa para definir el constructor de la clase
 - `self`. Representa la instancia del objeto que se va a crear
 
>Los atributos definidos fuera del constructor son denominados como 'atributos de clase', mientras que los atributos definidos dentro del constructor son denominados como 'atributos de instancia'

### Métodos
##### Métodos de instancia
```Python
class Pájaro: 
	#...
	
	def piar(self, parámetro)
		# Lógica del método
```
Estos métodos son capaces de acceder y modificar los atributos del objeto, además puede acceder a otros métodos y a su vez modifica el estado de la clase.
##### Métodos de clase
```Python
class Pájaro: 
	#...
	
	@classmethod
	def piar(cls)
		# Lógica del método

```
Pueden ser llamados directamente desde la clase, sin necesidad de tener una instancia. No puedes modificar los atributos de instancia, pero si los atributos de la clase.
##### Métodos de estáticos
```Python
class Pájaro: 
	#...
	
	@staticmethod
	def piar(parámetro)
		# Lógica del método
```
No modifica el estado de la clase ni de la instancia.
### Herencia
Para hacer una herencia en Python, se debe enviar como parámetro la clase padre a la clase hija.
```Python
class Animal:
	# Lógica de Animal

class Pajaro(Animal):
	# Lógica de Pájaro
```
### Herencia Extendida
```Python
class Padre:  
    def hablar(self):  
        print("Hola")  
  
  
class Madre:  
    def reir(self):  
        print("Ja, ja, ja")  
        
    def hablar(self):  
	    print("Hijo mío")
  
  
class Hijo(Padre, Madre):  
    pass  
  
class Nieto(Hijo):  
    pass


mi_nieto = Nieto()
mi_nieto.hablar()
mi_nieto.reir()
```
> Como hijo hereda tanto de padre y madre, y estás dos clases tienen el mismo método: "hablar", entonces se castea el primero que esté dentro de los parámetros de la clase hija. En cambio, si nieto quiere "hablar", primero se castea el método de la clase antecesora: hijo, si no tiene un método "hablar", sigue el orden anterior.
### Métodos y atributos
##### Método heredados
Son aquellos que se encuentran dentro de la clase padre y los usa el hijo sin modificarlos.
##### Métodos heredados modificados
Son aquellos que tiene la clase padre, sin embargo, dentro de la clase hija se modifica su lógica.
##### Métodos nuevos
Son aquellos que pertenecen a la clase hija pero no existe en la clase padre.
##### Atributos heredados
```Python
class Animal:  
    def __init__(self, edad, color):  
        self.edad = edad  
        self.color = color  
  
class Pájaro(Animal):  
    def __init__(self, edad, color, altura_vuelo):  
        super().__init__(edad, color)  
        self.altura_vuelo = altura_vuelo
```
### Polimorfismo
Los objetos pueden tomar diferentes formas. Es decir, un mismo método de la clase padre puede hacer diferentes cosas en sus clases hijas.
### Métodos Especiales
Su nomenclatura es la siguiente:
```Python
__método__
```
El método `__init__` es un método especial para definir el constructor de la clase.
En el caso de java, para imprimir una clase, se usa un `toString()` en Python, se hace un uso de un método especial para este caso:
```Python
class <something>:
	def __str__(self):  
	    return #something
```

Dentro de la documentación: [Clases](https://docs.python.org/es/3/tutorial/classes.html) se puede indagar más sobre los métodos especiales que una clase puede obtener.

---
# Módulos y Paquetes
- **[PyPi](https://pypi.org/)**
Se usa para instalar paquetes, esto se hace mediante la consola integrada que tiene el IDE PyCharm, para cometer dicho acto se debe usar el siguiente comando:
```Python
pip install
```
##### Módulos
Cualquier código de Python guardado en un archivo `.py`, aquí se pueden guardar funciones, métodos, variables y todo lo que se ha visto hasta ahora. Además se puede importar un módulo a otro usando:
```Python
import <modulo>
```
Con esto seremos capaces de usar cualquier recurso del módulo en cuestión, aunque tambien existe una manera de importan una función en especifico de un modulo para eso se sigue la siguiente sintaxis
```Python
from <modulo> import <something>
```
 
 >Para hacer uso de las importaciones se debe usar `<modulo>.something()`
##### Paquetes
Son un conjunto de módulos, debe contener por lo menos un archivo `.py` para que Python lo entienda como paquete y no como un directorio cualquiera.

>Para crear un paquete es fundamental que el mismo contenga un archivo denominado `__init__.py` pudiéndose denominar como 'el constructor del paquete'

Dentro de un paquete puede haber otro paquete, a esto se le denomina: ==subpaquete== y para importarlo dentro de un modulo se usa lo siguiente

```Python
from Paquete.Subpaquete import <something>
```
# Manejo de Errores
Permite ejecutar el codigo sin verse interrumpido por algun error de ejecucion. Para esto se usa la siguiente sintaxis donde se crea que pueden existir ciertos errores:
```Python
try:  
    # Codigo que queremos probar  
except <Error>:  
    # Codigo a ejecutar si hay un error  
else:  
    # Codigo a ejecutar si no hay un erro  
finally:  
    # Codigo que se va a ejecutar de todos modos
```
Este bloque de código se usa para prevenir cierto tipos de errores, cada uno de estos se encuentran especificados y detallados en la documentación de Python: [Errores y Excepciones](https://docs.python.org/es/3/library/exceptions.html#built-in-exceptions)
# Pytlint
Biblioteca que analiza un código fuente e informa sobre posibles problemas de estilo o graves dentro del mismo. Para instalarlo se debe ejecutar el siguiente comando dentro de la terminal de PyCharm o cualquier otra:
```Python
pip install pylint
```

Y para hacer la verificación se tiene que ejecutar el siguiente comando dentro del directorio en donde se encuentre el archivo que se quiere inspeccionar
```Python
 pylint <archivo>.py -r y
```

Este comando devolverá un reporte sobre el análisis completo del código siguiendo el formato PEP 8.
# Unittest
Permite probar el programa y verificar si se obtienen los resultados adecuados. Es una librería integrada.

Para usar esta librería se requieren dos aspecto:
- Archivo.py
```Python
# Lógica del archivo/modulo que se desea probar
```
- Otro_Archivo.py
```Python
import unittest
import <archivo_a_probar>

class Prueba(unittest.TestCase):
	def test_<algo>(self):
		# logica del test
```
>Dentro del archivo que tiene `unittest`, se pueden hacer tantas pruebas como se quiera.
# Decoradores
Funciones que modifican el comportamiento de otras funciones. Un ejemplo de esto se puede ver en el siguiente código:
```Python
def decorador(funcion):  
    def funcion_decoradora(palabra):  
        print("Hola")  
        funcion(palabra)  
        print("chao")  
  
    return funcion_decoradora  
  
  
@decorador  
def mayúscula(texto):  
    print(texto.upper())  
  
  
@decorador  
def minúscula(texto):  
    print(texto.lower())  
  
  
mayúscula("Texto")
```

>Para decorar una función es importante que se agregue el `@` antes de la función agregando el nombre del a función decoradora creada previamente.

>Dentro de Python las funciones también pueden ser consideradas como objetos, esto se puede ya que las funciones son consideradas ciudadanos de primera clase:
```Python
def saludar(): 
    print('Hola soy una función') 

def super_funcion(funcion): 
    funcion() 

funcion = saludar  # Asignamos la función a una variable
super_funcion(funcion) 
```
# Generadores
Son un tipo de funciones que en lugar que devolve run valor determinado, lo va formando poco a poco hasta entregarlo, es decir, hay que llamar a dicho valor que la función debe devolver. Esto se usa para cuidar el espacio de memoria del ordenar, es decir, para optimizar recursos.

La forma de distinguir esta función es siguiendo la siguiente sintaxis:
```Python
def mi_funcion()
	yield <something>
```

La función generadora puede tener tantos `yield` como se requieran, no es como las funciones tradicionales que con el `return` se para la ejecución del método y devuelve lo que tenga almacenado la variable.

Para imprimir los valores que debe devolver las funciones generadores se debe usar la siguiente sintaxis:
```Python
print(next(mi_generador()))
```
Esto devolverá lo que se haya requiera hasta el primer `yield` que se encuentre dentro de la función, si se vuelve hacer llamado, devolverá lo del siguiente y así consecutivamente.

>Al imprimir el valor de la función, esta misma será capaz de recordar hasta que punto se ejecutó y devolverá el siguiente valor cuando se vuelva a llamar a la función.

```Python
def mi_generador2():  
    x = 1  
    yield x  
  
    x += 1  
    yield x  
  
    x += 1  
    yield x
  
  
g = mi_generador2()  
print(next(g))        # Devolverá 1

# Más lógica de código

print(next(g))        # Devolverá 2

# Más lógica

print(next(g))        # Devolverá 3
```

>Si la función ya no tiene más valores que devolver se caerá en un error de ejecución.
---
# Collections
Ya que es parte de una biblioteca de Python, se debe importar usando:
```Python
from collections import *
```
Tiene tuplas, diccionarios, arreglos integrados, ayudándonos a manipular los mismos.
##### Counter
Es una función de collections que permite contar las repeticiones que tiene un arreglo, string o variable. Devuelve en forma de diccionario las repeticiones que encuentre dentro de la misma.
```Python
from collections import Counter

numeros = [8, 6, 3, 1, 8, 9, 2, 5, 9, 9, 3, 8, 7, 4] 
print(Counter(numeros))

>> Counter({8: 3, 9: 3, 3: 2, 6: 1, 1: 1, 2: 1, 5: 1, 7: 1, 4: 1})
```
Dentro de counter se tienen mas funciones que se pueden usar con la misma luego de poner `.`
##### defaultdic
Tiene varias funcionalidades, pero su principal función recae en lo siguiente:
```Python
mi_dic = {'uno': 1, 'dos': 2, 'tres': 3}  
print(mi_dic['cuatro'])  

>> Error
```
En el ejemplo anterior, se observa que cuando se crea un diccionario común, y luego se trata de manipular una clave que no existe dentro del mismo, recae en un error. Ahora, usando defaultdic:
```Python
mi_dic = defaultdict(lambda: 'uno')  

print(mi_dic['cuatro'])  
print(mi_dic['cinco'])  

print(mi_dic)

>> {'cuatro': 'uno', 'cinco': 'uno'}
```
Como se muestra en el anterior ejemplo, se puede determinar un valor por default que será asignado a una clase que se trate de manipular y no esté previamente creada, evitando el error de un diccionario normal.

Sus funcionalidades son variadas, para referirse a cada una de estas se puede revisar su [documentación](https://docs.python.org/3/library/collections.html#collections.defaultdict)
##### Más funciones de Collections

| [`namedtuple()`](https://docs.python.org/3/library/collections.html#collections.namedtuple "collections.namedtuple")  | factory function for creating tuple subclasses with named fields |
| :-------------------------------------------------------------------------------------------------------------------: | ---------------------------------------------------------------- |
|          [`deque`](https://docs.python.org/3/library/collections.html#collections.deque "collections.deque")          | list-like container with fast appends and pops on either end     |
|     [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap")      | dict-like class for creating a single view of multiple mappings  |
| [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") | dict subclass that remembers the order entries were added        |
|     [`UserDict`](https://docs.python.org/3/library/collections.html#collections.UserDict "collections.UserDict")      | wrapper around dictionary objects for easier dict subclassing    |
|     [`UserList`](https://docs.python.org/3/library/collections.html#collections.UserList "collections.UserList")      | wrapper around list objects for easier list subclassing          |
|  [`UserString`](https://docs.python.org/3/library/collections.html#collections.UserString "collections.UserString")   | wrapper around string objects for easier string subclassing      |
# Fechas
Para manipular fechas o el tiempo en general, se puede usar el módulo `datetime`:
```Python
import datetime
```
Sus funciones son varias y fáciles de usar, para adquirir todo lo relacionado a este módulo, seguir la [documentación](https://docs.python.org/3.10/library/datetime.html)
# Tiempo de ejecución
Existen varios módulos y formas para determinar el tiempo de ejecución de una función, sin embargo, los más comunes, son los siguientes:
##### Módulo time
```Python
import time  
  
def prueba_for(numero):  
    lista = []  
    for num in range(1, numero + 1):  
        lista.append(num)  
    return lista  
  
  
def prueba_while(numero):  
    lista = []  
    contador = 1  
    while contador <= numero:  
        lista.append(contador)  
        contador += 1  
    return lista  
  
  
inicio = time.time()  
prueba_for(1000000)  
final = time.time()  
print(final - inicio)  
  
inicio = time.time()  
prueba_while(1000000)  
final = time.time()  
print(final - inicio)
```
>Con este modulo se va a hacer una marca de tiempo desde el inicio de sus ejecución hasta el final de la misma, luego restando el tiempo final con el inicial, se obtendrá cuánto demoró en ejecutarse una función.

##### Módulo timeit
Este módulo se lo puede usar al momento de querer hacer pruebas de ejecución en funciones que demoran muy poco tiempo en hacerlo, ya que este módulo permite ejecutar la misma función N veces según se requiera:
```Python
import timeit  
  
declaración_for = """
prueba_for(1000000)
"""

set_up_for = """
def prueba_for(numero):  
    lista = []  
    for num in range(1, numero + 1):  
        lista.append(num)  
    return lista  
"""

print(timeit.timeit(declaración_for, set_up_for, number * <numero_de_repeticiones>))

declaración_while = """
prueba_while(1000000)
"""

set_up_while = """
def prueba_while(numero):  
    lista = []  
    contador = 1  
    while contador <= numero:  
        lista.append(contador)  
        contador += 1  
    return lista  
"""

print(timeit.timeit(declaración_while, set_up_while, number * <numero_de_repeticiones>))
```
>En el ejemplo anterior se puede ver que la función `timeit` requiere de 3 parámetros: la ejecución de la función (declaración), la función (set_up) y el número de veces que se quiera repetir la ejecución de dicha función `(number * N).` Entonces, lo que hace esta función es ejecutar la declaración las veces que se le diga y devolverá cuánto tiempo se demoró en cometer dicho acto. Cabe recalcar que estos parámetros deben ser recibidos en formato `string`.

# Matemática
Para esto se puede usar el módulo incorporado en python `math`
```Python
import math
```
Este módulo tiene gran variedad de funciones del campo matemático, por lo que, antes de hacer un cálculo que requiera el uso de esta ciencia, verifica si no existe su implementación dentro del módulo verificando su [documentación](https://docs.python.org/es/3.10/library/math.html)
# Expresiones Regulares
Permite construir un patrón para verificar si existen dentro de un contexto en específico.
##### Caracteres especiales
| Caracter |      Descripción      |                       Ejemplo                       |
| :------: | :-------------------: | :-------------------------------------------------: |
|    /d    |    digito numérico    |                         0-9                         |
|    /w    | caracter alfanumérico |                      a-z y 0-9                      |
|    /s    |   espacio en blanco   |                         ` `                         |
|    /D    |      NO numérico      |                         a-z                         |
|    /W    |    NO alfanumérico    |                       signos                        |
|    /S    |   NO espacio blanco   | cualquier grupo de caracteres sin espacio en blanco |
##### Cuantificadores
| Caracter | Descripción                                                                         |
| -------- | ----------------------------------------------------------------------------------- |
| +        | Al caracter que acompañe se puede repetir N veces.                                  |
| {n}      | Al caracter que acompañe se va a repetir n veces.                                   |
| {n, m}   | Al caracter que acompañe se repetirá entre n y m veces.                             |
| *        | Es lo mismo que `+` pero este toma en cuenta al 0, es decir, que puede no aparecer. |
| ?        | El caracter aparece una vez o ninguna                                               |

---

