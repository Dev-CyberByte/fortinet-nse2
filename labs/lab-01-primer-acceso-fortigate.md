# Lab 01 · Primer acceso a un FortiGate

**Objetivo:** acceder a la GUI y CLI, y reconocer la información básica del equipo.
**Requisitos:** FortiGate VM (evaluación) o equipo de práctica, y un PC en la misma red.

## Topología

```
[ PC 192.168.1.10 ] ───── port1 (192.168.1.99) [ FortiGate ]
```

## Pasos

1. Conecta el PC al `port1` del FortiGate (o a la red virtual host-only).
2. Asigna al PC una IP en el mismo rango, por ejemplo `192.168.1.10/24`.
3. Abre `https://192.168.1.99` y acepta el certificado autofirmado.
4. Inicia sesión con el usuario administrador y cambia la contraseña.
5. Revisa el **Dashboard**: versión de FortiOS, licencias, recursos, interfaces.
6. Entra a **Network → Interfaces** y localiza `port1`, `port2`, etc.
7. Abre la **CLI** desde la GUI y ejecuta:

```
get system status
get system interface physical
```

## Preguntas de verificación

- ¿Qué versión de FortiOS corre?
- ¿Cuál es el estado de cada interfaz?
- ¿Qué métodos de acceso están permitidos en `port1`?

## Resultado esperado

Documenta con capturas (oculta serial y datos sensibles) en `assets/`.
