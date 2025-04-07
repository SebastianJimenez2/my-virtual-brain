# APUNTES DE CURSO DE EH3W
"The **internet** is a network of connected computers"

La web es una parte del [[internet]], misma que maneja un protocola (http) 

El internet se crea antes de la [[web]]

Tuvo que existir el internet para que luego exista la web 

http://www.example.com/2011/samples/first.html

|Nombre|¿Qué es?|
|---|---|
|1. http:// | protocol|
|2. www |host name|
|2. example.com |domain name| 
|3. /2011/samples |directory pack|
|3. first.html| document|

### JavaScript DOM (Document Object Model)
It defines the logical structure of documents and the way a document is accessed and manipulated.

>World Wide Web Consortium (3W)

A DOM object is a tree comprising a collection of node objects

### Hypertext Transpor Protocol (http)
Uses a client-server model

Resource is the target of an HTTP 

## A01: Broken Access Control

El Broken Acces control subió de A05 en 2017 a A01 en la actualidad oor el hecho de que tiene más incidencia en las páginas actuales duante un estudio hecho

El control de acceso va a pemitir personas proces e incluso máquinas que tengan acceso a recursos del sistema o del SO

Hay procesos que van a pcupar ciertas características del SO 

El A01 se da cuando puden actuar fuera de sus permisos previstos 

Este problema se puede dar mediante:
- Aplicaciones, por una mala configuracion, cambiar URL, ataques orientadas a las APIs, entre otras
- Middleware
- Sistema Operativo
- Hardware

#### Amenaza
- Evento potencial malicioso o de otro tipo
- Podría afectar significativamente a un activo
Va a afectar a la información o incluso a un módulo del SO. 

#### Vulnerabilidad
* Es una debilidad que hace posible una amenaza
* Ejemplo: un mal diseño, errores de configuración, malas prácticas de codificación, etc... 

#### Ataque
* Es una acción que explota una vulnerabilidad o represeta una amenaza 

#### Principio del menor priviligio
Cada programa y cada usuario de sistema debe operar utilizando el conjunto mínimo de privilegios necesarios para completar su trabajo

**C** --> Create
**R** --> Read
**U** --> Update
**D** --> Delete

CRUD --> log
logging --> log

## Injection
Es uno de los ataques más comunes que se están dando

SQL --> Structured Query Language --> Nos permite alamcenar, manipular e interactuar con una base de datos

RDMS --> Relational Database Management Syste --> Software que nos permiten levantar una base de datos
Como se habl de seguridad, tambipen se deb hablar de cómo hacer SQL

DDL -> Data definition language

| Commad | Description                                                                    |
| ------ | ------------------------------------------------------------------------------ |
| Create | Crea una nueva tabla, una vista de tabla o algun otro objeto de base de datos  |
| Alter  | Modifica una objeto de base de datos existente, como una tabla                 |
| Drop   | Elimina la tabla entera, la vista de una tabla o un objeto en la base de datos |

DML --> Data Manipularion language

|Command| description|
|---|---|
|Select| Permite ver, observar informacion (registros de una o mas tablas)
|Insert| Permite crear un registro, una fila en una base de datos
|Update| Modifica un registro
|Delete| Elimina un registro

CRUD viene de las operaciones especificadas prevuamente
* create --> insert
* read --> select
* update --> update
* Delete --> delete
Cuando se habla de CRUD se habla de las operaciones basicas que se deben realizar para manejar entidades u objetos que se desean crear.

Operadores de comparacion
Existen bastantes pero los que se van a usar son 
"=" --> veridica si dos valores de dos operando son iguales o no, si lo son, la condicion se muestra como verdadera
"!=" --> Verifica si los valores de dos operandos son iguales o no, si los valores no lo son, la condicion se muestra como falsa.

Cuando se ejecute un statement de SQL va a tener un proceso de parcing, entre otras muchas cosas terminando con un output una vez validada la sintaxos y es donde se puede analizar si el resultado va a ser beneficioso para una aplicacion 

Lo que hacen los atacantes es:
El supabase es una alternativa del firebase y también incluye una API dentro de una plataforma.

Para crear una tabla se usa
* Create table (nombre)
* Luego se debe poner un identificador
* Luego se crean las variables algo tipo: email, password y rol

En supabase para "anular" una linea se usa --

Por lo que si se mete un valor tipo ' OR 1 = 1; --
* Al estar al final esos carácteres, lo que siga no va a importar, por lo que puede ser que el correo esté mal, pero la condicion 1=1 siempre se va a cunplir permitiendo obtener informacion de la base de datos que ha sido creada.

Prevenciones
1. Use of prepared statements 
2. Use of properly constructed soted procedures
3. Allow-list Input Validation 
4. Escaping All User Supplied Input 

# A02

En los sistemas lo que mas importa es la información

La criptografia es el conjunto de varias técnicas

Sensitive Data Exposure 

El a02 se enfoca en la criptografia, en el masl uso de las mismas, en las fallas o ausencias 

La criptografia es el estudio de tecnicas de comunicacion segura para que tanto el que envia y recibe el mensaje tenga el derehco a entenderlo.

La encrptacion estaá dentro de la ciptografia, siendo una tecnica de las muchas existentes.

![[Criptografía.png]]

El primer fallo en este aspecto es quemar las contraseñas, IP o cosas que no deberían conocer todos

Otro fallo es la elección de un algoritmo que es malo, o faicl de vulnerar. --> Broken or Risky Crypto Algorithm 

Por otro lado se tiene la entropía, ques basicamente es cuando seleccionas un servidor que no tiene tantas capacidades cuando la aplicación pide más cosas. 

### Hashing
Hashing es un meto de la criptografia, permite convertir un texto a traves de una función hash, para obtener un resultante diferente.

La función 'hash' tiene una lógica y depende de lo que utilice para obtener el resultante que basicamente una cadena de String (código Hexadecimales) de una longitud en esecifico

MD5 (Message-Digest Algorithm 5) --> es justamente una hash fuction, orientado a la seguridad informática.

Vamos a tener un input que puede ser una cadena de texto (data input) se le pasa por el algoritmo MD5 (que va a usar una función hash que va a tranformar algo en otra cosa) obteniendo un resultante (checksum) de 32 códigos hexadecimales. Esto se usa cuando se habla en la parte de contraseñas.

Los hashes son únicos para cada input.

Ronald Rives es el creador del rsa, aportante de la criptografía y era del MIT.

El error es que si alguien pone de contraseña 'admin123' y guarda en la base de datos esa misma contraseña pero como salida de MD5, sigue sin ser 100% seguro.

Hashcat utiliza tu máquina, tu CPU o GPU, para que haga un cacking de contraseñas 

##### Comando 
```
hashcat -m 0 hashes rockyou.txt

-m 0        --> Hashcat mode: 0 is MD5
hashes      --> archivo que tiene el hash (contraseña que está hasheada)
rockyou.txt --> wordlist 
```


Un 'wordlist' es una diccionario de contraseñas, es tener un archivo donde se tenga las contraseñas mas populares e incluso filtradas de los usuarios, generalmente sirve para hacer ataques de fuerza bruta. Es decir, comparar algo e igualar hasta que se obtenga algo del diccionario.

En nuestro caso va a buscar, comparando nuestra password hasheada que es lo que un atacate pudo obtener de una filtración de información de la base de datos.

##### Rockyou.txt
Este archivo tiene bastantes contraseñas que son muy usadas a nivel mundial y contraseñas que no tienen buenas políticas de seguridad.

**En parrot**
- Menú
- Wordlist
- rockyou.txt

```
1. sudo gunzip rock.you.txt.gz --> Permite descomprimir el gz que se tenía antes.

2. ls --> debe aparecer el archivo 'rockyou.txt' sin el .gz

3. cat rockyou.txt --> aparecen bastantes contraseñas

4. cp rockyou.txt ~/Desktop --> mover algo de un lugar a otro
	=> cd ~ == cd <user>

5. echo -n "1234" | md5sum | tr -d " -" >> hashes

6. hashcat -m 0 hashes rockyou.txt
```

##### Medidas de prevencion
1. Nunca guardar este tipo de contraseñas en texto plano 
2. No seleccionar un algoritmo de hashing débil
3. Utilizar PBKDF2 (password base key derivated function 2) que además del passwor busca hacer un hash pero aplicando un 'salt' (obtener un número o strings aleatorio)

##### Scrypt, Bcrypt and ARGON2
Estos dejan de lado el SHA, MD5 y buscan tener más medidas de seguridad, además de ser más complejos. Sería bueno aplicar ARGON2.

A04
Se enfoca en las malas practicas en la parte arquitectónica.

Modelo de amenazas es útil para entender en sí la parte del A04

Ver como fluye la información, el data flow es analizando la arquitectura que se tiene

Comand weakness enumeration --> categoriza las vulnerabilidades que generalmente presenta un sistema 

CWE-209 -> Generación de errores en mensajes de información sensible. Decir que el usuario no existe está mal.
CWE-256 -> Protección no adecuada o potente respecto a las credenciales de un usuario
CWE-501 -> Violación de los límites de confianza
CWE-522 -> Insufinciencia en la protección de credenciales, para los atacantes es algo de gran interés.

![[SDLC.png]]

El testing iria vien la parte de pruebas peor tambien en la parte de aplicación, todo dependiendo del objetivo de la aplicación