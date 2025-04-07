Denominado: no determinístico

Permiten que cualquier dispositivo acceda al medio siempre que tenga datos para enviar.

Como cualquiera puede acceder se deben establecer reglas para evitar caos en la comunicación, para ellos se usa un protocolo denominado CSMA (acceso múltiple por detección de portadora) 
Carrier --> una señal portadora
S --> Sensado
MA --> acceso múltiple

De forma generalizada funciona: cuando un nodo quiere transmitir un dato, **en primera instancia lo que hace es censar el canal**. 
* Si el canal se encuentra libre, envía la información, caso contrario, lo que detecta una señal portadora y con eso se conoce que el canal está ocupado (enviada por el host que está ocupando en ese momento el canal).

*Tipos de redes que lo usan*: ethernet y las inalámbricas.

Es posible que el proceso [[CSMA]] falle cuando dos nodos tengan acceso al medio al mismo tiempo lo que generará una colisión