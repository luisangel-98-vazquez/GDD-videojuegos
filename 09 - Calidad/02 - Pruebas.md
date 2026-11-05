# Pruebas

## Descripción de la sección

Define cómo se comprobará que el videojuego funciona como fue diseñado.

## Tipos de prueba

### Pruebas funcionales

Comprueban que una característica haga lo que debe.

**Cuándo:** antes de integrar cada característica. **Quién:** quien la implementa y otra persona del equipo.

### Pruebas de integración

Comprueban que varios sistemas funcionen correctamente juntos.

**Cuándo:** en cada hito, con una compilación de Windows. **Quién:** QA.

### Pruebas de usabilidad

Comprueban si los jugadores entienden y pueden utilizar el sistema.

**Cuándo:** una ronda breve en el vertical slice (H4) y la ronda principal en S7. **Quién:** al menos 5 personas ajenas al equipo, de preferencia dentro del [[03 - Público y Plataforma|público objetivo]]. Se les observa sin ayudarles, y al terminar se les entrevista para medir los objetivos de [[01 - Criterios de Calidad]].

### Pruebas de rendimiento

Comprueban FPS, memoria, tiempos de carga y estabilidad.

**Cuándo:** desde el MVP (H3) y en cada hito posterior. **Dónde:** un equipo cercano a los requisitos mínimos y uno recomendado, con una compilación de Windows.

## Caso de prueba

### CP-01 — Guardar y continuar

**Objetivo:** comprobar que la partida se conserva entre sesiones.

**Precondiciones:** partida nueva, con el nivel 2 alcanzado y al menos un curativo.

**Pasos:**

1. Entrar al nivel 3 y esperar el icono de guardado.
2. Anotar vida, experiencia, nivel del personaje y curativos.
3. Cerrar el juego, abrirlo otra vez y elegir Continuar.

**Resultado esperado:** el jugador aparece al inicio del nivel 3 con los mismos datos.

**Resultado obtenido:** Sin ejecutar.

**Estado:** Pendiente

### CP-02 — Reintentar contra el jefe final

**Objetivo:** comprobar que morir contra el jefe no bloquea la partida ni repite el recuerdo.

**Precondiciones:** nivel 9 alcanzado, tercer recuerdo recogido y sin curativos.

**Pasos:**

1. Entrar a la arena con poca vida.
2. Dejarse derrotar por el Señor del Mictlán.
3. Elegir Reintentar en la pantalla de derrota.

**Resultado esperado:** el jugador reaparece antes del combate con vida completa, sin volver a ver el recuerdo, y el tercer recuerdo sigue registrado.

**Resultado obtenido:** Sin ejecutar.

**Estado:** Pendiente

### CP-03 — Recuperar un guardado dañado

**Objetivo:** comprobar que un archivo dañado no impide jugar ni borra datos sin avisar.

**Precondiciones:** existen `save.json` y `save.bak.json` válidos.

**Pasos:**

1. Con el juego cerrado, reemplazar el contenido de `save.json` por texto inválido.
2. Abrir el juego y elegir Continuar.
3. Repetir dañando también `save.bak.json`.

**Resultado esperado:** primero se carga el respaldo y aparece un aviso. Con ambos archivos dañados, el juego avisa, ofrece Nueva partida y no se cierra.

**Resultado obtenido:** Sin ejecutar.

**Estado:** Pendiente

## Casos adicionales

Todos parten con estado **Pendiente** hasta su primera ejecución.

| ID | Tipo | Caso | Resultado esperado |
| --- | ---- | ---- | ------------------ |
| CP-04 | Funcional | Caminar contra una pared y saltar bajo un techo | El personaje se detiene, sin atravesar ni quedar atascado. |
| CP-05 | Funcional | Caer al agua o al vacío en los niveles 1, 5 y 8 | Se muestra la causa y se reinicia desde el punto de guardado. |
| CP-06 | Funcional | Quedar atrapado entre los bloques del nivel 2 | Muerte y reinicio. Siempre existe un paso posible en el ciclo. |
| CP-07 | Funcional | Atacar a un enemigo hasta derrotarlo | Baja su vida, desaparece y otorga experiencia una sola vez. |
| CP-08 | Funcional | Bloquear un ataque de frente y otro por la espalda | Solo el ataque frontal se bloquea. |
| CP-09 | Funcional | Bloquear flechas y proyectiles espirituales | Ambos se bloquean con el mismo resultado. |
| CP-10 | Funcional | Usar un curativo con vida completa, con daño y sin existencias | Solo se consume con daño. Los otros casos no cambian nada. |
| CP-11 | Funcional | Reunir la experiencia exacta para subir de nivel | Sube una vez, mejoran las estadísticas y aparece el aviso. |
| CP-12 | Funcional | Recoger cada uno de los tres recuerdos | Se muestra la escena y se puede consultar en el menú Recuerdos. |
| CP-13 | Funcional | Hablar con el alma en pena o ignorarla | El nivel 5 se puede completar en ambos casos. |
| CP-14 | Funcional | Golpe frontal y onda del jefe | Ambos tienen señal; el golpe se bloquea y la onda se evita saltando. |
| CP-15 | Funcional | Probar cada opción de [[04 - Guardado y Configuración]] y reiniciar | La opción se aplica y se conserva. |
| CP-16 | Funcional | Restablecer la configuración con una partida guardada | Vuelven los valores predeterminados y la partida no cambia. |
| CP-17 | Funcional | Nueva partida con una partida existente | Pide confirmación, y Cancelar conserva la partida. |
| CP-18 | Integración | Morir tras recoger experiencia, curativo y recuerdo sin pasar al siguiente nivel | Se revierten los datos y el nivel se restaura. |
| CP-19 | Integración | Pausar durante ataque, diálogo, proyectil y bloque móvil | Todo se detiene y continúa igual al reanudar, sin ejecutar acciones de más. |
| CP-20 | Integración | Ciclo menú, juego, pausa, menú y juego, repetido 5 veces | Sin audio doble, objetos duplicados ni errores en consola. |
| CP-21 | Integración | Avanzar por los nueve niveles sin morir y luego con muertes | Objetivos, salidas y guardados correctos, hasta créditos. |
| CP-22 | Integración | Sin permisos de escritura o sin espacio al guardar | El juego continúa y avisa, y conserva el último archivo válido. |
| CP-23 | Integración | Cargar un archivo con `dataVersion` anterior y uno posterior | El anterior se adapta sin perder datos. El posterior no se carga ni se modifica. |
| CP-24 | Usabilidad | Jugar el primer nivel sin instrucciones externas | El jugador usa los controles básicos y completa el nivel. |
| CP-25 | Usabilidad | Revisar los peligros de cada región, incluida la niebla | Quien juega los reconoce antes de recibir daño. |
| CP-26 | Usabilidad | Jugar sin sonido | Toda la información necesaria sigue disponible. |
| CP-27 | Usabilidad | Revisar la interfaz a 720p y 1080p | El texto es legible y ningún elemento queda cortado. |
| CP-28 | Rendimiento | Encuentro de mayor carga del nivel 7 y combate final | Cumple los FPS objetivo sin caídas sostenidas. |
| CP-29 | Rendimiento | Medir la carga de los nueve niveles | Menos de 5 segundos en todos los niveles. |
| CP-30 | Rendimiento | Jugar 30 minutos seguidos midiendo memoria | No supera 2 GB y no crece de forma sostenida. |
| CP-31 | Instalación | Ejecutar en un equipo sin Unity instalado | Inicia sin dependencias adicionales. |

Las pruebas críticas para la entrega son CP-01, CP-02, CP-03, CP-05, CP-14, CP-18, CP-21 y CP-31.


> **Navegación:** [[00 - Índice]] · ← [[01 - Criterios de Calidad]] · [[03 - Bugs y Seguimiento]] →
