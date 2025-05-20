## Stages de desarrollo
1. Producción
2. Development
3. Testing
## Web tradicional o legado
1. HTML / CSS / JS
2. PHP
3. ASP => equivalente a PHP pero de Microsoft => (`.asp`)
4. ASP.NET => (`.aspx`)
	1.  Se construye en dos lenguajes, la mejor práctica es con C#, pero suele ser usado con `visual basic`, no es recomendado escribirlo con `visual basic .net`
>[!Important]
>ASP y ASP.net no son lo mismo, el primero se relaciona con Microsoft, ASP.NET es usado con C#
5. JSF
6. JSP
## Web moderno
1. PHP + Laravel (Framework)
2. HTML5 + CSS3 + JS EM
3. Angular 19
4. React 19
5. NodeJS 23
6. Vue
7. .NET (core)
## Bases de datos
### Relacionales
1. PostgreSQL
	1. Community => DGIP
	2. Enterprise
2. MS SQL Server
	1. **Enterprise** => Usado por Produbanco
	2. **Standard** => <mark style="background: #FFB8EBA6;">para medianas empresas o bancos</mark>, es la más popular => DGIP
	3. **Express** => Se puede usar en modo producción, su limitación es que usa 1GB de RAM, tiene limitaciones también en virtual cores, es recomendado <mark style="background: #FFB8EBA6;">para empresas o proyectos pequeños</mark>
	4. <mark style="background: #ADCCFFA6;">Developer</mark> (es igual a la versión enterprise sin necesidad de pagar licencia)
3. SQLite
	1. Viene embebido en sistemas Android
	2. No es recomendado usarse para empresas
4. MariaDB
5. MySQL
6. Oracle
### NoSQL
1. MongoDB
2. Cassandra
3. Firebase 
	1. Firestore
	2. RealtimeDB
4. Dinamo
5. Redis
6. Neo4J
# Clientes-servidores
| Cliente     | Servidor    |
| ----------- | ----------- |
| Win11       | Win2025     |
| Win10       | Win2022     |
| Win8        | Win2019     |
| Win7        | Win2016     |
| WinXP       | Win2008     |
| **Win2000** | **Win2003** |
| Win98       | WinNT4.0    |
| Win95       | WinNT3.5    |
| Win3.1      |             |
| MSDOS       |             |
## Roles del servidor
1. Web Server
2. Storage
3. Datawarehouse
4. Database
5. Active Directory
6. FTP/SFTP
7. DNS
8. DHCP
9. Correo (exchange)
# Connection string
[All database connection strings](https://www.connectionstrings.com)
>[!Important]
>Se debe conocer el puerto (1433) de SQL server y cómo generar una trusted conexión

Se puede conectar a SQL server de diferentes formas:

| Forma de conexión    | Protocolo                   |
| -------------------- | --------------------------- |
| .                    | Shared Memory (por defecto) |
| localhost            | Shared Memory (luego TCP)   |
| localhost,1433       | TCP/IP explícito            |
| localhost\SQLEXPRESS | Shared Memory o TCP/IP      |
| 127.0.0.1            | TCP/IP                      |
| 127.0.0.1,1433       | TCP/IP explícito            |
| NOMBREPC (hostname)  | TCP/IP o Named Pipes        |
# Websocket
## Protocolos de red
![[Pasted image 20250520101253.png]]
## Aplicaciones web tradicionales
Las aplicaciones web funcionaban mediante el modelo de solicitud-respuesta, en el que un cliente (navegador) enviaba una solicitud al servidor y este respondía con la información solicitada.
![[Pasted image 20250520101327.png]]
Esta arquitectura tenía limitaciones que no permitían satisfacer las demandas de los usuarios y las expectativas de interacción en tiempo real.
### Ajax
A medida que las aplicaciones web se volvieron más avanzadas y las páginas más dinámicas, surgió un nuevo modelo, llamado <mark style="background: #BBFABBA6;">Ajax</mark> (**A**synchronous **J**avaScript **A**nd **X**ML).
>[!Note]
>Con Ajax es posible realizar una solicitud HTTP y obtener la respuesta HTTP sin tener que actualizar toda la página, introduciendo a las páginas con más dinamismo.
### JQuery
jQuery es una librería de JavaScript que facilita la programación del lado del cliente en aplicaciones web. Fue muy popular porque simplificó muchas tareas comunes que antes requerían más líneas de código o que no funcionaban igual en todos los navegadores.