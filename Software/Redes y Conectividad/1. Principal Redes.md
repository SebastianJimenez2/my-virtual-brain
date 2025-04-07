Cuando el humano interviene, deja de ser IoT y pasa a ser telemática

### Redes de Datos
Envío y recepción de la información entre dispositivos

### Componentes
* ***Dispositivos finales.*** 
	* Permiten la interacción entre la red humana y toda la red de comunicaciones. Ejemplo: computador. En otras palabras, son los dispositivos que usamos nosotros los humanos. 
	* Una característica de estos dispositivos es que son el inicio y fin de un mensaje.
	* Lo primero para tener una conexión es disponer una tarjeta de red, técnicamente conocida como [[NIC]] (Network Interface Card), luego se debe disponer una capacidad de comunicación que es igual a la [[capacidad de conexión]] más el direccionamiento. Con esas dos cosas serás capaz de enviar y recibir datos.
   
* ***Dispositivos intermediarios.***
	* Cumplen diferentes funciones y dependiendo de esta se clasifican en diferentes categorías.
	* **Funciones:**
		1. Permiten la interconexión de los dispositivos finales a la red
		2. Permiten la interconexión de redes formando una internet working 
		3. A la vez que se permite la interconexión de redes, los paquetes de una red deben encaminarse a otra red, es decir, rutar el tráfico entre diferentes redes
		4. Permiten establecer ciertos mecanismos de seguridad en la red
	* **Clasificación:**
		* Acceso a la red (cumplen la primera función)
			* Hub
			* Access point
			* Switch multicapa por su capacidad de switching
			* Switch LAN
			* Bridge
		* Interworking (cumplen la segunda función)
			* Router
			* Router inalámbrico
			* Switch multicapa por su capacidad de routing
		* Seguridad (cumplen la tercera función)
			* Firewall

* ***Medios de comunicación***
	* Son los que se conectan directamente a la [[NIC]]
	* Son el canal por el cual se maneja el mensaje
	* Se agrupan en dos clases
		* **Medios guiados**
			* Son aquellos que conducen el mensaje através del cable (hilos metálicos, cables de cobre, fibra óptica)
			* El cable de cobre es el estrella de este medio
			* Velocidades de transmisión
				* Par trenzado UTP-STP --> 1GB/s
				* Coaxial --> 2GB/s
				* Fibra óptica --> >10GB/s
		* **Medios no guiados**
			* Son aquellos que se conducen através del aire (transmisión inalámbrica)
			* No son tan seguros, los datos viajan por el aire y en cualquier momento pueden ser interceptados.
			* Velocidad de transmisión
				* Ondas de radio --> 1MB/s
				
* Existen más componentes pero los previamente mencionados son los más comunes

![[Tipos de dispostivos.png]]

### Red punto a punto
Los dispositivos finales funcionan tanto como clientes, como servidores.

### Topologías de Red
Rayo de color rojo --> WAN también denominada conexión serial 
Linea negra contínua --> LAN
ADN azúl --> Medio inalámbrico

**Topología física.** Es una representación gráfica o un mapa visual de como se encuentran físicamente conectados los diferentes dispositivos en la red

**Topología lógica.** Todo lo que no se pueda ver fisicamente es una representación de topología lógica
* Ejemplo: direccionamiento, IP, MAC

PDU --> Protocol Dara Unit

### IPV4
Hay varios componentes que deben ingresarse al configurar IPv4 para un dispositivo final:  
- Dirección IPv4: identifica de forma exclusiva un dispositivo final en la red  
- Máscara de subred: determina la parte de la dirección de red y la parte del host para una dirección IPv4  
- Puerta de enlace predeterminada: la dirección IP de la interfaz del enrutador utilizada para comunicarse con los hosts en otra red  
- Dirección del servidor DNS: la dirección IP del servidor del Sistema de nombres de dominio (DNS)  
- La dirección del servidor DHCP (si se usa DHCP) no se configura manualmente en los dispositivos finales. Lo proporcionará un servidor DHCP cuando un dispositivo final solicite una dirección IP.

### Direcciones IP
##### Clases
32 bits  y con MAC 48 bits
Divididos en 4 octetos
Expresado en formato decimal puntiagudo

|Tipo|Rango|[[Máscara Pura]]|Formato Abreviado|
|---|---|---|---|
|A|1.0.0.0 - 127.255.255.255|255.0.0.0|/8|
|B|128.0.0.0 - 191.255.255.255|255.255.0.0|/16|
|C|192.0.0.0 - 223.255.255.255|255.255.255.0|/24|
|D|224.0.0.0 - 239.255.255.255|
|E|240.0.0.0 - 255.255.255.255|

La D se utiliza como multicasting/experimentos
Como administradores solo podemos usar los tres primeros

Dir IP = IP + MK (máscara)
Si la máscara no es adecuada para la IP no va a funcionar 

En toda dirección IP tenemos dos porciones: 
NID --> Identificador de red
HID --> Host Identifier

A. Un octeto destinado para el NID y tres octetos para el HID
B. Dos octetos destinados para el NID y dos octetos para el HID
C. Tres octetos destinados para el NID y un octeto para el HID

Cada octeto se expresa en formato binario 

Para la máscara todos aquellos octetos destinado al NID llenamos con 1 y todos los octetos destinado al HID llenamos con 0's

Las direcciones de red no se pueden asignar a un host

La direcciones IP no pueden terminar en 0

**Ping.** Enviar 4 mensajes para comprobar la conexión entre dos redes
Todo servicio está asociado un protocolo

##### Servicio Web
Protocolo asociado: http y https
	- ***HTTP***: solicitud respuesta y trabaja con distintos mensjaes: get, post, put
		- Cuando accedemos a una página internamente lo que funciona es el método get seguido de la [[URL]] (localizador de recurso uniforme)

***GET***: Para obtener datos del servidor web
***POST, PUT***: Para subir datos del servidor web
***PUT***: Cargar los recursos o el contenido en el servidor

El protocolo HTTP trabajo con el puerto 80
El protocola [[HTTPs]] trabaja con el puerto 443

TCP --> Protocolo orientado a la simulación

**Capa 1:** Capa física
**Capa 2:** Enlace de datos, se trabaja con direcciones MAC
**Capa 3:** Se indica que el destino es 192.168.57.10 cuando el paquete va del cliente 1 al 2
**Capa 4:** El puerto de destino no puede ser aleatorio en la petición.

### Topología bus
La información viaja por todo el cable a todos los dispositivos y solo lo procesa el receptor
Topología bus funciona tanto física como lógicamente.

**Ventajas**
* Fácil de instalar y mantener
* Si falla una estación, no cae la red
**Inconvenientes**
* Si se rompe el cable principal (BUS) se inutiliza la red.

### Topología anillo
Desde el punto de vista lógico es igual al bus, la único diferencia es que en el bus tiene un principio y un final, mientras que aquí se encuentra empalmados formando un anillo concéntrico

Esta topología consta con varios nodos unidos donde cada uno de esos se conecta con su adyacente. Puede ser en una sola dirección (horario o antihorario)

El token es lo que le da la dirección, es un mensajero virtual. Solo escuchan el mensaje únicamente los que están en la ruta del token
![[Topología en anillo.png]]
Si A pasa el mensaje, lo escucha B y C.

Pueden transmitir solo cuando tienen el token. El token tiene un tiempo de vida útil por cada uno de los host.

Desde el punto de físico no se comporta como anillo, se tiene un punto central que generalmente es un concentrador al que se conectan los demás equipos. Es decir, físicamente funciona como estrella.

Ventajas
* Fácil detectar si una PC se cae
Inconvenientes
* Se rompe el cable, se paraliza la red.

### Topología en estrella
Se cuenta con un punto central, en donde todos los dispositivos están conectados. Este punto central puede ser cualquier concentrador (HUB) o un conmutador (que es el ideal) dependiendo de con cuál se trabaje tendrá diferente funcionalidad.

Con un concentrador el mensaje se envía a todos los dispositivos
![[Topología en Estrella.png]]
Si se manda de A a B se enviarán 5 mensajes pero solo B lo va a procesar.

Si usamos un HUB el funcionamiento lógico es como una topología en bu y si se usa un conmutador su funcionamiento va a ser como una topología estrella.

Físicamente con un concentrador o un conmutador funciona como estrella.

**Ventajas** 
* Si se rompe un cable no se inutiliza la red
* Fácil detectar fallas
* Escalable
**Inconvenientes**
* Mas cara
* Fallo en el nodo central, la red queda inutilizada.

### Topología estrella extendida
Es la unión de varias topologías en estrella. Existe un dispositivo central que une a las otras topologías, puede ser un conmutador o un concentrador.

Una colisión se produce cuando dos mensajes se envían al mismo tiempo desde distintos conmutadores/concentradores

**Ventajas**
* El cableado es mas corto
* Extender la longitud y tamaño de la red
**Inconvenientes**
* Falla el nodo central se pierde la comunicación entre topologías.

### Topología jerárquica o en árbol
Es similar a la topología estrella extendida

Los nodos intermediarios se conectan jerárquicamente,  no existe un nodo central

Se impone un orden jerárquico en la red 
JAMÁS existiría un HUB en una topología de árbol, siempre es un switch

**Ventajas** 
* Permite cubrir áreas extensas
* Permite establecer funciones de gestión de red y réplicas de las configuraciones

### Topología en malla
Se tienen varios enlaces redundantes, lo cuál garantiza que la información llegue porque tiene varia alternativas de envío de mensaje, así si se cae un enlace no resultará un problema para la recepción del mismo.
Tiene una alta disponibilidad

Una variante de esta topología es la malla parcial, que solo ciertas rutas permiten la conexión entre dispositivos, pero no todas.

### Diferentes tipos de redes
##### Local Area Network -LAN
En este aspecto tenemos dos tipos de redes, no son las únicas, pero son las vigentes a día de hoy

**LAN**. Es una infraestructura de res que proporciona acceso a usuarios y a dispositivos finales. Permite este acceso en una área geográfica pequeña de alrededor de 10km

son administradas por una sola organización, generalmente son implementadas en un hogar. Estas redes son propiedad de una empresa o de una persona, que es el que regula todas las políticas de administración de la red.

Proporciona un ancho de banda de alta velocidad 2-100 Mbps

El ancho de anda de mide como la cantidad de datos que se puede transmitir de un punto a otro  en un intervalo de tiempo 
Ancho de banda teórico y efectico, el efectivo es el que disponemos.

##### Wide Area Network WAN
El área que abarca es de 100 a 1000 km 
LA red WAN permite conectar varias redes LAN

El ISP originalmente 
TSP proveedor de telecomunicaciones 

**Router**.- Permite la interconexión de diferentes redes

![[Tipos de Redes.png]]

LAN cableadas Ethernet (IEEE 802.3 o fibra óptica)
LAN inalámbricas WI-FI (IEEE 802.11)

Internet. Es la conexión LAN y WAN a nivel mundial que permite conectar a las personas de manera global. No es propiedad de ninguna persona, ni de ningún grupo

El ISP y TCP controlaba la infraestructura para la conexión, solo la partecita que involucra la conexión WAN, cuando tenemos una nube significa que tenemos una conexión de varias infraestructuras que nos permiten el TCP.

Las redes LAN siguen siendo independientemente controlada por cada una de las empresas.

### Intranet y Extranet
##### Intranet
* Red interna, privada
* Se la implemente dentro de una organización específicamente
* Es una red en pequeño, todos los servicio disponibles en internet: correo, web, chat, etc. podemos tenerlo también en una intranet. La diferencia es que estos servicios solo pueden ser ingresados solo por miembros de la organización o por autorización.
* Puede estar construida por distintas redes WAN y LAN 
**Ventaja**
* La seguridad de los datos, puesto  que solo las persona autorizadas pueden ingresar a servicios.

##### Extranet
* Es una intranet extendida, pero no es una intranet
* Brinda acceso seguro a las oficinas de la empresa por parte de proveedores, clientes y colaboradores.
![[Tipos de Redes pt.2.png]]

### Internet of Things (IoT)
**Capa de percepción.** Capa más baja se encuentran todos los dispositivos IoT físico. 
* Capacidad de censado y actuación. Todos los dispositivos que son sensores (obtener información del en torno con ciertos parámetro) actuador (actuar en consecuencia de los sensores)
* La principal responsabilidad es la recopilación del entorno de los datos por el dispositivo de los sensores y recopilación del entorno a través de los actuadores.

**Capa de red.** Establece conexión entre los dispositivos. Debe ser capaz de extraer información de hardware y software de los dispositivos que se encuentran en la capa de percepción.

**Gateway**. Permite la interacción independientemente del fabricante.

**Middleware.** Existen varios servidores o puede existir uno solo. Aquí es donde se almacenan los datos, pero también extrae información de valor a partir del procesamiento de datos. Generalmente usan procesos basados con if/then.
* Se almacenan y se procesan los datos.
* Si os i debe existir procesamiento en una red IoT.

**Capa de aplicaciones**. Es donde ya se generan las aplicaciones a diferentes dominios a partir de la información mandada por los sensores. Ya se puede visualizar el funcionamiento de una aplicación y su interacción. 

### Enfoque de procesamiento
Fog Computing. Todo el procesamiento que teníamos en el cloud se encuentra mas cercano a dispositivos IoT

### Internet Service Provider (ISP)
Necesitamos un servicio de ISP para conectarse a internet. O su alternativa TSP.

ISP es una compañía que proporciona toda una infraestructura necesaria tanto de hardware como de software para acceder a internet. Inicialmente solo ofrecían servicio de internet, pero con el paso del tiempo cambiaron.

**ISP de nivel uno** proporciona conexiones nacionales e internaciones con velocidades muy altas, siendo esto referencial y no fijo van de 2 a 10 GBPs.
* **Ejemplos:**
	* Level 3
	* Cogent
	* Tinet
	* Tata communications
	* Telecom Italia
	* Hurricane Electric
	* Sprint
	* AT&T Services

**ISP de nivel 2** son más pequeños y ofrecen un servicio regional. Si deben pagarles a los ISP de nivel uno para que proporcionen conexión de internet y lleven su tráfico.
* **Ejemplos**
	* Vodafone
	* Easynet
	* British Telekom
	* Coloumbus

**ISP de nivel 3** también denominados como **ISP locales**, ofrecen servicios locales, es decir, son los ISP que nosotros los usuarios finales contratamos para que nos proveen el servicio de internet, ellos pagan a los ISP de nivel dos para que lleven su tráfico y les permitan el acceso al resto del internet.
* **Ejemplos**
	* CEDIA (lo usa la U)
	* Telconet
	* Comcast
	* Deutsche Telekom
	* Verizon Communications 

Los ISP se conectan a través de [[PoP]]

![[Niveles ISP.png]]

**Autonomous System (AS).**  Es una agrupación de varias redes y dispositivos en internet que son administrados por una sola autoridad en común. Cada uno de estos sistemas tienen identificadores y son únicos a nivel mundial.

La IANA es la encargada de asignación de nombre y números en internet.

### Conexiones a Internet
#### Domésticas y oficinas pequeñas
* Tecnología [[DSL]] 
* [[Fibra Óptica]]
* [[Cable]]
* [[Datos Móviles]]
* [[Conexión por Satélite]]

#### Empresas
Las opciones son similares a las anteriores, pero aquí se necesitan una gran cantidad de Mbps

* **Líneas arrendadas dedicadas**. Circuitos reales reservados por el proveedor de servicios, conectan oficinas que están geográficamente separadas.
* **DSL**, el servicio cambia de nombre a SDSL (simétrico), la velocidad de subida es igual a la de bajada

### Redes confiables
Para que una red sea confiable se requiere:
* Tolerancia a fallos, 
* Escalabilidad
* Calidad de servicio
* Seguridad

NO TODO TRAFICO ES IGUAL ENTONCES DEBEMOS USAR CALIDAD DE SERVICIO PARA RESOLVER ESE TRÁFICO

### Protocolos y estándares de red
Los protocolos son las reglas que rigen las comunicaciones
* Codificación del mensaje
* Formato y encapsulamiento del mensaje
* Tamaño del mensaje
* Sincronización del mensaje
* Opciones de entrega del mensaje

 Los dispositivos de red que implementan **protocolos estándar abiertos**, como los de la suite TCP / IP, es que los clientes y servidores que ejecutan diferentes sistemas operativos pueden comunicarse entre sí. Los protocolos estándar abiertos facilitan la innovación y la competencia entre proveedores y entre mercados, y pueden reducir la aparición de monopolios en los mercados de redes

TCP/IP, la más utilizada

Los protocolos que están basados en estándares son los mismo que han sido avalados y comprobados.

IETF, grupo de trabajo de ingenieros de internet. Verifica que lo implementado a nivel de protocolos estén funcionales, que cumpla al pie de la letra lo que dice.

RFC, request for comments. 

### Modelo OSI
Dos tipos de modelos de redes actualmente
* Modelo OSI (open system interconnection)
	* Fue creado por la ISO 
	* Las 7 capas de este modelo se corresponde con la del modelo TCP/IP
	* La **capa de aplicación** es la más cercana al usuario final porque nos provee los servicios que usamos, también se encarga de autenticar los servicios, pero no todos. Agrega datos a una PDU.
	* La **capa de presentación** es la encargada de asignar el formato de los datos: formato, estructura, sintaxis.
	* **Capa de sesión**, es la responsable de establecer la sesión entre dos nodos de red, siempre la comunicación se va a dar entre dos nodos de red, es decir iniciar la sesión, mantener la sesión, administrar la sesión y terminar la sesión-
	* **Capa de transporte**, es responsable de proporcionar un servicio confiable extremo a extremo. Es decir, garantiza que los datos lleguen sin errores a su destino (detección de fallos, el control de flujo de información y recuperación de errores)
	* **Capa de red**, es una de las más importantes, determina la ruta que deben tomar los paquetes para llegar del origen al destino (se vale del protocolo IP y se encarga del direccionamiento IP), si la comunicación no se garantiza no hay servicio que funcione.
	* **Capa de enlace de datos**, es encargada de proporcionar transferencia confiable de datos a través del enlace, a nivel de parte física. También determinan como los dispositivos acceden al medio
		* Básicamente se encarga del direccionamiento físico (MAC)
	* **Capa física**, es encargada de todos los aspectos como: velocidad, voltajes, conectores.

	* Facto es el modelo que actualmente está siendo usado e implementado
![[Capas de datos.png]]

Los datos que intercambian son las PDU (protocol data unit) 

* En la capa física la PDU es bits (0's y 1's)
* En la capa de enlace de datos la PDU es tramas, frames, celdas
* En la capa de red la PDU es Paquetes/Datagramas, depende mucho con que protocolo se trabaje si es con el protocolo TCP se llaman paquetes si es con UDP se llama datagrama.
* En la capa de transporte la PDU se denomina segmentos
* La tres últimas capas la PDU se denominan datos

En el origen la comunicación fluye desde la capa de aplicación hasta la física

A medida que va descendiendo los datos, cada uno de las capas OSI va agregando datos en el origen. En el origen se realiza el flujo de información en **encapsulamiento** (los datos que se pueden agregar son: encabezados, información final u otro tipo de información depende de los protocolos). Va añadiendo los datos respectivos para que sean entendidos por su capa homóloga

En el destino se realiza contrariamente, la información fluye de manera ascendente des la capa física hasta la capas de aplicación, en el destino cada una de las capas extrae únicamente la parte que le corresponde, denominado como **desencapsulamiento**

![[Modelos.png]]

#### Ejemplo de encapsulamiento
Suponiendo que se desea mandar un correo. 
* El correo empieza por la capa de aplicación, en donde funcionan varios protocolos, entre los que se utilizan para correos están, POP3, IMAP (este protocolo le agrega datos al inicio de dicho mensaje).
* La capa de presentación recoge la información de la anterior capa y agrega nuevos datos al inicio del mensaje
* Luego se remite a la capa de sesión, los protocolos que trabajan a nivel de esa capa agregan datos que pertenecen a un ID de sesión.
* Luego, en la capa de transporte los datos son fraccionados en pequeños bloques y para volverlos a reensamblarlos en la capa de destino.
	* Encabezado de segmento, en donde hay un identificar para reensamblar los mensajes.
* Posteriormente toda la información se envía a la capa de red, en donde se agrega una nueva cabecera, la que provee direcciones lógicas (IP).
	* Encabezado de paquete, en donde básicamente se encuentra la información referente a la dirección IP origen y a la dirección IP destino.
* Luego, en la capa de enlace se envía una nueva cabecera que contiene el direccionamiento físico (MAC). Esta capa también contiene información final de la trama, siendo añadido un bloque de información final, que tiene un bloque de control de la información, denominado FCD (Frame Check Sequence, utilizado para verificar la integridad de la información recibida mediante CRC o checksum, mediante un algoritmo matemático que devuelve un número, el cuál se compara con la información final de la trama (lo que hay en el CRC) si está exactamente igual la información se envía, sino, de existir un cambio, la descarta).
	* Encabezado de trama.
* Finalmente toda la información se convierte en 0's y 1's siendo enviado a través del medio de comunicación que puede ser cableado.

![[Modelo de Referencia.png]]

#### Ventajas del modelo de Referencia OSI
* Asegura la interoperabilidad de la tecnología, porque este modelo proporciona estándares.
* Reduce la complejidad de la comunicación de datos, porque todo el flujo de la comunicación se divide en capas, un problema complejo se divide en partes más simples.
* Facilita el diseño modular, en cada una de las capas dependiendo de su funcionalidad entonces al implementar una topología de red se regulará el tráfico de datos.
* Estandariza la comunicación entre capas homólogas, debido a las PDU's que se manejan en cada capa
* Acelera la evolución de los dispositivos y protocolos, al estar divida entre distintas capas, cada uno de los protocolos pueden evolucionar o los nuevos pueden desarrollarse independientemente a los de otra capa. 
* Simplifica la enseñanza y aprendizaje de redes y comunicación de datos

### Modelo TCP/IP
DNS, DHCP y FTP son todos protocolos de capa de aplicación en el conjunto de protocolos TCP / IP. ARP y PPP son protocolos de capa de acceso a la red, y NAT es un protocolo de capa de Internet en el conjunto de protocolos TCP / IP.

Consta de cuatro capas: aplicación, transporte, Internet y acceso a la red. De estas cuatro capas, es la capa de Internet la responsable de enrutar los mensajes. La capa de sesión no forma parte del modelo TCP / IP, sino que forma parte del modelo OSI.

Al modelo TCP/IP se lo conoce como modelo de internet porque este modelo está implementado en la red de redes

También conocido como modelo de protocolos, porque primero se definieron los protocolos y luego las capas en los que estos iban a trabajar. Fue creada por el departamento de defensa de EEUU, cada una de las capas de este modelo abarcan varias capas del modelo iso

**Acceso a la red**, guarda relación con todo los componentes tanto físico como lógicos necesarios para establecer una conexión física 
	- Capa física
	- Capa de enlace de datos
**Internet,** tiene funciones similares a la capa de red, transporta paquetes con la finalidad de que llegue a su destino independientemente de la ruta que tome, garantizando que el paquete llegue a su destino
	- Red
**Capa de transporte**, se garantice aspectos de calidad se servicio, que sea confiable, control de flujo, corrección de errores, etc...
	- Capa de transporte
**Capa de aplicación**
	- Sesión
	- Presentación
	- Capa de aplicación 

#### Similitudes de la capa TCP/IP y OSI
* Ambas se dividen en capaz
* Ambas tienes capaz de transporte y de red similares
* El encapsulamiento se da desde la capa de aplicación hacia la física en ambos
* Ambas tienen capa de aplicación aunque incluye servicios diferentes
* Ambos tiene protocolos
* Ambos modelos deben ser conocidos por profesionales de modelos de networking

#### Diferencias
* El modelo TCP/IP tiene menos capas que el modelo OSI
* TCP/IP es de FACTO y el OSI es de JURE
* TCP/IP fue creado por el departamento de EEUU y el OSI por ISO
* TCP/IP se centra en los protocolos, OSI en la funcionalidad de cada capa
* TCP/IP generalmente se utiliza para la implementación de redes, el modelo OSI para comprender el proceso de comunicación

## Capa Física
---
La capa física está implementada en el hardware 
Los estándares de la capa física especifica todo lo que tiene que ver con señales conectores o cableados, todo lo que  podamos ver

El propósito de la capa física es transportar los bits por medios cableados 

#### Funciones de la capa física
Existen tres funciones
* Componentes Físicos
* Codificación
	* Transformar los 0's y 1's en un patrón predecible, por lo que debe ser fácil identificable para los dos (emisor-receptor)
	* Bits de control, en donde se distingue el inicio y fin de una trama (facilita las detecciones de errores), hasta la capa de enlace da datos se tiene una certeza de los datos viniendo de las capas superiores, luego al ser 0's y 1's puede ser confuso.
	* Codificación Manchester es un de las codificaciones mas antigua de FastEthernet
		* Ethernet 10 Mbps 10 BASE T
			* 10 hace referencia básicamente a la velocidad de transmisión
			* BASE hace referencia al tipo de señalización utilizada (base band, a través de este medio solo se presta un servicio)
			* T hace referencia al medio físico que se está utilizando para la transmisión (Twisted Pair, par trenzado conocido como cable UTP categoría 3, 4, 5 y STP)
		* FastEthernet 100 Mbps 100 BASE TX
			* TX hace referencia a la categoría 5, 5e o superior.
		* Gigabithernet 1000 Mbps 1000 BASE T/TX
		* Fibra óptica 100 Base FX
	* A velocidades más altas, codificaciones más complejas
* Señalización, al final lo que se envía es una señal, al final siempre los 0's y 1's se convierten en señales.
* La señales se pueden transportar de manera sincrónica y asincrónica 
	* Sincrónica. Se transmiten si una señal de reloj asociada 
		* DCE establece la señal de reloj
	* Asíncronas, dos personas se conectan a una señal UTP
	* La latencia se refiera a la cantidad de tiempo, incluido las demoras, desde emisor a receptor.
	* Capacidad de transferencia útil, desde el pinto de vista del usuario final es el más importante. Capacidad de datos utilizables, que son útiles para el usuario final que llegan a la capa de aplicación.

Goodput = Rendimiento - overhead

El cable de cobre es el medio mas utilizado por las comunicaciones de datos
* Una de sus limitaciones es la atenuación, lo que consiste en el debilitamiento de la señal. Cuanto mayor sea la distancia que recorre la señal más se va a atenuar. 

#### Cable UTP
Consta 4 pares de hilos 

![[Conexiones - Tipos de Cable.png]]

### Fibra Óptica
Se destaca por que es completamente inmune a EMI / RFI, por que ya se trabaja con pulsos de luz.
Se tiene mayor ancho de banda comparado con otros medios de comunicación porque no hay una atenuación eléctrica por lo que permite cubrir mayores distancias.
Por mayor ancho de banda permite la transmisión de datos a través de distancias mas extensas.

#### Tipos
- La fibra óptica esta constituida pro un componente principal: el núcleo. Es la parte de la fibra por donde se transmiten las señales
de luz
- La cubierta que le sigue al núcleo se llama glass cladding, por lo que al ser de vidrio funciona como espejo, es decir, los pulsos se propagan por el núcleo mientras la cubierta los refleja ayudando a mantener los pulsos dentro del núcleo.
- Finalmente se tiene un revestimiento que protege al núcleo y al cladding.

**Monomodo (SMF).** Las fibras que tienen núcleo pequeño se denominan monomodo
	- La luz entra en un solo ángulo, no tiene espacio para desviarse. Debe entrar en el núcleo en un ángulo muy preciso. Se usa láser para la transmisión.
	- La dispersión se refiere a la propagación de un pulso de luz a lo largo del tiempo, cuando se tiene una mayor perdida de la fuerza de la señal. Por lo que en este tipo de fibra se tiene menor dispersión.
**Multimodo (MMF).** Posee un tamaño importante en el núcleo
	- Poseen un ángulo elevado, por lo que puede entrar en diferente ángulos, diferentes modos. Se usan leds para la transmisión.
	- Posee mayor dispersión

Conexión dúplex puede enviar y recibir datos de forma simultánea.
- Conexión Fulldúplex, permite el tráfico bidireccional al mismo tiempo
- Conexión Halfdúplex, solo permite enviar o recibir porque solo hay un carril

En la fibra óptica se utiliza dos cables en Fulldúplex porque la luz viaja en una sola dirección.

#### Diferentes tipo de Patch Cords
El estándar que regula los colores (codificación) de cables es TIA-598.
Simple mod -> Color amarillo
Multi mod -> Color anaranjado

#### Usos 
- Se utiliza en redes de cableado para BackBone y empresariales
- Se usa en redes FTTH (fibra hasta el hogar) y redes de acceso 
- Se usa para redes de largo alcance, como redes de proveedores de servicio que usan la fibra óptica para conectar países o ciudades
- Finalmente, se usan para redes submarinas.


Para la implementación de una red inalámbrica WLAN se requiere de algunos dispositivos:
* Wireless acces point siempre debe existir, lo que hace es concentrar las señales inalámbricas de los usuarios, y gracias a este se crea una red inalámbrica, nadie puede crear una red inalámbrica sin este. Con un ethernet no se necesita eso.

El acces point es un punto central que permite crear la red inalámbrica 
1. Router
2. Switch
3. AP --> SSID es un identificador de red, service set identifier, 32 bits, todos los dispositivos deben compartir ese SSID

## Capa de enlace de datos
---
Es la única capa que se divide en dos subcapas:
* Parte que pertenece al software
* Parte que pertenece al hardware

**Capa superior LLC (control de enlace lógico)**
* Se define a nivel de software, todo lo que está de la capa de enlace para arriba corresponder al software. Define los procesos de software que proporcionan servicios a la capa de red  y a su vez con que protocolo está trabajando.

**Capa inferior MAC (control de acceso al medio)**
* Es la que tiene mas protagonismo dentro de la capa de enlace de datos, porque cumple mas funcionalidades. Está implementada a nivel de hardware, es responsable de la encapsulación de datos. 
* Encapsula el paquete que viene de la capa tres, añade la información y hace que la trama sea compatible con la red de trama que se va a usar.
* Realiza varios subprocesos para llevar a cabo el encapsulamiento de los datos:
	* *Delimitar la trama.* Identificar el inicio y el fin de una trama 
	* *Direccionamiento físico.* Proporciona la MAC origen y MAC destino.
	* *Detección de errores.* CFS - CRC (se guarda el valor de un algoritmo matemático sobre toda la trama)
* Otra de las funcionalidades es el control de acceso al medio

**Diferentes tipos de comunicación**
* *Semidúplex*. Se tiene medios compartidos, necesitando de un arbitraje. Cuando los datos fluye en una u otra dirección pero no las dos al mismo tiempo
* *Fulldúplex.* No se requiere control de acceso al medio puesto a que los medios no son compartidos.

> Cuando se está trabajando con ethernet el estándar en la capa LLC se denomina IEEE 802.2. Mientras que el estándar IEEE 802.3 describa las funciones de la capa física y MAC 

La capa LLC permite identificar el tipo con el que se está trabajando y se almacena en el campo de trama denominado tipo.

#### Acceso a los medios
La capa de enlace de datos prepara los paquete que viene de la capa de red, en donde siempre se va a encontrar un dirección IP origen y destino 

PC y Router --> Medio de transmisión: Ethernet 
Router y antena --> Fibra óptica
Router inalámbrico y laptop --> Enlace inalámbrico 

![[Acceso a los medios.png]]

La capa de enlace de datos prepara la trama de tal manera que se transmite en Ethernet va a ser diferente a que si es satelital, en cada segmento físico la trama va a ir cambiando. El paquete va a tener la misma información del origen al destino, lo único que cambia es la trama.

 ***Router***. Acepta la trama del medio de red. Luego desencapsula la trama para procesarla (determina si la trama es para él o no). Si no es para él, vuelve a encapsular el paquete en una nueva trama para cruzar el nuevo segmento.

Las tramas **SON DEPENDIENTES DEL MEDIO** y en función de ello van cambiando, mientras que los paquetes **NO SON DEPENDIENTES DEL MEDIO**, el direccionamiento lógica se va a mantener si o si.

**Factores que determinan el control de acceso al medio**
* Topología
* Si existe uso compartido o no de los medios.

#### Topologías
A nivel de la capa de enlace de datos se definen las topologías tanto como físicas como
**Topologías LAN**
- Estrella
- Estrella extendida
- Bus
- Anillo
**Topologías WAN**
* *Punto a punto,* se tiene dos puntos finales, en donde puede existir todo un abanico de conexiones en donde pueden existir varios dispositivos, pero lo que existe en un solo canal dedicado exclusivo para conectar el nodo A con el B lo que significa que no se está compartiendo el medio con otros nodos. Aquí no es necesario el control de acceso al medio. 
![[Topología WAN - Punto A Punto.png]]
* *Hub and spoke,* es una versión WAN de la topología en estrella en la que existe un sitio central que interconecta sitios remotos o sitios de sucursales mediante una conexión de enlace punto a punto. Los sitios de sucursales no pueden intercambiar datos con otros sin pasar por el punto central. Hub el punto central y spoke los que lo rodean.
![[Topología WAN - Hub&Spoke.png]]
* *Malla*, se usa tanto en lo que es LAN como en WAN, existe una malla completa y una parcial. **El internet trabaja con un tipo de topología de malla parcial**.
![[Topología WAN - Malla.png]]

#### Control de acceso al medio para medios compartidos, mecanismos
**Mecanismos de control de acceso al medio:** Técnicas que se usan para determinar las tramas que se van a colocar en el medio y como se van recibir al medio.

Para saber como se van a compartidos medios se necesitan de reglas y arbitraje.

Existen dos mecanismos de control de acceso al medio para medios compartidos:
**[[Control de acceso controlado]].** Cada nodo tiene su propio tiempo para usar el medio.
**[[Control de acceso por contienda]].** Todos los nodos compiten por el uso del medio.

![[Comparativa.png]]

#### Control de acceso al medio para medios no compartidos, mecanismos.
Los métodos que introducen un alto grado de control impiden las colisiones pero el proceso que genera tiene mucha sobrecarga, porque se tiene que cumplir más funciones.

Los métodos que introducen un bajo nivel de control tiene poca sobrecarga porque el trabajo que va a ser para arbitraje va a ser poco o casi nulo, pero hay colisiones con más frecuencias.

Estilos de trama ethernet:
- Revisado estándar IEEE 802.3ac
- Original

Estas dos no son compatibles entre sí, su mayor diferencia es la inclusión de un limitador de inicio de trama (revisado) y también se tiene un pequeño cambio en el campo tipo que incluye la longitud de la trama

**Ambiente frágil.** Mayor información de control, por lo que el encabezado y tráiler van a ser más grandes. Existe mayor sobrecarga y a su vez la mayor sobrecarga está relacionada con velocidad de transmisión más lentas.

**Ambiente controlado**. Menor control para que llegue la trama a su destino lo que se traduce en campos y tramas mas pequeñas. Se tiene una menor sobrecarga y por lo tanto velocidades de transmisión rápidas.

#### Tres métodos de transmisión de manera generalizada.
**Simplex**. Se transmite en un solo sentido (origen-destino), el destino no puede devolver datos. No sirve para las redes debido a que se necesita de una conexión bidireccional 
**Half-dúplex.** Cuando se comparte un enlace entre dos ordenadores pero solo un host puede enviar datos a la vez, se envía en una sola dirección pero considerando el tiempo, solo un host a la vez pueda enviar datos, hasta el que el host libere el canal, el otro no puede enviar, si recibir. Se necesita arbitraje de acceso.
**Full-dúplex.** Puede enviar y recibir datos al mismo tiempo, hay una comunicación bidireccional.

>**Auto-negociación**. Si se tiene dos enlaces que conectan a dos PCs y la [[NIC]] de una y trabaja a 1 GB full-dúplex y la otra a diez megabits Half-dúplex la comunicación no se puede dar, pero con la auto-negociación alguna de las NIC debe adaptarse a la otra, generalmente el de mayor velocidad se debe adaptar al velocidad mas lento y a su método de transmisión. Por lo que en este caos, el primero se adaptará el segundo PC, estableciendo la ejecución.

## **Capa de Red**
---
Es importante la conectividad y direccionamiento lógico, sin esto no funciona.
**Propósito:** Determinar la ruta que van a tomar los paquetes de un origen a un destino.

Realiza cuatro procesos básicos: 
1. *Direccionamiento*, debe tener una dirección único tanto el origen como el destino, por lo tanto, la capa de red es la encargada de poner la dirección IP que permita la conectividad entre ellos, ***se agrega un encabezado IP***
2. *Encapsulamiento*, toma la PDU que proviene de la capa de transporte y lo encapsula en una nueva PDU que viene a ser un paquete o datagrama con información adicionales, que básicamente es el segmento con el direccionamiento IP
3. *Enrutamiento*, como ya se tiene el encabezado IP, dirección de origen, de destino, empaquetado se comienza el proceso de enrutamiento, proporcionando los servicios para dirigir los paquete a su host de destino (no siempre los host están en la misma red). Función del router, determinar la ruta y dirigirlo a su destino 
4. *Desencapsulamiento*, procesa el paquete examinando la dirección de destino para verificar si está correcto, y si es correcto toma la información correspondiente (todo lo agregado) y lo pasa a la siguiente capa.
Todos los dispositivos que tienen una dirección IP se lo puede denominar como host 

##### Dirección IP
Está formada por 32 bits separados en cuatro octetos que no pueden superar el valor de 255

|Clase|DIR RED|DIR BROADCAST|Uso|Tamaño|
|---|---|---|---|---|
|A|1.0.0.0|127.255.255.255|LAN & WAN|Redes grandes|
|B|128.0.0.0|191.255.255.255|LAN & WAN|Redes medianas|
|C|192.0.0.0|223.255.255.255|LAN & WAN|Redes pequeñas|
|D|224.0.0.0|239.255.255.255|Multicasting|-|
|E|240.0.0.0|255.255.255.255|Investigación y desarrollo|-|

Primera dirección válida de una clase: DIR RED +1
Última dirección válida de una clase: DIR BROADCAST -1

* En la clase A el primer octeto es destinado para el NID y los demás para el HID
* En la clase B los dos primeros octetos son destinados para el NID y los demás para el HID
* En la clase C los tres primeros octetos son destinados para el NID y los demás para el HID

>Todos los dispositivos que pertenecen a una misma red deben tener el mismo NID

Red grande: A mayor número de host, mayor es la red. Mientras más octetos se tenga designado al HID, se va a tener más host, pero menos redes.

```
Cálculo de hosts = (2 exp bits asignados al NID) - 2
```

##### **Tipos de direcciones IP**
* *Dirección de RED*, no se puede asignar a un host, es una dirección IP que representa la red en la cuál estamos trabajando, todos los octetos destinados para el HID se llenan con 0's 
* *Dirección de HOST*, es una dirección IP válida que es asignada a la interfaz de un dispositivo
* *Dirección de BROADCAST*, todos los octetos destinados para el HID se llenan con 1's (255), se utiliza para enviar un paquete a todos los dispositivos que forman parte de la red.
* *Dirección de LOOPBACK*, es una dirección especial que todos los host usan para dirigir tráfico asimismos, al hacer un ping a esta dirección, el tráfico se dirige asimismo, se verifica que la pila de protocolos de TCP/IP esté OK. Van desde 127.0.0.0 hasta 127.255.255.255, al ser reservadas no deben ser asignadas a una dirección de host válida.

RED + HOST + BROADCAST = MISMO NID

## Formas de enviar un paquete desde un origen a uno destino
- Afectan a las direcciones ipv4 de destino

1. **Transmisión unicast.** La transmisión se da mediante el envío de un dispositivo a otro, es decir, uno a uno. Dirección IP de host válida, es decir, un paquete de unidifusión que va a un solo destinatario.
2. **Transmisión broadcast (difusión)**. Un dispositivo envía un mensaje a todos los dispositivos de red de comunicación, es decir, de uno a todos. Además todos procesan esa información. El origen es una dirección unicast y el destino una broadcast. Cada red representa un dominio de difusión
3. **Transmisión multicast**. Transmisión dirigida, no es uno a uno, ni uno a muchos, sino de uno a unos cuantos, pero no a todos. Un host manda a un conjunto de destinatarios. Se crean grupos de multidifusión. Es importante la creación de esos grupos y que la transmisión sea de uno a un grupo de host que pertenecen al mismo grupo.

### Difusión grande es cuando existen más hosts.

**Direcciones privadas.** No exponen ningún servicio al exterior. Son reutilizables. Rango de direcciones privadas establecido para cada clase

|Clase|Rango|
|---|---|
|Clase A| 10.0.0.0 - 10.255.255.255|
|Clase B|172.16.0.0 - 172.31.255.255|
|Clase C|192.168.0.0 - 192.168.255.255|

la IANA es un organismo regulador a nivel mundial, distribuye varia bloques de dirección de IP direcciones llamados [[RIRs]] (registros regionales de internet)

Protocolos de capa de red u protocolo de internet
IPv4 --> decimal --> 4 octetos --> 32 bits
IPv6 --> hexadecimal --> 8 hexets --> 128 bits

Este protocolo es sin conexión, máximo esfuerzo y de medios independientes

**IPv4 - Sin conexión.** No necesita establecer una conexión previa para enviar paquetes de datos, el emisor no notifica al emisor que va enviar un paquete o y viceversa respecto a la recepción, ninguno necesita estar conectado. El emisor envía el mensaje pero el emisor no sabe si el receptor ya tiene la carta o si la leyó y por contraparte el receptor no sabe cuándo le llegara la carta o cuando la pueda abrir. 

**IPv4 - Mejor esfuerzo.** A este servicio se le denomina servicio no confiable porque el protocola dice que yo hago mi mejor esfuerzo para enrutar el paquete lo mas rápido posible, pero no garantiza la recepción de los paquetes enviados. Pero eso no significa que sea un protocolo malo, el que no sea confiable, significa que no tiene la capacidad de administrar o recuperar paquetes no entregados o corruptos. Por lo tanto, a nivel de comunicación para no dejar esta desventaja de que no llegan los paquetes o que se perdieron existen protocolos de capa superior que realizan este trabajo, si un paquete fue perdido, existen protocolos que realizan este trabajo para recuperar los mensajes en un momento dado, pero el protocolo IP no lo hace, los protocolos que lo hacen el el TCP o UDP, que son los encargados de recuperar los mensajes (que puede o no ser)

**IPv4 - Medios independientes.** Cualquier paquete puede ser comunicado pro cualquier medio que el protocolo IP es totalmente independiente de los medios por los cuales se va a transmitir el paquete. 

LA MTU es el tamaño máximo de la PDU que puede transportar un medio, se mide en bytes. En ethernet la MTU máxima es de 1500 bytes

### Agrupamiento de dispositivos en red
##### Dominio broadcast
Conjunto de dispositivos y ordenadores que pertenecen a una misma área lógica (misma red, a nivel lógico). Cada red posee un único dominio de broadcast, pero el tamaño puede ir variando dependiendo de los hosts existentes. Mientras mas grande sea la red, mas grande va a ser el dominio de broadcast
**Problemas:**
* Mayor numero de host el trafico de red es mayor, lo que degrada el rendimiento de la red 
* Es mucho mas difícil aplicar políticas de seguridad en redes grandes que en pequeñas, por lo que se tiene temas de seguridad
* Administración de direcciones, a todos los host se les asigna direcciones IP, no es lo mismo asignar a 20 que a 1000, si no se usa servicios DHCP y se hace manualmente es complejo llevar el registro par que no exista una duplicación entre direcciones 
Para solucionar estos problemas el paso a seguir es dividir la gran red en varias subredes

##### Criterios que se deben usar para agrupar dispositivos en diferentes redes:
También se le conoce como subneting
Para dividir una red lo primero que se debe considerar unos criterios de como se van a agrupar los host, existen varios criterios comunes. 
* Una opción es agrupar los host en función de la ubicación geográfica
* Otra opción seria en función del propósito, es decir, a los usos específicos que se le va a dar a la red. 
* Finalmente se tiene el criterio definido por la propiedad, se usa una base organizacional que puede ser la base de la compañía, es decir, una estructura jerárquica

## Subnetting
Al proceso de dividir la redes grandes en pequeñas se le denomina subneting

Permiten agotar el direccionamiento de las direcciones IPv4 porque  a partir de una dirección red, se crean direcciones de subredes

>Para realizar el Subneteo únicamente se puede utilizar la porción del HID, el NID es intocable

Hay dos requerimientos para hacer el Subnetting
* En función al número de redes, cantidad de subredes necesarias ($2^n$)
	* Donde n es la cantidad de bits tomados prestados de izquierda a derecha de la parte del HID
* Cantidad de hosts necesarios ($2^m$ - 2)
	* Donde m es la cantidad de bit restantes una vez tomados los n bits del HID
 ![[Subnetting.png]]
##### **Ejemplos**
**1. Dada al dirección de red Clase C 192.168.57.0/24 se desea subnetear para crear tres subredes para la FIS de acuerdo a las siguientes especificaciones**:
	- **Estudiantes (60)**
	- **Docentes (20)**
	- **Administradores (10)**

Subredes = 3
Host mínimos = 60 (siempre es el valor más alto de las necesidades)
Clase = C
Octetos para el HID en la clase = 1
n  = 2 -->  2$^n$      = 4 subredes de las 3 necesitadas
m = 6 --> 2$^m$ - 2 = 62 host 

Se debe sacar dirección de RED
Se debe sacar direccion de BROADCAST
Se debe sacar primer direccion IP valida
Se debe sacar ultima direccion IP valida

numero mágico = se calcula en función del n bit 
n = 2

**Combinaciones:**
00 ==> no es valido
01 ==> 64
10 ==> 128
00 ==> no es valido

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|1|

Numero mágico de la segunda combinación es 64

| SR  | DIR RED        | DIR BROADCAST  | PRIMERA IP     | ULTIMA IP      |
| --- | -------------- | -------------- | -------------- | -------------- |
| 1   | 192.168.57.0   | 192.168.57.63  | 192.168.57.1   | 192.168.57.62  |
| 2   | 192.168.57.64  | 192.168.57.127 | 192.168.57.65  | 192.168.57.126 |
| 3   | 192.167.57.128 | 192.168.57.191 | 192.168.57.129 | 192.168.57.190 |
| 4   | 192.167.57.192 | 192.168.57.255 | 192.168.57.193 | 192.168.57.244 |

Mascara: 
* Tome dos bits y se tiene tres octetos inamovibles (de 8 bits cada uno) por lo que: 2 + (8 x 3) = /26 
* 255.255.255.192 (para el ultimo valor se suman los dos bits usados 128 + 64 de la primera tabla)

**2. Dada la direccion de red 220.8.7.0/24 se desea crear 5 redes con un mínimo de 12 host cada uno. Determinar la direccion de red, broadcast y las direcciones IP calidad para los host de las 5 subredes**

Subredes = 5
Host mínimos = 12
Clase = C
Octetos para el HID en la clase = 1
n  = 3 -->  2$^n$      = 8 subredes de las 5 necesitadas
m = 5 --> 2$^m$ - 2 = 30 host 

**Combinaciones:**
000 ==> no es valido
001 ==> 32
010
011
100
101
110
111 ==> no es valido

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|1

Numero mágico de la segunda combinación es 32

|SR|DIR RED|DIR BROADCAST|PRIMERA IP|ULTIMA IP|
|---|---|---|---|---|
|1|220.8.7.0|220.8.7.31|220.8.7.1|220.8.7.30|
|2|220.8.7.32|220.8.7.63|220.8.7.33|220.8.7.62|
|3|220.8.7.64|220.8.7.95|220.8.7.65|220.8.7.94|
|4|220.8.7.96|220.8.7.127|220.8.7.97|220.8.7.126|
|5|220.8.7.128|220.8.7.159|220.8.7.129|220.8.7.158|

**Mascara**: 
* Tome tres bits y se tiene tres octetos inamovibles (de 8 bits cada uno) por lo que: 3 + (8 x 3) = /27
* 255.255.255.224

**3. Dada la red 132.18.0.0/16 se nos pide que mediante Subneteo obtengamos un mínimo de 50 subredes y 1000 hosts por subred**

Subredes = 50
Host mínimos = 1000
Clase = B
Octetos para el HID en la clase = 2
n  = 6 -->  2$^n$      = 64 subredes de las 50 necesitadas
m = 10 --> 2$^m$ - 2 = 1022 host 

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|0|0|0|1|

Numero mágico de la segunda combinación es 4

|SR|DIR RED|DIR BROADCAST|PRIMERA IP|ULTIMA IP|
|---|---|---|---|---|
|1|132.18.0.0|132.18.3.255|132.18.0.1|132.18.3.254|
|2|132.18.4.0|132.18.7.255|132.18.4.1|132.18.7.254|
|3|132.18.8.0|132.18.11.255|132.18.8.1|132.18.11.254|

**Mascara**: 
* Tome seis bits y se tiene dos octetos inamovibles (de 8 bits cada uno) por lo que: 6 + (8 x 2) = /22
* 255.255.252.0

**4. Usted tiene un IP 156.233.42.56 con una máscara de subred de 7 bits, cuantos host validos y cuantas subredes son posibles?**

156.233.42.56
Clase B

n  = 7 -->  2$^n$      = 128 subredes
m = 9 --> 2$^m$ - 2 = 510 host 

**5. Una red clase B será dividida en subredes. Que mascara se deberá utilizar para obtener un total de 500 host por subred?**

Red Clase B

m = 9 --> 2$^m$ - 2 = 510
n = 7 --> $2^n$ = 128

* Tome siete bits y se tiene dos octetos inamovibles (de 8 bits cada uno) por lo que: 7 + (8 x 2) = /23
* 255.255.254.0

**6. Se tiene la red de clase B 146.201.0.0 y se la desea subnetear para el siguiente esquema de red**

**Aclaración**: Si es que solo están especificados los host y en el enunciado no es indica explícitamente que dentro de los host se debe incluir la direccion IP de la interfaz del router, se debe incluir. 

Cuando se habla de conexiones WAN se habla de una conexión punto a punto. Para una conexión **WAN se requiere siempre 2 HOSTS** porque es una conexión punto a punto

![[Ejerciocio 6 (Subnetting).png]]

Cada cable es una subred

![[Ejerciocio 6 pt.2 (Subnetting).png]]

Subredes = 6
Numero mínimo de host = 51
Clase = B
Octetos para el HID en la clase = 2
n  = 3 -->  2$^n$      = 8 subredes de las 6 necesitadas
m = 13 --> 2$^m$ - 2 = 8190 host 

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|1|

Numero mágico de la segunda combinación es 32

|SR|DIR RED|DIR BROADCAST|PRIMERA IP|ULTIMA IP|
|---|---|---|---|---|
|1|146.201.0.0|146.201.31.255|146.201.0.1|146.201.31.254|
|2|146.201.32.0|146.201.63.255|146.201.32.1|146.201.63.254|
|3|146.201.64.0|146.201.95.255|146.201.64.1|146.201.94.254|
|4|146.201.96.0|146.201.127.255|146.201.96.1|146.201.127.254|
|5|146.201.128.0|146.201.159.255|146.201.128.1|146.201.159.254|
|6|146.201.160.0|146.201.191.255|146.201.160.1|146.201.191.254|

**Mascara**: 
* Tome 3 bits y se tiene dos octetos inamovibles (de 8 bits cada uno) por lo que: 3 + (8 x 2) = /19
* 255.255.224.0

**7. Su red utiliza la direccion IP 172.30.0.0/16. Inicialmente existen 25 subredes. Con un mínimo de 1000 hosts por subred. Se proyecta un crecimiento en los próximos años de un total de 55 subredes. Que mascada de subred se deberá utilizar?**

Clase B
Octetos para el HID en la clase = 2
n  = 6 -->  2$^n$      = 64 subredes de las 55 necesitadas
m = 12--> 2$^m$ - 2 = 4094 host 

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|0|0|0|1|

* Tome 6 bits y se tiene dos octetos inamovibles (de 8 bits cada uno) por lo que: 6 + (8 x 2) = /22
* 255.255.252.0

**8. A partir de la direccion IP 172.18.71.2 y mascara 255.255.248.0. Cual es la direccion de subred y de broadcast a la que pertenece el host?**

Clase B
172.18.71.2
255.255.248.0

n = 5

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|0|0|1|

Numero mágico de la segunda combinación es 8

|SR|DIR. RED|DIR. BROADCAST|
|--|---|---|
|1|172.18.0.0|-|
|2|172.18.8.0|-|
|3|172.18.16.0|-|
|4|172.18.24.0|-|
|5|172.18.32.0|-|
|6|172.18.40.0|-|
|7|172.18.48.0|-|
|8|172.18.56.0|-|
|**9**|**172.18.64.0**| **172.18.71.255**|

**9. Se tiene una direccion IP 172.17.111.0 mascara 255.255.254.0. Cuantas subredes y cuantos host validos habrá por subred?**

255.255.**254**.0

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|0|0|0|0|1|

Clase B
Octetos para el HID en la clase = 2
n  = 7 -->  2$^n$      = 128 subredes
m = 9 --> 2$^m$ - 2 = 510 host 

**10. Cuales de las siguientes mascaras de red equivale /24**

|Tipo|Rango|[[Máscara Pura]]|Formato Abreviado|
|---|---|---|---|
|C|192.0.0.0 - 223.255.255.255|255.255.255.0|/24|

Es abreviatura pura, por lo que la respuesta es la D

**11. Se tiene la red de clase B 146.201.0.0 y se la desea subnetear para el siguiente esquema de red. Tener en cuenta que el numero de hosts que se especifica "incluye" la direccion IP de los router.**

![[Ejerciocio 11 (Subnetting).png]]

146.201.0.0
Subredes = 126
Numero mínimo de host = 126
Clase = B
Octetos para el HID en la clase = 2
n  = 7 -->  2$^n$      = 128 subredes de las 126 necesitadas
m = 9 --> 2$^m$ - 2 = 510 host 

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|0|0|0|0|1|

Numero mágico de la segunda combinación es 2

|SR|DIR RED|DIR BROADCAST|PRIMERA IP|ULTIMA IP|
|---|---|---|---|---|
|1|146.201.0.0|146.201.1.255|146.201.0.1|146.201.1.254|
|2|146.201.2.0|146.201.3.255|146.201.2.1|146.201.3.254|
|3|146.201.4.0|146.201.5.255|146.201.4.1|146.201.5.254|

* Tome 7 bits y se tiene dos octetos inamovibles (de 8 bits cada uno) por lo que: 7 + (8 x 2) = /23
* 255.255.254.0

**12. ¿Cuál de las siguientes es la dirección de difusión para una ID de red Clase B que utiliza la máscara de subred por defecto?**

Opción B, al ser clase B solo los dos primeros octetos se mantienen, mientras que los restantes se los rellena con 1.

**13. ¿Cuál es el rango de host válido del cual es parte la dirección IP 172.16.10.22 / 255.255.255.240?**

Clase B
n  = 4 -->  2$^n$      = 16 subredes

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|0|1|

Numero mágico de la segunda combinación es 16

|SR|DIR RED|DIR BROADCAST|PRIMERA IP|ULTIMA IP|
|---|---|---|---|---|
|1|172.16.10.0|172.16.10.15|172.16.10.1|172.16.10.14|
|2|172.16.10.16|172.16.10.31|172.16.10.17|172.16.10.30|

**14. ¿Cuál es la dirección de difusión (broadcast) que corresponde a la IP 10.254.255.19 / 255.255.255.248?**

255.255.255.248

Con la mascara se ve cuantos octetos se mantiene y cuantos cambian, en este caso al tener tres octetos iguales a 255 los tres primeros octetos de la direccion IP se mantienen.

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|
|0|0|0|0|1|

numero mágico 8
Clase A
n = 5

|SR| DIR RED| DIR BROADCAST|
|---|---|---|
|1 |10.254.255.0| 10.254.255.7 |
|2 |10.254.255.8 |10.254.255.15| 
|3 |10.254.255.16| 10.254.255.23| 
|4 |10.254.255.24 |10.254.255.31 |

**15. Existe la red 199.141.27.0 con una máscara de subred 255.255.255.240, identifique las direcciones de nodo válidas.**

Clase C
255.255.255.240
n totales = 28
n = 4
numero mágico = 16

|SR| DIR RED| DIR BROADCAST|
|---|---|---|
|1 |199.141.27.0| 199.141.27.15 |
|2 |199.141.27.16 |199.141.27.31| 
|3 |199.141.27.32| 199.141.27.47| 
|4 |199.141.27.48 |199.141.27.63 |
|5 |199.141.27.64 |199.141.27.80 |
|6 |199.141.27.80 |199.141.27.96 |
|7 |199.141.27.96 |199.141.27.111 |
|8 |199.141.27.112 |199.141.27.127 |
|9 |199.141.27.128 |199.141.27.143 |
|10 |199.141.27.144 |199.141.27.159 |
|11|199.141.27.160 |199.141.27.175 |
|12|199.141.27.176 |199.141.27.191 |
|13|199.141.27.192 |199.141.27.207 |
|14|199.141.27.208 |199.141.27.223 |

## VLSM
Uno de los problemas más importantes fue la crisis del direccionamiento IPv4. Por lo que se han planteado las siguientes soluciones a largo plazo:
* Subnetting, solución a corto plazo
* División de subredes de longitud variable, es lo que se conoce como VLSM 
* Enrutamiento entre dominio sin clase
* Direcciones IPv4 privadas, que son reutilizables, por lo que todo el mundo puede usar las mismas direcciones IP, sin la existencia de solapamiento o algún problema relacionado.
* Traducción de direcciones de red (NAT, network address translation)
* La solución definitiva a la escases de IPv4 fue la creación del IPv6.

Cuando se realiza Subnetting la mascara que se genera es una de longitud fija, lo que quiere decir que si se tienen 3 subredes, todas las máscaras de estas redes serán las mismas, fijas y estables. El desperdicio en esta técnica es bastante notorio. Y para no desperdiciar, se ha creado el VLSM.

VLSM significa Variable Length Subnet Mask, maximiza la eficiencia del direccionamiento porque permite desperdiciar la menor cantidad de direcciones IP's.

Maximiza la eficiencia del direccionamiento, debido a que lleva su direccionamiento en función de los host necesarios de cada subred, es decir, ya no se centra en el host mínimo de cada subred, cada subred será tratada de manera independiente en función de sus necesidades.

Las máscaras que se generan en VLSM son de longitud variable, se dividen en:
* Máscaras largas --> /32
	* Se utilizan para menor cantidad de hosts
|NID|HID|
|---|---|
||menos bits = menos hosts|
* Máscaras cortas --> /24

**1. Dada al dirección de red Clase C 192.168.57.0/24 se desea subnetear para crear tres subredes para la FIS de acuerdo a las siguientes especificaciones**:
	- **Estudiantes (60)**
	- **Docentes (20)**
	- **Administradores (10)**
>Se desperdician 96 IP's con Subnetting.

**Pasos para hacer VSLM**
1. Ordenar de mayor a menor según el numero de usuarios.
2. Calcular el número de bits para cumplir con la cantidad de host que se requiere en cada subred.
3. Establecer la máscara
4. Establecer cuál es el rango IP, para lo que se necesita calcular el número mágico
6. Calcular la direccion de red

|Subred|M|N|/mascara|Rango (#mágico)|DIR RED|DIR BROADCAST|
|---|---|---|---|---|---|---|
|Estudiantes (60)|6|2|/26|64|192.168.57.0|192.168.57.63|
|Docentes (20)|5|3|/27|32|192.168.57.64|192.168.57.95|
|Administrativos (10)|4|4|/28|16|192.168.57.96|192.167.57.111|

Se desperdician 16 direcciones IP

**2. Dada la red 192.168.0.0/24, desarrolle un esquema de direccionamiento que cumpla con los siguientes requerimientos. Use VLSM, es decir, optimice el espacio de direccionamiento tanto como sea posible**
	**- Una subred de 20 hosts para ser asignada a la VLAN de Profesores**
	**- Una subred de 80 hosts para ser asignada a la VLAN de Estudiantes**
	**- Una subred de 20 hosts para ser asignada a la VLAN de Invitados**
	**- Tres subredes de 2 hosts para ser asignada a los enlaces entre enrutadores.**

|Subred|M|N|/mascara|Rango (#mágico)|DIR RED|DIR BROADCAST|
|---|---|---|---|---|---|---|
|Estudiantes (80)|7|1|/25|128|192.168.0.0|192.168.0.127|
|Docentes (20)|5|3|/27|32|192.168.0.128|192.168.0.159|
|Invitados (20)|5|3|/27|32|192.168.0.160|192.168.0.191|
|Enrutadores (2)|2|6|/30|4|192.168.0.192|192.168.0.195|
|Enrutadores (2)|2|6|/30|4|192.168.0.196|192.168.0.199|
|Enrutadores (2)|2|6|/30|4|192.168.0.200|192.168.0.203|

|Subred|1ERA IP|ULT. IP|Máscara|
|---|---|---|---|
|Estudiantes (80)|192.168.0.1|192.168.0.126|255.255.255.128|
|Docentes (20)|192.168.0.129|192.168.0.158|255.255.255.224|
|Invitados (20)|192.168.0.161|192.168.0.190|255.255.255.224|
|Enrutadores (2)|192.168.0.193|192.168.0.194|255.255.255.252|
|Enrutadores (2)|192.168.0.197|192.168.0.198|255.255.255.252|
|Enrutadores (2)|192.168.0.201|192.168.0.202|255.255.255.252|

**3. Se tiene una red clase C cuya dirección base es 192.168.10.0. Se quiere dividir dicha red en 4 subredes. Subred Alfa con 50 host, subred Beta con 20 host, subred Gamma con 10 host, y subred Delta con 10 host. Determine una manera de asignar direcciones utilizando VLSM**

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|

|Subred|M|N|/mascara|Rango (#mágico)|DIR RED|DIR BROADCAST|
|---|---|---|---|---|---|---|
|Alfa (50)|6|2|/26|64|192.168.10.0|192.168.10.63|
|Beta (20)|5|3|/27|32|192.168.10.64|192.168.10.95|
|Gamma (10)|4|4|/28|16|192.168.10.96|192.168.10.111|
|Delta (10)|4|4|/28|16|192.168.10.112|192.168.10.127|


|Subred|1ERA IP|ULT. IP|Máscara|
|---|---|---|---|
|Alfa (50)|192.168.10.1|192.168.10.62|255.255.255.192|
|Beta (20)|192.168.10.65|192.168.10.94|255.255.255.224|
|Gamma (10)|192.168.10.97|192.168.10.110|255.255.255.240|
|Delta (10)|192.168.10.113|192.168.10.126|255.255.255.240|

**4. Dada la siguiente dirección de red: 172.25.0.0/16, divídala en subredes de las siguientes capacidades:**
	**- 2 subredes de 1000 hosts**
	**- 2000 hosts**
	**- 5 hosts**
	**- 60 hosts**
	**- 70 hosts**
	**- 15 enlaces de 2 hosts por enlace**

Clase B

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|

|2$^7$|2$^6$|2$^5$|2$^4$|2$^3$|2$^2$|2$^1$|2$^0$|
|---|---|---|---|---|---|---|---|
|128|64|32|16|8|4|2|1|

|Subred|M|NT|N|OCT|/mascara|máscara|Rango (#mágico)|
|---|---|---|---|---|---|---|---|
|(2000)|11|5|5|3|/21|255.255.248.0|8|
|(1000)|10|6|6|3|/22|255.255.252.0|4|
|(1000)|10|6|6|3|/22|255.255.252.0|4|
|(70)|7|9|1|4|/25|255.255.255.128|128|
|(60)|6|10|2|4|/26|255.255.255.192|64|
|(5)|3|13|5|4|/29|255.255.255.248|8|
|(2)|2|14|6|4|/30|255.255.255.252|4|
|(2)|2|14|6|4|/30|255.255.255.252|4|

|Subred|DIR RED|DIR BROADCAST|1ERA IP|ULT. IP|
|---|---|---|---|---|
|(2000)|172.25.0.0|172.25.7.255|172.25.0.1|172.25.7.254|
|(1000)|172.25.8.0|172.25.11.255|172.25.8.1|172.25.11.254|
|(1000)|172.25.12.0|172.25.15.255|172.25.12.1|172.25.15.254|
|(70)|172.25.16.0|172.25.16.127|172.25.16.1|172.25.16.126|
|(60)|172.25.16.128|172.25.16.191|172.25.16.129|172.25.16.190|
|(5)|172.25.16.192|172.25.16.199|172.25.16.193|172.25.16.198|
|(2)|172.25.16.200|172.25.16.203|172.25.16.201|172.25.16.202|
|(2)|172.25.16.204|172.25.16.207|172.25.16.205|172.25.16.206|

## **Dispositivos de Interconexión**
- Repetidor
- Concentrador (HUB)
- Conmutador (Switch)
- Dominio de colisión y broadcast

Dispositivos intermediarios permiten conectar dispositivos finales, estos trabajan en las tres capas del modelo OSI

![[Pasted image 20220827124908.png]]
**Capa Física** (bits) 
- Transavers (el primero). Se utiliza cuando se está trabajando con fibra óptica, utilizado para enviar y recibir señales eléctricas y ópticas entre instalaciones 
- Hub (los dos últimos)

**Cape de Enlace de Datos** (direcciones MAC)
* Puentes (el primero)
* Switch's. 
	* Switch capa 2 (mitad)
	* Switch capa 3 (último)

**Capa de Red** (direcciones IP)
* Router

Los dispositivos intermediarios se clasifican en diferentes tipos: dispositivos de acceso a la red, internetworking y seguridad.
	1. **Dispositivos de acceso a la red.** Permiten el acceso de los dispositivos finales a la red. Como por ejemplos: switch, HUB, acces point, switch multicapa y bridge.
	2. **Dispositivos de internetworking.** Interconectan redes. Como ejemplo: router, router inalámbrico y switch multicapa
	3. **Dispositivos de Seguridad.** Permiten establecer políticas para filtrar el tráfico entrante y saliente de una red. Como por ejemplo: firewall

#### **Repetidores**. 
Trabajan a nivel de la capa física. Se conocen como concentradores, porque concentran la señal que pasan por ellos.

Sirve para conectar dos segmentos de UNA MISMA RED bien sea por cable o de manera inalámbrica. Un repetidor tiene dos puertos, uno de entrada y de salida.

En el cable coaxial se llegan a usar menores cantidades de repetidores. Debido a que sus limitaciones respecto a distancia son menores a otros, tales como cables STP y UTP.

* Si estamos implementando redes de datos por cable se debe tener en consideración la extensión del cable para evitar atenuaciones. Cuando se llega al máximo de longitud, entran los repetidores que permiten extender esta longitud máxima a su doble, triple o etc...
	* **El repetidor regenera un señal que viene baja o distorsionada y la convierte en una señal más alta para transmitirla en el medio.** Si ya es una señal mala, el repetidor transmite la misma señal mala, no es capaz de mejorarla si la señal ya está excediendo su máximo en el metraje.

Se tiene dos tipos de repetidores: analógicos y digitales.
* **Analógicos**. Son independientes de la señal de entrada, es decir, pueden amplificar una señal analógica o digital en entrada, o sea son independientes de la señal de entrada.
* **Digitales**. Amplifican solo señales de entrada digital si o si.

Una de las desventajas de los repetidores es que introducen mucho retardo en la red.

En un ***dominio de broadcast*** cualquier dispositivo puede transmitir directamente a cualquier otro dispositivo sin precisar de un router.

Un ***dominio de colisiones*** es un conjunto de dispositivos que pertenecen a un mismo segmento físico.

Un repetidor tiene un solo dominio de broadcast y un solo dominio de colisión.

#### **HUB (Concentrador)**
También trabaja a nivel de la capa física. Es un repetidor multi puerto, cada puerto del HUB es un repetidor. Concentra las señales de todos los dispositivos que se encuentran conectados a él. 

* Reenvía la información a todos los puertos activos, el que procesa la información es al destinatario. No toma decisiones de envío, todo lo que llega envía a todos los puertos activos y el host destinatario lo procesa, asegurando que la información le llegue al que tiene que llegarle.
	* Este proceso de enviar todo a todos los puertos activos se conoce como flooding/inundación.

Los HUB's igual que los repetidores tiene UN solo dominio de broadcast y un solo dominio de colisiones. 
* El HUB como concentra las señales, propaga las colisiones.

Tanto el HUB como los repetidores tienen el efecto de aumentar el TAMAÑO de dominio de colisiones. El tamaño del dominio de colisiones aumenta, conforme aumenta el numero de dispositivos que pertenezcan a la red.

* Con el HUB el rendimiento se ve afectado porque solo puede transmitir un solo dispositivo en un tiempo determinado.
* Todos los dispositivos conectados a un HUB comparte el mismo ancho de banda, a más dispositivos conectados, menos ancho de banda

Se tiene dos tipos: activos y pasivos
* **Activos**. A más de concentrar las conexiones, regeneran la señal
* **Pasivos**. Solo concentran las conexiones, no las regeneran.

##### El tiempo de latencia y tiempo de retardo.
* **Tiempo de latencia.** El tiempo que se demora el paquete en llegar de origen a destino, incluyendo el tiempo de retardo
* **Tiempo de retardo.** Tiempo que se demora el paquete dentro de un dispositivo
Entre más dispositivos tenga que pasar un paquete, mayor será el tiempo de latencia y por ende el tiempo de retar, en general, un HUB activo tiene mayor tiempo de latencia y retardo que uno pasivo.

**El HUB SIEMPRE trabaja a la velocidad del dispositivo más lento.**

## **Conmutador (Switch)**
Ayudan a aliviar el dominio de colisiones que se presenten en los HUB's. Básicamente reduce las colisiones y permite una mejor utilización del ancho de banda. En el switch cada uno de los puertos puede tener un ancho de banda dedicado, lo que permite aumentar el rendimiento de la red

Con una arquitectura full dúplex se tiene una velocidad de descarga y una velocidad de subida

Permite conectar dispositivos que trabajan con distintas tecnología y velocidades. Siempre y cuando los dos tengan la misma velocidad

Cada puerto del switch es un HUB pequeño, por lo que el dominio de colisiones es uno por cada puerto activo. Con un switch capa dos, se tiene un solo dominio de broadcast, y con un switch capa tres se tiene tantos dominios de broadcast como redes se tenga.

Permiten funciones de switching tanto en capa dos como en capa tres, y routing solo en capa tres. Tanto los switch's como capa dos y capa tres se clasifican en switch's administrables y no administrables.
* **No administrable**. Es un switch que cuenta con un firewall que no nos permita al usuario interactuar con él.
* **Administrable**. Dispositivo que nos permite realizar configuraciones externas. Para acceder a estos dispositivos se puede acceder de diferentes manera, ya sea por la GUI o la CLI, sin embargo, también se le puede asignar un direccionamiento IP. **TODO SWITCH ADMINISTRABLE SE LE DEBE PODER ASIGNAR UNA DIRECCIÓN IP**
	* Con un switch administrable se pueden establecer prioridades de diferentes tipos de tráfico
	* Los switch's permiten aislar el tráfico entre aplicaciones, en otras palabras, permiten segmentar y solo los dispositivos pertenecientes a la misma VLAN tienen conexión directa, los otros podrían tener conexión si se usa un router.

Cuando se envía un paquete, el switch extrae la MAC de destino, una vez obtenida consulta al MAC address table (se genera conforme se envían tramas), localiza el puerto y lo envía. 

Cuando no se tiene datos en la MAC address table, es decir, el switch es completamente nuevo, hace un flooding y registra tanto la dirección de entrada del emisor y receptor con sus respectivos puertos.

Método de conmutación determina como un switch recibe, procesa y reenvía una trama ethernet de capa dos (porque estamos a nivel de capa dos).

**Tres métodos de switching**
* **Store and Forward Switching**
Se desea enviar una trama desde el host A hacia al host B
![[Pasted image 20220817092243.png]]
El switch cuando le llega la trama , toma toda la trama completa, es decir, este método exige la recepción de la trama completa (el tamaño máximo de un trama ethernet es de 1518 bits (sin VLAN's) 1522 (con VLAN's)) y una vez con esa trama lo almacena en un buffer

Posteriormente el switch realiza un [[cálculo (CRC)]] para verificar si ha existido o no errores en la trama. La trama cuando se envía ya tiene un tramo CRC, el switch lo vuelve a calcular para verificar que el valor sea exactamente igual al que le llegó en un inicio. Si no coinciden los valores, el switch lo descarta.
Este método se usa cuando existe la posibilidad de varias tramas corruptas o cuando se trabaja a distintas velocidades de ethernet.

Si se usa otro método de switching con distintas velocidades de ethernet no se almacenará en el buffer y se enviará rápidamente y como están trabajando a distintas velocidades las tramas se van a perder. 

Para evitar cualquier desajuste entre los dispositivos de entrada y salida el switch almacena en un buffer lo que hace que se estabilice las velocidades

La ventaja de este método es que se va atener menos tramas corruptas, todas las que pasen van a ser correctas por la comprobación que se hace. Mientras que la desventaja es que en función del tamaño de la trama va a existir un alto tiempo de latencia (porque el tiempo de latencia involucra el tiempo de retardo)

* **Método Cut Through Switching**
No espera que le llegue la trama completa, se va a usar los 14 bits de la trama y empieza a funcionar. Estos 14 bits están constituidos por el preámbulo y la direccion MAC de la trama. No se hace verificación de errores porque en los 14 bits no está contemplado el checksum, por lo que el paso de tramas corruptas es existente. Su ventaja es que realiza una rápida conmutación de tramas, se tiene menor tiempo de latencia en tramas pero es mas susceptible a errores. 

Se usa para aplicaciones informáticas de alto rendimiento, de alrededor de 10 microsegundos o menos, un ejemplo de esto podría ser aplicaciones críticas de medicina, aviación, etc...

Para decidir a donde se envían las tramas el switch usa la direccion MAC de destino, misma que se encuentra justamente en los 14 primeros bits. 

Con este método tan pronto como se reciba la direccion MAC de destino empieza a enviar la trama.

* **Método Fragment Free Switching**
Es un mix entre los dos métodos anteriores, se cree para compensar los inconvenientes de estos dos métodos. 

Cuando un trama llega el switch lo que hace es almacenar los 64 bits (tamaño mínimo de la trama) en donde se encuentran: MAC de destino, MAC de origen. tipo de ethernet y datos.

En ese método no puede revisar errores antes de enviar la trama, hace una validación pero lo hace en función de la longitud de la trama para saber si puede ser aceptada o no porque justamente se garantiza de admitir los 64 bits., si una trama tiene menos de 64 bits es una trama corrupta y se descarta inmediatamente. Existen tramas corruptas pero son menos que el método cut through, a su vez tiene mayor tiempo de latencia que el C-T y menor al S&F.

### Dominio de broadcast y colisiones
Cuando trabajamos con dispositivos de capa uno lo que se debe saber es que los mismos no segmentan ni dominios de broadcast ni de colisiones.

Los dispositivos de de capa dos segmentan dominios de colisiones, pero no de broadcast ***O NO NECESARIAMENTE*** (con VLAN's )

Los dispositivos de capa tres segmentan servicios de broadcast y colisiones.

![[Pasted image 20220817095235.png]]
Dominio de Broadcast: 1
Dominio de Colisiones: 1

![[Pasted image 20220817095540.png]]
Dominio de Broadcast: 1
Dominio de Colisiones: 1

![[Pasted image 20220817100300.png]]
Dominio de Broadcast: 2
Dominio de Colisiones: 5
![[Pasted image 20220817100447.png]]

## **VLANS (Virtual LAN)** 
Tenemos diferentes tipos de switch y la mayoría de estos permiten la creación de VLANS, no se necesita de un capa 3 necesariamente. Las VLANS solo se crean a nivel de switch, no hay ningún dispositivo que tenga esta ventaja.

##### Funcionamiento
Uno de los factores importantes en las redes es el rendimiento, y este se ve afectado por los grandes dominios de broadcast (cuando se tiene demasiados dispositivos que están formando una misma red).

La división de los grandes dominios de broadcast a dominios mas pequeños ayuda al rendimiento, se puede implementar VLANS para lograr esto, ya que las mismas son totalmente independientes, por cada una de las VLANS se tiene un dominio de broadcast específico.

Al decir virtual, significa que no se puede ver, se implementa a nivel de software. Se puede ejecutar algunos comandos para saber si está instalada o no. 

Las VLANS permiten la creación de redes lógicamente independiente dentro de una misma red física. Los host que pertenezcan a una VLAN X no tendrán a una VLAN Y, justamente por la independencia de las mismas, se va a tener una segmentación y cada uno de ellos o solo los host que pertenezcan a VLANS van a tener conexiones entre sí, salvo a que se genere un enrutamiento entre las mismas.

##### Ejemplo
Se tiene en el siguiente esquema una suposición de la FIS, en donde el primer piso corresponde a departamentos designados para docentes, estudiantes y administrativos, en el segundo piso, los laboratorios, que son usados por: docentes, estudiantes y administrativos, finalmente, en el tercer piso se tienen las aulas, destinadas específicamente para estudiantes.

![[Pasted image 20220822103311.png]]

Para una mejor perspectiva, lo que se ha hecho es reemplazar a los hub's con switch's, pero en cada uno de estos se crean las diferentes VLANS a trabajar.

![[Pasted image 20220822103316.png]]

La conexión del router y switch inicial, puede o no estar.

Cuando se crea una VLAN se da un identificador y nombre. único y exclusivo. Al momento en que se cambie este identificador, es una VLAN diferente.

El router del esquema está puesto para generar una conexión entre los VLANS2, 3 y 4

En un switch pueden coexistir varias VLANS, al rededor de 255 (dependiendo de las especificaciones del switch).

Cuando solo se crean las VLANS al red no está segmentada, es decir, los dispositivos aún tendrían conexión entre sí. Se debe decir por cuáles host están constituidas dichas VLANS.

##### **Configuraciones en VLANS**
- **Puertos o (configuración de VLAN de nivel 1).**
	- Consiste en que si todos los dispositivos están conectados en un puerto n, van a formas la VLAN
	- Una vez que pertenecen una VLAN, no pueden pertenecer a dos o más. Cada puerto de un switch se puede asignar a una sola VLAN.
- **MAC o (configuración de VLAN de nivel 2)**
	- Se hace una lista de las MAC address y se les asignan a una VLAN, debido a que la MAC es la misma, el switch la detectará y la asignara a la VLAN correspondiente (no importa la ubicación geográfica).
- **Direcciones IP o (configuración de VLAN de nivel 3)**
	- Se crean en función de dirección IP de ***ORIGEN*** de las tramas. Todos aquellos ordenadores que pertenezcan a la subred X, pertenecerán a la VLAN X. 
	- Los más recomendable a día de hoy es que cada una de las subredes le pertenezca una VLAN.
	- Existe una ligera disminución del rendimiento
- **Protocolos**
	- Todos aquellos hosts que están trabajando con el protocolo HTTP van a manejarse en la misma VLAN

##### Etiquetas de VLANS
Cada identificador único de una VLAN es denominado como VID (VLAN Identifier) que consta de 12 bits 

##### Tipos de VLANS
1. VLAN de Datos
2. VLAN predeterminada
3. VLAN Nativa
4. VLAN Administración

La  SVI debe estar asignada a una interfaz de una VLAN

##### Modos puertos del switch
* **Acces**. 
	* La principal utilidad es para conectar equipos finales, aunque más allá de conectar a un dispositivo final, lo que realmente hace este modo, es permitir y transportan el tráfico de UNA SOLA VLAN
* **Trunk** 
	* La principal utilidad es cuando se realiza la conexión entre switch o entre dispositivos de interconexión (switch o router).
	* Por estos puertos se transportan el tráfico de VARIAS VLANS, no se puede configurar un puerto en modo trunk si no se va a transportar el tráfico de 2 o más VLANS
	* Un solo cable conectan dos switch's y a través de ese cable se realizan los transportes de tráfico
	* **Protocolos**
		* ISL (Inter Switch Link). 
		* 802.1Q (dot1Q). La mayoría de configuraciones se realiza en este protocolo, ya que no pertenece a Cisco y puede usarse generalmente en cualquier switch

##### **Ventajas de las VLANS**
* Reducción de costos
* Disminución del tamaño de dominio de broadcast
* Crea dominio de broadcast
* Reducción de recursos: CPU
* Seguridad
* Flexibilidad

## **Switch**
Todos los switch's algún momento son  nuevos, cuando un switch se enciende por primera vez tiene una secuencia especifica que tiene que seguir
* Lo primero que hace es cargar un programa de auto prueba de encendido, técnicamente denominado como POST que consiste en hacer una verificación a nivel de hardware del switch.
* Segundo, se carga el programa Boot Loader, denominado técnicamente como bootstrap, que es el cargador de arranque (en un switch siempre va a existir un solo SO) y básicamente inicializa todo lo que tiene que ver por ejemplo registros de CPU
* El cargador de arranque ubica una imagen del IOS que normalmente se encuentra en la memoria flash (no volátil) o puede estar de igual manera en un servidor TFTP (un servidor de transferencia de archivos pero a la vez de interconexión). Primero se va a la memoria flash, y si no se encuentra y existe un servidor TFTP se va al servidor y carga el SO
* Una vez ejecutado, se pasa a la memoria RAM
* Luego, se busca el archivo de configuración de inicio. En el switch este archivo se llama config.txt (también encontrado en la memoria flash), en realidad, este archivo es un enlace a la configuración de inicio que se encuentra en la NVRAM y específicamente en el archivo startup-config
* Para determinar el SO que se quiere ejecutar se usa el comando Boot system

##### **Colores de las luces LED's**
* Verdes
* Ámbar
* Sin color
* Parpadeando
 1. **Led del sistema**, muestra si está recibiendo energía o funcionando correctamente. 
	 * Verde, si está funcional
	 * Apagado, significa que el sistema no no está encendido. 
	 * Ámbar, significa que esta recibiendo la alimentación pero no está funcionando correctamente (Error POST)
2. **RPS (subministro monótono de energía)**. Indica si la fuente remota está en uso
	* Verde, la alimentación de backup está conectada y funcionando
	* Apagado, o no se conecto la alimentación e backup o no existe
	* Ámbar, significa que esta en modo reserva o falla
3. **Led STAT**
	* Apagado, ningún enlace activo
	* Verde, el enlace está operativo pero sin actividad
	* Verde parpadeando, el puerto está enviando y recibiendo datos
	* Ámbar, el puerto no envía datos porque está bloqueado a nivel administrativo
	* Alternar entre verde y ámbar, el enlace está fallando
4. **Led Dúplex,** muestra el modo de transmisión (dúplex, full-dúplex)
	* Verde, puerto opera en modo full-dúplex
	* Apagado, en modo half-dúplex
5. **Led Speed**, indica a que velocidad está trabajando el puerto
	* Apagado, velocidad de 10 Mbps
	* Verde, velocidad de 100 Mbps
	* Verde parpadeando, velocidad de 1 Gbps
6. **Led PoE**, hace referencia a la tecnología del mismo nombre (Power over Ethernet)
	* Verde, significa que está habilitada la tecnología
7. **Botón MODE**, permite cambiar entre los diferentes estados, si se presiona por más de 15 segundos hace que se reinicie el dispositivo con los valores de fábrica.

##### **Modos de configuración del switch**
Se puede conectar al IOS de manera local y de manera remota. Para conectarse de manera local, existe un cable denominado cable de consola. Si se quiere conectar de manera remota se tiene que levantar el servicio de manera remota, estos servicios son: telnet o SSH.

Como administradores no se debe ingresar mediante la interfaz gráfica, sino a través del CLI (command line interface)

El primer modo con el que nos vamos a encontrar es el de 
* EXEC Usuario que usa el identificador: "nombre-del-switch >"
* EXEC Privilegiado que usa el identificador: "nombre-del-switch #"
* EXEC Configuración Global que usa el identificador: "nombre-del-switch (config)#"

Para pasar:
* De Usuario a Privilegiado se usa el comando: enable
* De privilegiado a Configuración Global se usa el comando: configure terminal

Para salir:
* Se puede usar un comando en común, denominado "exit"
* De Configuración Global a Privilegia se usa los comandos: Ctrl Z o end
* De privilegiado a Usuario se usa el comando: disable

**EXEC Usuario**. Se pueden ejecutar comandos de monitoreo peo muy básicos, estos comandos no permiten cambiar las configuraciones del dispositivo, cuando se está en este modo se está en modo de LECTURA
**EXEC Privilegia**. Se pueden realizar configuraciones (muy pocas), lo que más permite este modo es la verificación de las configuraciones, usando el comando show, en otras palabras, permite una visualización general sobre las configuraciones.
**EXEC Configuración Global.** Aquí se configura todo lo que se necesite en el switch

Para ingresar a la interfaz del router, se dice ejecutar el comando: *interface fa0/1*, en esta ocasión se entra a un **modo de configuración específico**

Con el comando *IP route*, se ingresa a un modo de configuración específico que es de enrutamiento

## Acceso al switch
* **Puerto de consola.** Puerto de administración que proporciona acceso fuera de banda a los dispositivos (se refiere al acceso mediante un canal de administración dedicado que se utiliza únicamente para el mantenimiento del dispositivo), es decir, este puerto es específico para configuración. Casi siempre es de color celestre.
	* Cuando no tiene ninguna configuración previa en un switch, si o sí se usa el puerto de consola. No hay manera de acceder al IOS del switch sin usar el puerto de consola.
	* Cuando no se tiene servicios de red levantados igual se usa este puerto, caso contrario, podemos usar telnet o SSH.
	* Como administrador puedo tener configurado, operativo y funcional a un switch, pero por A o B no funciona y fallaron los servicios de red configurados, y no se tiene acceso ni por telnet ni por SSH, deley se debe acceder por el puerto de consola, de lo contrario, no podremos ingresar.
	* Se debe estar in situ para lograr el acceso a switch mediante este puerto, porque necesita de un cable, por lo tanto, el acceso es de forma local.
	* **Cable de consola o roll-over.** Es de color celeste.
		* *A nivel de hardware*, se conecta a un extremo en el puerto RJ45 (en la parte de atrás del switch) y el otro extremo termina en un puerto denominado DB-9 o puerto serial.
		* *A nivel de software*, en el ordenador del administrador se necesita ejecutar un software denominado "Emulador de terminal" (cualquiera que permita emular una terminal, como puede ser PuTTY). Los parámetros que hay que configurar son:
			* *Baud rate*, velocidad con la que se va a configurar, debe ser de 9600 (pre-definido)
			* *Data bits*, el valor es 8
			* *Paridad*, ninguna
			* *Stop bits*, el valor es 1
			* *Flow control*, ninguno.
		   Cuando se da "OK" y si todo está configurado adecuadamente, ingresamos directamente al modo de EXEC usuario del switch.
		* Se tienen distintos accesos del cable:

![[Cables del switch.png]]

* **Telnet o SSH.** Son servicios de red que permiten el acceso de manera remota. Los protocolos de estos servicios tienen el mismo nombre. Independientemente de si se usa SSH o telnet, es importarte que el dispositivo cuente con una dirección IP y máscara. En el switch estos dos aspectos están asociadas a un SVI (switch virtual interface) y a la vez esta está ligada a una interfaz de una VLAN que esté creada 
	* En promedio las líneas VTY en un switch cisco es 16, pero generalmente, se configuran 5, para acceder a estas líneas, se usa el comando 'line vty (rango)'. A cada una de estas líneas se debe signar una contraseña, con el comando 'password (texto)'
	* Se debe habilitar la autenticación con el comando 'login'
![[Telnet.png]]

* **SSH**
SSH es un servicio pero también es un protocolo (secure share), proporciona un inicio de sesión remoto al igual que telnet, pero con este servicio todo va encriptado. Proporciona una autenticación de contraseña más potente (encriptación) respecto a telnet.

![[SSH.png]]

**1er paso - Generar una clave RSA.** Se genera  a través de dos parámetros:
* Nombre de dominio al switch (algo.algo)
	* ip domain-name 'dominio'
* Nombre de switch (SwAlgo)
	* hostname 'nombre'
* Generar el rsa
	* crypto key generate rsa
		* un mensaje del tamaño de bits aparecerá, se puede cambiar o no, en cada IOS del switch existen diferentes tamaños
**2do paso - Especificar un usuario y un password**
* username 'usuario' secret 'contraseña
**3er paso - Configurar líneas vty**
* line vty 'rango'
**4to paso - Permitir el tráfico entrante del ssh** (exclusivamente por esas líneas se va a exportar el tráfico de ssh)
* transport input ssh
* transport input telnet
* transport input none
* transport input all (todos los protocolos, ya sea ssh o telnet)
**5to paso - Autenticar el password**
* login local (autentica el password y usuario)
**6to paso - Salir**
* exit
**7to paso - Establecer versión de ssh**
* ip ssh versión 2 (última versión)
**8avo paso - Salir**
**9no paso - PC a switch**
* ssh -l 'usuario' 'IP del switch'
* Ingresar el password

## Enrutamiento
Se el conoce como encaminamiento, ruteo o routing, consiste básicamente en encaminar paquetes entre diferentes redes (dos o más). El enrutamiento se puede implementar tanto en un router como en un switch capa tres. 

Usa el protocolo IP, el cual determina el camino, una vez determinado, redirecciona esos paquetes hasta alcanzar dicho destino, a este proceso de lo conoce como enrutamiento 

Misma red local - Envío directo

Gateway, puerta de enlace o pasarela permite redireccionar los paquetes de manera indirecta, siendo un dispositivo de internet working (router, Sw3) o también un ordenar (solo si se lo prepara). Su característica importante es que tiene que estar conectado al menos a dos redes para que pueda redirigir los paquetes (conocido como forwarding)

**Gateway Predeterminado.** Es el que se encuentra directamente conectado a un segmento de red local

Cuando se envía un paquete se extrae la dirección de red del destino.

Cada router tiene su tabla de enrutamiento, nosotros como administradores debemos configurar dicha tabla. En esta tabla van a a existir redes directamente conectadas y redes remotas (redes que no alcanza).

**Redes directamente conectadas a RA:** X, Y
**Redes remotas a RA:** Z
![[Ejemplo - Redes directamente conectadas y remotas.png]]

Cuando una red está directamente conectada no necesita de un gateway. Mientras que si es una remota necesariamente se debe especificar un gateway por el cuál se va a alcanzar dicha red.

![[Ejemplo de tabla de enrutamiento.png]]
**Redes directamente conectadas:**
1. Configurar las interfaces
	1. interface fa0/0
	2. ip address (ip) (mk)
2. Levantar las interfaces
	1. no shutdown

**Redes indirectamente conectadas:**
1. Conf global
	1. Configurar una ruta estática (una por cada red indirecta)
	2. Ruta estática - ip route (DIR RED) (MK) (GW) 

**Verificar la tabla:** 
1. show ip route 
	1. s - estáticas
	2. c - directamente conectadas

### Enrutamiento Estático
Aconsejable usar en redes pequeñas

### Enrutamiento Dinámico
Tener el conocimiento de los protocolos del direccionamiento dinámico con el fin de que ellos hagan el trabajo por nosotros, se usa en redes grandes.

### Enrutamiento - Ruta estática por defecto (s*)
A medida que la red crece y se interconecta, las tablas se hacen más largas y complejas porque deben estar presentes todas las entradas a todas la redes que se desean alcanzar

Generalmente, las tablas son largas porque existe redundancia.

**¿Qué significa redundancia?** - Tener el mismo gateway para alcanzar varias redes o en otras palabas, cuando se tiene varias entradas alcanzadas por un mismo gateway. Para enfrentar estos problemas se tiene varia soluciones:
* Si se trabaja con enrutamiento estático, se usa rutas estáticas por defecto
* Enrutamiento dinámico (trabajo realizado por los protocolos de enrutamiento)

##### **Nomenclatura de la ruta estática por defecto**
* **cualquier red:** 0.0.0.0 --> cualquier red 
* **cualquier máscara:** 0.0.0.0 --> cualquier máscara
* **gateway:** gateway para alcanzar varias redes y evitar redundancia 
* **comando:** ip route 0.0.0.0 0.0.0.0 -gateway-

La rutas por defecto se utiliza cuando se está trabajando con enrutamiento estático, mientras que, tenemos otra alternativa que es el enrutamiento dinámico. 

![[Ruta estática por defecto.png]]
* En la parte derecha del R1 se tiene una red interna
* En la parte izquierda del R1 se tiene la conexión a internet
* El R1 es lo que nos dio nuestro ISP, más conocido como router de borde, cuando se trabaja con este tipo de router, se debe trabajar con ruta estática por defecto.

**Red Stub.** Red que tiene un único punto de entrada y salida hacia las direcciones externas. El único punto de entrada es el R y el único punto de salida es el 

##### **Ejemplo**:
* **Desde el punto de vista de R1**
![[Ejemplo de ruta estática por defecto.png]]

### Conexiones WAN
Las conexiones WAN se usan para comunicaciones de larga distancias, se pueden tener varias redes LAN. Para realizar una conexión entre redes LAN debemos contratar servicio de un proveedor de servicios (ICP) para tener comunicación 

Se las conoce igual como conexiones seriales, porque las transmisiones son seriales. Las conexiones WAN son conexione punto a punto porque de un extremo se tiene a un router de borde que se va a conectar y harpa de frente a distintas LAN a interconectar.

También se les conoce como conexiones o líneas arrendadas, porque son arrendadas a una compañía prestadora de servicios, puede ser un ICP o un TCP (proveedor de servicios de telecomunicaciones).

Existen dos situaciones en donde se poden usar una conexión WAN:
* Interconectar redes LAN dentro de una red empresarial
* Para conectar redes LAN a redes WAN

Nosotros tenemos nuestra red LAN y se conecta al proveedor de servicios a través de una conexión WAN.

Una conexión serial se realiza entre dos equipos, en un extremo un equipo se denomina como [[DTE]] (equipo terminal de datos) y el otro extremo es [[DCE]] (equipo de comunicación de datos). Cada uno debe trabajar con un perfil.

En cada conexión WAN debe ser identificado el DCE y el DTE. Solo se establece la sincronización en aquel que esté trabajando cómo DCE.

El conector hembra se conecta la interfaz DCE, mientras que el macho a la interfaz DTE

> **Para poner un default gateway al switch: 'ip default-gateway  (gateway-del-router)'**

### Enrutamiento Inter-VLAN
Se usa una interfaz para cada VLAN
1. En el router
	1. Se selecciona la interfaz
	2. Encapsulamiento con identificador de la VLAN
	3. ip address
2. En el switch
	1. Selecciona la interfaz conectada al router
	2. Acceso troncal
	3. Permitir el tráfico de todas las VLAN's
3. En los dispositivos finales
	1. Asignar IP
	2. Asignar máscara
	3. Asignar gateway, el cuál viene a ser la dirección IP de la subinterfaz creada.
# **Proyecto**
Tres universidades:

![[Proyecto.png]]