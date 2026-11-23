# 05 · Security Fabric y ecosistema Fortinet

## Fortinet Security Fabric

Es el enfoque de plataforma de Fortinet: **productos que se integran y comparten información** para dar visibilidad, correlación y respuesta automatizada. Se resume en tres ideas:

| Pilar | Significado |
| ----- | ----------- |
| **Amplia (Broad)** | Cubre toda la superficie: red, endpoints, nube, aplicaciones, IoT/OT |
| **Integrada (Integrated)** | Los componentes intercambian inteligencia entre sí |
| **Automatizada (Automated)** | Respuestas y políticas reaccionan sin intervención manual |

## Mapa de productos (visión general)

| Área | Producto | Para qué sirve |
| ---- | -------- | -------------- |
| **Firewall / NGFW** | FortiGate | Seguridad de red, VPN, SD-WAN |
| **Gestión** | FortiManager | Administración centralizada de configuraciones y políticas |
| **Logs y reportes** | FortiAnalyzer | Recolección de logs, correlación, reportes |
| **Análisis de malware** | FortiSandbox | Detonación de archivos en entorno aislado |
| **Endpoint** | FortiClient / FortiEDR | Protección y detección/respuesta en dispositivos |
| **Aplicaciones web** | FortiWeb | WAF: protege aplicaciones y APIs web |
| **Correo** | FortiMail | Seguridad de correo (antispam, antiphishing) |
| **Red cableada** | FortiSwitch | Switching seguro gestionado desde FortiGate |
| **Red inalámbrica** | FortiAP | Puntos de acceso gestionados |
| **Acceso remoto / nube** | FortiSASE | Seguridad entregada desde la nube para usuarios remotos |
| **Identidad** | FortiAuthenticator / FortiToken | Autenticación y MFA |
| **Orquestación y respuesta** | FortiSOAR / FortiSIEM | Automatización y correlación de eventos |
| **Inteligencia** | FortiGuard Labs | Investigación y servicios de actualización |

> Nota: nombres y portafolio evolucionan. Confirma el catálogo vigente en la web de Fortinet.

## Ejemplo de flujo integrado

```
1. Un usuario descarga un archivo sospechoso
2. El FortiGate lo envía a FortiSandbox
3. FortiSandbox lo detona y lo califica como malicioso
4. La firma se comparte con el Fabric (FortiGate, endpoints)
5. FortiAnalyzer registra el evento y genera alerta/reporte
6. El endpoint afectado se aísla automáticamente
```

## Zero Trust (idea relacionada)

- **"Nunca confiar, siempre verificar."**
- Se valida identidad, dispositivo y contexto en **cada acceso**, no solo al entrar a la red.
- Se complementa con **segmentación** para reducir movimiento lateral.

⬅️ [04 FortiGate](04-fortigate-fortios.md) · ➡️ [06 Ejemplos](06-ejemplos-practicos.md)
