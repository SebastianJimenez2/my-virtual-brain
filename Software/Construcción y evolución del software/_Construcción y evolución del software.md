>[!Note] Siempre se debe buscar menor acoplamiento y mayor cohesión
# Código Limpio
Busca que el código sea tanto elegante como eficiente (más óptimo y mejor uso de recursos del computador)
>[!Note] La recursividad es muchísima más costosa que las iteraciones cuando n es demasiado grande.
## Nombres significativos
- Nombres que revelen intenciones, evitando desinformación en el código
- Poner distinciones entre variables para evitar la ambigüedad
- Nombres que se puedan pronunciar y localizar fácilmente.
## Funciones
- Deben cumplir un y solo un objetivo, por lo que su tamaño debe ser reducido
- Se debe respetar la indentación
- Los argumentos no deben ser mayores a seis, si lo es, se debe replantear la el método.
- Es importante hacer el uso de excepciones o bloques try/catch.
# Excepciones
![[resources/Untitled 15.png|Untitled 15.png]]
- Excepciones Comprobadas.
    - Conexiones para una BDD
    - Abrir un archivo
# Refactorización
Es una técnica disciplinada para reestructuras el código existente, alterando su estructura interna para que sea más fácil de entender sin cambiar su comportamiento externo.
- Mejora el diseño del software
- El software es más fácil de entender
- Permite encontrar bugs
- Ayuda a programar más rápido
# Cambio Divergente
Se requiere cambiar muchos métodos no relacionados cuando realiza cambios en una clase.  
>[!Note] 
>**Top-down.** Cascada, similar descomponer de complejo a sencillo.
