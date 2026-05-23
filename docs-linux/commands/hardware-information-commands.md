# Comandos de Información del Hardware

## Objetivo

Aprender comandos básicos para la obtención de información de nuestro equipo,es de mucha utilidad para hacer diagnósticos precisos,etc.

## Introducción

Linux proporciona diferentes herramientas para consultar información del hardware del sistema desde la terminal.

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

