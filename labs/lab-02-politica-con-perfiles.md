# Lab 02 · Política de salida con perfiles de seguridad

**Objetivo:** permitir salida a Internet desde la LAN aplicando AV, Web Filter, IPS y App Control.

## Topología

```
[ PC LAN ] ── port2 (192.168.10.1) [ FortiGate ] port1 ── Internet
```

## Pasos

1. Configura `port2` con `192.168.10.1/24` y rol LAN.
2. Configura `port1` hacia Internet (DHCP o IP estática) y la ruta por defecto.
3. Crea el objeto `LAN-USUARIOS = 192.168.10.0/24`.
4. Crea la política **LAN-a-Internet**:
   - Entrada `port2`, salida `port1`, origen `LAN-USUARIOS`, destino `all`.
   - Servicio `ALL`, NAT activado.
   - Perfiles: Antivirus, Web Filter, IPS, Application Control.
   - Logging: todo el tráfico.
5. Desde el PC prueba navegar a un sitio normal.
6. Bloquea una categoría en Web Filter (por ejemplo, una de entretenimiento) y vuelve a probar.
7. Revisa **Log & Report → Forward Traffic** y **Security Events**.

## Verificación

- ¿Navega con normalidad el tráfico permitido?
- ¿Se bloquea la categoría configurada?
- ¿Aparecen los eventos en los logs?

## Reto extra

Crea una segunda política que bloquee una aplicación concreta y colócala **arriba** de la primera. Observa el efecto del orden.
