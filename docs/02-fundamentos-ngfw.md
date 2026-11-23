# 02 · Fundamentos del Next Generation Firewall (NGFW)

## Definición

Un **NGFW** es un firewall que, además del filtrado por IP, puerto y estado de sesión, **identifica aplicaciones, usuarios y contenido**, y aplica **prevención de amenazas** en la misma plataforma.

## Firewall tradicional vs NGFW

| Característica | Firewall tradicional | NGFW |
| -------------- | -------------------- | ---- |
| Decisión basada en | IP, puerto, protocolo | IP, puerto, **aplicación, usuario, contenido** |
| Visibilidad de apps | Casi nula (todo "HTTPS" parece igual) | Identifica aplicaciones específicas (p. ej. una red social dentro de HTTPS) |
| Prevención de intrusiones | Aparte (IPS externo) | **Integrada** |
| Antimalware | Aparte | **Integrado** |
| Tráfico cifrado | Pasa sin inspección | **Inspección SSL/TLS** |
| Identidad de usuario | Solo por IP | Integración con directorio (AD/LDAP/SSO) |
| Inteligencia de amenazas | Manual | Actualizaciones continuas |

## Capacidades centrales de un NGFW

1. **Filtrado con estado** (stateful inspection).
2. **Control de aplicaciones** (Layer 7).
3. **Sistema de prevención de intrusiones (IPS)**.
4. **Antimalware / antivirus**.
5. **Filtrado web y DNS**.
6. **Inspección SSL/TLS** (tráfico cifrado).
7. **Identificación de usuarios y dispositivos**.
8. **Integración con sandbox** y *threat intelligence*.
9. **VPN** (IPsec y SSL) y, en muchos casos, **SD-WAN**.

## ¿Por qué importa el rendimiento?

Activar todas las inspecciones consume recursos. Los NGFW de Fortinet usan **procesadores de seguridad dedicados** (SPU: NP para red, CP para criptografía/contenido) para mantener el rendimiento. Al elegir un equipo se compara el *throughput* **con** funciones de seguridad activas, no solo el de firewall puro.

## Dónde se coloca un NGFW

| Ubicación | Objetivo |
| --------- | -------- |
| **Perímetro / borde** | Proteger la red interna de Internet |
| **Segmentación interna (ISFW)** | Separar zonas (servidores, usuarios, IoT) y frenar movimiento lateral |
| **Centro de datos** | Proteger cargas críticas con alto rendimiento |
| **Sucursal** | Seguridad + conectividad WAN en un equipo |
| **Nube** | Versiones virtuales (VM) para AWS, Azure, etc. |

```
Internet ──► [ NGFW perímetro ] ──► DMZ (servidores públicos)
                    │
                    └──► [ NGFW interno ] ──► LAN usuarios / IoT / servidores
```

⬅️ [01 Evolución](01-evolucion-ciberseguridad.md) · ➡️ [03 Funciones de seguridad](03-funciones-seguridad.md)
