Es uno de los ataques más comunes que se están dando
SQL --> Structured Query Language --> Nos permite almacenar, manipular e interactuar con una base de datos
RDMS --> Relational Database Management System --> Software que nos permiten levantar una base de datos
  
Como se habla de seguridad, también se deb hablar de cómo hacer SQL:  
DDL -> Data definition language
#### DDL
|Commad|Description|
|---|---|
|[[Create]]|Crea una nueva tabla, una vista de tabla o algun otro objeto de base|
|[[Alter]]|Modifica una objeto de base de datos existente, como una tabla|
|[[Drop]]|Elimina la tabla entera, la vista de una tabla o un objeto en la base de datos|
  
  
DML --> Data Manipulation language
#### DML
|Command|description|
|---|---|
|[[Select]]|Permite ver, observar informacion (registros de una o mas tablas)|
|[[Insert]]|Permite crear un registro, una fila en una base de datos|
|[[Update]]|Modifica un registro|
|[[Delete]]|Elimina un registro|
  
  
CRUD viene de las operaciones especificadas previamente
- create --> insert
- read --> select
- update --> update
- Delete --> delete  
    Cuando se habla de CRUD se habla de las operaciones básicas que se deben realizar para manejar entidades u objetos que se desean crear.  
    
### Operadores de comparación
Existen bastantes pero los que se van a usar son  
"=" --> verídica si dos valores de dos operando son iguales o no, si lo son, la condición se muestra como verdadera  
"!=" --> Verifica si los valores de dos operandos son iguales o no, si los valores no lo son, la condición se muestra como falsa.  
Cuando se ejecute un statement de SQL va a tener un proceso de parcing, entre otras muchas cosas terminando con un output una vez validada la sintaxis y es donde se puede analizar si el resultado va a ser beneficioso para una aplicación
### Lo que hacen los atacantes es:
El supabase es una alternativa del firebase y también incluye una API dentro de una plataforma.
Para crear una tabla se usa
- Create table (nombre)
- Luego se debe poner un identificador
- Luego se crean las variables algo tipo: email, password y rol
En supabase para "anular" una línea se usa --
Por lo que si se mete un valor tipo ' OR 1 = 1; --
- Al estar al final esos caracteres, lo que siga no va a importar, por lo que puede ser que el correo esté mal, pero la condición 1=1 siempre se va a cumplir permitiendo obtener información de la base de datos que ha sido creada.
### Prevenciones
1. Use of prepared statements
2. Use of properly constructed stored procedures
3. Allow-list Input Validation
4. Escaping All User Supplied Input