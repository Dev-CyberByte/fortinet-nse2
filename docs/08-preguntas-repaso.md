# 08 · Preguntas de repaso

> Preguntas **originales** para practicar conceptos. No son del examen oficial ni incluyen respuestas de examen.
> Intenta responder antes de abrir cada respuesta.

---

**1. ¿Qué limitación principal tiene un firewall de filtrado de paquetes frente a un NGFW?**
<details><summary>Ver respuesta</summary>
Solo decide por IP, puerto y protocolo; no entiende sesiones ni aplicaciones, por lo que no detecta amenazas que usen puertos permitidos.
</details>

**2. ¿Qué diferencia hay entre IDS e IPS?**
<details><summary>Ver respuesta</summary>
El IDS detecta y alerta; el IPS está en línea y además <b>bloquea</b> el tráfico malicioso.
</details>

**3. ¿Por qué es necesaria la inspección SSL/TLS?**
<details><summary>Ver respuesta</summary>
Porque gran parte del tráfico es cifrado y las amenazas pueden ocultarse dentro. Sin descifrar, el NGFW no puede analizar el contenido.
</details>

**4. ¿Qué ventaja da el sandboxing frente al antivirus por firmas?**
<details><summary>Ver respuesta</summary>
Detecta malware desconocido (zero-day) observando su comportamiento en un entorno aislado, sin depender de una firma previa.
</details>

**5. Si dos políticas coinciden con el mismo tráfico, ¿cuál se aplica?**
<details><summary>Ver respuesta</summary>
La primera que coincida de arriba hacia abajo. Por eso las reglas específicas van antes que las generales.
</details>

**6. ¿Qué sucede con el tráfico que no coincide con ninguna política?**
<details><summary>Ver respuesta</summary>
Se bloquea por el <i>deny</i> implícito.
</details>

**7. ¿Qué es FortiOS y qué es FortiGate?**
<details><summary>Ver respuesta</summary>
FortiGate es el NGFW (el equipo); FortiOS es el sistema operativo que corre en él.
</details>

**8. ¿Para qué se usa un Virtual IP (VIP)?**
<details><summary>Ver respuesta</summary>
Para traducir una IP pública a un servidor interno (DNAT) y publicar servicios.
</details>

**9. ¿Qué aporta FortiAnalyzer a la Security Fabric?**
<details><summary>Ver respuesta</summary>
Centraliza logs, correlaciona eventos y genera reportes de seguridad.
</details>

**10. ¿Qué diferencia hay entre inspección flow-based y proxy-based?**
<details><summary>Ver respuesta</summary>
Flow-based analiza paquetes al vuelo (más rápido, menos memoria). Proxy-based reconstruye el contenido completo antes de analizarlo (más profundo, más recursos).
</details>

**11. ¿Qué significa Zero Trust?**
<details><summary>Ver respuesta</summary>
No confiar por defecto en nada ni nadie, dentro o fuera de la red; verificar identidad, dispositivo y contexto en cada acceso.
</details>

**12. Un usuario descarga un archivo desconocido. ¿Qué componentes pueden intervenir en una arquitectura Fortinet?**
<details><summary>Ver respuesta</summary>
FortiGate (antivirus y envío al sandbox), FortiSandbox (análisis), FortiGuard (actualización de firmas), FortiAnalyzer (registro) y el endpoint (contención).
</details>

⬅️ [07 Glosario](07-glosario.md) · ➡️ [09 Recursos](09-recursos.md)
