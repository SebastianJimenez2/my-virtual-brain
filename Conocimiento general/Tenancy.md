# Enfoques
## Multi-tenancy de base de datos única
En este enfoque, todos los inquilinos comparten la misma base de datos, pero sus datos están separados mediante un identificador de inquilino.
- **Estructura**: Todas las tablas incluyen una columna `tenant_id` que identifica al propietario de cada registro.
- **Consultas**: Todas las consultas deben filtrarse por el `tenant_id` del inquilino actual.
- **Aislamiento**: El aislamiento se implementa a nivel de aplicación, no a nivel de infraestructura.
## Multi-tenancy múltiple base de datos
Cada inquilino tiene su propia base de datos separada, lo que proporciona el máximo nivel de aislamiento.
- **Estructura**: Cada inquilino tiene una base de datos dedicada con su propio conjunto de tablas.
- **Conexiones**: La aplicación debe gestionar múltiples conexiones de base de datos.
- **Aislamiento**: Aislamiento total a nivel de infraestructura.
## Multi-tenancy con esquemas (PostgreSQL)
Utiliza esquemas separados dentro de la misma base de datos para cada inquilino. Este enfoque es especialmente útil en bases de datos PostgreSQL.
- **Estructura**: Cada inquilino tiene su propio esquema con un conjunto completo de tablas.
- **Aislamiento**: Buen nivel de aislamiento sin necesidad de múltiples bases de datos.
#  Identificación y Enrutamiento de Inquilinos
Otro aspecto fundamental de la arquitectura multi-tenant es cómo identificar al inquilino actual y enrutar las solicitudes adecuadamente.
## 1. Identificación por Subdominio
Cada inquilino tiene su propio subdominio (ej: `tenant1.aplicacion.com`, `tenant2.aplicacion.com`).
#### Ventajas:
- **Claridad**: Fácil de entender para los usuarios.
- **SEO**: Mejor para el posicionamiento en buscadores.
- **Seguridad**: Facilita la implementación de políticas de seguridad como cookies y CORS.
#### Desventajas:
- **Certificados SSL**: Puede requerir certificados wildcard o múltiples certificados.
- **DNS**: Requiere configuración de DNS para los subdominios.
## 2. Identificación por Ruta (Path)
Los inquilinos se identifican por una sección de la URL (ej: `aplicacion.com/tenant1/`, `aplicacion.com/tenant2/`).
#### Ventajas:
- **Simplicidad**: No requiere configuración de DNS.
- **Certificados SSL**: Un solo certificado para todos los inquilinos.
- **Implementación**: Más sencillo de implementar inicialmente.
#### Desventajas:
- **SEO**: Menos óptimo para posicionamiento.
- **UX**: Experiencia de usuario menos clara.
- **Complejidad de rutas**: Las rutas se vuelven más largas y complejas.
## 3. Identificación por Dominio
Cada inquilino tiene su propio dominio (ej: `tenant1.com`, `tenant2.com`).
#### Ventajas:
- **Marca**: Permite a los inquilinos usar su propia marca.
- **SEO**: Óptimo para posicionamiento.
- **Personalización**: Máxima flexibilidad para los inquilinos.
#### Desventajas
- **Complejidad**: Mayor complejidad en la configuración y mantenimiento.
- **Certificados SSL**: Requiere múltiples certificados.
- **DNS**: Configuración de DNS más compleja.
### 4. Identificación por Solicitud
El inquilino se identifica por un parámetro en la solicitud, como un header personalizado o un token.
#### Ventajas:
- **API**: Ideal para servicios API.
- **Simplicidad**: Sin necesidad de configuraciones DNS o modificación de URLs.
#### Desventajas:
- **UX**: No es adecuado para aplicaciones orientadas al usuario final.
- **Seguridad**: Mayor riesgo si no se implementa correctamente.
# Ciclo de vida
![[Drawing 2025-07-01 14.01.34.excalidraw]]

| Biblioteca                      | Compatibilidad Laravel 12                           | Enfoques soportados                                                                                                                               | Integración con Inertia/Vue                                                                                                                                                              | Ventajas principales                                                                                                                                                                                                                                                            | Limitaciones principales                                                                                                                                                                                                                                                       |
| ------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Tenancy (stancl/tenancy)**    | **Sí** – Soporte explícito en v3.9 (Laravel 12)     | Bases de datos múltiples; base de datos única (con _traits_); esquemas PostgreSQL                                                                 | Middleware para identificar inquilino (por dominio, subdominio, etc.); integración transparente (cambio automático de conexión)                                                          | - Arranque automático sin modificar código existente.- Riqueza de funcionalidades “enterprise” (caches separadas, colas, **usuarios compartidos**, **impersonación**, etc.).- Alta flexibilidad y extensibilidad mediante eventos.                                              | - Curva de aprendizaje más alta por su complejidad y sistema de eventos.<br>- Configuración más pesada si la app es sencilla (puede ser excesivo para casos básicos).                                                                                                          |
| **Spatie Laravel Multitenancy** | **Sí** – Requiere Laravel 11.0+ (compatible con 12) | Base de datos única o múltiples bases de datos (enfoque mínimo, sin soporte explícito de esquemas)                                                | _Tenant finders_ y _middleware_ incluidos para resolver inquilino (e.g. por dominio). No provee _scaffolding_ de front-end específico, pero funciona con Inertia sin cambios especiales. | - Filosofía de **“lo esencial”**: paquete simple y poco intrusivo.<br>- Incluye utilidades útiles (colas multi-tenant, comandos artisan para cada tenant, _traits_ para modelo con conexión específica).<br>- Mantenimiento activo de Spatie (con estándares de calidad altos). | - Se enfoca solo en lo básico de multitenencia).<br>- Requiere implementar ciertas funcionalidades manualmente si se necesitan (por ejemplo, no incluye herramientas avanzadas como sincronización de usuarios o gestión de esquemas).                                         |
| **Tenancy (tenancy/tenancy)**   | **Sí** – Versión 2.4.x soporta Laravel 9–12         | Múltiples bases de datos (central + por tenant); base de datos única con **prefijos de tablas** (opcional); _hooks_ para personalizar estrategia. | Drivers de identificación (HTTP, consola, etc.) y eventos para aislar contexto. No ofrece integración de frontend específica; el desarrollador integra manualmente (similar a Hyn).      | - **Muy flexible** y modular: brinda una “framework” de multitenencia para construir lógica a medida (drivers para DB, identicación, etc.).<br>- Sucesor mejorado del paquete Hyn (aprendió de sus fallas de testabilidad, etc.).                                               | - Documentación limitada y más compleja de implementar rápidamente.<br>- No trae tantas soluciones listas (se espera que el desarrollador arme su arquitectura usando sus componentes).<br>- Sin soporte nativo para esquemas PostgreSQL (requiere personalización adicional). |

