**Sección crítica:** Una secuencia de instrucciones que accede a recursos compartidos ya que se debe ejecutar de forma indivisible o atómica (todo o nada).
* Mientras un hilo está ejecutando código de esa región ningún otro hilo lo hará (aunque haya cambios de contexto).
* La forma de sincronización que se usa para proteger una sección crítica y evitar una condición de carrera se llama [[Exclusión Mutua]].
	* El programador debe:
		* Identificar las secciones críticas de su código.
		* Debe marcar el inicio y fin de la sección crítica usando las herramientas soportadas en el sistema

El sistema operativo ofrece llamadas al sistema para marcar el inicio y fin de la sección crítica: 
* Inicio: Si ningún otro hilo ha pedido acceso a la región crítica se deja que continúe accediendo, sino se hace que el hilo espere hasta se libere el acceso a la sección crítica.
* Fin: Se libera el acceso a la sección crítica y si algún hilo estaba esperando el permiso para acceder se le permite el acceso.

### [[Mutex]] (Mutual Exclusión)
Dos hilos no pueden mantener el mismo MUTEX bloqueado al mismo tiempo.