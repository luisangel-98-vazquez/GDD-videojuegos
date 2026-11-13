# Reglas y Estados del Juego

## Descripción de la sección

Define las reglas globales y los estados que puede atravesar el videojuego.

## Estados principales

- **Menú principal:** Nueva partida o Continuar.
- **Carga:** transición de escena con controles de juego desactivados.
- **Jugando:** controles, IA, peligros e interacciones activos.
- **Pausa:** simulación detenida; Esc reanuda y R reinicia el intento.
- **Victoria:** jefe final derrotado y selección de desenlace (alcance del nivel 9).
- **Derrota / Reintento:** muerte común reinicia en el checkpoint local, con vida completa; no muestra pantalla de derrota separada.
- **Game Over:** humanidad en cero; termina el viaje y ofrece comenzar de nuevo.
- **Créditos:** cierre del epílogo.

## Transiciones

| Estado origen | Evento | Estado destino | Condición |
|---|---|---|---|
| Menú principal | Nueva partida | Carga | Reiniciar el progreso existente tras confirmar |
| Menú principal | Continuar | Carga | Existe guardado válido |
| Carga | Escena cargada | Jugando | Se restauran datos persistentes y checkpoint de entrada |
| Jugando | Esc | Pausa | No hay diálogo modal |
| Pausa | Esc / Reanudar | Jugando | Continúa simulación |
| Jugando | Salud llega a 0 o peligro mortal | Reintento | Se restablece último checkpoint local y vida máxima |
| Jugando | Humanidad llega a 0 | Game Over | Se bloquea control y se muestra fin del viaje |
| Jugando | Usar salida de región | Carga | Objetivo de región completo; persiste el progreso |
| Jefe derrotado | Resolver elección final | Créditos | Desenlace elegido y epílogo terminado (alcance campaña) |

## Reglas globales

1. El juego es para una persona, sin conexión; Yaotl es el único personaje controlable.
2. Reintentar restaura salud, enemigos y peligros temporales; XP, objetos, equipo y decisiones persistentes no se pierden ni duplican.
3. Daño normal tiene 0.65 s de invulnerabilidad; caídas, agua mortal, aplastamiento y derrumbe ignoran escudo e invulnerabilidad.
4. El escudo protege únicamente el frente y los ataques compatibles; las ondas bajas deben saltarse.
5. Los checkpoints intermedios son de sesión; al volver a abrir el juego se carga la entrada de la región.

## Casos especiales

El ataque espiritual se desbloquea con 12 de poder, cuesta 1 de humanidad y llega a radio de 6 unidades. Si el uso lleva humanidad a cero, se activa Game Over. Xólotl cura una vez por intento cuando humanidad ≥70, la confianza no es negativa y la vida está por debajo del 30 %. Los cuatro desenlaces usan las condiciones registradas en [[01 - Premisa y Trama]].


> **Navegación:** [[00 - Índice]] · ← [[06 - Economía y Recursos]] · [[01 - Premisa y Trama]] →
