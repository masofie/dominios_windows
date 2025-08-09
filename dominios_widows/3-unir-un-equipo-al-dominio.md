# 🖥️ Unir un equipo de Windows al Domino 
<br>

**📑 Indice**
- [🖥️ Unir un equipo de Windows al Domino](#️-unir-un-equipo-de-windows-al-domino)
  - [🔧 1. Maquina Virtual](#-1-maquina-virtual)
    - [⚙️ 1.2 Configuración](#️-12-configuración)
  - [🛠️ 2. Configuración y Unión del Dominio](#️-2-configuración-y-unión-del-dominio)
    - [🚀 2.1 Primer Paso](#-21-primer-paso)
    - [🤝 2.2 Unir Equipo](#-22-unir-equipo)
    - [🔍 2.3 Comprobación desde el Servidor](#-23-comprobación-desde-el-servidor)
    - [🕵️ 2.4 Comprobación desde el Cliente](#️-24-comprobación-desde-el-cliente)

<br>

## 🔧 1. Maquina Virtual 
<br>

### ⚙️ 1.2 Configuración 
<br>

1 - Crear una máquina Windows 10: 

Primero, creamos una máquina virtual con Windows 10 que será unirse al dominio.

![Crear una máquina Windows 10](./img/3-unirequipo1.png)
<br><br>


2 - Conectar máquina a la Red:

Luego, conectamos la máquina virtual a la red donde está el servidor del dominio para asegurar la comunicación entre ellos.

![Conectar máquina a la Red](./img/3-unirequipo2.png)
<br><br>



## 🛠️ 2. Configuración y Unión del Dominio
<br>

### 🚀 2.1 Primer Paso
<br>

1 - Configurar IP de la máquina:

Asignamos una ``ip`` fija a la máquina Windows 10, asegurándonos que esté en la misma subred que el servidor del dominio. El servidor DNS preferido debe apuntar al servidor del dominio para resolver correctamente las peticiones.


![Configurar ip de la máquina](./img/3-unirequipo3.png)
<br><br>


2 -  Cambiar nombre del equipo:

Modificamos el nombre del equipo para identificarlo fácilmente dentro del dominio y la red.

![Cambiar nombre del equipo](./img/3-unirequipo4.png)
<br><br>


### 🤝 2.2 Unir Equipo
<br>

1 - Procedemos a unir el equipo Windows 10 al dominio, ingresando el nombre del dominio y las credenciales del administrador de dominio para autorizar la unión.


![Conectar el equipo al dominio](./img/3-unirequipo5.png)
<br><br>


### 🔍 2.3 Comprobación desde el Servidor 
<br>


1 - Acceder a Usuarios y equipos de Active Directory:

Verificamos que el equipo Windows 10 aparezca correctamente listado en la consola de Usuarios y Equipos de Active Directory.

![Acceder Usuarios y equipos de Active Directory](./img/3-unirequipo6.png)
<br><br>


2 - Acceder a Administrador de DNS:

Comprobamos en el Administrador de ``dns`` que el registro del equipo Windows 10 exista para garantizar la correcta resolución de nombres.

![Acceder Adminitrador de DNS](./img/3-unirequipo7.png)
<br><br>


### 🕵️ 2.4 Comprobación desde el Cliente
<br>

1 -  Iniciar en Windows 10 como Administrador:

Para iniciar sesión en el equipo unido al dominio, usamos la cuenta de administrador del dominio con la siguiente sintaxis

~~~
ASIR\Administrador
~~~

![Comprobamos la union del dominio](./img/3-unirequipo8.png)
<br><br>



2 - Iniciar sesión con Windows 10 como usuario ``admin``:

Finalmente, iniciamos sesión en Windows 10 con el usuario administrador para comenzar a usar el equipo dentro del dominio.

~~~
.\Windows10-27
~~~

![Iniciar sesión con W10 con el usuario admin](./img/3-unirequipo9.png)