# Sistemas del Juego

## Descripción de la sección

Los sistemas son conjuntos de reglas y componentes que trabajan juntos: combate, inventario, IA, diálogo, progresión, economía, misiones, etc.

## Inventario de sistemas

| Sistema | Propósito | Dependencias | Estado |
|---|---|---|---|
| Movimiento 2D | Caminar, correr, agacharse, saltar y colisionar | Input System, Physics 2D | Implementado en prototipo |
| Combate y vida | Espada, escudo, daño, curación y reintento | `PlayerCombat2D`, `Health2D` | Implementado; prueba registrada para nivel 2 |
| Enemigos y peligros | IA, señal previa, obstáculos cíclicos y derrumbe | Salud, motor, `AttemptState2D` | Implementado en escenas 1–5; jefe final definido en contenido |
| Progresión RPG | XP, atributos, equipo, humanidad y poder espiritual | `RpgRules`, `ProgressStore2D` | Implementado en proyecto |
| Interacción / narrativa | Almas, Xólotl, diálogos, cofres, recuerdos y salidas | `Interactable2D`, `RpgWorld2D` | Implementado en escenas disponibles; tres recuerdos son alcance de campaña |
| Persistencia / reintento | Guardar progreso permanente y reiniciar estado temporal | JSON, respaldo, `RetryController2D` | Implementado; evidencia de nivel 2 incluida en ZIP |
| HUD y cámara | Estado, controles, objetivo, cámara lateral | Componentes del jugador y la escena | Implementado en prototipo |
| Audio y opciones | Ambiente y efectos; opciones objetivo | Unity Audio, UI | Especificación de campaña; implementación final no incluida en escenas del ZIP |

## Plantilla de sistema

### Nombre

**Objetivo:**

**Entradas:**

**Procesamiento / reglas:**

**Salidas:**

**Estados posibles:**

**Dependencias:**

**Interacciones:**

**Datos que necesita:**

**Datos que genera:**

**Riesgos:**

**Criterios de aceptación:**

## Relaciones entre sistemas

El Input System entrega acciones al motor y al combate. `Health2D` comunica daño/muerte; `RetryController2D` coordina el reinicio con `AttemptState2D`. `ProgressStore2D` recibe recompensas y decisiones con identificadores únicos, y `RpgRules` calcula nivel, atributos, equipo y desenlaces. La interfaz consulta esos datos y presenta indicaciones sin duplicar reglas.


> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →
