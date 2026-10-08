## ¿Que es DNS?
El DNS (Domain Name System o Sistema de Nombres de Dominio) es una servicio que su función principal es traducir los nombres de dominio legibles para los humanos (como google.com) en direcciones IP numéricas (como 142.250.184.206) que las computadoras utilizan para identificarse y comunicarse entre sí en la red.

## ¿Cómo funciona el proceso de resolución?

*  Cuando escribes un sitio web en el navegador, ocurren los siguientes pasos en cuestión de milisegundos:
    * Solicitud de usuario: Tu navegador pregunta al resolvedor DNS local (por lo general, el servidor de tu proveedor de Internet o un servicio configurado como Cloudflare o Google) por la IP de un dominio.

    * Consulta a la raíz (Root Server): Si la dirección no está en la memoria caché, el resolvedor consulta a los servidores raíz, los cuales lo dirigen al servidor del dominio de nivel superior (TLD, como .com o .es).

    * Consulta al TLD: El servidor TLD orienta la petición hacia el servidor de nombres autoritativo del dominio específico.

    * Respuesta autoritativa: El servidor autoritativo devuelve la IP exacta correspondiente al sitio.

    * Conexión: Tu navegador recibe la IP y carga la página web requerida.
 

  
