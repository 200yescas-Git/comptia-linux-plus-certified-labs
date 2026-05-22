# System Management commands

## Obejtivo

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
