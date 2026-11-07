# Accesibilidad

## Descripción de la sección

La accesibilidad busca que el mayor número posible de jugadores pueda comprender y utilizar el videojuego.

## Opciones previstas

Una casilla marcada indica que la opción forma parte de la versión objetivo. La tabla siguiente explica cada decisión.

- [ ] Tamaño de texto
- [x] Subtítulos
- [x] Contraste
- [ ] Modo para daltonismo
- [ ] Reasignación de controles
- [ ] Sensibilidad
- [x] Reducción de movimiento
- [x] Reducción de destellos
- [ ] Asistencia de apuntado
- [ ] Dificultad ajustable
- [x] Volumen independiente
- [x] Indicadores visuales para sonidos importantes

| Opción | Decisión | Implementación o motivo |
| ------ | -------- | ----------------------- |
| Tamaño de texto | Deseable | Normal y Grande, si queda tiempo. La fuente base se diseña legible a 720p. |
| Subtítulos | Incluida | Toda la narrativa se presenta como texto, por lo que no se pierde información sin audio. |
| Contraste | Incluida por diseño | Personajes, enemigos, peligros y objetos deben distinguirse del fondo. Es una regla de arte, no una opción del menú. |
| Modo para daltonismo | No incluido | Se sustituye por diseño redundante: la información de color también usa icono, forma o texto. |
| Reasignación de controles | Deseable | Input System la permite, pero la interfaz y sus pruebas añaden trabajo. Primero se cierra el juego base. |
| Sensibilidad | No aplica | El mouse no controla cámara ni puntería. |
| Reducción de movimiento | Incluida | Desactiva la sacudida de cámara y reduce el movimiento de fondos. |
| Reducción de destellos | Incluida | Sustituye los destellos de pantalla por parpadeos suaves y limita las partículas intensas. |
| Asistencia de apuntado | No aplica | Los ataques son cuerpo a cuerpo y siguen la dirección del personaje. |
| Dificultad ajustable | No incluida | La curva es única, y la ayudan los puntos de guardado frecuentes, los curativos y la vida completa al reintentar. |
| Volumen independiente | Incluida | General, Música y Efectos. |
| Indicadores visuales | Incluida | Toda señal sonora de peligro tiene su señal visual previa. |

## Consideraciones

Documenta cualquier necesidad específica derivada del diseño del juego.

- **Lectura sin límite de tiempo:** diálogos y recuerdos avanzan cuando el jugador lo decide, y la partida se puede pausar durante un diálogo.
- **Rojo y verde:** daño y curación usan colores que pueden confundirse con daltonismo. El curativo debe llevar icono propio y los peligros deben reconocerse por su forma y su señal previa.
- **Niebla y viento:** en [[02 - Niveles|Izmictlán Apochcalolca]] la niebla es solo visual y debe permitir distinguir plataformas y peligros; en [[02 - Niveles|Itzehecayan]] el viento no altera el movimiento.
- **Secuencias de ritmo:** los bloques de Tépetl Monamictlán y las trampas de flechas se basan en ciclos regulares y visibles. No exigen reacciones rápidas sin aviso, sino observar el patrón.
- **Pulsación sostenida:** bloquear requiere mantener una tecla. Si se añade la reasignación, también se evaluará una opción de alternar.
- **Lenguaje y contenido:** los términos en náhuatl se muestran con su traducción en el nombre de cada región. El prólogo avisará que el juego es una ficción inspirada en la mitología mexica, no una recreación histórica.

> [!warning] Fuera de alcance
> No se plantea soporte de lectores de pantalla ni navegación por voz en esta versión.


> **Navegación:** [[00 - Índice]] · ← [[02 - UI y Menús]] · [[04 - Guardado y Configuración]] →
