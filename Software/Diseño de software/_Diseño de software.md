[[Exposiciones]]
## Características del Diseño
- Materia prima igual, sin embargo, las propiedades cambian dependiendo del objetivo para el cuál se vaya a usar.
## ¿Qué es diseño?
Es algo que se construye con una finalidad, en general, no hay un diseño en específico para cumplir con un mismo objetivo. En un diseño siempre va a existir un ganar-perder.
Es variable, no es fijo.
## Diseño de Software
Se aplica sin importar el modelo del proceso que se utilice. Comienza una vez se han analizado u modelado los requerimientos, es la última acción de la ingeniería de software dentro de la actividad de modelado y prepara la etapa de construcción.
Las fases existentes son:
- Análisis de Requerimientos ⇒ Se entrega documentación: ERS, casos de uso, etc.
- Diseño ⇒ Convertir documentación en diagramas. Es la parte **más visual.**
- Desarrollo e implementación ⇒ Código en un lenguaje específico
- Pruebas
- Mantenimiento
Estas fases no necesariamente son secuenciales. Pueden variar dependiendo del modelo.
## Costo de los Daños
Cada etapa que pase el costo se eleve por diez.
## Comprensibilidad
Cada módulo en el diseño debe ser dependiente y comprensible po sí mismo, sin tener la necesidad de entender la totalidad del completo. De esta forma si se asigna un trabajo por grupos en módulo del diseño, las personas encargadas deben entender por separado sin necesidad de preocuparse por la funcionalidad completa del sistema.
## Fácil de dividir en equipos
El diseño debe ser fácil de dividir para poder asignar tareas en grupos y hacer del diseño algo más eficiente.
## Modificabilidad
El sistema debe ser apto a cambios, debido a que un diseño nunca es estático, debe ser modificable al punto de que dichos cambios sean óptimos en costo, tiempo y eficacia. Un cambio solicitado debe causar el menor impacto posible dentro del sistema.
![[resources/Untitled 5.png|Untitled 5.png]]
- **Diseño Arquitectónico**
    - Posee grandes componentes
    - El diseñador toma esto y plantea la arquitectura dependiendo del objetivo que se requiera.
- **Diseño Detallado**
    - Posee diagramas de clases de secuencias
    - Pseudocódigo
---
# PARADIGMA ESTRUCTURADO Y PARADIGMA ORIENTADO A OBJETOS
Un paradigma es una forma de pensar que se adopta por un tiempo.
[[Paradigma Estructurado]]
[[Paradigma Orientado a Objetos]]
# Principios de Diseño
[[Ejercicio en clase]]
## **Descomposición**
La descomposición se realiza para hacer del sistema algo más comprensible y fácil de manipular, debido a que, si descomponemos una clase en sus tipos, es más fácil la asignación de trabajo al equipo desarrollador del sistema.
## **Herencia y Polimorfismo**
Permite implementar de manera compleja un método en donde cada clase que lo hereda puede tener su propio funcionamiento sin afectar a la clase padre.
> **Principio de Sustitución de Liskov.** Una clase hijo puede reemplazar a la clase padre y el sistema sigue funcionando de manera normal.
## **Abstracción**
Obtener de una cosa lo más importante y dejar de lado el resto.
## **Principio de ocultación de Información**
**NO**. Se tiene atributos privados y métodos públicos, a través de los métodos privados se accede a los atributos públicos: getAtributo()
Nace en 1972 por David Parnás.
Este principio se basa en que solo se muestre lo necesario, tener una división de diseño oculta y revelar tan poco como sea posible de su funcionamiento intenro.
## **Encapsulación.**
La encapsulación es un principio de diseño que permite ocultar y proteger la información dentro de una clase, evitando que sea accesible desde fuera de ella. Se logra mediante el uso de modificadores de acceso en los atributos y métodos de la clase.
# Relaciones
**Asociación**. ‘B’ pertenece a ‘A’, siguiendo la imagen a continuación:
![[resources/Untitled 1 2.png|Untitled 1 2.png]]
**Agregación**. Si muere A, B sigue viviendo.
![[resources/Untitled 2 2.png|Untitled 2 2.png]]
**Composición**. Si muere A, muere B.
![[resources/Untitled 3 2.png|Untitled 3 2.png]]
**Dependencia**. A depende de B. En el ejemplo, se podría decir que cajero depende de algo que cuenta en específico, ya sea un atributo o algo para que un método dentro de cajera pueda funcionar.
![[resources/Untitled 4 2.png|Untitled 4 2.png]]
**Herencia**. Estructura de generalización. Se tiene una clase que generaliza a sus clases hijas, conocida como super clase, padre, base y a sus herencias como subclase, hijo, derivada.
![[resources/Untitled 5 2.png|Untitled 5 2.png]]
- **Herencia Vertical:**
![[Untitled 6.png]]
# Clase abstracta
En UML viene representada como cualquier otra clase, sin embargo, se diferencia de una ordinaria, debido a que la misma se escribe en cursivas.
Esta clase debe tener por lo menos un **método virtual.**
>[!Info] Un método virtual es un método que se define en una clase base y se puede sobrescribir en una clase derivada. Esto permite que las clases derivadas proporcionen una implementación específica de un método heredado o agreguen funcionalidad adicional al método base. Los métodos virtuales se definen utilizando la palabra clave `virtual` en C++ o `override` en C#.

![[Untitled 7.png]]

# Interface
No tiene atributos y todos sus métodos son virtuales
![[Untitled 8.png]]
# SOLID
## Principio de responsabilidad única. 
Una clase debe tener métodos que sean coherentes a la misma, en otras palabras, una clase debe tener únicamente lo que a la clase le corresponde.
## Principio de abierto/cerrado:
Una clase debe estar abierta a extensiones, pero cerrada a modificaciones.
## Principio de sustitución de Liskov
La clase padre debe ser capaz de reemplazar a la clase hijo y el funcionamiento del código no debe verse afectado. Si una clase hija tiene el método heredado, pero lo único que se tiene ahí es una excepción, se está irrumpiendo al código.
- **Objetivo:** Permite que, si hacemos una herencia, la misma esté bien hecha.
- En una interfaz está garantizada el principio de sustitución de Liskov
- _La clase rectángulo debe ser capaz de reemplazar a la clase cuadrado._
![[Untitled 9.png]]
## Principio de segregación de la interfaz
Es preferible contar con muchas interfaces que definan pocos métodos que tener una interface forzada a implementar muchos métodos a los que no dará uso.
## Principio de inversión de dependencias
- Los módulos de alto nivel **no deberían depender de módulos de bajo nivel**. Ambos deberían depender de abstracciones.
- **Las abstracciones no deberían depender de los detalles**. Los detalles deberían depender de las abstracciones.
# Cohesión vs. acoplamiento
- **Cohesión**. Tener todos los métodos relacionados entre sí
    - Nivel más alto de cohesión se logra con el principio de responsabilidad única
- **Acoplamiento**. En un sistema que tan dependiente estoy de la otra parte del sistema.
    - Menor acoplamiento
>[!Important] 
>Mayor cohesión, menor acoplamiento
# Patrones
Establecido por Christopher Alexander. Factor común en la elaboración de algo específico.
Son soluciones de diseño a problemas de diseño recurrentes. Adoptada por miles de personas que han pasado por el mismo problema.
>[!Important]
>**The Gang of Four - Patrones de Diseño**

[[Ejercicios]]
[[Ejercicios Prueba]]
## Patrón Observador
Existe un cambio constante, este cambio afecta a una clase, por ende, se aplica este patrón.
## Patrón Estado
Hay un cambio en tiempo de ejecución.
![[Untitled 10.png]]
## Patrón Cadena de Responsabilidad
Debe haber una petición.
![[Untitled 11.png]]
## Patrón Decorador
Cuando se tiene un objeto y tiene varias variaciones. La clase decorador es una clase abstracta.
![[Untitled 12.png]]
## Patrón de Fachada
Cuando un cliente quiere hacer uso de alguno de los subsistemas de un sistema, y para no acceder a todos, existe la fachada que hace que el mismo interactúe con un subsistema en concreto de manera directa.
![[Untitled 13.png]]
# Antipatrones
- Poca optimización / eficiente
- ==**NO**== es el mal uso del patrón
- Dificulta el diseño inicial
## Golden Hammer.
Tenemos un martillo y parece ser que funciona para realizar para cualquier actividad, sin embargo, no siempre es el método más eficiente o más corto de ejecutar.
## The blob 
Cargar una clase de métodos.
- Trasladar métodos de otras clases a una clase “dios” y la misma crece y crece hasta estar sobrecargada.
## Lava flow 
La codificación no va acorde a la arquitectura, entonces puede ser que se tenga pedazos de código obsoletos.
## Functional Decomposition 
Usar lenguaje procedural en donde se requiere usar un paradigma orientado objetos.
## Poltergeist
Clases fantasmas que lo único que hacen es llamar o mandar mensajes a otras clases.
## Cut-and-paste programming
Rehusar códigos externos sin previo análisis que van a complicar el mantenimiento del mismo.
