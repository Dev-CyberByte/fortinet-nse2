# 01 · Evolución de la ciberseguridad

> Entender **por qué** existen los NGFW ayuda a recordar **qué hacen**. Cada generación de defensa nació para responder a un tipo de ataque que la anterior ya no detenía.

## Línea de tiempo simplificada

```
Años 80-90         Años 90            Años 2000            Años 2010+
┌────────────┐   ┌────────────┐   ┌──────────────┐   ┌──────────────────┐
│ Packet     │ → │ Stateful   │ → │ UTM          │ → │ NGFW + Security  │
│ filtering  │   │ inspection │   │ (todo-en-uno)│   │ Fabric / Zero    │
│            │   │            │   │              │   │ Trust / SASE     │
└────────────┘   └────────────┘   └──────────────┘   └──────────────────┘
 IP/puerto        Estado de la     FW + AV + IPS +     Apps, usuarios,
                  conexión         Web filter          contenido, nube
```

## Generaciones de firewall

| Generación | Qué inspecciona | Fortaleza | Limitación |
| ---------- | --------------- | --------- | ---------- |
| **Packet filter** | IP origen/destino, puerto, protocolo (capas 3-4) | Rápido y simple | No entiende conexiones ni aplicaciones; fácil de evadir |
| **Stateful** | Lo anterior + **estado de la sesión** | Permite solo respuestas legítimas a conexiones iniciadas | Sigue sin ver el contenido ni la aplicación real |
| **Proxy / application gateway** | Tráfico a nivel de aplicación (capa 7) | Inspección profunda | Lento, difícil de escalar |
| **UTM** | Firewall + AV + IPS + filtrado web + VPN en un equipo | Simplifica la gestión | Rendimiento al activar todo; visibilidad limitada de apps |
| **NGFW** | Aplicaciones, usuarios, contenido, amenazas, tráfico cifrado | Políticas por app/usuario, prevención integrada | Requiere hardware/diseño adecuado y buena configuración |

## Cómo evolucionaron las amenazas

| Etapa | Amenaza típica | Respuesta defensiva |
| ----- | -------------- | ------------------- |
| Primeros años | Virus que se propagan por disco o correo | Antivirus basado en firmas |
| Internet masivo | Gusanos, escaneo de puertos, intrusiones | Firewall perimetral, IDS/IPS |
| Web 2.0 y apps | Malware por navegador, phishing, apps evasivas | Filtrado web, control de aplicaciones |
| Amenazas avanzadas | Malware desconocido (*zero-day*), APT, ransomware | Sandboxing, análisis de comportamiento, EDR |
| Nube y movilidad | Usuarios y datos fuera del perímetro | Zero Trust, SASE, segmentación, visibilidad centralizada |

## Ideas clave para recordar

- El perímetro **ya no es una sola línea**: hay usuarios remotos, nube, IoT y SaaS.
- Las firmas **solas** no bastan: hace falta análisis de comportamiento y *threat intelligence*.
- Seguridad **integrada y automatizada** > muchos productos aislados que no se comunican.
- Gran parte del tráfico va **cifrado**; sin inspección SSL/TLS los ataques pasan inadvertidos.

## Conexión con Fortinet

Fortinet (fundada en el año 2000) impulsó el enfoque de **seguridad integrada** y diseñó procesadores propios (**ASIC / SPU**) para inspeccionar sin sacrificar rendimiento. Esa idea evolucionó hacia la **Fortinet Security Fabric** (ver `05`).

⬅️ [00 Ruta](00-ruta-nse.md) · ➡️ [02 Fundamentos NGFW](02-fundamentos-ngfw.md)
