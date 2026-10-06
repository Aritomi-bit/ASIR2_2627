# Encabezado del Editor (GNU nano)
```
GNU nano 8.7.1 /etc/dhcp/dhcpd.conf
```
Indica que estás utilizando el editor de texto Nano en su versión 8.7.1 y muestra la ruta del archivo que estás editando (/etc/dhcp/dhcpd.conf), el cual contiene la configuración del servidor DHCP.

# Bloque de Comentarios / Encabezado
1. Indica el nombre del archivo de configuración.
```
# dhcpd.conf
```

2. Nota informativa que señala que este es un archivo de configuración de plantilla o muestra proporcionado por el programa.
```
# Sample configuration file for ISC dhcpd
```

3. Primera parte de una advertencia importante: señala que si el archivo /etc/ltsp/dhcpd.conf existe en tu sistema se usará ese otro archivo como la configuración activa en lugar del actual.
```
# Attention: If /etc/ltsp/dhcpd.conf exists, that will be used as
# configuration file instead of this file.
```

4. Comentario que actúa como subtítulo para indicar que las opciones escritas abajo se aplicarán de forma general (global) a todas las redes administradas por el servidor.
```
# option definitions common to all supported networks...
```
# Parámetros de Configuración Activos
```
1. option domain-name "example.org";
```
Le indica al servidor que asigne el sufijo de dominio "example.org" a todos los dispositivos/clientes que se conecten a la red.
```
2. option domain-name-servers ns1.example.org, ns2.example.org;
```
Define las direcciones o nombres de los servidores DNS (ns1.example.org y ns2.example.org) que recibirán los clientes para resolver nombres de dominio en internet o la red local.
```
3. default-lease-time 600;
```
Establece el tiempo de concesión por defecto de la dirección IP asignada. El valor está en segundos, por lo que 600 segundos = 10 minutos. Si el cliente no solicita un tiempo específico, obtendrá la IP durante 10 minutos antes de tener que renovarla.
```
max-lease-time 7200;
```
Establece el tiempo máximo permitido de concesión de una IP. El valor está en segundos, por lo que 7200 segundos = 2 horas. Aunque un cliente solicite mantener la IP por un tiempo mayor, el servidor no le concederá más de 2 horas.

# Comentarios
```
# The ddns-update-style parameter controls whether or not the server will
# attempt to do a DNS update when a lease is confirmed. We default to the
# behavior of the version 2 packages ('none', since DHCP v2 didn't
# have support for DDNS.)

```
Explica que el parámetro ddns-update-style controla si el servidor DHCP intentará o no actualizar automáticamente los registros del servidor DNS cuando se confirme la entrega (concesión) de una IP a un equipo. Añade que por defecto se utiliza el comportamiento clásico de la versión 2 del paquete ('none'/ninguno), dado que la versión 2 de DHCP no tenía soporte para DNS Dinámico (DDNS).

