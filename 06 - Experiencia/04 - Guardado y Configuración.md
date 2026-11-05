# Guardado y Configuración

## Descripción de la sección

Define cómo se conserva el progreso y qué opciones puede modificar el jugador.

## Guardado

**Tipo:** Automático. El jugador no puede guardar manualmente.

**Cuándo se guarda:**

- Al entrar a cada nivel.
- En [[02 - Niveles|Chicunamictlán]], después de recoger el tercer recuerdo y antes del combate final.
- Al terminar el epílogo, para registrar que el juego se completó.

Un recuerdo o una estadística obtenidos durante el nivel se consolidan al entrar al siguiente. Si el jugador muere antes, los recupera al repetir ese nivel.

**Qué datos se guardan:** nivel y punto de guardado actuales, vida, experiencia y nivel del personaje, curativos, recuerdos recuperados y si el juego se completó. La estructura técnica está en [[04 - Datos y Persistencia]].

**Cantidad de ranuras:** 1. Nueva partida reemplaza la existente después de una confirmación ([[02 - UI y Menús]]).

**Qué ocurre si el guardado falla:** el juego no se detiene. Muestra el aviso "No se pudo guardar", conserva el último archivo válido y vuelve a intentarlo en el siguiente punto de guardado. La recuperación de archivos dañados está en [[05 - Seguridad y Riesgos Técnicos]].

### Reglas al reanudar

| Situación | Resultado |
| --------- | --------- |
| Morir | Se recarga el último punto de guardado con **vida completa** y los demás datos guardados. Los objetos y enemigos del nivel se restauran. |
| Continuar desde el menú | Se recarga el último punto de guardado con la vida guardada. |
| Salir a mitad de un nivel | Se pierde el avance posterior al último punto de guardado. La confirmación lo advierte. |
| Morir contra el jefe final | Se repite el combate sin volver a ver el tercer recuerdo. |
| Continuar con el juego completado | Se regresa al punto de guardado previo al jefe final. |

La vida completa al reintentar evita que el jugador quede atrapado si guardó con poca vida y sin curativos. Como se revierten la experiencia y los curativos del intento fallido, tampoco se puede repetir un nivel y morir a propósito para acumularlos.

## Configuración

| Categoría | Opciones |
|---|---|
| Audio | Volumen General (100 %), Música (80 %) y Efectos (100 %), de 0 a 100 %. |
| Video | Pantalla completa o ventana (pantalla completa); resolución de 1280 × 720, 1600 × 900 o 1920 × 1080 (1920 × 1080). |
| Controles | Consulta de la asignación predeterminada. Reasignación: deseable, ver [[03 - Accesibilidad]]. |
| Accesibilidad | Reducción de movimiento (desactivada), reducción de destellos (desactivada). Tamaño de texto: deseable. |
| Jugabilidad | Mostrar indicaciones de control (activado). |

Entre paréntesis se indica el valor predeterminado. Los cambios de audio se aplican al momento; los de video, al pulsar Aplicar.

### Asignación predeterminada

| Acción | Entrada |
| ------ | ------- |
| Mover | A / D o flechas izquierda / derecha |
| Saltar | Espacio |
| Atacar | Clic derecho |
| Bloquear (mantener) | Clic izquierdo |
| Interactuar y avanzar diálogo | E |
| Usar curativo | Q |
| Pausa y regresar | Esc |

> [!note] Pendiente de [[04 - Controles]]
> La asignación toma de base el borrador de Mecánicas de la rama `feact/02-diseño`, que define WASD o flechas y clic derecho para atacar. Saltar, bloquear, interactuar y curar son una propuesta. Esta tabla debe coincidir con el mapa de controles cuando se complete esa sección.

## Restablecimiento

¿Qué opciones pueden volver a valores predeterminados?

Audio, Video, Controles, Accesibilidad y Jugabilidad se pueden restablecer por separado, con el botón Restablecer de cada categoría y una confirmación. Restablecer la configuración nunca borra la partida. El progreso solo se reemplaza al iniciar una Nueva partida.


> **Navegación:** [[00 - Índice]] · ← [[03 - Accesibilidad]] · [[01 - Arquitectura Técnica]] →
