
# Modelos de Red a traves de maquinas virtuales
Introducción del Tema
  Tipo de modos de red a traves de VirtualBox.
* NAT --> Permite acceder a Internet y a la red externa.
* Adaptador puente --> Conecta la maquina directamente a la red física.
* Red interna --> Crea una red privada virtual exclusiva.
* Adaptador solo anfitrión --> Permite crear una red aislada exclusivamente entre el equipo anfitrión y la máquina virtual.
* Controlador generico --> Permite elegir un controlador avanzado de red especializado.
* Red NAT --> Permite que varias máquinas virtuales conectadas a la misma red se comuniquen se comuniquen directamente entre sí
* Red en la nube (Experimental): Permite conectar una máquina virtual local directamente a una subred remota en la nube.
* No conectado --> No tiene conexión a la red.

## Conexión SSH mediante claves entre dos equipos virtuales con Ubuntu
 # Paso 1: Configurar el Servidor Ubuntu
 1. Actualizar e instalar el servidor SSH:
```
sudo apt update
sudo apt install openssh-server -y
```
2. Vereficar que el servicio esté activo y ejecutándose:
```
sudo systemctl enable --now ssh
sudo systemctl status shh
```
3. Permitir el puerto 22 en UFW
```
sudo ufw allow ssh
sudo ufw reload
```
4. Averiguar la dirección IP del servidor:
```
ip a
```

5. Conectarse a la maquina virtual

  # Paso 2: Generar y Configurar la Clave en el Cliente Ubuntu
1. Generar el par de claves SSH
```
ssh-keygen -t ed25519 -c
```


