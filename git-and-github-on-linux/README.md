# Git and GitHub On Linux

## Objectivo
Instalar Git y GitHub en sistemas operativos linux principalmente en Debian y CentOS Stream 10 donde se llevarán acabo nuestras prácticas para la certificación CompTIA Linux+.

## Introducción
Git nos permite llevar un control de versiones sobre archivos y proyectos.Facilitando el siguimiento de cambios en proyectos,recuperación de versiones anteriores y sobre todo trabajar de forma ordenada junto con colaboraciones de equipos en tecnología.

GitHub es el alojamiento y colaboración,permitiendo hacer repositorios como el actual trabajamos que hemos creado,compartiendo documentación técnica pública para replicar trabajos y proyectos.

## Uso de Git y GitHub en ambientes Linux y SysAdmin

En el área de SysAdmin, DevOps e infraestructura, Git y GitHub no solo se utilizan para desarrollo de software, sino también para:

- Documentar laboratorios y configuraciones
- Administrar scripts Bash
- Respaldar archivos de configuración
- Controlar cambios en automatizaciones
- Colaborar en equipos de infraestructura

## Diferencia entre gestión de paquetes en Debian y CentOS Stream 10

Los sistemas basados en Debian utilizan el gestor de paquetes `apt` para instalar, actualizar y administrar software.

CentOS Stream 10 utiliza el gestor de paquetes `dnf`, el cual cumple la misma función de administración de paquetes en sistemas basados en Red Hat Enterprise Linux.

Ambos gestores permiten:
- instalar paquetes
- actualizar el sistema
- eliminar software
- administrar dependencias


## Permisos administrativos para instalar software

En Linux, para instalar software es necesario contar con privilegios administrativos.

Esto se debe a que la instalación de paquetes modifica directorios y archivos importantes del sistema operativo.

Por seguridad, normalmente no se recomienda trabajar directamente como `root`. En su lugar, se utiliza el comando `sudo` para ejecutar tareas administrativas de manera temporal.

Ejemplo en Debian:

```bash
sudo apt install git -y
```

## Instalación de Git en Debian

### 1. Arrancar la máquina virtual de Debian

- Actualizar el sistema con el siguiente comando:

```bash
sudo apt update
```

- Instalar Git desde el repositorio
```bash
sudo apt install git -y
```

### 2. Verificación de instalación de Git
- Para verificar si Git se encuentra instalado en  nuestro sistema revisar de forma manual con el siguiente comando:

```bash
git --version
```
### 3. Configuración inicial de Git
- Git almacena de forma local por lo que se requiere conectar a nuestra cuenta GitHub para guardar repositorios de forma remota.

- El primer comando de configuración es colocar el nombre de la persona que realizara labores dentro del sistema.

```bash
git config --global user.name "Brayan Yescas"
```

- Colocar el correo electrónico del usuario para enlazar repositorios.

```bash
git config --global user.email 200yescas@gmail.com
```

- listar los datos para confirmar la los comandos anteriores

```bash
git config --list
```

## Flujo básico de trabajo con Git y GitHub

### 1. Definir una ruta específica para el repositorio remoto

- Clonar repositorio remoto

```bash
git clone URL_DEL_REPOSITORIO
```


## Errores y solución durante la instalación de Git en Debian

### 1. Usuario sin permiso sudo

Durante la actualización de los paquetes del sistema el usuario debianlabs no contaba con permisos sudo por ende se optó ingresar con usuario root y agrgear al grupo de sudo con los siguientes comandos.

```bash
sudo -
```

```bash
groups debianlabs
```

- Agregar al grupo si no contiene sudo

```bash
usermod -aG sudo debianlabs
```

- Reiniciar el sistema ya que inicando de nuevo cargan correctamente los sistemas de administración

```bash
reboot
```
### 2. Paquete de instalación de Git no encontrado

Cuando el sistema no encuentra los paquetes de instalación de algún software el problema radica en mal escritura del comando y negatividad en conexión a internet.

- Rectificar si la estructura del comando es correcta.

```bash
sudo apt install git -y
```

- Revisar conexión a internet

```bash
ping -c 4 google.com
```
- La conexión a internet es estable y activa,si el problema persiste revisar los repositorios.

```bash
cat /etc/apt/sources.list
```

- Tenemos comentada la línea deb cdrom del único repositorio que es del DVD/ISO y es lo correcto ya que no se necesita para instalar paquetes online.

```
#deb cdrom:[Debian GNU/Linux 13.4.0 _Trixie_ - Official amd64 DVD Binary-1 with firmware 20260314-11:54]/ trixie contrib main
```
- Agregar repositorios de manera manual

```bash
sudo nano /etc/apt/sources.list
```

- Escribir los siguientes repositorios oficiales de la versión de Debian 13.4.0 Trixie 

```
deb http://deb.debian.org/debian trixie main contrib non-free non-free-firmware

deb http://deb.debian.org/debian trixie-updates main contrib non-free non-free-firmware

deb http://security.debian.org/debian-security trixie-security main contrib non-free non-free-firmware
```

- Limpiar el sistema de forma saludable.

```bash
sudo apt clean
sudo rm -rf /var/lib/apt/lists/*
sudo apt update
```
- Debian 13.4.0 Trixie nos indica que existen paquetes por actualizar pero ya puede conectarse a ellos.
- Se recomienda actualizar con el comando:

```bash
sudo apt upgrade -y
```

- De esta forma nuestros paquetes están actualizados para futuras instalaciones de software en nuestro sistema.

## Instalación de Git en CentOS Stream 10

### 1. Arrancar la máquina virtual de CentOS Stream 10

El entorno gráfico de CentOS Stream 10 es muy diferente ya que es una instalación mínima;es decir,un estado más puro,un proceso crudo sin animaciones y colores llamativos.

- Al iniciar se muestra el entorno servidor con la versión del S.O y kernel
- Ingresar usuario localhost login: root
- Password: ********

### 2. Actualizar el sistema de paquetes dnf

- Actualizar el sistema de paquetes en la CLI:

```bash
sudo dnf update -y
```

- Una vez ya actualizado los paquetes,es hora de instalar Git

```bash
sudo dnf install git -y
```

### 3. Verificación de la instalación de Git

- La verificación se realiza de forma sencilla con el siguiente comando

```bash
git --version
```

### 4. Configuración inicial de Git

- Inicio de configuración para repositorios local y remoto agregando nombre del usuario

```bash
git config --global user.name "Brayan Yescas"
```

- Agregar correo electrónico de nuestra cuenta GitHub

```bash
git config --global user.email 200yescas@gmail.com
```

- Verificar los datos agregados

```bash
git config --list
```

## Evidencias del proceso de instalación

Adjunto screenshots en las carpetas siguientes:

* Git en Debian

```
assets/screenshots/debian-git-installation
```

* Git en CentOS Stream 10

```
assets/screenshots/centos-git-installation
```

Incluyen:

- Instalación de Git en cada laboratorio
- Configuración de usuario y cuenta de correo electrónico
- Errores y solución presentados durante la instalación
- Clonación de repositorio remoto

## Aprendizaje obtenido

- Diferencias de paquetes de instalación en cada distribución
- Configuración básica de Git
- Organización de estructura de repositorios
- Git para trabajar en formato colaborativo
- Truobleshooting
- Linux en entorno escritorio y server

## Estado del laboratorio
- Laboratorios o centros de pruebas funcionales
- Git instalado para empezar a documentar de forma local en ambos sistemas
- Repositorio actual clonado

> [!NOTE]
> Este centro de pruebas o laboratorio forma parte para mi preparación en obtener la certificación CompTIA Linux+ y prepararme para roles SysAdmin/DevOps/Infraestructure IT
