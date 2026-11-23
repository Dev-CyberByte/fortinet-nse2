<div align="center">

![Fortinet](https://img.shields.io/badge/Fortinet-NSE_2-EE3124?style=for-the-badge&logo=fortinet&logoColor=white)
![Estado](https://img.shields.io/badge/Estado-Certificado-2ea44f?style=for-the-badge&logo=checkmarx&logoColor=white)
![Nivel](https://img.shields.io/badge/Nivel-Fundamentos-1BA0D7?style=for-the-badge)
![Idioma](https://img.shields.io/badge/Idioma-Español-0A66C2?style=for-the-badge)
![Licencia](https://img.shields.io/badge/Licencia-MIT-181717?style=for-the-badge)

# Fortinet NSE 2 — Notas de estudio

**Guía de repaso en español sobre Next Generation Firewalls y el ecosistema Fortinet**

</div>

```
╔══════════════════════════════════════════════════════════════════╗
║  > Cargando módulo NSE 2...                      [██████████] ✓  ║
║  > Certificación Fortinet NSE 2                  [ COMPLETADA ]  ║
║  > Compartiendo lo aprendido                     [  ACTIVO    ]  ║
╚══════════════════════════════════════════════════════════════════╝
```

> **Aviso:** estas son **notas originales** escritas con mis propias palabras para repasar y ayudar a otros.
> No son material oficial de Fortinet, no reproducen el curso y **no contienen respuestas de examen**.
> El contenido oficial está en el [Fortinet Training Institute](https://training.fortinet.com/local/library/?category=Certification:NSE_2).

---

## ¿Para quién es este repo?

- Estudiantes de redes / ciberseguridad que van a empezar NSE 1 y NSE 2.
- Quien viene de CCNA y quiere entender cómo se ve la seguridad perimetral del lado Fortinet.
- Cualquiera que quiera un repaso rápido antes de tomar el curso.

## Contenido

| # | Documento | Qué cubre |
| - | --------- | --------- |
| 00 | [Ruta NSE y cambios 2026](docs/00-ruta-nse.md) | Niveles NSE, qué cambió en 2026, cómo se obtiene la certificación |
| 01 | [Evolución de la ciberseguridad](docs/01-evolucion-ciberseguridad.md) | Amenazas, generaciones de firewall, de packet filter a NGFW |
| 02 | [Fundamentos del NGFW](docs/02-fundamentos-ngfw.md) | Qué es un NGFW y qué lo diferencia de un firewall tradicional |
| 03 | [Funciones de seguridad](docs/03-funciones-seguridad.md) | App Control, IPS, AV, Web Filter, SSL Inspection, Sandbox |
| 04 | [FortiGate y FortiOS](docs/04-fortigate-fortios.md) | Políticas, NAT, perfiles, VPN, SD-WAN, interfaz y CLI |
| 05 | [Security Fabric y ecosistema](docs/05-security-fabric-ecosistema.md) | FortiAnalyzer, FortiManager, FortiSandbox, FortiEDR, etc. |
| 06 | [Ejemplos prácticos](docs/06-ejemplos-practicos.md) | Políticas y comandos de FortiOS comentados |
| 07 | [Glosario](docs/07-glosario.md) | Términos clave A–Z |
| 08 | [Preguntas de repaso](docs/08-preguntas-repaso.md) | Preguntas originales con respuesta razonada |
| 09 | [Recursos oficiales](docs/09-recursos.md) | Enlaces para estudiar y practicar |

### Laboratorios

| Lab | Descripción |
| --- | ----------- |
| [Lab 01](labs/lab-01-primer-acceso-fortigate.md) | Primer acceso a un FortiGate y reconocimiento de la interfaz |
| [Lab 02](labs/lab-02-politica-con-perfiles.md) | Crear una política de salida con perfiles de seguridad |
| [Lab 03](labs/lab-03-troubleshooting.md) | Troubleshooting básico de tráfico y políticas |

### Certificado

Mi evidencia de certificación está en [`certificado/`](certificado/README.md).

---

## Cómo usar este repo

1. Lee `docs/00` y `docs/01` para ubicar el contexto.
2. Estudia `02`–`05` en orden; son el núcleo del curso.
3. Practica con `06` y los labs.
4. Cierra con `08` y revisa el glosario.

## Contribuciones

¿Encontraste un error o quieres agregar algo? Abre un *issue* o un *pull request*. Ver [CONTRIBUTING.md](CONTRIBUTING.md).

## Autor

**Juan Pablo Olivares** — Estudiante ITI · Redes e Infraestructura
[GitHub](https://github.com/Dev-CyberByte) · [LinkedIn](https://linkedin.com/in/juan-pablo-olivares-71abb5323)

Ver también: [`ccna-networking-labs`](https://github.com/Dev-CyberByte/ccna-networking-labs) · [`cisco-ios-cheatsheet`](https://github.com/Dev-CyberByte/cisco-ios-cheatsheet)

---
<sub>Fortinet, FortiGate, FortiOS y NSE son marcas registradas de Fortinet, Inc. Este repositorio no está afiliado ni respaldado por Fortinet.</sub>
