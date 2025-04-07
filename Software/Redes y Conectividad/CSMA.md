**Variantes**
1. [[CSMA-CD]]. Básicamente tiene una detección de colisiones. Después de una colisión se debe restablecer 
	* El dispositivo que detecta una colisión envía una señal JAM (señal de atasco, que tiene 32 bits) a todas estaciones, y automáticamente se paran. 
	* En cada uno de ellas se ejecuta un algoritmo denominado back off o de postergación que dura alrededor de 10ms (espera un tiempo aleatorio antes de volver a intentar la transmisión, en cada una de las estaciones se activa un reloj)
	* Este solo se puede usar solo en redes ethernet, en inalámbricas no debido a que aquí no todos pueden detectar a otro debido a su rango de cobertura
1. [[CSMA-CA]]. Origen que va a enviar la trama a un destino y si todo está OK lo que el destino envía un ACK que es la confirmación, si no llega el origen supone que hubo una colisión.
	* El emisor antes de enviar una trama calcula un campo denominado "campo de duración de la trama --> tiempo que el canal va a estar ocupado" en función del: tamaño de la trama y la velocidad de transmisión.
	* Tiempo retrospectivo denominado NAV (network allocator vector) cuyo valor se actualiza con el campo de duración de la trama. El valor inicial del NAV es igual para todos. Mientras el NAV sea mayor a 0 nadie puede transmitir. Cuando sea cero se ejecuta un tiempo aleatorio entre 0 - 255 ms que depende mucho del hardware de cada dispositivo.
	* El back off se decrementa solo si el canal está vacío por lo tanto el dispositivo siempre deben censar el canal para enviar la información, de los contrario se mantiene.
	* El back off counter va en función de slot de tiempos
	* Cuando el back off llega a 0 la trama se transmite y de esa manera ya se ejecuta todo el algoritmo CSMA/CA