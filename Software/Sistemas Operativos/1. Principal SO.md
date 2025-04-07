### Sistema operativo
* Es el software que se sitúa entre la máquina y los programas ([[Jerarquía]])
* Gestiona los tres recursos fundamentales de un computador (la parte hardware), que son:
1. El [[Procesador]] o CPU
2. La memoria principal
3. Los dispositivos de E/S

### Núcleo del Sistema Operativo
* El núcleo del sistema operativo, también conocido por la terminología Kernel, es la parte más esencial del SO. Es la parte del código del SO que se ejecuta en [[Modo privilegiado]] del procesador
* Un error de programación en el núcleo resulta en un error fatal del cual el sistema solo puede recuperarse mediante el reinicio del sistema. A tal error fatal también se le conoce en los SO UNIX por Kernel panic y en los SO Windows por el nombre de pantallazo azul

### Kernel del Sistema Operativo
* La parte mas importante de un sistema operativo es el Kernel o núcleo, que se encarga de facilitar a las distintas aplicaciones de acceso seguro al hardware del sistema informático
* Puesto a que hay muchas aplicaciones y el acceso al hardware es limitado, el Kernel decide también qué aplicación podría hacer uso de un dispositivo de hardware y durante cuánto tiempo

### Utilidades del Sistema Operativo
* Abstrae el hardware
* Proporciona una biblioteca de métodos a las aplicaciones de usuario usados por los programadores
* Gestiona los recursos de manera equitativa
* Debe consumir el mínimo de recursos
* Lanzador de aplicaciones de usuario

### A nivel de usuario
* El usuario de las aplicaciones, no está preocupado de los detalles de hardware del computador
* El usuario final ve a un sistema de computación en términos de un conjunto de aplicaciones

### A nivel de programador
* Si el desarrollador de aplicaciones debiera programa también el conjunto de instrucciones de máquina para controlar el hardware el trabajo sería extremadamente complejo
* El SO provee un conjunto de programas de sistema que permite la abstracción de esta tarea a través de utilitarios o librerías de programación
* El SO contiene las funciones que asisten a la creación de un programa, la administración de archivos y el control de los dispositivos I/O
* Por lo tanto el SO es la colección más importante de programas del sistema.

En conclusión, el SO oculta los detalles de HW al usuario y provee de una intrfaz mas conveniente para utilizar el computador

### Evolución de un SO
Un SO evoluciona por lo siguiente:
- Nuevos tipos de hardware
- Nuevos servicios
- Mejoras en el SO

### Tipos de SO
*Según cuántas aplicaciones pueda ejecutar a la vez:*
1. ***Monoprogramables***
* En un determinado instante de tiempo, solo hay un único proceso en ejecución que monopoliza todos los recursos del sistema Ej.: DOS, BeOS
2. ***Multiprogramables***
* Permite ejecutar múltiples procesos en un único procesador
* Se tienen varios programas cargados simultáneamente en la memoria, así que el SO debe controlar los accesos y los pesacios de la misma.
* Tienen mecanismos de protección del espacio de memoria (el SO impide que una aplicación acceda al espacio de memoria de otra)
* 
**Características**
* *Multiusuario.-* Múltiples usuarios trabajando simultáneamente
* *Multiprocesamiento.-* soporta mas de un procesador y hace uso de todos ellos
* *Tiempo real.-* Intenta garantizar que determinadas tareas se ejecuten en un plazo de tiempo específico
* *Distribuido.-* Permite la ejecución de múltiples proceso en diferentes máquinas comunicadas por un enlace de red

3. ***Según cómo se presta el servicio***
	1. Sistemas operativos para servidor
	2. Sistemas operativos para computador personal
	3. Sistemas operativos en tiempo real
	4. Sistemas operativos embarcados/integrados/"embebidos"
	5. Sistemas operativos web

4. ***Según la cantidad de funcionalidad que se implementan en su núcleo***
	1. ***Monolíticos***. Implementan en el núcleo: la planificación de procesos, la administración de la memoria principal, la administración de ficheros y la gestión de los dispositivos de E/S
	2. ***Micronúcleos***. Núcleo implementa únicamente: planificación de procesos, mecanismo de comunicación entre procesos y gestión de interrupciones. Los demás componentes se ejecutan fuera del espacio del núcleo del SO
	3. ***Híbrido***. Usa conceptos de arquitectura del diseño monolítico y de micronúcleo.

### Sistemas operativos para servidor
1. Windows Server
2. Debian
3. Red Hat
4. FreeBSD
5. Debian
6. Fedora

### Sistemas operativos para computador
1. Microsoft Windows
2. OS X
3. GNU / Linux
4. Chrome OS

### Sistemas operativos para dispositivos móviles
1. Apple IOS
2. Google Android
3. Windows Phone

### Arquitectura de Windows
En el ***modo Kernel*** se tiene los siguientes componentes principales:
* **Executive**. Contiene los servicios de Kernel del SO
* **Kernel**: El núcleo o Kernel es la parte central de un SO y es el que se encarga de realizar toda la comunicación segura entre el software y el hardware del computador. En Windows Kernel es NT
* **Hardware abstraction layer (HAL)**. Aísla al SO de las diferencias de hardware

En el ***modo usuario*** se soportan 4 tipo de procesos:
* **Procesos del sistema**. Administración de sesión, autenticación
* **Procesos de servicio**. Servicios que trabajan con los controladores de dispositivos
* **Aplicaciones**. .exe y .dll
* **Subsistemas de ambiente**. Llamadas a procedimientos que no son Windows.

### Distribuciones GNU/Linux
Es una distribución de software basada en el núcleo GNU/Linux que incluye determinados paquetes para satisfacer las necesidades de un grupo específico de usuarios, dando así origen a ediciones domésticas, empresariales y para servidores.

### Arquitectura de Linux
* *Señales*. Utilizadas por el Kernel para llamar a los procesos
* *Llamadas al sistemas*. Utilizadas por los procesos para solicitar un servicio específico del Kernel
* *Programador de procesos*. Prueba, administra y programa procesos
* *Memoria virtual.* Asigna memoria virtual para los procesos
* *Sistema de archivos*. Namespace para archivos y directores
* *Protocolo de red*. Soporte del protocolo TCP/IP
* *Controladores del dispositivos de carácter*. Administra terminales, impresoras y módems
* *Controladores de dispositivo de bloque*. Administra discos magnéticos, CD ROMs, etc.
* *Controladores de dispositivo de red*. Administra interfaces de red, puertos, dispositivos de red como switches, routers 
* *Traps y fallas*. Administra interrupciones generadas por el software y fallas generadas por el procesador
* *Memoria física*. Administra la memoria física y asigna memoria virtual
* *Interrupciones.* Administra interrupciones para dispositivos periféricos 

### Android
- Basado en Linux originalmente diseñado para teléfonos inteligentes de pantalla táctil, Tablet o computadores
- Android es el SO más popular para dispositivos móviles
- Inicialmente Android fue desarrollado por Android Inc., el cual fue comprado por Google en el año 2005

### Capa de framework de aplicaciones
* Utilizada por los programadores para desarrollar nuevas aplicaciones
* Algunos de sus componentes son:
	* Administrador de actividad
	* Administrador de ventana
	* Administrador de paquete
	* Administrador de telefonía

### Capa de librerías del sistema
* Es una colección de funciones del sistemas escritas en C o C++
* Algunas principales librerías del sistema son:
	* Surface Manager
	* Open Graphics Library
	* Media Framework
	* SQL Database
	* Browser Engine
	* Bionic

### Componentes básicos de un sistema operativo
1. [[Gestión de Procesos]]
2. [[Administración de Memoria]] principal
3. [[Protección de la información]]
4. [[Programación y administración de recursos]]

* El hardware del procesador, junto con el SO, proveen al usuario de un "procesador virtual" que tiene acceso a la memoria virtual
* La unidad de administración de memoria relaciona direcciones virtuales a direcciones reales.

### Principales errores en el desarrollo de SO
**Sincronización inapropiada**
* Un programa que inicia una lectura en un dispositivo de I/O debe esperar hasta que los datos estén disponibles en un buffer
* Diseño inapropiados en los mecanismos de señalización pueden permitir que las señales de que los datos están disponibles se pierdan o se dupliquen

**Exclusión de falla mutua**
* Dos usuarios pueden intentar editar el mismo archivo al mismo tiempo. Debe existir un mecanismo de exclusión mutua que permita una sola rutina de actualización del archivo a la vez

**Operación no determinada de programa**
* Cuando los programas comparten memoria, pueden interferir con otros al escribir en áreas comunes de memoria de manera impredecible

**Interbloqueos**
* Es posible que dos o más programas se congelen esperando por otro
* Dos programas pueden requerir dos dispositivos I/O para realizar alguna operación, ambos están esperando por el otro programa para alcanzar el dispositivo requerido

### Sistemas Operativos Modernos
![[Sistemas Operativos Modernos.png]]
### Mecanismos del SO ante fallas
Algunas técnicas pueden ser incorporadas en un SO para soportar tolerancia a fallas, entre ellas se pueden mencionar: 
1. Aislamiento de procesos
2. Control de concurrencias
3. Máquinas virtuales
4. Checkpoints y rollbacks

### Procesos de arranque de un sistema informático
* El hardware, por si solo es totalmente incapaz de realizar ninguna acción, necesita un software que le indique qué tiene que hacer
* Cuando se enciende un sistema informático, se pone en marcha hardware, por lo que se necesitan medios especiales para hacer que se cargue un primer software

### Arranque inicial Power-on-self-test
* El proceso comienza siempre en la BIOS
* Cuando se da voltaje a la fuente de alimentación y una vez que la alimentación se estabiliza, genera una señal denominada "Power Good" en uno de los cables que va de la fuente de alimentación a la placa base
* Esta señal es recibida en el juego de chips instalado en la placa, y a su vez generan una señal de reinicio (reset) al procesador. La finalidad de este proceso es evitar que el procesador arranque prematuramente, cuando los voltajes de alimentación no son todavía correctos, lo que podría producir daños en el hardware.
* El procesador arranca cuando se retira la señal de reset. En este momento no existe en su memoria ninguna instrucción o dato, por lo que no puede hacer absolutamente nada
* Para salvar este obstáculo, los fabricantes incluyen en la circuitería de la placa base un mecanismo especial. El sistema se dirige a una dirección fija de memoria, la FFFF0H. Esta dirección, generalmente está situada muy cerca del final de la memoria del sistema, es el punto de inicio de la BIOS
* Este punto de inicio contiene una instrucción de salto que indica al procesador donde tiene que dirigirse para encontrar el punto donde comienza realmente el programa de arranque del sistema operativo (BOOTSTRAP) de la BIOS. Este programa contenido en esa dirección se lleva a la CPU y se ejecuta.
* La primera parte de este programa de la BIOS inicia con un procesador de comprobación del hardware denominado Power On Self Test (POST)
* El orden de las comprobaciones del POST depende del fabricante, pero generalmente la secuencia de comprobaciones se resume como sigue:
	1. Comprobación del procesador.
	2. Varias comprobaciones sobre la memoria RAM.
	3. Inicializar los dispositivos de video y teclado.
	4. Determinar el tamaño de la RAM completa y comprobar su funcionamiento.
	5. Inicializar los puertos: COM (comunicaciones serie), LPT (comunicaciones paralelo), USB, S ATA, SCSI, etc.
	6. Inicializar el sistema IDE, S ATA o SCSI. (Discos duros, CDROMS, etc.).
* A continuación la BIOS recorre la memoria en busca de la posible existencia de otros programas en ROM para ver si alguno tiene BIOS, lo que ocurre por ejemplo, con los controladores de disco duro IDE/ATA, cuyas BIOS se encuentran en la dirección C8000H; otros elementos que suelen contar con sus propias BIOS son las tarjetas de red y las controladoras SCSI. Estos módulos son cargados y ejecutados.
* A continuación, el BIOS muestra su pantalla principal (generalmente con los créditos del fabricante número de versión y fecha).
* La BIOS realiza una especie de inventario del sistema y algunas pruebas para verificar que su funcionamiento es correcto.
* En un sistema informático actual se pueden tener múltiples discos duros, cada uno de ellos con varias particiones donde pueden estar almacenados varios sistemas operativos En la BIOS de casi todos los equipos modernos es posible encontrar información acerca de dónde va a arrancar el sistema Boot
* Generalmente, en el primer sector de todo disco duro no se sitúa un sector de arranque, en su lugar se sitúa una tabla de particiones Master Boot Record (MBR)
* Esta tabla de particiones incluye una tabla donde se definen las particiones que pueden estar presentes en nuestro disco duro y un pequeño programa que permite localizar la partición activa, leer su sector de arranque y usarlo para arrancar el sistema informático

### Llamadas al sistema
* Método o función que puede invocar un proceso para solicitar un cierto servicio al SO
* El SO actúa como intermediario, ofreciendo una interfaz del programa (API) que el programa puede usar en cualquier momento para solicitar recursos gestionados por el SO
* *Ejemplos*:
	* *write*, que se emplea para escribir un dato en cierto dispositivo de salida
	* *read*, leer un dispositivo de entrada
	* *open*, obtener un descriptor de un fichero del sistema, este fichero suele pasarse a write
	* *close*, para cerrar un descriptor de fichero
* Toda llamada al sistema se identifica mediante un valor numérico que no debe ser modificado a lo largo de la vida del SO para evitar que se rompa la compatibilidad hacia atrás.

### Familias de llamadas al SO
* Las dos familias de APIs estandarizadas más importantes son:
	* POSIX
	* WIN32/64
	* Además, existen emuladores como Wine (permite instalar y ejecutar aplicaciones de Windows en distribuciones de Linux) que también las implementan.


![[Sistemas de I-O.png]]
![[Fases.png]]
![[Interrupciones.png]]
![[Ejemplo.png]]
![[Flujo de programa de control.png]]

### Interrupciones y el ciclo de instrucción
* Para el programa de usuario, uno interrupción suspende la secuencia normal de una ejecución
* Cuando se completa el procesamiento de la interrupción, se reanuda la ejecución
* Por tanto, el programa de usuario no tiene que contener ningún código especial para tratar las interrupciones
* El procesador y el sistema operativo son responsables de suspender el programa y volver al mismo punto

![[Ciclo de instrucción con interrupciones.png]]

### Procesamiento de interrupciones
* Cuando ha ocurrido una única interrupciones
* Varios procesos en HW y en SW
* PSW(Program Status Word)

![[Hardware vs Software.png]]

### Múltiples interrupciones
* Un programa puede estar recibiendo datos de una línea de comunicación e imprimiendo resultados al mismo tiempo
* La impresora generará una interrupción cada vez que completa una operación de impresión
* La línea de comunicación generará una interrupción cada vez que llega una unidad de datos
* Es posible que se produzca una interrupción de comunicación mientras se está procesando una interrupción de la impresora.

##### ¿Qué hacer para evitarlas?
Dos posibilidades
1. Deshabilitar interrupciones mientras una interrupción está siendo procesada.
2. Añadir prioridades a las interrupciones 

### ¿Qué es un [[proceso]]?
* Una instancia de un programa ejecutándose en un computador
* La entidad que puede ser asignada y ejecutada en un procesador
* Una unidad de actividad caracterizada por la ejecución de un secuencia de instrucciones, un estado actual y un conjunto asociado de recursos del sistema
* Un proceso es una entidad que consiste de varios elementos, entre los principales se tiene:
	* [[Código de programa]]
	* [[Conjunto de datos]]
	* [[Bloque de control de proceso]]

### Estados del proceso
* Cuando un programa es ejecutado, un proceso o tarea es creado para este programa.

***[[Desde el punto de viste del procesador]]***
* Ejecuta instrucciones en alguna secuencia determinada por los valores del registro Program Counter (PC)
* El PC puede referir hacia código en diferentes programas que son parte de diferentes procesos.

***Desde el punto de vista de un programa individual***
* Su ejecución involucra una secuencia de instrucciones dentro del programa
	* **Trace** --> Lista de secuencia de instrucciones
	* **Dispatcher** --> Programa que conmuta el procesador de un proceso a otro

### Modelos de dos estados
* La principal responsabilidad del SO es controlar la ejecución de los procesos
* En este modelo, un procesos puede estar 

### Creación de un proceso
* SO construye a estructura de datos a sr utilizada para administrar el proceso
* Asigna espacio en memoria principal
* Un procesos puede crear a otro proceso
* Si el SO crea el proceso por requerimiento de otro, se denomina [[Process Spawning]]

# IGUALARSE
### Estados de los hilos
Los hilos al igual que los procesos, tienen estados de ejcución:
* Ejecutando, listo y bloqueado.
Hay cuatro operaciones básicas relacionadas con los hilos que están asociadas con un cambio de estado de hilo:
* Creación
* Bloqueo
* Desbloqueo
* Finalización 

#### Creación 
* Se crea un nuevo proceso --> Se crea un nuevo hilo
* Un hilo del proceso puede crear otro hilo dentro de mismo proceso.
* Al nuevo hilo se le proporciona:
	* Su propio registro de contexto
	* Su propio espacio de pila
	* Se le coloca en la cola de espera del estado Listo

#### Bloqueo de un hilo
* Un hilo necesita esperar por un evento
* Almacena sus registros de usuario, contador de programa y punteros de pila
* Procesador puede ejecutar otro hilo en estado Listo (del mismo o diferente proceso)
* Pueden existir hilos que bloqueen todo el proceso

#### Desbloqueo
* Sucede el evento esperado
* Hilo pasa a cola de espera del estado Listo

#### Finalización
* Se completa un hilo
* Se libera su registro de contexto y pila

### Llamadas a procedimientos remotos usando hilos (RPC)
![[Llamadas a procedimientos remotos usando hilos (RPC).png]]

#### Interleaving
* Intercalado de múltiples hilos con múltiples procesos

#### Sincronización de hilos
* Todos los hilos de un proceso comparten mismos recursos
* Cualquier alteración de un recurso afecta a todos los hilos del mismo proceso
* Por lo tanto, se necesitan técnicas de sincronización 

![[Relación Hilo-Proceso.png]]

#### Comunicación mediante memoria compartida
* La literatura de sistemas operativos está repleta de interesantes problemas que se han descrito y analizado ampliamente, mediante el usp de una variedad de métodos de sincronización
* Se examinarán tres de los problemas más conocidos:

#### Problema de los filósofos comelones
* Cinco filósofos están sentados alrededor de una mesa circular
* Cada filósofo tiene un plato de espagueti
* El espagueti es tan resbaloso, que un filósofo necesita dos palillos para comerlo
* Entre cada par de platos hay un palillo

**Opción uno**: Cada uno de los filósofos intenta tomar los palillos al mismo tiempo.
![[Ejemplo-Condición de Carrera.png]]

### Condición de carrera (Race Condition)
* No se tiene certeza de cuál será el resultado de la ejecución de un programa. 
* Se dice que existe una condición de carrera (Race Condition) si el resultado de la ejecución depende del orden en que se intercalan las instrucciones de los procesos intervinientes.
* Se debe evitar una condición de carrera (Race Condition) en los programas multiproceso implementados
* 2 procesos (PA y PB) + 1 recurso (R)
	* El recurso compartido es una variable inicialmente con el valor o.

![[Pasted image 20220613074539.png]]

* Para evitar las condiciones de carrera se debe identificar las secciones críticas (secciones con recursos (variables) comunes) y garantizar que se ejecuten de forma atómica ([[Exclusión Mutua]]) .

> ***Condición de carrera es el problema y la exclusión mutua es la solución***

### Consideraciones al implementar la [[Exclusión Mutua]]
El programador debe tener en cuenta lo siguiente:
* Las regiones críticas deben ser lo más pequeñas posibles para maximizar la concurrencia.
* La “incorrecta” sincronización de hilos puede traer los siguientes problemas: 
	1. Interbloqueo (deadlock). Cuando todos hacen una cosa a la vez y ninguna llega a nada.
	2. Inanición (starvation). Los que tienen mayor prioridad llegan a usar un recurso, pero el de menor prioridad jamás lo llega a usar 
* Mas ejemplos:
![[Posibles errores.png]]

#### Solución de 1. y 2.
* Un filósofo sólo se puede mover al estado de comer si ningún vecino está comiendo.
* El programa debe utilizar un arreglo de semáforos, uno por cada filósofo, de manera que los filósofos hambrientos puedan bloquearse si los palillos que necesitan están ocupados.
* Existirá un procedimiento filósofo que cada proceso ejecutará como su código principal, y otros procedimientos como tomar_palillos, poner_palillos y comer son comunes.

### Semáforos
* De acuerdo a Dijkstra (1965), dos o más procesos pueden cooperar por medio de simples señales, tales que un proceso pueda ser obligado a parar en un lugar específico hasta que haya recibido una señal específica
* Para la señalización, se utilizan variables especiales llamadas semáforos.
* Para transmitir una señal vía el semáforo s, el proceso ejecutará la primitiva **semSignal(s).**
* Para recibir una señal vía el semáforo s, el proceso ejecutará la primitiva **semWait(s)**

#### Semáforo con contador o general
El semáforo es una variable que contiene un valor entero sobre el cual sólo están definidas tres operaciones:
1. Un semáforo puede ser inicializado a un valor no negativo.
2.  La operación **semWait** decrementa el valor del semáforo. Si el valor pasa a ser negativo, entonces el proceso que está ejecutando semWait se bloquea.
3. La operación **semSignal** incrementa el valor del semáforo. Si el valor es menor o igual que cero, entonces se desbloquea uno de los procesos bloqueados en la operación semWait.

#### Semáforo binario o mutex
Sólo puede tomar los valores 0 y 1 y se puede definir por las siguientes tres operaciones: 
1. Un semáforo binario puede ser inicializado a 0 o 1.
2. La operación semWaitB comprueba el valor del semáforo. Si el valor es cero, entonces el proceso que está ejecutando semWaitB se bloquea. Si el valor es uno, entonces se cambia el valor a cero y el proceso continúa su ejecución.
3. La operación semSignalB comprueba si hay algún proceso bloqueado en el semáforo. Si lo hay, entonces se desbloquea uno de los procesos bloqueados en la operación semWaitB. Si no hay procesos bloqueados, entonces el valor del semáforo se pone a uno

Para ambos, semáforos con contador y semáforos binarios, se utiliza una cola para mantener los procesos esperando por el semáforo.
* **Semáforo fuerte**: Incluye la política FIFO (First In First Out), el proceso que lleve más tiempo bloqueado es el primero en ser extraído de la cola.
* **Semáforo débil**: No especifica el orden en que los procesos son extraídos de la cola.

#### Exclusión mútua con semáforos
➢ El semáforo se inicializa en 1. 
➢ El primer proceso que ejecute un semWait será capaz de entrar en su sección crítica inmediatamente, poniendo el valor de s a 0. 
➢ Cualquier otro proceso que intente entrar en su sección crítica la encontrará ocupada y se bloqueará, poniendo el valor de s a -1. 
➢ Cualquier número de procesos puede intentar entrar, de forma que cada intento insatisfactorio conllevará otro decremento del valor de s. 
➢ Cuando el proceso que inicialmente entró en su sección crítica salga de ella, s se incrementa y uno de los procesos bloqueados (si hay alguno) se extrae de la lista de procesos bloqueados asociada con el semáforo y se pone en estado Listo. 
➢ Cuando sea planificado por el sistema operativo, podrá entrar en la sección crítica.

![[Semáforo.png]]

**Ejemplo**:
* Si se tienen 3 procesos A, B, C y un contador que representa un semáforo con valor inicial igual a 1 al tiempo 0min. Al tiempo 1min el proceso A envía una señal semWait(s), al minuto 2 el proceso B envía una señal semWait(s) y al minuto 3 el proceso C envía una señal semWait(s). Si el proceso A envía una señal semSignal(s) al minuto 4, y los procesos B y C envían una señal semSignal(s) al ejecutarse durante 1 min. Determinar en cada tiempo el valor del semáforo, los procesos que se encuentran ejecutando y los que se encuentran en cola.
![[Semáforo pt.2.png]]

### Monitores
➢ Puede ser difícil producir un programa correcto utilizando semáforos. 
➢ Monitor es una construcción del lenguaje de programación que proporciona una funcionalidad equivalente a la de los semáforos pero es más fácil de controlar. 
➢ Un monitor es un módulo software consistente en uno o más procedimientos, una secuencia de inicialización y datos locales. 
➢ Las principales características de un monitor son las siguientes: 
	1. Las variables locales de datos son sólo accesibles por los procedimientos del monitor y no por ningún procedimiento externo. 
	2. Un proceso entra en el monitor invocando uno de sus procedimientos. 
	3. Sólo un proceso puede estar ejecutando dentro del monitor al tiempo; cualquier otro proceso que haya invocado al monitor se bloquea, en espera de que el monitor quede disponible.
➢ Un monitor soporta la sincronización mediante el uso de variables condición que están contenidas dentro del monitor y son accesibles sólo desde el monitor. 
➢ Las variables condición son un tipo de datos especial en los monitores que se manipula mediante dos funciones: 
	1. **cwait(c)**: Bloquea a un proceso y lo coloca en la condición c. El monitor queda disponible para ser usado por otro proceso. 
	2. **csignal(c)**: Retoma la ejecución de algún proceso bloqueado por un **cwait** en la misma condición. Lo coloca en estado Listo. Si hay varios procesos, elige uno de ellos; si no hay ninguno, no hace nada.

# Mira los ejercicios en clase últimos 30 mins
### Mensajes
* Contenedor que se emplea para intercambiar información entre dos o más procesos en diferentes máquinas.
* Tienen un formato generalmente compuesto por una cabecera, que contiene información sobre la fuente y el destinatario, y un cuerpo, que contiene información específica.
* Los mecanismos de mensajería se refieren al conjunto de funcionalidades que permiten al sistema operativo realizar la entrega de un mensaje a uno o varios procesos.
* Los sistemas operativos generalmente ofrecen dos primitivas o llamadas al sistema para que un proceso pueda enviar y recibir mensajes: 
		➢ send(destino, mensaje): Envía un mensaje a un destino. 
		➢ receive(fuente, mensaje): Recibe un mensaje de una fuente.

#### Formas de identificación
**Denominación Directa**
Se emplea un ID que permite identificar a la fuente y al destinatario, Ej. el PID de un proceso. La denominación directa permite tres configuraciones: 
1. ***Unicast***, una fuente y un destinatario.
2. ***Broadcast***, mensaje a todos los procesos existentes en el sistema.
3. ***Multicast***, mensaje a un grupo de procesos.
El principal inconveniente de la denominación directa es que se pierde el mensaje si el destino no se encuentra

**Denominación Indirecta**
Se emplea un elemento intermediario denominado buzón. El sistema operativo ofrece llamadas al sistema que permiten la creación y destrucción de buzones para comunicación entre procesos, Ej. CreateMailbox y DestroyMailbox. 
1. ***Buzón limitado***: De un proceso a otro.
2. ***Buzón de entrada***: De varios a uno.
3. ***Buzón de salida***: De uno a varios.
4. ***Buzón múltiple***: Varios procesos entre sí con el mismo buzón

**Transmisión por copia en caso de escritura (COW)**
* Permite que los procesos emisor y receptor tengan acceso a la zona de memoria del mensaje de forma controlada.
* La zona puede pertenecer a uno de los procesos, o al SO, y se accede a ella a través de una ventana en el espacio de direcciones que inicialmente sólo permite consultar la información.
* Cuando uno de los procesos intenta modificar el contenido del mensaje, se detecta esta escritura gracias al mecanismo de protección de la memoria.
* El SO hace una copia para uno de ellos, actualiza las referencias, y deja que ambos procesos continúen.

#### Formas de Comunicación
**Emisor, send()**
* ****Síncrona***: el proceso emisor que realiza el send () queda Bloqueado hasta que el receptor llama a recv () y el proceso bloqueado pasa a estado 
* ***Asíncrona***: suponemos una estructura de datos con capacidad de almacenamiento limitada, dependiente del proceso destinatario o en el buzón del SO. Al ser enviados, los mensajes irán encolándose para que el proceso receptor pueda gestionarlos cuando pueda.

**Receptor, recv()**
* ***Bloqueante***: una llamada a recv () sin mensajes a procesar pasa el proceso llamante a estado Bloqueado. Un send () de otro proceso que añada un mensaje a la cola del proceso bloqueado hace que éste pase a estado Listo. 
* ***No bloqueante****: una llamada a recv () sin mensajes a procesar devuelve un mensaje de error, pero la ejecución del proceso llamante continúa.

#### Formato de los Mensajes
* ***Fijo**: Los procesos acuerdan emplear un formato fijo para sus mensajes. Ej. SNMP. 
* **Variable**: Basado en los datos que se envían . Ej. CSV, XML, JSON.
* **Mixto**: Los procesos acuerdan emplear mensaje con partes cuyo formato es fijo, como por ejemplo una cabecera inicial, seguido de partes de tamaño variable. Ej. IPv4.


## Planificación de Procesos
Se encarga de asignar procesos a ser ejecutados por el procesador.

* **Instante de lanzamiento (H0)**: Instante de lanzamiento del proceso. 
* **Instante de finalización (Hf)**: Instante de finalización del proceso. 
* **Tiempo de ejecución (t)**: Unidades de tiempo que requiere el proceso para finalizar su ejecución. 
* **Tiempo de terminación (T = Hf - H0)**: Diferencia entre el instante de lanzamiento y el instante de terminación del proceso. 
* **Tiempo perdido (T-t)**: Es el tiempo durante el cual un proceso no está asignado al procesador, es decir, el tiempo en el que un proceso está en estado preparado o bloqueado. 
* **Índice de penalización (z = T / t)**: Indica que un proceso ha tardado % veces más en ejecutarse.
* **Tiempo de inactividad:** Específico del procesador. Tiempo durante el cual el procesador está ocioso (idle, en inglés), es decir, que no tienen ningún proceso asignado. Un procesador está ocioso cuando no hay procesos en estado Listo. 
* **Tiempo del sistema:** Tiempo empleado por el planificador para la conmutación de procesos. Un buen planificador debe tomar muy poco tiempo en tomar la decisión de planificación y realizar la conmutación. 
* **Tiempo de espera:** Tiempo desde el instante de lanzamiento hasta que el proceso pasa a estado preparado.

#### Ejemplos:
![[Ejemplo 1.png]]
![[Solución ejemplo 1.png]]

#### Tipos de planificación
![[Tipos de Planificación.png]]
![[Ejemplo de TP.png]]

#### Planificación por Prioridades
A cada proceso se le asigna una prioridad y el planificador siempre elegirá un proceso de prioridad mayor sobre un proceso de prioridad menor. **Ejemplo: Excel Taller 3**

#### Planificación a corto plazo
Existen dos tipos:
**[[Apropiativa]]**. El proceso puede ser desalojado
**[[No apropiativa]]**. Se deja ejecutar el proceso hasta que se bloquee o termine voluntariamente

### Gestión de memoria
Requerimientos de los usuarios para la memoria
- Muy rápida --> pequeña y cara
- Muy grande --> barata y lenta
- Bajo costo --> grande y lenta

##### Tipos de memoria de computadores
2 grandes grupos
- *Volátil*
	- RAM
	- SDRAM
	- DRAM
	- SRAM --> para memoria y caché
	- DDR SDRAM
		- DDR2
		- DDR3
		- DDR4
- *No volátil*
	- PROM (programmable)
	- EEPROM
	- EPROM
	- NVRAM (no volátil)
	- Solid State
	- Flash memory

Es importante la gestión de memoria porque nunca hay suficiente principal para contener todos los programas

El administrador de memoria es la parte del sistema operativo que se encarga de gestionar la memoria principal existente en el sistema. Para ello, asigna zonas de memoria principal a cada uno de los procesos existentes en base a sus necesidades

Todo proceso, desde el punto de vista de la memoria, está compuesto de cuatro secciones:
1. ***Código***. Contiene el código de nuestro proceso, las instrucciones que componen el programa
2. ***Variables globales y constantes.*** Constantes definidas en el código del programa Además, incluyen también las variables globales
3. ***Pila (Stack).*** Se emplea para reservar espacio a las variables locales, y en la invocación de funciones
4. ***Montículo libre (Heap)*** Es la sección de memoria que se reserva de manera dinámica mediante las llamadas malloc y free() de la biblioteca estándar de C, que invocan a las llamadas al sistema brk y mmap cuando corresponde

Cuando se lanza un programa desde el lanzador de aplicaciones se hace uso de las llamadas al sistema fork y exec 

#### **Técnicas de gestión de memoria**
![[Técnicas de gestión de memoria.png]]

**Particionamiento fijo.** Se refiere a que ya nuestra memoria va a estar divida en diferentes tamaños: iguales o distintas.
* **Iguales**
	* Cuando hay una partición disponible, un proceso se almacena ahí. Debido a que todas las particiones son del mismo tamaño, no importa qué partición se utiliza.
	* Si todas las particiones se encuentran ocupadas por procesos que no están listos para ejecutar, entonces uno de dichos procesos debe llevarse a memoria secundaria
* **Diferentes**
	* Existe dos formas posibles de asignar los procesos a las particiones:
		* Una cola por partición
		* Una única cola
	* Los dos anteriores son eficientes, 
* Cuando se tiene una sola cola 

**Particionamiento dinámico**. La memoria se va particionando conforme va llegando cada uno de los procesos. Cuando se lleva un proceso a la memoria principal, se le asigna exactamente tanta memoria como requiera y no más.
![[Ejemplo particionamiento dinámico de memoria.png]]
* **Problemas**:
	* **Fragmentación externa**, finalmente existen muchos huecos pequeños en la memoria
	* A medida que pasa el tiempo, la memoria se fragmenta cada vez más y la utilización de la memoria se decrementa
	* Ejemplo anterior 16 MB sin uso
	* Una técnica para eliminar la fragmentación externa es la compactación el Sistema Operativo desplaza los procesos en memoria, de forma que se encuentren contiguos

##### Algoritmos de ubicación para particionamiento variable
![[Ejemplo particionamiento de memoria.png]]
Se tienen 3 algoritmos:
1. [[Mejor-ajuste]] (best-fit)
2. [[Primer-ajuste]] (first-fit)
3. [[Siguiente-ajuste]] (next-fit)

#### Método Buddy 
* Los bloques de memoria se dividen en potencias de 2
* No es un método usado, ya que el mismo desperdicia espacio internamente
![[Ejemplo de sistema Buddy.png]]

### Paginación
Parte de la idea de particionamiento fijo. Sus problemas son:
* Fijo: Fragmentación interna
* Dinámico: Fragmentación externa

Con paginación: 
	- **Memoria principal** se divide en pequeñas porciones (**[[MARCOS]]**) de tamaño fijo
	- Cada **proceso** se divide en pequeñas porciones (**PÁGINAS**) de tamaño fijo
	- Espacio de memoria malgastado más pequeño por fragmentación interna
	- No existe fragmentación
Para ejecutar un programa de n páginas, se necesitan n marcos libres para cargar el programa. 

![[Ejercicio Paginación.png]]

### Direcciones Lógicas
* **Número de página (p).** Se usa con un índice en la tabla de paginas que contiene la dirección base de cada pagina en memoria física
* **Desplazamiento (o tamaño de página (d))**. Combinado con la dirección base define la dirección física que se enviar a la unidad de manejo de memoria (mmu)
* **Paginación Sencilla**. No existe fragmentación externa, pero si existe un poco de fragmentación interna, pero no a nivel del particionamiento fijo.

![[Ejercicio 2 (Paginación).png]]

![[Ejercicio 3 (Paginación).png]]

![[Ejercicio 4 (Paginación).png]]
![[Ejercicio 5 (Paginación).png]]
![[Ejercicio 6 (Paginación).png]]

---
## **Segmentación**
Se basa en el particionamiento dinámico, pero un programa podría ocupar más de una partición, por lo que presenta fragmentación externa menor.
* Dividir a la memoria principal en longitud y base
* Cada proceso se divide en pequeñas porciones (SEGMENTOS) de tamaño variable.
* Existe una longitud máxima del segmento
* Dirección lógica: consta de número de segmento y desplazamiento

##### **Relación de direcciones lógicas y físicas**
Existen tablas de segmentos para cada proceso.
Ejemplo:
* Para una dirección de n + m bits
	* n => numero de segmento
	* m => corresponde al desplazamiento
		* Si n = 4 y m = 12, tamaño máximo de segmento => 2^12 = 4096

**Traducción**
**=> Dirección física:** desplazamiento *(no mayor a la longitud)* + base
![[Ejercicio 1 (Segmentación).png]]

![[Ejercicio 2 (Segmentación).png]]

![[Ejercicio 3 (Segmentación).png]]

	![[Pasted image 20220801075637.png]]

## AAAA
##### Virtualización
Virtualización se puede definir como la capacidad de ejecutar en un único equipo físico (el anfitrión o host) múltiples sistemas operativos invitados (guests)
##### Hipervisor
* Es un administrador de máquina virtual a nivel de software
* Permite que múltiples VMs coexistan seguramente en un único servidor físico y comparten sus recursos
* XD



![[Virtualización - Ejercicio 2.png]]

![[Virtualización - Ejercicio 1.png]]
Si no nos dice cuanto espacio ocupa el hipervisor, siempre se le asigna 1GB por defecto.

## Seguridad
Amenaza. Algo que trata de acceder a servicios privados. Pueden estar dentro de la red o pueden estar fuera (internas o externas) aunque la mayor parte son internas

Dependiendo de las vulnerabilidades de los sistemas activos (valor monetario a las empresas) se dan ciertos ataques. Para evitarlos, necesitan cumplir los Objetivos de la Seguridad