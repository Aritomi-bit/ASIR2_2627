```yaml
Modelos de Red a traves de maquinas virtuales
```

Introducción del Tema
  Tipo de modos de red a traves de VirtualBox.
    - NAT --> Permite acceder a Internet y a la red externa.
    - Adaptador puente --> Conecta la maquina directamente a la red física.
    - Red interna --> Crea una red privada virtual exclusiva.
    - Adaptador solo anfitrión --> Permite crear una red aislada exclusivamente entre el equipo anfitrión y la máquina virtual.
    - Controlador generico --> Permite elegir un controlador avanzado de red especializado.
    - Red NAT --> Permite que varias máquinas virtuales conectadas a la misma red se comuniquen se comuniquen directamente entre sí
    - Red en la nube (Experimental): Permite conectar una máquina virtual local directamente a una subred remota en la nube.
    - No conectado --> No tiene conexión a la red.

```
ip a
```
Se consulta las interfaces de red del sistema ubuntu
interfaz del local (lo) (127.0.0.1).
interfaz de red nat enp0s3

```
sudo systemctl status ssh
```
Se revisa el servicio SSH, 

```
sudo systemctl enable --now ssh
```
Se activa el servidor SSH para que se inicie autamaticamente en el arranque y se pone en marcha de forma inmediata.
