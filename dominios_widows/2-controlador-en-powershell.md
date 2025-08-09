# 📦 Instalador de Controlador de Dominio en PowerShell 
<br>

**📑 Indice**
- [📦 Instalador de Controlador de Dominio en PowerShell](#-instalador-de-controlador-de-dominio-en-powershell)
  - [💡 Qué es PowerShell](#-qué-es-powershell)
  - [🖥️ 1. Máquina Virtual](#️-1-máquina-virtual)
    - [⚙️ 1.1 Configuración](#️-11-configuración)
  - [🌐 2. Creación de Dominio](#-2-creación-de-dominio)
    - [🛠️ 2. Configuración](#️-2-configuración)
  - [✔️ 2. Comprabar Dominio](#️-2-comprabar-dominio)

<br>

## 💡 Qué es PowerShell
<br>

<img src="./img/portada-powershell.png" alt="Portada" align="right" width="400" height="400">

``PowerShell`` es una consola interactiva diseñada por Microsoft para administrar sistemas y automatizar tareas mediante comandos y scripts. Es muy utilizada por administradores de sistemas para gestionar entornos Windows de forma eficiente.
  
- Lanzada el 14 de noviembre de 2006 bajo licencia MIT.
- [Más información](https://es.wikipedia.org/wiki/PowerShell)

<br>


## 🖥️ 1. Máquina Virtual
<br>

### ⚙️ 1.1 Configuración
<br>

1 - Nombre:

Añadimos el nombre de la máquina virtual 

![Creamos una nueva máquina virtual , desde consola ](./img/2-powershell1.png)
<br><br>


2 - Creacion de Red NAT:

Creamos una red ``NAT`` para conectar nuestra máquina virtual a la red local y permitir el acceso a internet.

![Nueva Red NAT](./img/2-powershell2.png)
<br><br>


3 - Conectamos la máquina virtual a la red ``NAT`` recién creada para que forme parte de la red.

![Conectar a la Red NAT](./img/2-powershell3.png)
<br><br>



## 🌐 2. Creación de Dominio
<br>

### 🛠️ 2. Configuración 
<br>

1 -  Seleccionar adaptador de red:

Seleccionamos el adaptador de red para la configuración de ``ip`` y ``dns``

![Seleccionando Adaptador](./img/2-powershell4.png)
<br><br>


2 - Configurar IP:

Asignamos la dirección ``ip``, máscara de subred y puerta de enlace según la configuración de red.

![Configurando ip](./img/2-powershell5.png)
<br><br>


3 - Añadir DNS:

Configuramos el servidor ``dns`` para que el dominio funcione correctamente dentro de la red.

![Añadiendo DNS](./img/2-powershell6.png)
<br><br>


4 - Comprobamos la configuración de la red 

![Añadiendo DNS2](./img/2-powershell7.png)
<br><br>


5 - Instalar Dominio Raíz:

Ejecutamos el siguiente comando para instalar el rol de ``Servicios de Dominio de Active Directory (AD DS)``:

~~~
Install-AdsForest AD-Domain-Services
~~~

![Instalar Dominio Raíz](./img/2-powershell8.png)
<br><br>



6 - Descargar servicios de dominio y DNS:

Descargamos el instalador para el dominio raíz con el nombre del dominio que vamos a usar:

~~~
Install-AdsForest -domainname asir.local
~~~

![Descargar Servicios de domnio y DNS ](./img/2-powershell9.png)
<br><br>


7 - Reiniciar máquina:

Después de instalar los servicios, el sistema se reinicia automáticamente para aplicar los cambios.

![Reinicio](./img/2-powershell10.png)
<br><br>


## ✔️ 2. Comprabar Dominio
<br>

Verificar ``ip``:

Finalmente, verificamos la configuración de ``ip`` con el siguiente comando:

~~~
ipconfig /all
~~~

![Ver la ip](./img/2-powershell11.png)