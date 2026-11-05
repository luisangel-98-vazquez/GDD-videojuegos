# UX y Flujo del Jugador

## Descripción de la sección

UX (experiencia de usuario) describe qué tan comprensible, cómoda y coherente resulta la interacción con el videojuego.

## Flujo principal

```text
Inicio → Menú → Nueva partida → Prólogo → Nivel 1 (tutorial) → Niveles 2 a 8 → Nivel 9 (jefe final) → Epílogo → Pantalla de finalización → Créditos → Menú
```

Flujos secundarios:

```text
Menú → Continuar → Último punto de guardado → Juego
Juego → Pausa → Juego
Juego → Pausa → Menú (se conserva el último punto de guardado)
Juego → Muerte → Pantalla de derrota → Último punto de guardado → Juego
Fin de nivel → Carga → Guardado automático → Siguiente nivel
```

## Primeros minutos

Documenta exactamente qué descubre y aprende el jugador.

El prólogo y [[02 - Niveles|Itzcuintlán]] funcionan como tutorial integrado: cada acción se enseña cuando hace falta usarla, sin pantallas de instrucciones separadas.

| Momento | Qué ocurre | Qué aprende el jugador |
| ------- | ---------- | ---------------------- |
| Prólogo | Texto e imágenes presentan el despertar en el Mictlán y la búsqueda de la sacerdotisa. Se puede adelantar con una tecla. | Quién es el protagonista y por qué está ahí. |
| Orilla inicial | Aparece la indicación de caminar y, ante el primer desnivel, la de saltar. | Moverse y saltar. |
| Encuentro con el xolo | El xolo espera en un punto fijo y señala la ruta. Aparece la indicación de interactuar. | Interactuar y que el xolo orienta el camino. |
| Plataformas sobre el río | Primeros saltos con el agua mortal visible debajo. | Que caer al agua provoca la muerte y que se reinicia sin perder mucho avance. |
| Guerrero caído | Primer enemigo, en terreno plano y seguro. Aparece la indicación de atacar. | Atacar, recibir daño y ganar experiencia. |
| Curativo | Objeto visible cerca del combate. Aparecen las indicaciones de recoger y de usar el curativo si hay daño. | Recoger objetos y recuperar vida. |
| Orilla de salida | Se interactúa con el acceso a las montañas. | Cómo se termina un nivel. |

Bloquear no se enseña aquí: se introduce en [[02 - Niveles|Itztépetl]], el nivel 3, junto con los fragmentos de recuerdo.

## Retroalimentación

Para cada acción importante define:

**Entrada → Respuesta visual → Respuesta sonora → Resultado**

| Entrada o evento | Respuesta visual | Respuesta sonora | Resultado |
| ---------------- | ---------------- | ---------------- | --------- |
| Caminar | Animación de caminata | Pasos según la superficie | El personaje se desplaza |
| Saltar | Animación de salto y polvo al aterrizar | Impulso y aterrizaje | Se alcanza otra plataforma |
| Atacar | Animación y trazo de la espada | Corte al aire | Se activa el golpe durante un instante |
| Golpe acertado | Destello en el enemigo y pausa muy breve | Impacto | El enemigo pierde vida |
| Derrotar enemigo | Disolución del enemigo y experiencia en turquesa | Disolución y ganancia | Se suma experiencia |
| Bloquear con éxito | Chispa en el escudo | Choque metálico | No se recibe daño |
| Recibir daño | Parpadeo rojo y sacudida leve | Golpe y quejido | Baja la barra de vida y hay un breve margen de invulnerabilidad |
| Señal de ataque enemigo | Pose previa o brillo antes del impacto | Aviso distintivo | El jugador puede bloquear o esquivar saltando |
| Recoger curativo | Brillo verde y contador animado | Recolección | Aumenta el contador de curativos |
| Usar curativo | Partículas verdes | Curación | Sube la vida y baja el contador |
| Interactuar | Indicador sobre el objeto y resaltado | Confirmación | Se abre el diálogo o se activa el acceso |
| Recoger recuerdo | Brillo dorado y transición a la escena | Tema del recuerdo | Se muestra y registra el recuerdo |
| Subir de nivel | Aviso en el HUD y brillo dorado | Fanfarria corta | Mejoran las estadísticas automáticamente |
| Guardado automático | Icono en una esquina durante 2 segundos | Sin sonido | Se actualiza el punto de guardado |
| Muerte | Animación y fundido a la pantalla de derrota | Golpe grave y silencio | Se ofrece reintentar |

Los colores siguen [[01 - Dirección de Arte]]: verde para curación, rojo para daño y peligro, turquesa para energía y dorado para recompensas. Ninguna información depende solo del color (ver [[03 - Accesibilidad]]).

## Fricción intencional

¿Qué dificultad forma parte del diseño y qué dificultad es simplemente mala experiencia de usuario?

**Fricción intencional (se conserva):**

- Calcular el momento para pasar entre los bloques de [[02 - Niveles|Tépetl Monamictlán]].
- Administrar los curativos para llegar con reservas al jefe final.
- Observar las señales de ataque antes de bloquear o saltar.
- Repetir el nivel actual tras morir.
- La incertidumbre sobre lo ocurrido con la sacerdotisa, que se resuelve con los recuerdos.

**Mala experiencia (se debe eliminar):**

- Morir por un peligro que no se distingue del fondo, también en las zonas con niebla.
- Recibir un ataque sin señal previa.
- Repetir diálogos, recuerdos o escenas ya vistos tras morir.
- Perder avance de más de un nivel.
- Quedar sin vida ni curativos en un punto de guardado sin posibilidad de avanzar.
- Tiempos de carga mayores a 5 segundos ([[03 - Requisitos Técnicos]]).
- Tener que abrir un menú para usar un curativo durante el combate.

## Descubrimiento

¿Cómo sabe el jugador:

- **Qué hacer?** El HUD muestra siempre una línea con el objetivo actual del nivel y las indicaciones de control aparecen cuando se necesitan por primera vez.
- **Dónde ir?** El avance es lineal de izquierda a derecha, y el xolo, la iluminación y las plataformas señalan la ruta. El xolo solo aparece en puntos fijos.
- **Qué puede interactuar?** Los objetos interactivos tienen contorno claro y muestran el indicador de la tecla al acercarse. Solo los elementos con este indicador se pueden usar.
- **Qué ocurrió?** Cada acción tiene la respuesta visual y sonora de la tabla anterior; los cambios de vida, experiencia y curativos se ven en el HUD.
- **Por qué ganó o perdió?** La pantalla de derrota nombra la causa ("Derrotado por un guerrero caído", "Caíste al río"). Al vencer al jefe se pasa al epílogo y a la pantalla de finalización.


> **Navegación:** [[00 - Índice]] · ← [[05 - Audio y Música]] · [[02 - UI y Menús]] →
