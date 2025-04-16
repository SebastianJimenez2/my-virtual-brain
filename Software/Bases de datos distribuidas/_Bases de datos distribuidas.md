## Propósito de una DBMS
Inconvenientes con usar archivos del sistema (cont.)
- Atomicidad en actualización
    - Los errores pueden dejar la BDD en un estado de inconsistencia
- Concurrencia del acceso por múltiples usuarios
    - El acceso concurrente necesita de rendimiento
    - El acceso concurrente no controlado puede generar inconsistencias.
- Problemas de seguridad
    - Es difícil dar a algunos usuarios acceso a los datos
Los sistemas de bases de datos ofrecen soluciones a todos los problemas mencionados anteriormente.
## Propiedades de una DBMS
**A** ⇒ atomicidad, todas las instrucciones que conforman una transacción deben ejecutarse en conjunto o ninguna de ellas.
**C** ⇒ consistencia, solo se guardan datos válidos.
**I** ⇒ aislamiento, las transacciones no se afectan entre sí.
**D** ⇒ durabilidad, los datos escritos no se van a perder.
## Niveles de Abstracción
- **Físico**, como está almacenado
- **Lógico**, como se lo ve
- **Vista**, porciones de la BDD que pueden ser accedidos para cierto personal
## Instancias y Esquemas
- **Esquema** ⇒ Estructura lógica de una BDD
- **Instancia** ⇒ Es el contenido de una BDD en un determinado momento de tiempo
- **Independencia de datos** ⇒ El nivel físico se puede modificar sin tener fallos en el sistema lógico.
## Modelos de Datos
Formas de representar los datos
- Modelo relacional, se puede expresar en forma de grafo relacional y en forma de tabla.
### DML - Data Manipulation Language
Lenguaje de manipulación de datos, forma en la que se pueden realizar consultas en la BDD, existen dos:
- **Procedural**, se le indica al sistema qué y cómo obtener algo
- **Declarativo**, especifica lo que quiero sin especificar el cómo
    - Algebra Relacional,
### DDL - Data Definition Language
Permiten crear la base de datos. Generan un conjunto de tablas que están almacenados en un diccionario de datos.
## Diseño de BDD
- Obtención y análisis de requerimientos
- Modelo conceptual (MER)
- **Modelo lógico,** decide el esquema de la BDD. Requiere una buena conexión de esquemas, debe estar en su tercera forma normal.
- **Modelo físico**, es cómo se va a implementar el modelo previo en la BDD.
⇒ En la práctica a veces es necesario desnormalizar por cuestiones de rendimiento
---
[Normalización de Bases de Datos](https://programas.cuaed.unam.mx/repositorio/moodle/pluginfile.php/872/mod_resource/content/7/Contenido/index.html)

---
Fundamentos de Bases de Datos de Korth <== Investiga

---
# Definiciones

- **Bases de Datos Distribuidas.**
    - Consiste en una colección de sitios conectados por medio de algún tipo de red de comunicación, en el cual cada sitio es un sistema de BD completo por derecho propio.
    - Es en realidad un tipo de BBD virtual cuyas partes componentes están almacenada en varias BBD “reales” distintas que se encuentran en varios sitios distintos.
    - Dos **sitios** pueden coexistir en la misma máquina física.
    - Se adapta a la estructura organizacional de la empresa
    - La tecnología relacional es un requisito previo para una tecnología distribuida.
- **Reglas de una BBDD**
    - Autonomía local.
    - No dependencia de un sitio central
    - Operación continua
    - Independencia de ubicación
    - Independencia de fragmentación
    - Independencia de replicación
    - Procesamiento de consultas distribuidas
    - Administración de transacciones distribuidas
    - Independencia de HW
    - Independencia de SO
    - Independencia de red
    - Independencia de DBMS
Calculo función costo de una BDD:

# DISEÑO
**Ascendente**. Existen BDD locales ya implementadas en vario nodos de la red y lo que se trata es integrar los datos que van a ser compartidos en un solo esquema global conceptual. Se aplica cuando existen varios nodos trabajando independientemente en la red (multibases). A partir del esquema global conceptual se pueden crear sistemas externos.
- El esquema global conceptual es un subconjunto de los esquemas locales.

**Descendente**. Se usa cuando se va a planificar un BDDD, no existe una integración, sino una distribución.
- La distribución surge del esquema global hacia los locales
- Existe una sola base d datos centralizada la cual va a asignar la distribución.
- **GCS = LCS1 U LCS2 … U … LCSn**
El diseño parte del esquema lógico global (grafo relacional) y a partir del mismos e va a identificar todos los requerimientos de distribución.
## Tipos de esquemas
- **Fragmentación**. Es la forma en que se va a dividir una tabla en diferentes fragmentos, con esto se hace un análisis para asignar la fragmentación de los datos adecuadamente según el uso que se vaya a dar, puede darse en filas o columnas.
- Agrupación de atributos dentro del esquema de una relación y cómo se van a interpretar los mismos y que los mismos pertenezcan a una misma entidad, entre mejor sea la semántica, más preciso será el modelo ⇒ **Semántica**
- Normas para asegurar la calidad de la fragmentación:
	- **Completitud**. Todos los datos de una relación fragmentada han de encontrar en al menos un fragmento
	- **Disyunción**. _Los datos aparecen en un fragmento no deben aparecer en otro; excepto las claves primarias_ donde si pueden aparecer más de una vez como en el casi de la fragmentación vertical.
	- **Reconstrucción**. Siempre se ha de poder reconstruir la BD global a partir de los fragmentos.
>[!Important]
>**Tuplas Espurias.** Son tuplas que no pertenecen a la relación de una entidad, pero aparecen en los resultados de las consultas debido a una fragmentación mal diseñada. La fragmentación incompleta o mal hecha puede generar tuplas espurias. Estas tuplas son problemáticas porque no representan datos reales y pueden afectar la precisión de las consultas y los resultados obtenidos.
- **Fragmentación Vertical.** Separar la tabla basándose en los atributos.
**Original**

|**a**|**b**|**c**|
|---|---|---|
|1|4|7|
|2|5|8|
|3|6|8|
|6|5|7|

**R1**

|**b**|**c**|
|---|---|
|4|7|
|5|8|
|6|8|
|5|7|

**R2**

|**a**|**b**|
|---|---|
|1|4|
|2|5|
|3|6|
|6|5|

**r = R1 join R2**

|**a**|**b**|**c**|
|---|---|---|
|1|4|7|
|2|5|8|
|3|6|8|
|6|5|7|
|**6**|**5**|**8**|
|**2**|**5**|**7**|

Lo marcado en rojo son las denominadas tuplas espurias. Por lo tanto, para solucionar, la tabla R1 debería haberse fragmentado teniendo la columna primaria, es decir, reemplazar **b** por **a**.
- **Fragmentación Horizontal**
    - **Primaria**. (Usa sigma) Se aplica cuando el campo de fragmentación forma parte de los atributos de esa relación
    - **Derivada**. (Usa semi-join)
        - **Condiciones para fragmentar:**
            - Tenga asociación a una tabla y ya haya sido fragmentada horizontalmente previamente.
            - No pertenezca el campo de fragmentación en sus atributos.
# Esquema de Replicación
Mantener la consistencia mutua de todas las tablas duplicadas.
- **Lazy**. Actualiza una tabla master y la master actualiza a las demás
Es importante saber cuántas réplicas se van a tener, en los nodos específicos.
**Tipos de Replicación:**
1. **Unidireccional.** Implica que se debe poner un nodo de gestión. Las actividades de borrado, actualizaciones e inserción, entre otros se realiza en el nodo de gestión y los cambios se verán reflejados en los nodos restantes.
    1. **Ejemplo**: En la tabla 1 se replica porque **es usada principalmente para consulta** unidireccional en los nodos `____` y se gestiona en el nodo `____`.
    2. Se usan en tablas que tienen poca transaccionalidad.
2. **Bidireccional.** Se pueden hacer las operaciones de inserción, borrado y actualización en cualquier nodo y esto se verá reflejado en los demás. No hace falta poner un nodo de gestión.
# Query Decomposition
**Normalización.** Manipular las consultas.
- Conjuntiva (and)
- Disyuntiva (or)
**Análisis**
- Connection graph
- Join Graph
**Simplificación**
- Eliminación de redundancia
    - Reglas de idempotencia
# Transacciones
Es una unidad de programa que cuando se ejecuta accede y posiblemente actualiza los datos.
# Transacciones Distribuidas
En la parte distribuida no sirve el ‘save transaction’
**DTC** ⇒ Distributed Transaction Coordinator
**Protocolo más común** ⇒ 2 face commit (envía las consultas a diferentes nodos)
- **Primera fase**. Enviar el subquery correspondiente a cada nodo, cada una efectúa su parte y deja la parte parcialmente comprometida
- **Segunda fase.** Recibe cada una de las confirmaciones que los nodos que quedaron parcialmente comprometidos. Si todos son correctos los comprometen completamente, caso contrario se envía un mensaje de error a cada uno de los nodos.
**Transacciones Implícitas**. INSERT, UPDATE, DELETE no necesitan un ‘begin’ sino que empiezan sin problema
**Transacciones Explícitas**. Tiene definido explícitamente un inicio y un fin, es decir, se marca su bloque de ejecución con ‘begin’ y ‘end’
# Vistas
**Vista Particionada**
- Puede ser actualizable o no
- Si es actualizable se debe usar ‘UNION ALL’
    - create view
```SQL
select ___ from s1.bdd1.esquema.tabla1
UNION ALL
select ___ from s2.bdd2.esquema.tabla2
```
