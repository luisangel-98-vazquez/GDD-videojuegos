# Arquitectura Técnica

## Descripción de la sección

Explica cómo está construido técnicamente el videojuego y cómo se comunican sus componentes.

## Arquitectura

```text
Entrada            Input System → InputReader
  ↓
Controlador        PlayerController, PlayerCombat, EnemyAI
  ↓
Lógica de juego    GameManager, LevelManager, reglas de vida y daño
  ↓
Sistemas           Progresión, inventario, interacción, diálogo, recuerdos
  ↓
Datos / Persistencia   ScriptableObjects (solo lectura), SaveSystem (JSON)
  ↓
Presentación       Animator, HUD y menús, AudioManager, cámara
```

Se trata de un juego de una sola escena activa a la vez. Cada nivel es una escena independiente, y los servicios globales persisten entre ellas.

## Componentes principales

| Componente | Responsabilidad | Dependencias |
| ---------- | --------------- | ------------ |
| `GameManager` | Estado global (Menú, Carga, Jugando, Pausa, Derrota, Final) y pausa mediante `Time.timeScale`. Persiste entre escenas. | `SceneLoader`, `SaveSystem` |
| `SceneLoader` | Carga asíncrona de escenas y pantalla de carga. | Unity SceneManagement |
| `SaveSystem` | Único componente que lee y escribe archivos. Aplica el versionado y la recuperación. | `JsonUtility`, modelos de [[04 - Datos y Persistencia]] |
| `InputReader` | Traduce el Input System en eventos y separa los mapas Gameplay y UI. | Input System Package |
| `PlayerController` | Movimiento, salto, detección de suelo y estado del personaje. | `InputReader`, Physics 2D |
| `PlayerCombat` | Ataque, bloqueo y uso de curativos. | `InputReader`, `Health`, `InventorySystem` |
| `Health` | Vida, daño, curación y muerte. Compartido por jugador, enemigos y jefe. | Ninguna |
| `EnemyAI` | Base de patrulla, detección y ataque. Variantes `FallenWarrior` y `WanderingSoul`. | `Health`, `EnemyData`, Physics 2D |
| `BossController` | Alterna los dos patrones del Señor del Mictlán con su señal previa. | `Health`, `EnemyData` |
| `Projectile` | Movimiento, colisión y bloqueo. Común a proyectiles espirituales y flechas. | Physics 2D |
| `Hazard` | Daño o muerte por agua, vacío, obsidiana y bloques móviles. | `Health` |
| `ProgressionSystem` | Experiencia, subida de nivel y mejora automática de estadísticas. | `Health`, tabla de progresión |
| `InventorySystem` | Cantidades de curativos y equipo. | `ItemData` |
| `InteractionSystem` | Detección de objetos interactivos e indicador de tecla. | `InputReader` |
| `DialogueSystem` | Presentación de líneas para xolo, alma en pena y protagonista. | `DialogueData`, `UIManager` |
| `MemorySystem` | Activación y registro de los tres recuerdos. | `MemoryData`, `UIManager` |
| `LevelManager` | Objetivo, punto de guardado y salida de cada nivel. | `GameManager`, `SaveSystem` |
| `UIManager` | HUD y menús. Solo presenta datos. | TextMeshPro, eventos de los sistemas |
| `AudioManager` | Música, efectos y volúmenes. Persiste entre escenas. | `SettingsData`, AudioMixer |

## Escenas

| Escena | Contenido |
| ------ | --------- |
| `MainMenuScene` | Menú principal y configuración. |
| `PrologueScene` | Prólogo con texto e imágenes. |
| `Level01Scene` a `Level09Scene` | Las nueve regiones de [[02 - Niveles]]. |
| `EpilogueScene` | Epílogo, finalización y créditos. |

## Comunicación

¿Cómo intercambian información los sistemas?

- **Eventos de C#:** los sistemas publican cambios (`Health.Damaged`, `Health.Died`, `ProgressionSystem.LevelUp`, `InventorySystem.Changed`) y la UI y el audio se suscriben. Toda suscripción se cancela en `OnDisable`.
- **Referencias por Inspector:** las dependencias dentro de un prefab o escena se asignan en el editor. Se evita `GameObject.Find` durante el juego.
- **Servicios globales:** solo `GameManager` y `AudioManager` persisten con `DontDestroyOnLoad` y evitan duplicados al volver al menú.
- **ScriptableObjects:** `EnemyData`, `ItemData`, `DialogueData`, `MemoryData` y `LevelData` guardan datos de diseño de solo lectura, para ajustar el balance sin modificar código.
- **Guardado:** al guardar, `SaveSystem` pide una copia del estado a los sistemas y escribe el archivo. Al cargar, reparte los datos antes de activar el nivel.

## Principios técnicos

- Bajo acoplamiento cuando sea razonable.
- Responsabilidades claras.
- Código mantenible.
- Datos separados de lógica cuando corresponda.
- Evitar dependencias innecesarias.


> **Navegación:** [[00 - Índice]] · ← [[04 - Guardado y Configuración]] · [[02 - Motor y Herramientas]] →
