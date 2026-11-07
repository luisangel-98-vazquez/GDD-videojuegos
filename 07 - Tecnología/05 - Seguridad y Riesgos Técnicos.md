# Seguridad y Riesgos Técnicos

## Descripción de la sección

Documenta riesgos técnicos y medidas para reducir fallos, pérdida de datos o abuso de sistemas.

## Riesgos

| Riesgo | Probabilidad | Impacto | Mitigación |
| ------ | ------------ | ------- | ---------- |
| Conflictos de Git en escenas y prefabs editados por varias personas | Alta | Alto | Serialización en texto, un responsable por escena a la vez, niveles divididos en prefabs y fusiones pequeñas y frecuentes. |
| Versiones distintas de Unity entre integrantes | Media | Alto | Fijar el mismo parche de 2022.3 LTS desde `ProjectVersion.txt` y actualizarlo solo mediante [[05 - Gestión de Cambios]]. |
| Arte 2D grande que supere la memoria objetivo o alargue la carga | Media | Alto | Límite de resolución por tipo de asset, Sprite Atlas, compresión y medición por nivel desde el vertical slice. |
| Bajo rendimiento en gráficos integrados por luces 2D y partículas | Media | Medio | Probar pronto en un equipo cercano al mínimo, limitar luces por escena y desactivar efectos en calidad baja. |
| Peso del repositorio por sprites y audio | Media | Medio | Mantener `.ai` y `.kra` fuera de `Assets/`, `.gitignore` de Unity y Git LFS para binarios grandes. |
| Partida bloqueada por un punto de guardado con poca vida | Baja | Alto | Reaparecer con vida completa tras morir y probarlo en cada nivel. |
| Cambios en el formato de guardado que invaliden partidas | Media | Medio | `dataVersion`, valores predeterminados y prueba con un archivo de la versión anterior. |
| Atravesar paredes, plataformas o golpes por alta velocidad | Media | Medio | Detección continua en el jugador y proyectiles, física en `FixedUpdate` y capas de colisión definidas. |
| Duplicados de servicios globales al volver al menú | Media | Medio | Patrón de instancia única y prueba del ciclo completo menú-juego-menú. |
| Suscripciones a eventos no canceladas al cambiar de escena | Media | Medio | Suscribir en `OnEnable`, cancelar en `OnDisable` y revisar la consola en cada prueba. |
| Dependencia de una sola persona para sistemas clave | Media | Alto | Revisión de cada fusión por otro integrante y documentación básica de cada sistema. |

## Datos sensibles

¿El juego almacena información personal, cuentas, estadísticas en línea u otros datos?

No. El juego no tiene cuentas, no recopila datos personales, no usa analítica y no se conecta a internet. Solo guarda de forma local el progreso y la configuración. Por ello no se cifran los archivos: se trata de un juego de un solo jugador sin clasificaciones ni economía real, y editar un archivo solo afecta la partida de quien lo hace.

## Multijugador

No aplica. _Sombras del Mictlán_ es un juego de un jugador sin conexión ([[02 - Visión del Juego]]), por lo que no se requieren autenticación, validación, autoridad de servidor, comunicación en red ni protección contra manipulación.

## Recuperación

¿Qué ocurre ante corrupción de datos, pérdida de conexión o fallo del programa?

| Situación | Respuesta del juego | Pérdida máxima |
| --------- | ------------------- | -------------- |
| `save.json` dañado o ilegible | Carga `save.bak.json` y avisa al jugador. | Un punto de guardado |
| Partida y respaldo dañados | Avisa y ofrece Nueva partida. No borra los archivos dañados hasta que el jugador lo confirme. | Toda la partida |
| `settings.json` dañado o inexistente | Crea uno con valores predeterminados. | Las preferencias |
| Error al escribir (disco lleno o sin permisos) | Conserva el último archivo válido, avisa y reintenta en el siguiente punto de guardado. | Avance posterior al último guardado |
| Cierre inesperado o fallo del programa | Al abrir, Continuar carga el último punto de guardado. La escritura segura evita archivos a medias. | Un nivel, como máximo unos 5 minutos |
| Archivo de una versión más nueva | No lo carga ni lo modifica, y avisa al jugador. | Ninguna |
| Pérdida de conexión | No aplica, el juego funciona sin conexión. | Ninguna |

Los errores se registran en `Player.log`, y ese archivo se adjunta en los reportes de [[03 - Bugs y Seguimiento]].


> **Navegación:** [[00 - Índice]] · ← [[04 - Datos y Persistencia]] · [[01 - Alcance]] →
