# 04 · FortiGate y FortiOS

- **FortiGate** = el NGFW de Fortinet (hardware, virtual o en nube).
- **FortiOS** = el sistema operativo que corre en el FortiGate.

## Interfaces de administración

| Método | Uso |
| ------ | --- |
| **GUI (web, HTTPS)** | Configuración visual, dashboards, logs |
| **CLI (SSH / consola)** | Automatización, troubleshooting, configuración fina |
| **API REST** | Integración y automatización |
| **FortiManager** | Gestión centralizada de muchos equipos |

## Conceptos base

| Concepto | Descripción |
| -------- | ----------- |
| **Interfaz** | Puerto físico o lógico (VLAN, agregado) con IP y rol (LAN/WAN/DMZ) |
| **Zona** | Agrupación de interfaces para simplificar políticas |
| **Objetos de dirección** | IPs, subredes, rangos o FQDN reutilizables |
| **Servicios** | Protocolos y puertos (HTTP, DNS, personalizados) |
| **Horarios (Schedules)** | Cuándo aplica una política |
| **Perfiles de seguridad** | AV, Web Filter, IPS, App Control, DNS Filter, DLP... |
| **Política de firewall** | Regla que une todo lo anterior y decide el tráfico |

## La política de firewall

Cada política responde: **¿quién → hacia dónde → qué servicio → cuándo → qué hacer → con qué inspección?**

| Campo | Ejemplo |
| ----- | ------- |
| Interfaz de entrada | `lan` |
| Interfaz de salida | `wan1` |
| Origen | `LAN-Usuarios` |
| Destino | `all` |
| Servicio | `HTTP, HTTPS, DNS` |
| Horario | `always` |
| Acción | `ACCEPT` o `DENY` |
| NAT | Activado (salida a Internet) |
| Perfiles de seguridad | AV + Web Filter + IPS + App Control |
| Logging | Todo el tráfico |

### Reglas de oro

1. Las políticas se evalúan **de arriba hacia abajo; gana la primera coincidencia**.
2. Al final existe un **deny implícito**: lo no permitido se bloquea.
3. Pon lo más **específico arriba** y lo general abajo.
4. Aplica **mínimo privilegio** y activa logs.

## NAT (Network Address Translation)

| Tipo | Uso |
| ---- | --- |
| **Source NAT (SNAT)** | Los equipos internos salen a Internet con la IP pública (usa la IP de la interfaz de salida o un pool) |
| **Destination NAT (DNAT / VIP)** | Publicar un servidor interno hacia fuera (**Virtual IP**) |

## Modos de inspección

| Modo | Característica |
| ---- | -------------- |
| **Flow-based** | Inspecciona paquetes al vuelo; más rápido, menos memoria |
| **Proxy-based** | Almacena y analiza el contenido completo; inspección más profunda |

## VPN

| Tipo | Escenario |
| ---- | --------- |
| **Site-to-site IPsec** | Unir dos sedes por Internet de forma cifrada |
| **Acceso remoto (IPsec/SSL)** | Usuarios remotos entrando a la red corporativa (con FortiClient) |

## SD-WAN

- Combina **varios enlaces WAN** (MPLS, internet, LTE) y elige la mejor ruta **por aplicación** según latencia, pérdida y jitter.
- En Fortinet está **integrado en el FortiGate**, junto con la seguridad.

## Alta disponibilidad (HA)

- Dos o más FortiGate en **clúster** (activo-pasivo o activo-activo) para continuidad si uno falla.

## Logs y monitoreo

- **Forward traffic:** tráfico que atraviesa el equipo.
- **Local traffic:** tráfico hacia/desde el propio FortiGate.
- **Security events:** detecciones de los perfiles (AV, IPS, web...).
- Se pueden enviar a **FortiAnalyzer** para análisis y reportes.

⬅️ [03 Funciones](03-funciones-seguridad.md) · ➡️ [05 Security Fabric](05-security-fabric-ecosistema.md)
