# System Management commands

## Objetivo

Aprender comandos básicos para la administración de sistemas linux y la gestión del estado de nuestra máquina.

## Introducción

Linux proporciona una serie de comandos del sistema para reiniciar,apagar o cambiar de niveles que son usados frecuentemente por administradores de sistemas linux SysAdmin/DevOps/Infraestructure IT.

## Comandos de apagado y reinicio

| Comando | Descripción |
|---|---|
| `shutdown now` | Apaga el sistema inmediatamente |
| `reboot` | Reinicia el sistema |
| `poweroff` | Apaga el sistema |
| `halt` | Detiene el sistema |
| `init 0` | Cambia al runlevel 0 (apagado) |
| `init 6` | Cambia al runlevel 6 (reinicio) |
| `systemctl reboot` | Reinicia usando systemd |
| `systemctl poweroff` | Apaga usando systemd |

## Ejemplos prácticos

### Reiniciar sistema

```bash
sudo reboot
```

### Apagar sistema

```bash
sudo shutdown now
```

### Cambiar a runlevel 0

```bash
sudo init 0
```

> [!NOTE]
> Los comandos `init 0` e `init 6` son comandos tradicionales basados en SysVinit.
> En distribuciones Linux modernas se utiliza principalmente `systemctl` debido al uso de `systemd`.
> Es necesario tener privilegios para poder ejecutar esos comandos dentro de la administración de sistemas linux.

## Evidencia

Los screenshots se encuentran en la siguiente carpeta:

```
assets/screenshots/linux-commands/system-management-commands
```

## Conclusión

Los comandos de administración del sistema permiten controlar el estado operativo de Linux, incluyendo apagado, reinicio y gestión básica del sistema.

