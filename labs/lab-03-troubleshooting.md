# Lab 03 · Troubleshooting básico

**Objetivo:** aprender a descubrir por qué un tráfico no pasa.

## Método (de abajo hacia arriba, como con OSI)

1. **Capa física/enlace:** ¿la interfaz está *up*?
2. **Capa de red:** ¿IP y máscara correctas? ¿hay ruta por defecto?
3. **Política:** ¿existe una política que coincida? ¿está arriba de otra que bloquea?
4. **Perfiles:** ¿un perfil de seguridad bloquea el tráfico?
5. **Servicios externos:** DNS, licencias, actualizaciones.

## Comandos

```
get system interface physical
get router info routing-table all
execute ping 8.8.8.8
diagnose sys session list
```

## Debug flow

```
diagnose debug reset
diagnose debug flow filter addr 8.8.8.8
diagnose debug flow show function-name enable
diagnose debug flow trace start 20
diagnose debug enable
```

Genera tráfico desde el PC y observa si hay *policy match*, *no route* o *denied by policy*.
Al terminar:

```
diagnose debug disable
diagnose debug reset
```

## Ejercicio

Rompe a propósito el laboratorio (quita la ruta por defecto, desactiva NAT, mueve una política) y documenta el síntoma y la solución.
