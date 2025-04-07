**Reglas**:
* Un hilo no puede bloquear un mismo Mutex dos veces al mismo tiempo.
* Un hilo no puede desbloquear (unlock) un Mutex que ha sido bloqueado por otro. 
* Un hilo no puede desbloquear un Mutex que no ha sido bloqueado.