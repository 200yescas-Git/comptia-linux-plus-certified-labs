# GNOME Terminator Terminal Emulator on Debian 13.4.0 Trixie

Terminator es un emulador de terminal Linux , distribuido bajo la Licencia Pública General ( GPL ) y disponible para sistemas operativos GNU/Linux . Este programa permite usar múltiples terminales divididas y redimensionadas simultáneamente en una sola pantalla, de forma similar al multiplexor de terminales tmux.

## Objetivo

Instalar el paquete de GNOME terminator para tener un mejor rendimiento a lo largo de nuestras pruebas de laboratorio en administración de sistemas Linux.

## Proceso de instalación de GNOME terminator en Debian 13.4.0 Trixie

### 1. Iniciar Debian e ir a la terminal

> [!NOTE]
>  No hay necesidad de añadir repositorios ya que Terminator forma parte de un proyecto independiente a cualquier distribución linux,ya se encuentra dentro de Debian en la última actualización de los repositorios realizado en el trasncurso de las prácticas.

```bash
sudo apt update
```

```bash
sudo apt install terminator -y
```


