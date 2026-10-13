# Servidor DNS con BIND9 en Ubuntu Server (Máquina Virtual)

Guía completa y paso a paso para instalar, configurar y probar un servidor DNS local utilizando **BIND9** en una máquina virtual con Ubuntu.

---

## Prerrequisitos

* Una máquina virtual con Ubuntu Server instalado.
* Privilegios de administrador (`sudo`).
* Dirección IP estática configurada en la máquina virtual.

---

## 🚀 Pasos de Instalación y Configuración

### Paso 1: Actualizar el sistema e instalar BIND9
Actualiza los repositorios de paquetes e instala BIND9 junto con sus herramientas de consulta:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install bind9 bind9utils bind9-doc -y
```

### Paso 2: Configurar los reenviadores (Forwarders)
Para permitir que el servidor resuelva consultas de Internet (como dominios externos), edita el archivo de opciones:
```
sudo nano /etc/bind/named.conf.options
```
Descomenta y configura los servidores DNS externos en la sección forwarders:
```
forwarders {
    8.8.8.8;
    1.1.1.1;
};
```
### Paso 3: Reiniciar y habilitar el servicio
Aplica los cambios reiniciando BIND9 y configurándolo para que inicie automáticamente:
```
sudo systemctl restart bind9
sudo systemctl enable bind9
```
### Paso 4: Configurar el Firewall (UFW)
Abre el puerto 53 (TCP/UDP) en el cortafuegos para permitir las consultas DNS de los clientes:
```
sudo ufw allow 53/tcp
sudo ufw allow 53/udp
sudo ufw reload
```
  * Cómo verificar: Ejecuta sudo ufw status para confirmar que el puerto 53 esté listado y permitido.

### Paso 5: Probar el funcionamiento del servidor
Realiza una consulta utilizando la herramienta dig apuntando al servidor local:
```
dig @localhost google.com
```
  * Cómo verificar: En la salida del comando, comprueba que aparezca ;;
    SERVER: 127.0.0.1#53 y que la sección ANSWER SECTION devuelva las direcciones IP correspondientes.



