# Estructura del Contenido

## Descripción de la sección

Sombras del Mictlán es un videojuego RPG, aventura en 2D con desplazamiento lateral. El protagonista recorre el Mictlán para encontrar a la persona que ama, acompañado por un xoloitzcuintle que lo orienta en momentos específicos.
El contenido se organiza en un mundo, tres capítulos y nueve niveles breves y consecutivos. Cada nivel representa una región inspirada en el Mictlán y combina plataformas, combate y narrativa.

## Estructura

```text
Sombras del Mictlán
├── Prólogo: El despertar en el Mictlán
├── Capítulo 1: El inicio del recorrido
│   ├── Nivel 1: Itzcuintlán — El río de las almas
│   ├── Nivel 2: Tépetl Monamictlán — El paso entre montañas
│   ├── Nivel 3: Itztépetl — La montaña de obsidiana
│   └── Evento: Primer recuerdo del protagonista
├── Capítulo 2: Las pruebas del camino
│   ├── Nivel 4: Itzehecayan — El viento cortante
│   ├── Nivel 5: Paniecatacoyan — El camino suspendido
│   ├── Nivel 6: Timiminaloayan — El sendero de las flechas
│   └── Evento: Segundo recuerdo del protagonista
├── Capítulo 3: El último umbral
│   ├── Nivel 7: Teocoyohuehualoyan — La prueba del combate
│   ├── Nivel 8: Izmictlán Apochcalolca — El río de la niebla
│   └── Nivel 9: Chicunamictlán — El último umbral
│       ├── Evento: Tercer recuerdo del protagonista
│       └── Jefe final: Custodio del Umbral
└── Epílogo: Resolución de la búsqueda
```

## Cantidad estimada

| Tipo | Cantidad |
|---|---|
| Mundos | 1: el Mictlán |
| Capítulos | 3 |
| Niveles o zonas breves | 9 |
| Misiones principales | 1, dividida en 9 objetivos |
| Misiones secundarias | 0 |
| Tipos de enemigos comunes | 2: guerreros caídos y almas errantes |
| Jefes | 1: Señor del Mictlán |
| NPC con interacción | 2: xoloitzcuintle guía y un alma en pena |
| Tipos de objetos | 4: espada, escudo, curativo y fragmento de recuerdo |
| Recuerdos coleccionables | 3: uno por capítulo |

## Dependencias

¿Qué contenido debe existir antes de otro?

| Contenido | ¿Qué debe existir antes? |
|---|---|
| Construcción de los nueve niveles | Movimiento, salto, cámara y colisiones del protagonista. |
| Combate | Animaciones básicas, ataque, bloqueo, vida, daño y muerte. |
| Guerreros caídos | Sistema de combate y comportamiento de patrulla, detección y ataque cuerpo a cuerpo. |
| Almas errantes | Sistema de combate y comportamiento de desplazamiento, detección y ataque. |
| Progresión RPG | Enemigos que otorguen experiencia, subida de nivel y mejora automática de estadísticas. |
| Curativos e inventario | Sistema de recolección, registro de cantidades y recuperación de vida. |
| Xolo guía y alma en pena | Sistema de interacción y presentación de indicaciones o diálogos breves. |
| Tres recuerdos coleccionables | Guion de las escenas, imágenes y sistema de activación y registro. |
| Avance entre niveles | Salidas funcionales, carga de zonas y actualización del objetivo principal. |
| Guardado de partida | Datos del nivel desbloqueado, estadísticas, inventario y recuerdos obtenidos. |
| Señor del Mictlán | Combate del protagonista funcional, dos patrones de ataque y arena final. |
| Epílogo | Desenlace narrativo definido y detección de la derrota del jefe final. |




> **Navegación:** [[00 - Índice]] · ← [[04 - Diálogos y Narrativa]] · [[02 - Niveles]] →
