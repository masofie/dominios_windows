# 🗄️ Instalación de DC Adicional
<br>

**📑 Indice**
- [🗄️ Instalación de DC Adicional](#️-instalación-de-dc-adicional)
  - [🤔 Qué es un Dominio Adicional?](#-qué-es-un-dominio-adicional)
  - [🖥️ 1. Máquina Virtual](#️-1-máquina-virtual)
    - [⚙️ 1.1 Configuración](#️-11-configuración)
  - [🛠️ 2. Configuración del Dominio](#️-2-configuración-del-dominio)
    - [📝 2.1 Configuración Básica](#-21-configuración-básica)
  - [📦 2.2 Instalamos los Controladores](#-22-instalamos-los-controladores)
  - [🚀 3. Promover el Servidor](#-3-promover-el-servidor)
    - [🔧 3.1 Configuración](#-31-configuración)
  - [🔍 4. Acceder a los Controladores](#-4-acceder-a-los-controladores)
    - [👥 4.1 Usuarios y Equipos de Active Directory](#-41-usuarios-y-equipos-de-active-directory)
    - [💻 4.2 Configuración de los Clientes](#-42-configuración-de-los-clientes)
    - [➕ 4.3 Crear Nuevo Usuario](#-43-crear-nuevo-usuario)

<br>

## 🤔 Qué es un Dominio Adicional? 

Un ``Dominio Adicional`` es una copia exacta del ``Dominio Principal`` que permite la redundancia.
Si el servidor principal falla, el secundario toma el relevo.
Esto mejora la disponibilidad y el rendimiento del dominio.

<br>

## 🖥️ 1. Máquina Virtual
<br>

### ⚙️ 1.1 Configuración
<br>

1 - Creamos una nueva máquina de Windows Server . En ``VirtualBox`` creamos la máquina para el servidor adicional.

![Creamos una nueva máquina de Windows Server](./img/4-dc1.png)
<br><br>


2 - Conectamos la máquina a la misma red del servidor principal.

![Añadimos la máquina a la red ](./img/4-dc2.png)
<br><br>



## 🛠️ 2. Configuración del Dominio 
<br>

### 📝 2.1 Configuración Básica 
<br>

1 - Configurar ``ip`` del Equipo:

Configuramos la ``ip`` . El servidor preferido será el principal, el secundario es este servidor adicional.

![Cambiamos la red de la máquina](./img/4-dc3.png)
<br><br>


2 - Cambiar nombre del equipo:

Cambiamos el nombre para identificarlo fácilmente. Se reinicia la máquina para aplicar cambios.

![Cambiamos el idioma de la maquina](./img/4-dc4.png)
<br><br>


## 📦 2.2 Instalamos los Controladores
<br>

1 - Instalamos Active Directory Domain Services y DNS para que se comunique con el servidor principal.

![Instalamos los controladores](./img/4-dc5.png)
<br><br>


## 🚀 3. Promover el Servidor
<br>

### 🔧 3.1 Configuración
<br>

1 - Promovemos el servidor desde el aviso en la barra de tareas ``⚠️``

![Promover el Servidor](./img/4-dc6.png)
<br><br>

2 - Seleccionar implementación

- 1️⃣ Elegimos Agregar un controlador de dominio a un dominio existente.
- 2️⃣ Escribimos el nombre del dominio principal. 
<br>

![Seleccionar Implementación 1](./img/4-dc7.png)
<br><br>


3 - Contraseña de dominio principal:

Ingresamos la contraseña de administrador del dominio 

![Seleccionar Implementación 2](./img/4-dc8.png)
<br><br>


4 - Configuración de Implementación:

Indicamos el nombre del servidor principal en opciones adicionales.

![Seleccionar Implementación 3](./img/4-dc9.png)
<br><br>


5 - Contraseña para dominio secundario:

Ingresamos la contraseña para el dominio secundario e incluimos el Catálogo Global (GC).

![Contraseña para Dominio Secundario](./img/4-dc10.png)
<br><br>


6 - Opciones adicionales:

Indicamos el nombre del servidor principal en opciones adicionales.

![Opciones Adicionales](./img/4-dc11.png)
<br><br>


7 - Comprobar instalación:

Reiniciamos el servidor adicional. Verificamos que se haya unido correctamente al dominio.

![Comprobar Instalación](./img/4-dc12.png)
<br><br>



##  🔍 4. Acceder a los Controladores
<br>

### 👥 4.1 Usuarios y Equipos de Active Directory
<br>


1 - Desde el servidor principal y verificamos que ambos controladores estén visibles.

![Usuarios y Equipos de Active Directory 1](./img/4-dc13.png)
<br><br>


2 - Hacemos lo mismo para  con el adicional 

![Usuarios y Equipos de Active Directory 2](./img/4-dc14.png)
<br><br>


### 💻 4.2 Configuración de los Clientes
<br>

1 - Configuramos el DNS secundario en clientes Windows y Ubuntu con la IP del servidor adicional.

![Configuración de los clientes 1](./img/4-dc15.png)
<br><br>


2 - Apagamos el servidor principal y comprobamos que el inicio de sesión siga funcionando.

![Configuración de los clientes 2](./img/4-dc16.png)
<br><br>


### ➕ 4.3 Crear Nuevo Usuario
<br>

``¿Qué ocurre si creamos un usuario en DC adicional y luego arrancamos el principal``


1 - Crear nuevo usuario:

Creamos un usuario en el controlador adicional.

![Nuevo Usuario](./img/4-dc17.png)
<br><br>



2 - Asignar contraseña:

Le asignamos contraseña y bloqueamos el cambio por parte del usuario.

![Contraseña de Usuario](./img/4-dc18.png)
<br><br>



3 - Usuario creado:

Usuario creado correctamente.

![Usuario Creado](./img/4-dc19.png)
<br><br>


4 - Ver usuario en Active Directory:

Verificamos el usuario en el directorio activo.

![Usuario y Equipos de Active Directory ](./img/4-dc20.png)