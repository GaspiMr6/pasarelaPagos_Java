# pasarelaPagos_Java
Proyecto realizado en Java que simula un sistema distribuido de pasarela de pagos. El funcionamiento del sistema consiste en que un usuario, por medio de un formulario de una página web envía una petición de que quiere realizar un pago al servidor.

El servidor se compone de los siguientes componentes, relacionados mediante sockets:
- ServidorHTTP: lanza hilos concurrentemente para atender a cada uno de los usuarios. Cada hilo se se encarga de aceptar peticiones y devolver respuestas HTTP. Cuando el cliente pide un recurso estático lo devuelve directamente, mientras que si se trata de uno dinámico debe conectarse con el Gateway (o pasarela).
- Gateway: dependiendo de la petición recibida, consultará el fichero Bines.txt para decidir con qué procesador debe comunicarse. Una vez sepa cuálm leerá el fichero Procesadores.txt para saber su IP y puerto de escucha.
- Procesadores: autoriza o deniega una transacción con tarjeta (dependiendo de los datos del fichero config.txt que lea).

