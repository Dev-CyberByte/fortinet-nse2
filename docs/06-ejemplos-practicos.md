# 06 · Ejemplos prácticos (FortiOS)

> Ejemplos **ilustrativos** para entender la lógica. Úsalos en un laboratorio (FortiGate VM de prueba o equipo de práctica), no en producción sin revisar.

## 1. Configurar una interfaz

```
config system interface
    edit "port2"
        set alias "LAN"
        set mode static
        set ip 192.168.10.1 255.255.255.0
        set allowaccess ping https ssh
        set role lan
    next
end
```

## 2. Crear objetos de dirección

```
config firewall address
    edit "SERVIDOR-WEB"
        set subnet 192.168.10.10 255.255.255.255
    next
    edit "LAN-USUARIOS"
        set subnet 192.168.10.0 255.255.255.0
    next
end
```

## 3. Política de salida a Internet con perfiles

```
config firewall policy
    edit 1
        set name "LAN-a-Internet"
        set srcintf "port2"
        set dstintf "port1"
        set srcaddr "LAN-USUARIOS"
        set dstaddr "all"
        set action accept
        set schedule "always"
        set service "ALL"
        set nat enable
        set utm-status enable
        set ssl-ssh-profile "certificate-inspection"
        set av-profile "default"
        set webfilter-profile "default"
        set ips-sensor "default"
        set application-list "default"
        set logtraffic all
    next
end
```

**Lectura:** los usuarios de `LAN-USUARIOS` salen por `port1` con NAT, inspeccionados por AV, filtrado web, IPS y control de aplicaciones, y se registra todo.

## 4. Ruta por defecto

```
config router static
    edit 1
        set gateway 203.0.113.1
        set device "port1"
    next
end
```

## 5. Publicar un servidor (Virtual IP)

```
config firewall vip
    edit "VIP-WEB"
        set extip 203.0.113.10
        set extintf "port1"
        set mappedip "192.168.10.10"
    next
end
```

Luego se crea una política `port1 → port2` cuyo destino sea `VIP-WEB` con el servicio `HTTPS`.

## 6. Comandos de diagnóstico útiles

| Comando | Para qué |
| ------- | -------- |
| `get system status` | Versión, serial, modo de operación |
| `get system interface physical` | Estado de interfaces |
| `get router info routing-table all` | Tabla de rutas |
| `execute ping 8.8.8.8` | Prueba de conectividad desde el FortiGate |
| `diagnose sys top` | Procesos y consumo de CPU |
| `get system performance status` | CPU, memoria, sesiones |
| `diagnose sys session list` | Sesiones activas |

## 7. Debug flow (ver por qué una política bloquea o permite)

```
diagnose debug reset
diagnose debug flow filter addr 8.8.8.8
diagnose debug flow show function-name enable
diagnose debug flow trace start 20
diagnose debug enable
# ... generar tráfico ...
diagnose debug disable
diagnose debug reset
```

## Escenario de ejemplo

| Requisito | Solución |
| --------- | -------- |
| Los empleados navegan pero sin sitios de phishing | Web Filter con categoría Phishing bloqueada |
| Bloquear descargas por P2P | App Control con categoría P2P bloqueada |
| Proteger el servidor web publicado | VIP + política + IPS en esa política |
| Ver quién genera más tráfico | Logs + FortiAnalyzer / dashboards |

⬅️ [05 Security Fabric](05-security-fabric-ecosistema.md) · ➡️ [07 Glosario](07-glosario.md)
