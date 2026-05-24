# Comandos de Información del Hardware

## Objetivo

Aprender comandos básicos para la obtención de información de nuestro equipo,es de mucha utilidad para hacer diagnósticos precisos,etc.

## Introducción

Linux proporciona diferentes herramientas para consultar información del hardware del sistema desde la terminal.

## Comandos lshw y dmidecode

Los comandos `lshw` y `dmidecode` permiten visualizar detalles importantes sobre:
- procesador
- memoria RAM
- discos
- BIOS
- placa madre
- dispositivos conectados
- arquitectura del sistema

Estas herramientas son ampliamente utilizadas en:
- administración de sistemas
- troubleshooting
- auditorías
- inventarios de hardware
- soporte técnico

## Instalación de lshw

#### Sistemas Basados en Debian

```bash
sudo apt install lshw
```

#### Sistemas Basados en Red Hat

```bash
sudo dnf install lshw
```

## Comando `lshw`

El comando `lshw` (List Hardware) muestra información detallada sobre los componentes físicos del sistema.

### Ejemplo básico

```bash
sudo lshw
```

#### Mostrar Resumen Corto del Hardware

```bash
sudo lshw -short
```

#### Mostrar Información de Red

```bash
sudo lshw -class network
```

#### Mostrar Información de Discos

```bash
sudo lshw -class disk
```

## Funciones principales

- Detectar hardware instalado
- Mostrar especificaciones técnicas
- Consultar dispositivos conectados
- Obtener información del sistema

> [!NOTE]
> Requiere privilegios de root para mostrar toda la información.
> Útil para diagnóstico e inventario de hardware.

## Instalación de dmidecode

#### Sistemas Basados en Debian

```bash
sudo apt install dmidecode
```

#### Sistemas Basados en Red Hat

```bash
sudo dnf install dmidecode
```

## Comando `dmidecode`

El comando `dmidecode` obtiene información del hardware desde la tabla DMI/SMBIOS del sistema.

### Ejemplo básico

```bash
sudo dmidecode
```

#### Mostrar Información del BIOS

```bash
sudo dmidecode -t bios
```


#### Mostrar Información de Memoria RAM

```bash
sudo dmidecode -t memory
```

#### Mostrar Información del Sistema

```bash
sudo dmidecode -t system
```

## Funciones principales

- Mostrar información del BIOS
- Consultar fabricante del sistema
- Ver información de memoria RAM
- Obtener datos de la motherboard
- Consultar números de serie y versiones

> [!NOTE]
> Requiere privilegios de root.
> Útil para visualizar información del BIOS, placa madre, RAM y fabricante del sistema.

## Diferencias Entre lshw y dmidecode

| Comando | Función |
|---|---|
| `lshw` | Muestra hardware detectado por el kernel de Linux |
| `dmidecode` | Muestra información almacenada en BIOS/SMBIOS |

## Importancia

Los comandos `lshw` y `dmidecode` son herramientas fundamentales para administradores Linux y profesionales de infraestructura, ya que permiten analizar y diagnosticar el hardware directamente desde la terminal.

## Comandos free y lspci

Los comandos `free` y `lspci` permiten obtener información importante sobre:
- memoria RAM
- memoria swap
- dispositivos PCI
- tarjetas de red
- controladores SATA
- tarjetas gráficas
- hardware conectado al sistema

Estas herramientas son utilizadas frecuentemente en:
- administración Linux
- troubleshooting
- monitoreo del sistema
- diagnóstico de hardware
- soporte técnico

## Comando `free`

El comando free nos sirve para obtener información de la memoria RAM y memoria swap en linux.

### Ejemplo básico

```bash
free
```

#### Mostrar Información en Formato Legible

```bash
free -h
```

#### Actualizar Información Cada 2 Segundos

```bash
free -s 2
```

#### Mostrar Memoria en Megabytes

```bash
free -m
```

#### Mostrar Memoria en Gigabytes

```bash
free -g
```

## Funciones principales de `free`

- Consultar el uso de memoria RAM del sistema
- Mostrar memoria libre y utilizada
- Visualizar memoria swap
- Monitorear recursos del sistema
- Analizar consumo de memoria
- Ayudar en tareas de troubleshooting y rendimiento
- Verificar memoria disponible para aplicaciones
- Obtener información rápida del estado de la memoria

## Comando `lspci`

El comando `lspci` muestra información sobre los dispositivos conectados al bus PCI del sistema.

### Ejemplo Básico

```bash
lspci
```

#### Mostrar Información Detallada

```bash
lspci -v
```

#### Mostrar Información Muy Detallada

```bash
lspci -vv
```

#### Mostrar Dispositivos de Red

```bash
lspci | grep -i network
```

#### Mostrar Dispositivos VGA o Tarjeta Gráfica

```bash
lspci | grep -i vga
```

#### Mostrar IDs Numéricos de Dispositivos

```bash
lspci -n
```

## Funciones principales de `lspci`

- Detectar tarjetas de red
- Identificar tarjetas gráficas
- Ver controladores SATA/NVMe
- Consultar dispositivos PCI instalados
- Obtener información de hardware conectado


