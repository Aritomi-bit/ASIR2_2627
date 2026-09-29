## CONFIGURAR UN SERVIODR DHCP PARA QUE ASIGNE DIRECCIONES IP
# Paso1: Configurar las Redes Virtuales
1 En VirtualBox:
* Ve a la configuración de la máquina virtual Servidor -> Red.
* Conecta el Adaptador 1 a Red interna (Internal Network) y asígnale un nombre (por ejemplo, red-interna1).
* Haz lo mismo con la máquina virtual Cliente: ve a su configuración de Red y conéctala a la misma Red interna (red-interna1).

# Paso2: Configurar la IP Estática en el Servidor Ubuntu
1. Encendemos la maquina de servidor
2. Identificamos el nombre de la interfaz de red ejecutado:
```
ip a
```
3. Configura una IP estática:
```
sudo nano /etc/netplan/00-installer-config.yaml
```
# Paso3: Instalar y configurar el Servidor DHCP
1. Actualiza los repositorios e instala el paquete del servidor DHCP
```
sudo apt update
sudo apt install isc-dhcp-server -y
```
