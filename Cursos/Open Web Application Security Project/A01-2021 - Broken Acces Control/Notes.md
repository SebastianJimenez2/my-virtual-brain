## A01: Broken Access Control
El Broken Acces control subió de A05 en 2017 a A01 en la actualidad por el hecho de que tiene más incidencia en las páginas actuales durante un estudio hecho
El control de acceso va a permitir personas, procesos incluso máquinas que tengan acceso a recursos del sistema o del SO
Hay procesos que van a ocupar ciertas características del SO
El A01 se da cuando pueden actuar fuera de sus permisos previstos
Este problema se puede dar mediante:
- Aplicaciones, por una mala configuración, cambiar URL, ataques orientadas a las APIs, entre otras
- Middleware
- Sistema Operativo
- Hardware
### Amenaza
- Evento potencial malicioso o de otro tipo
- Podría afectar significativamente a un activo  
    Va a afectar a la información o incluso a un módulo del SO.  
### Vulnerabilidad
- Es una debilidad que hace posible una amenaza
- Ejemplo: un mal diseño, errores de configuración, malas prácticas de codificación, etc...
### Ataque
- Es una acción que explota una vulnerabilidad o representa una amenaza
### Principio del menor privilegio
Cada programa y cada usuario de sistema debe operar utilizando el conjunto mínimo de privilegios necesarios para completar su trabajo
**C** --> Create  
**R** --> Read  
**U** --> Update  
**D** --> Delete
  
CRUD --> log  
logging --> log  
## Deber de View Basket
Lo primero que hice para completar el challenge fue loggearme en una cuenta en Juice Shop que ya habíamos creado previamente
![[Untitled 21.png|Untitled 21.png]]
Una vez dentro, me fuí a mi “basket”
![[Untitled 1 8.png|Untitled 1 8.png]]
La misma que como se puede observar está vacía, posteriormente se procede a poner F12 (cuando estemos dentro del basket) para abrir lo de inspeccionar de la página que no me acuerdo cómo se llama xd
![[Untitled 2 8.png|Untitled 2 8.png]]
Aquí se sigue la siguiente ruta: Application - Storage - Session Storage - Link que aparece ahí. Una vez dentro, nos van a aparecer dos llaves, una correspondiente al “bid” y otra al “ítem total”.
Según lo que entendí el valor que tiene la llave “bid” es la correspondiente a distintas canastas, y el “item total” es el precio de la canasta, entonces en este caso estos valores de las llaves se pueden cambiar a gusto del usuario, por lo que nuestro valor actual es 8:
![[Untitled 3 7.png|Untitled 3 7.png]]
Vemos como mi canasta está vacía, pero si cambio el valor de la llave “bid” por otro, ejemplo: 1, 2 o 3, y refrescamos la página, mi canasta aparecerá de la siguiente forma:
![[Untitled 4 6.png|Untitled 4 6.png]]
Como se ve, de como tenía al principio a lo que se está mostrando, me aparecieron tres productos que jamás agregué yo manualmente, por lo que asumo que si se cambia ese valor podemos ver canastas de otros usuarios registrados, pero tengo ciertas dudas que no me terminaron de cerrar:
- ¿Por qué pude cambiar este valor?
- ¿Es normal?
- ¿Qué significa en realidad este valor y las llaves?
- ¿Es mi canasta o es la de otro usuario random y me adueñé de ella?
- ¿Para qué me sirve cargarme el valor de otra canasta a mi cuenta? xd
### Bases de datos
SQL —> Structures Query Language
Se va a trabajar con base de datos, las cuales van a tener bastante información con la cual debemos trabajar.
El Query viene de consultas
RDMS —> Relational database management system
Una asociación tiene uno o más miembros