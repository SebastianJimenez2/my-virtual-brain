##### [[Repaso]]
---
##### [[Proyecto]]
##### [[Retroalimentación]]
---
Verificamos lo que elicitamos.

Todo proyecto se enmarca en lo siguiente:
- Tiempo (limitado)
- Costo (limitado)
- Alcance (el agilismo se enfoca en este punto)
> Si una se ve afectada, las demás igual.

Minimizar el alcance minimiza el ==riesgo==. Si existe un proyecto grande, la mejor solución es dividirlo en iteraciones (features) es ir escalando poco a poco.
![Triangulo Triple Restricción](https://es.smartsheet.com/sites/default/files/IC-Triple-Constraint-Triangle-ES.png)
> ==Ingeniería de software== es la aplicación de un acercamiento científico y empírico (observación) para buscar soluciones eficientes y económicas a problemas prácticos en software. 
# Cynefin Framework
![Cynefin Framework](https://miro.medium.com/v2/resize:fit:1358/0*3cAM3lOXfLyJad7m)
# Métrica, medida e indicador
Las **métricas del software** se refieren a un amplio elenco de mediciones para el software de computadora. La medición se puede aplicar al proceso del software con el intento de mejorarlo sobre una base continua. Se puede utilizar en el proyecto del software para ayudar en la estimación, el control de calidad, la evaluación de productividad y el control de proyectos. Finalmente, el ingeniero de software puede utilizar la medición para ayudar a evaluar la calidad de los resultados de trabajos técnicos y para ayudar en la toma de decisiones táctica a medida que el proyecto evoluciona.
- **Ejemplo**: Tiempo promedio de espera de los clientes.

Una **medida** proporciona una indicación cuantitativa de la extensión, cantidad, dimensiones, capacidad o tamaño de algunos atributos de un proceso o producto.
- **Ejemplo:** Cuántos minutos se demora.

Un **indicador** es una métrica o una combinación de métricas que proporcionan una visión profunda del proceso del software, del proyecto de software o del producto en sí.
- **Ejemplo:** Percentage de clientes que abandonan el restaurante por el tiempo.
---
**Métricas**. ¿Cómo hacer el proceso? Regla general que dice como funciona.
	Consistente en el esquema de medición
	Debe tener una característica matemática
> Algo común se convierte en un estándar. Para cada aspecto de calidad se debe saber su métrica, medica, proceso de medición, indicador, etc.

**Medida.**  Atributos expresados en unidad o cantidad dependiente de la métrica. => Valor, unidad y hace referencia a un atributo
> Un proceso de medición es diferente a la medida. La medida tiene un significado cuando se puede comparar.

**Indicador.** Cuando se comparan dos medidas, se tiene un indicador sobre un atributo. ==Define las interpretaciones de los resultados.==

---
**Ejemplo estimación ágil**
- **Métrica.** Poker planning
- **Indicador.** Incertidumbre y complejidad
- **Medida.** Escala de Fibonacci

**Ejemplo semáforo.**
- **Métrica**. Sistema de colores puesto por ANT.
- **Medida**. Tiempo de duración del color.
- **Indicador**. Significado del color.

**Ejemplo profesores**
- **Métrica.** Resultado de la encuesta de estudiantes
- **Medida.** Tiempo tomado para planificar las clases
- **Indicador.** ¿Cuál es el mejor profesor?
# INVEST
Medir una historia de usuario.
No es un atributo, es una forma de evaluar (indicador). 
# Proceso de medición
Puede partir de una métrica.
Proceso ==planificado==, no podemos medir cuestionar al azar.
- Capacidad de recopilación (¿cómo, cuándo, cada qué tiempo?)
- Conocimiento del atributo (debe tener el atributo a medirse)
- Nivel de significancia (¿qué significan esos valores?)
- Capacidad de operación (es matemático, debe ser operable)
### Fases clave para formalizar un proceso de medición
- Identificar el atributo
- Identificar las relaciones empíricas de un atributo (operadores relacionales)
- Identificar relaciones numéricas, se debe transferir lo empírico en algo medible
- Se define un mapeo, ¿qué significa cada cosa?
- ¡¡PROCESO DE MEDICIÓN!!
# Calidad en Software
Comunicación para definir el alcance. Definir roles.
> Que tan apto es algo cuando lo vamos a dar. ¿Sirve para cumplir con el objetivo de uso? Si lo cumple, tiene calidad. No se debe inflar al producto de actividad que no aporten. Una buena prácticas, proceso, metodología, tecnología puede garantizar la calidad.

Es de calidad si:
- Es apto para el uso desde el punto de vista económico y eficiente.
- Si es conforme con los requerimientos.
El producto se centra en la medición del resultado final.
---
- ### [[Software Quality Assurance]] (QA)
- ### [[Software Quality Control]] (QC)

![[Difference between QA and QC.png]]

Para asegurar la calidad se deben realizar tareas de ==VERIFICACIÓN.==
- ### [[Verificación]]
- ### [[Validación]]

![[Differrence between Verification and Validation.png]]

**Sistema que permita X cosa**
- Acercándose a alejándose de X cosa
- Estoy usando lo adecuado para construirlo

**Sistema de boletos de cine**
- Enfocado a la validación
---
# Evolución de la Calidad
- **INSPECCIÓN**. Inspección de productos terminados.
- **QC**. Detecta productos defectuosos y eliminarlos pero también encuentra la causa de los defectos llamado ==detección de errores.==
- **QA**. Más enfocado en el proceso de producción para prevenir errores. Si el proceso es bueno, entonces el proceso tiende a ser de buena calidad, ==prevención de errores.==
- **TQM**. Asegura que la organización mejore en un todo usando ==mejora continua.== 
# Core aspects of Quality
![[Core aspects of Quality.png]]
> **Process Tailoring.** Making, altering, or adapting a process description for a particular end. For example, a project or work group tailors its defined process from the organization's set of standard processes to meet objectives, constraints, and the environment of the project or work group.
# DEVELOPMENT TESTING
**Unit testing.** Un pequeño módulo
**Integration Testing.** La comunicación entre módulos
**System Testing.** Todo el sistema
# USER ACCEPTANCE TESTING
**Alfa.** Es ejecutada por un equipo QA para imitar el comportamiento real del usuario 
**Beta.** Si la alfa está lista, empieza esta. Es conducida por los usuarios target para asegurar el rendimiento del producto.

![User Acceptance Testing](https://www.deviqa.com/static/images/posts/uatesting/types-of-uat.webp)
# FASES DEL TESTING
- **Smoke Testing.** Probar algo rápidamente.
- **Re-testing.** Volver a probar en el sentido de cambios
- **Sanity Testing.** Veo que el cambio sea funcional
- **Regression Testing.** Prueba el impacto que ha generado el cambio
**Más información:** [Testing](https://katalon.com/resources-center/blog/sanity-testing-vs-smoke-testing)
# Teorema de la Correctitud
Si una condición, V, es verdadero antes de la ejecución del programa, S, entonces la condición, P, puede ser verdadera después de la ejecución de S
```
{V} S {P}
```
V ==> Precondiciones
P ==> Postcondiciones
> Si algo no tiene correctitud, no se han definido las precondiciones y las postcondiciones necesarias.
---
# Proyecto
- ¿Cómo?
# Proceso Tradicional
![[Normal Route.png]]
# Proceso BDD
> Empieza con los objetivos del negocio, y luego con el conocimiento lo transformamos en algo de valor.

Se basa en el comportamiento del sistema. Sistema no es lo mismo que software.
![[BDD Route.png]]

# Example Mapping
A partir de una característica se deben hacer ejemplos.
![Example Mapping](https://openpracticelibrary.github.io/opl-media/images/example-mapping-2-.png)

# Cuatro pilares de negocio ágil
Son:
1. Entregar valor pronto
2. Entregar calidad a velocidad
3. Descubrir valores efectivos
4. Adaptarse con confianza
Se logra con:
1. A BDD mindset
2. A DevOps Culture
3. Agile Methods
4. Engineering Discipline
# Pirámide
**![[Pirámide.png]]**

---
# [[Exposiciones]]
---
# Atributos de calidad
