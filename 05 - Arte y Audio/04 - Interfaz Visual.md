# Interfaz Visual

## Descripción de la sección

Documenta la información que el juego muestra al jugador y las reglas visuales de la interfaz.

## HUD

Elementos:

- Vida actual y máxima.
- Nivel y experiencia.
- Humanidad y poder espiritual.
- Objetivo o guía de la región.
- No hay minimapa ni munición.
- Contador de curativos y puntos de atributo disponibles.
- Indicadores contextuales para interactuar, atacar, curar, pausar y confirmar decisiones.

## Jerarquía visual

1. Vida, enemigo y peligro inmediato. 2. Objetivo e indicador de interacción. 3. Curativos, nivel/XP, humanidad y poder espiritual. 4. Mensajes narrativos y avisos no urgentes.

## Estados

Normal: HUD compacto. Advertencia: señal previa por color, forma y sonido. Daño: baja visible de vida y reacción breve. Éxito: confirmación de objeto, XP o decisión guardada. Error: mensaje corto si falta un requisito o falla el guardado. Bloqueo: el estado del escudo y la dirección del ataque quedan claros.

## Convenciones

**Tipografía:** sans serif legible; reservar la tipografía ornamental para títulos.

**Iconografía:** corazón/vida, recipiente/curativo, tecla para acción, indicador de interacción; acompañar color con forma o texto.

**Tamaños mínimos:** texto de cuerpo legible a 1280×720; referencia inicial 18 px a 1080p y escala proporcional.

**Contraste:** texto claro en panel oscuro y señales distinguibles sobre el arte; nunca depender solo del color.

**Animaciones:** transiciones breves; destellos limitados y opción objetivo para reducir movimiento.

## Pantallas

- Menú principal y diálogo/prólogo.
- Pausa y menú de personaje.
- Configuración (objetivo de campaña; no incluida en escenas del ZIP).
- Equipo e inventario de curativos.
- No hay minimapa; el recorrido es lateral y guiado.
- Victoria, finales y créditos (nivel 9, alcance de campaña).
- La muerte común reinicia checkpoint automáticamente; humanidad cero muestra fin del viaje.


> **Navegación:** [[00 - Índice]] · ← [[03 - Entornos]] · [[05 - Audio y Música]] →
