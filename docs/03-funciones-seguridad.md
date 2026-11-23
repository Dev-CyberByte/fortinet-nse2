# 03 · Funciones de seguridad del NGFW

Cada función se aplica mediante **perfiles de seguridad** dentro de una política de firewall (ver `04`).

## 1. Control de aplicaciones (Application Control)

- Identifica aplicaciones por **firmas y comportamiento**, no solo por puerto.
- Permite **permitir, bloquear, monitorear o limitar** por categoría (redes sociales, streaming, P2P, proxies anónimos...).
- **Ejemplo:** permitir Microsoft Teams, bloquear BitTorrent y limitar streaming en horario laboral.

## 2. IPS — Sistema de prevención de intrusiones

- Compara el tráfico con **firmas de vulnerabilidades/ataques** y detecta anomalías.
- **IDS** = detecta y alerta. **IPS** = detecta y **bloquea** en línea.
- Sirve como **parche virtual**: protege un servidor vulnerable mientras se aplica el parche real.
- **Ejemplo:** bloquear un intento de explotación contra un servidor web.

## 3. Antivirus / Antimalware

- Analiza archivos en tránsito (web, correo, transferencias).
- Combina **firmas**, **heurística** y **reputación**.
- Puede enviar archivos sospechosos a un **sandbox**.

## 4. Filtrado web (Web Filtering) y DNS

- Clasifica sitios por **categoría** (noticias, apuestas, malware, phishing...).
- **DNS filtering:** bloquea dominios maliciosos antes de que se establezca la conexión.
- **Ejemplo:** bloquear categoría "Phishing" y "Malicious websites" para todos.

## 5. Inspección SSL/TLS

- Gran parte del tráfico va cifrado; los atacantes lo aprovechan.
- El NGFW actúa como intermediario: **descifra, inspecciona y vuelve a cifrar**.

| Modo | Qué hace | Cuándo usarlo |
| ---- | -------- | ------------- |
| **Certificate inspection** | Revisa solo el certificado y datos del handshake | Ligero; clasificación básica |
| **Deep inspection** | Descifra todo el contenido | Máxima visibilidad; requiere instalar el certificado CA en los equipos |

> ⚠️ Consideraciones: privacidad (exentar banca/salud), rendimiento y certificados.

## 6. Sandboxing (análisis de amenazas avanzadas)

- Ejecuta archivos sospechosos en un **entorno aislado** para observar su comportamiento.
- Detecta malware **desconocido (zero-day)** que las firmas no conocen.
- En Fortinet: **FortiSandbox** (local) o servicio en la nube.

## 7. Prevención de fuga de datos (DLP)

- Detecta y bloquea información sensible (números de tarjeta, documentos clasificados) que intenta salir.

## 8. Identidad y control de acceso

- Políticas por **usuario o grupo**, no solo por IP.
- Integración con **Active Directory / LDAP / RADIUS / SSO**, autenticación multifactor (MFA).

## 9. Inteligencia de amenazas (Threat Intelligence)

- Los equipos reciben actualizaciones continuas de firmas y reputación.
- Fortinet las produce mediante **FortiGuard Labs** (servicios FortiGuard).

## Resumen rápido

| Función | Responde a... | Ejemplo de acción |
| ------- | ------------- | ----------------- |
| App Control | Apps no deseadas o evasivas | Bloquear P2P |
| IPS | Explotación de vulnerabilidades | Bloquear exploit |
| Antivirus | Malware conocido | Bloquear archivo infectado |
| Web/DNS Filter | Sitios peligrosos o inapropiados | Bloquear phishing |
| SSL Inspection | Amenazas ocultas en cifrado | Descifrar e inspeccionar |
| Sandbox | Malware desconocido | Detonar archivo en aislamiento |
| DLP | Fuga de información | Bloquear envío de datos sensibles |

⬅️ [02 Fundamentos](02-fundamentos-ngfw.md) · ➡️ [04 FortiGate y FortiOS](04-fortigate-fortios.md)
