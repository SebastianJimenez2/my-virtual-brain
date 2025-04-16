[[Clase Extra UML]]
# Cookies
Es una pequeña pieza de datos que el **servidor envía al browser cliente.**
Con las cookies almacenadas, el browser envía la información para que así el servidor sepa quién es la que está haciendo las solicitudes.
## Funcionamiento de una Cookie
- El servidor lo genera.
- La cookie es almacenada por el navegador.
![[resources/Untitled 16.png|Untitled 16.png]]
## Recomendaciones
- La información de la cookie no debe ser predecible, es decir, deben estar cifradas para que alguien no pueda doblegar la cookie.
- No se debe enviar información vulnerable.
## Usos
- El uso de cookies mejora la experiencia de usuario del sitio web
## Cookies en PHP
- **Generar una cookie.** Define una cookie para ser enviada junto con el resto de cabeceras HTTP.
```PHP
setcookie (string $name,int $expires = 0, ...) : bool;
```
- **Acceder a la cookie.** Array asociativo con el contenido de cookies creadas.
```PHP
$_COOKIE [nombre_de_la_cookie];
```
---
# Sesiones
Una **sesión** es una variable global que es almacenada en forma de fichero de texto dentro de un directorio temporal del servidor.
## Proceso de creación de una sesión
1. Servidor crea sesión
2. Servidor asigna ID a la sesión (cada sesión tiene un ID)
3. Servidor envía ID al cliente a través de una cookie
4. La cookie, que contiene el ID de la sesión, viaja en cada solicitud realizada al servidor web
5. Cuando la cookie llega al servidor, este consulta la información asociada al ID guardado en la cookie
En el caso de que el cliente no soporte cookies, el ID es enviado en la URI (como parámetro en la cadena de consulta)
---
# JavascrZzZZzz
Es un lenguaje interpretado (no necesita de un compilador para verse lo programado). Es un lenguaje orientado a funciones.
**DOM (Document Object Model)**
- Es el código HMTL de la página subido a la página del navegador (árbol de jerarquía del HTML)
- El origen del origen es el objeto ==**window**==, el cual contiene todo el documento (que es el HTML de la página)
## Funciones
```JavaScript
function nombre(param1 ... paramN) {
	sentencias
}
```
## Funciones anónimas
```JavaScript
function (){
	alert("hola");
}
```
## Incorporar JavaScript
- **En línea**. Tiene palabras clave para llamarlo.
- **Embebido**. Se usa `<script>`
- **Externo.** Se crea un archivo .js y se inserta con src
## Manejadores de Eventos
- Todo lo que empiece con “on” es un manejadores. Hay tres formas de usar manejadores:
    - En línea
    ```JavaScript
    	<p onclick="alert('clic');"/p>
    ```
    - En memoria
    ```JavaScript
    elementoHTML.onclick = funcion-a-ejecutar();
    ```
    - Método
    ```JavaScript
    elemtoHTML.addEventListener('click', saludad, false);
    ```
## Funciones
### Funciones Flecha
```JavaScript
var <nombre_funcion> = (param1 ... paramN) => { expresion };
expresion ==> si existe más de una expresión se pone el 'return' caso contrario, no es necesario.
```
# Back-end
[[Configurar Eclipse]]
# Patrón MVC
**Controlador**. Controla el flujo de trabajo. Recibe las peticiones de un usuario.
**Modelo**. Representa a los datos.
![[resources/Untitled 1 4.png|Untitled 1 4.png]]
## Modelo MVC en arquitectura web
Llega un petición a través de HTTP, lo recibe al controlador.
![[ArquitecturaWeb.svg]]
## Modelo MVC en arquitectura java
![[PrincipiosTecnologicos-02.svg]]
**Servlet**. Objeto java que responde a las peticiones mediante el protocolo HTTP
Una dependencia también se puede usar cuando la clase de la que depende la otra se usa la instancia dentro de un método.
**HTTPServletRequest**. Representa a la petición que llega, es decir, el mensaje HTTP que llega con los parámetros, en el cuerpo por POST o en la URL si fue con get.
**HTTPServletResponse**, Método HTTP de respuesta, posee el código de estado, las cabeceras, el cuerpo, es decir, el HTML en general.
![[resources/Untitled 2 4.png|Untitled 2 4.png]]
A pesar de un archivo .jsp es una vista, como base es considerado como un servlet en ejecución.
# Persistencia
La manera en la que se guardan los datos, en este aspecto, nos vamos a enfocar en una **base de datos relacional.**
>[!Note] La debilidad de una base de datos relacional es más costoso que en una no relacional, esta son más veloces pero no poseen una estructura.

**JDBC.** Es una especificación, un documento. Este contrato ayudó a las BDD a crear librerías para que cada una de estas tenga una manera de conectarse a Java.
Con esta especificación se crean librerías que son conocidas como conectores.
El modelo es el encargado de hablar con el repositorio de datos. Este es el responsable de transferir los datos a la base de datos. Esta transferencia o conexión que tiene el modelo con el motor de base de datos es conocido como persistencia.
>[!Note] Al momento de hacer una consulta desde java, se crea una especie de capsula, en donde es ‘introducida’ la consulta, esta capsula es enviada por un ‘tubo’ al motor de la BDD. La misma cápsula es devuelta con la información requerida. La capsula es **‘Prepared Statemet’** que siempre uso.  
>   
> - **PreparedStamente** ⇒ Permite el envío de parámetros  
> - **Statement** ⇒ No permite el envío de parámetros
---
# DAO
Es un patrón de consumo de datos.
![[resources/Untitled 3 3.png|Untitled 3 3.png]]
# ACTIVE RECORD
En los métodos del modelo se mete la lógica del consumo de la BDD.
![[resources/Untitled 4 3.png|Untitled 4 3.png]]
# JPA - Java Persistence API
Es la implementación de Java para ORM. Es una especificación de Java, que es implementada para poder conectarse a la BDD.
**ORM (Object Relational Mapping)** ⇒ El objeto se mapea a una tabla de la base de datos. La clase se mapea con una clase, y los objetos de esa clase se mapean con las filas de la tabla.
Tipos de value:
- Create Table. Cada que se abre el JPA se crean las tablas automáticamente
- Drop and Create Table. Cada que se ejecuta el JPA borra todo lo que está en la BDD y recrea el esquema.
- None. No hace nada
---
# Servicios Web
Es un sistema de software diseñado para admitir la interacción interoperable de máquina a máquina a través de una red
Sin estado. El servidor responde la solicitud y corta al conexión.
La arquitectura **REST** se basa en el protocolo HTTP, cada que se mande una solicitud el servidor lo va a tomar como una solicitud nueva.
## Arquitectura REST
Recursos remotos. Páginas web o datos que tiene un sistema.
Es un estilo arquitectónica diseñado para y sobr eun sistema distribuido particular, la web.
![[resources/Untitled 5 3.png|Untitled 5 3.png]]
### Comunicación tradicional
- HTLM y .jsp y código, viven en el servidor, por lo que, el sistema web que estamos haciendo es un ==monolito==
- El cliente solo sirve como render
### Comunicación en REST
- En el servidor ya no se tiene el HTML, .jsp o código, sino que el servidor ya no es responsable de crear las UI, va a ser responsable únicamente de responder la lógica del negocio y obtener los datos de la BDD siendo pasados por el canal de comunicación hacia el otro sistema.
### Servicio Web RESTful
Un sistema web usa un recurso para consumir otro recurso de otra aplicación.
- **Recurso.** Es una entidad, la cual se almacena principalmente en un servidor y el cliente solicita el recurso utilizando los servicios RESTful. Es habitualmente un objeto de negocio.
![[resources/Untitled 6 2.png|Untitled 6 2.png]]
### Implementación en Java
**JAX-RS.** API de apoyo a la creación de Servicios Web estilo REST. Dispone de un servlet que funge como dispatcher.
Se implementa usando ==JERSEY==
==Jakson== para hacer cambios de representación de ==JAVA a JSON==
==JAXB== para hacer cambios de representación de ==JAVA a XML==
**Cambios de representación**
- **Marshalling**: de objeto Java JSON/XML
- **Unmarshalling**: de objeto JSON/XML a objeto Java
![[resources/Untitled 7 2.png|Untitled 7 2.png]]
# Manejadores de contenido
CMS sistema manejador de contenido, permite a uno o varios usuarios crear, editar y publicar contenido web.
**Hosting.** Es una empresa que tiene servidores físicos, entonces, nosotros como ingenieros en sistemas queremos tener una página web (sebas.com) y la misma se accesible en internet, por lo que, contratamos a la empresa en cuestión y ellos usan nuestros archivos para mostrar nuestra página.
**Nombres de sitios web.** Una empresa guarda y registra este nombre para que tu página sea pública, ya que ellos nos ofrecen una dirección IP la cual debe ser apuntada por el servidor hosting.