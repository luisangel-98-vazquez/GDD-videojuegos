# Criterios de Calidad

## Descripción de la sección

Define qué significa que una característica esté correctamente terminada.

Las casillas se marcan al revisar cada hito de [[03 - Roadmap]]. Permanecen sin marcar porque el juego aún no se ha implementado.

## Calidad funcional

- [ ] Funciona según las reglas documentadas.
- [ ] No produce errores conocidos críticos.
- [ ] Maneja casos límite importantes.

Casos límite que se revisan siempre: pausar durante un ataque o diálogo, morir mientras se usa un curativo, usar un curativo con vida completa o sin existencias, derrotar al jefe y morir a la vez, y cerrar el juego durante un guardado.

## Calidad de experiencia

- [ ] El jugador entiende el objetivo.
- [ ] Las respuestas del juego son claras.
- [ ] La dificultad es coherente.
- [ ] La interfaz es comprensible.

## Calidad técnica

- [ ] Rendimiento aceptable.
- [ ] Sin errores críticos.
- [ ] Guardado estable.
- [ ] No existen dependencias rotas.

## Objetivos medibles

| Área | Criterio | Objetivo | Cómo se comprueba |
| ---- | -------- | -------- | ------------------ |
| Rendimiento | FPS en equipo recomendado a 1920 × 1080 | 60 FPS estables | Profiler y compilación final |
| Rendimiento | FPS en equipo mínimo a 1280 × 720 | Al menos 30 FPS (objetivo provisional) | Compilación final |
| Rendimiento | Carga entre escenas | Menos de 5 segundos | Cronómetro en cada nivel |
| Rendimiento | Memoria en ejecución | Máximo 2 GB | Memory Profiler |
| Estabilidad | Partida completa | Sin cierres ni bloqueos | Tres partidas completas |
| Guardado | Reanudar en cada punto de guardado | 100 % de los casos correctos | Casos CP-01 a CP-03 |
| Comprensión | Usuarios que entienden los controles básicos sin ayuda | Al menos 4 de 5 | Prueba de usabilidad |
| Comprensión | Usuarios que entienden por qué murieron | Al menos 4 de 5 | Entrevista posterior |
| Duración | Tiempo de una primera partida | De 20 a 30 minutos | Prueba de usabilidad |
| Dificultad | Usuarios que completan el juego | Al menos 3 de 5 | Prueba de usabilidad |
| Identidad | Usuarios que reconocen el Mictlán como ambientación | Al menos 4 de 5 | Entrevista posterior |

## Definición de terminado

Una característica se considera terminada cuando:

1. Cumple sus criterios de [[04 - Criterios de Aceptación]].
2. Se integró en la rama principal y otra persona revisó el cambio.
3. Sus casos de [[02 - Pruebas]] aprobaron en una compilación, no solo en el editor.
4. No tiene errores críticos ni altos abiertos, y la consola no muestra errores nuevos.
5. Usa los recursos finales o tiene registrado el recurso pendiente en el backlog.
6. No baja el rendimiento por debajo de los objetivos medibles.
7. El GDD refleja cómo funciona en realidad.


> **Navegación:** [[00 - Índice]] · ← [[05 - Gestión de Cambios]] · [[02 - Pruebas]] →
