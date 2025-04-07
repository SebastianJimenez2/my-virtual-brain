# Atributos de calidad
¿Qué es la calidad? => Grado de satisfacción de un cliente respecto a sus necesidades.
- **Funcionalidad**. Si se cumplen con los requisitos FUNCIONALES. Los requisitos NO FUNCIONALES deben ser documentados y tomados en consideración siempre.

La escases de documentación del código generan ==brechas de seguridad==.

---
# Preguntas interesantes
**¿Por qué debe existir seguridad?**
- Por que se maneja información confidencial y delicada
- Leyes
- Para no generar mala reputación, ya que es algo que es muy difícil de recuperarse. Una mala reputación cae en la pérdida de clientes y por tanto en la pérdida de dinero.

**¿Qué es lo que debemos proteger?**
- Datos sensibles

**¿De quién debo cuidarme?**
- Cracker
> Un hacker es aquel que sabe modificar algo en beneficio de los demás, no necesariamente para hacer daño.
- Cibercriminal 
- Internos, personas que pertenecen a la misma organización 
> El 80% de los ataques se hace a manera de venganza por los *insiders*.
---
# Fundamentos básicos de la seguridad
La seguridad trata de proteger datos del usuario
- [[Conceptos básicos]]
- [[Triada de la seguridad]]
- [[Service Level Agreement ]]
- [[Principios importantes]]
- [[Actores de la ciberseguridad]]
- [[Mecanismos]]

---
# Fundamentos de seguridad
> Todo lo que tenga que ver con ==cifrado== es reversible.
- [[Contraseñas]]
- [[Tarjetas de crédito]]
- [[Cifrado simétrico]]
- [[Cifrado asimétrico]]
- [[HASH]]
---
# "Metodologías" de seguridad
- [[Modelado de amenazas]]
---
# Requerimientos de seguridad
* Ecuador es el ==tercer== país con más ciberataques
---
# Anonimización
La anonimización es el proceso de modificar los datos personales e manera que no se puede identificar a una individuo. Con esto se busca proteger la identidad de las personas y prevenir la divulgación de información sensible.

---
# Arquitectura Zero Trust
Es un marco de seguridad,  ningún usuario se puede confiar implícitamente, incluso si se encuentra dentro de la red de la organización.
Es un nuevo paradigma de seguridad.
> "No confiar, verificar"

Este modelo es esencial para el entorno actual donde los usuarios acceden a recursos desde diferentes dispositivos.
## Principios
- **Verificación constante**. No se confía en nadie, verifica continuamente la identidad y autorización
- **Control perimetral**. Fortalece los límites tradicionales y extiende la protección a todos los puntos de acceso
- **Seguridad proactiva**. Minimiza el riesgo de ataques interno y externos al asumir una postura de no confianza. No espera a que pase el ataque, sino que se está siempre atento
- **Flexibilidad y adaptabilidad.** Se adapta a entornos dinámicos.
## Dónde usar?
- Redes corporativas
- Servicios en la nube
- IoT y dispositivos móviles
## Componentes claves
1. Identidad y acceso
2. Políticas de acceso. Principio de mínima necesidad.
3. Análisis y control de la seguridad
4. Encriptación y seguridad del dato. Proteger en el transporte y en el reposo.
## Flujo de autenticación y autorización
1. Enviar solicitudes de accesos para tomar una decisión
2. Verificar la identidad
3. Evaluación de la autorización
4. Aprobar o denegar
La autenticación verifica la identidad del usuario o dispositivo, mientras que la autorización determina el nivel de acceso permitido.
## Políticas
1. Principios de acceso mínimo, se limita el acceso a usuarios a un recurso en específico
2. Segmentación y asilamiento
3. Verificación continua
4. Implementación basada en políticas
## Gestión de identidades
- Autenticación de usuarios
- Control de acceso basado en políticas
Para eso se usa un gestor de identidades que permite hacer el control.
## Seguridad del perímetro
La confianza se extiende a todos los recursos y dispositivos, incluso de la red.
## Orquestación y automatización
1. Automatización de tareas repetitivas
2. Control de acceso dinámico mediante el ajuste de las políticas y problemas obtenidas, y en base al avance de amenazas
3. Escalabilidad y eficiencia
4. Integración con herramientas existentes
## Retos de implementación
- Complejidad técnica
- Resistencia al cambio
- Gestión de identidades y accesos
- Seguridad del perímetro
## Roles
- Equipo de seguridad, responsable de la arquitectura
- Equipo de IT, levantar la infraestructura
- Equipo de desarrollo, integra la arquitectura 
- Equipo des gestión, define las políticas de acceso roles y responsabilidades
