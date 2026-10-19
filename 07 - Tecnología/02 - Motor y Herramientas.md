# Motor y Herramientas

## Descripción de la sección

Documenta las herramientas utilizadas para crear el videojuego y por qué fueron seleccionadas.

## Motor

**Motor: Unity

**Versión: 2022.3 LTS

**Renderizado: Universal Render Pipeline (URP) 2D

**Física: Unity Physics 2D

**Sistema de entrada:** Input System Package

## Lenguajes

| Lenguaje | Uso                                                                                                                              |
| -------- | -------------------------------------------------------------------------------------------------------------------------------- |
| C#       | Programación de la lógica del juego, comportamiento de personajes, mecánicas de combate, interfaz de usuario y flujo de niveles. |

## Herramientas

| Herramienta             | Propósito                                                                                                                                       | Versión                |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| Unity Editor            | Entorno principal de desarrollo, integración de assets, ensamblado de niveles y pruebas.                                                        | 2022.3 LTS             |
| Visual Studio / VS Code | Entorno de desarrollo integrado (IDE) para la escritura y depuración de código en C#.                                                           | Última versión estable |
| Adobe Illustrator       | Creación de bocetos vectoriales, diseño de interfaz de usuario                                                                                  | CC                     |
| Krita                   | Pintura digital, ilustración de escenarios, conceptualización visual de personajes.                                                             | 5.x                    |
| Huion H640P             | Tableta digitalizadora utilizada para la ilustración a mano alzada, bocetado de concept art y dibujo de assets gráficos en Krita e Illustrator. | Hardware               |
| Git / GitHub            | Control de versiones para el trabajo colaborativo, respaldo del código y control de cambios del proyecto.                                       | Última versión         |

## Dependencias

- **2D Tilemap Editor:** Para la creación y edición estructurada de los escenarios y niveles del Mictlán.
    
- **2D Animation / Sprite Shape:** Para la preparación y animación de sprites de personajes y enemigos en 2D.
    
- **TextMeshPro:** Para el renderizado de texto nítido y personalización de fuentes en la interfaz de usuario y diálogos.
    
- **Universal RP:** Paquete de renderizado optimizado para luces 2D y efectos visuales.

## Convenciones del proyecto

- Estructura de carpetas
Assets/
├── Animations/      # Clips de animación y controladores de animación
├── Audio/           # Música de fondo y efectos de sonido (SFX)
├── Fonts/           # Fuentes tipográficas del proyecto
├── Prefabs/         # Elementos reusables (jugador, enemigos, coleccionables, tramas)
├── Scenes/          # Escenas del juego (Menú principal, Niveles del Mictlán, Pantalla de Game Over)
├── Scripts/         # Código fuente en C#
│   ├── Audio/
│   ├── Enemies/
│   ├── Player/
│   └── UI/
├── Sprites/         # Recursos gráficos 2D (Personajes, Fondos, Tilesets)
└── Tilemaps/        # Paletas y mapas de azulejos para los niveles

- Nomenclatura
-- **Archivos y carpetas:** PascalCase (ej. `PlayerController`, `MainMenuScene`, `EnemySprites`).
    
- **Prefabs:** Prefijo descriptivo en PascalCase (ej. `PF_Player`, `PF_EnemyBase`, `PF_HealthPotion`).
    
- **Sprites / Texturas:** Prefijo de tipo (ej. `SP_Player_Idle`, `BG_Mictlan_Level1`).
-
- Control de versiones
-- **Herramienta:** Git con repositorio alojado en GitHub.
    
- **Estrategia de ramas:**
    
    - `main` / `master`: Código estable y probado para entregas.
        
    - `dev`: Rama principal de integración para el equipo.
        
    - **Ramas de trabajo:** `feature/nombre-funcionalidad` (ej. `feature/player-movement`, `feature/mictlan-level-1`).
        
- **Uso de `.gitignore`:** Archivo configurado para Unity (excluyendo carpetas pesadas/temporales como `Library/`, `Temp/`, `Logs/` y `obj/`).

- Formato de assets
-- **Gráficos e imágenes:** PNG con fondo transparente (Sprite 2D y UI).
    
- **Audio:** MP3 o WAV (WAV para efectos de sonido cortos; MP3 para música de fondo).
    
- **Vectorial / Arte original:** Formatos `.ai` (Illustrator) y `.kra` (Krita) guardados fuera del folder `Assets/` de Unity para edición.
-
- Convenciones de código
-- **Clases y Métodos:** PascalCase (ej. `PlayerHealth`, `TakeDamage()`).
    
- **Variables privadas:** camelCase con guion bajo al inicio (ej. `_moveSpeed`, `_currentHealth`).


> **Navegación:** [[00 - Índice]] · ← [[01 - Arquitectura Técnica]] · [[03 - Requisitos Técnicos]] →
