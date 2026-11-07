# UI y Menús

## Descripción de la sección

Define la estructura funcional de las interfaces y menús.

## Mapa de navegación

```text
Menú principal
├── Nueva partida
├── Continuar
├── Configuración
│   ├── Audio
│   ├── Video
│   ├── Controles
│   └── Accesibilidad
├── Créditos
└── Salir

Durante la partida
├── HUD
├── Diálogo
├── Escena de recuerdo
├── Pantalla de derrota
└── Pausa
    ├── Reanudar
    ├── Estado e inventario
    ├── Recuerdos
    ├── Configuración
    └── Volver al menú
```

Todos los menús se manejan con teclado y con mouse. Esc siempre regresa a la pantalla anterior.

## Pantallas

### Menú principal

**Propósito:** iniciar o retomar la partida y acceder a las opciones.

**Elementos:** título del juego, fondo del Mictlán y opciones del mapa de navegación.

**Acciones disponibles:** Nueva partida, Continuar, Configuración, Créditos y Salir.

**Estados:** con partida guardada, Continuar está disponible y seleccionado; sin partida guardada, Continuar aparece desactivado y se selecciona Nueva partida.

**Transiciones:** Nueva partida → Prólogo. Continuar → Carga → último punto de guardado. Salir → cierre del juego, con confirmación.

### Carga

**Propósito:** cubrir el cambio entre escenas, con un objetivo menor a 5 segundos.

**Elementos:** fondo oscuro, nombre de la región e icono animado.

**Acciones disponibles:** ninguna.

**Estados:** cargando; error de carga, que muestra un aviso y vuelve al menú principal.

**Transiciones:** Carga → nivel o menú principal.

### HUD

**Propósito:** mostrar el estado del personaje sin tapar la acción.

**Elementos:** barra de vida con valor numérico, nivel y barra de experiencia, contador de curativos con su tecla, objetivo actual e icono de guardado.

**Acciones disponibles:** ninguna directa. El curativo se usa con su tecla, sin abrir menús.

**Estados:** vida baja, con barra parpadeante e icono; sin curativos, con contador en gris; barra de vida del jefe visible solo en la arena final.

**Transiciones:** se oculta en diálogos, recuerdos y pausa.

### Diálogo

**Propósito:** presentar las indicaciones del xolo, la conversación con el alma en pena y los pensamientos del protagonista.

**Elementos:** nombre de quien habla, retrato si existe, texto e indicador de continuar.

**Acciones disponibles:** avanzar. Completa el texto en la primera pulsación y pasa a la siguiente línea en la segunda.

**Estados:** escribiendo texto, texto completo.

**Transiciones:** al terminar regresa al juego. El mundo permanece en pausa mientras está abierto.

### Escena de recuerdo

**Propósito:** presentar cada uno de los tres recuerdos del protagonista.

**Elementos:** imágenes estáticas, texto e indicador de continuar.

**Acciones disponibles:** avanzar y, si ya se había visto, omitir.

**Estados:** primera vista; revisión desde el menú Recuerdos.

**Transiciones:** al terminar vuelve al nivel o al menú Recuerdos.

### Pausa

**Propósito:** detener la partida y dar acceso a la información y las opciones.

**Elementos:** mundo congelado y atenuado, opciones del mapa de navegación.

**Acciones disponibles:** Reanudar, Estado e inventario, Recuerdos, Configuración y Volver al menú.

**Estados:** disponible en niveles y diálogos. No disponible en carga ni en la pantalla de derrota.

**Transiciones:** Esc o Reanudar → juego. Volver al menú → confirmación → menú principal.

### Estado e inventario

**Propósito:** consultar el progreso del personaje.

**Elementos:** vida, nivel, experiencia, ataque, espada, escudo y curativos.

**Acciones disponibles:** usar curativo y regresar.

**Estados:** curativo no disponible cuando la cantidad es 0 o la vida está completa.

**Transiciones:** regresar → pausa.

### Recuerdos

**Propósito:** volver a ver los recuerdos recuperados.

**Elementos:** tres espacios; los bloqueados aparecen como silueta sin título.

**Acciones disponibles:** abrir un recuerdo recuperado y regresar.

**Estados:** bloqueado, recuperado.

**Transiciones:** abrir → escena de recuerdo. Regresar → pausa.

### Configuración

**Propósito:** modificar las opciones descritas en [[04 - Guardado y Configuración]].

**Elementos:** pestañas de Audio, Video, Controles y Accesibilidad; botones Aplicar y Restablecer.

**Acciones disponibles:** cambiar valores, aplicar, restablecer y regresar.

**Estados:** sin cambios, con cambios pendientes.

**Transiciones:** regresar → pantalla de origen (menú principal o pausa).

### Pantalla de derrota

**Propósito:** explicar la causa de la muerte y permitir reintentar de inmediato.

**Elementos:** mensaje con la causa y opciones Reintentar y Volver al menú.

**Acciones disponibles:** Reintentar y Volver al menú.

**Estados:** único.

**Transiciones:** Reintentar → último punto de guardado. Volver al menú → menú principal, sin confirmación porque el progreso ya está guardado.

### Pantalla de finalización y créditos

**Propósito:** cerrar la experiencia después del epílogo.

**Elementos:** mensaje final, nivel alcanzado, recuerdos recuperados y créditos del equipo.

**Acciones disponibles:** avanzar y volver al menú.

**Estados:** único.

**Transiciones:** Finalización → Créditos → menú principal.

## Confirmaciones

Documenta acciones destructivas o irreversibles y cómo se confirman.

| Acción | Se confirma | Mensaje | Opción predeterminada |
| ------ | ----------- | ------- | --------------------- |
| Nueva partida con una partida existente | Sí | "Se borrará la partida guardada. ¿Continuar?" | Cancelar |
| Nueva partida sin partida existente | No | — | — |
| Volver al menú desde la pausa | Sí | "Regresarás al último punto de guardado. ¿Salir?" | Cancelar |
| Salir del juego | Sí | "¿Salir de Sombras del Mictlán?" | Cancelar |
| Restablecer configuración | Sí | "¿Restablecer los valores de esta categoría?" | Cancelar |
| Cambiar resolución | Sí, con cuenta atrás | "¿Conservar este modo de video?" Se revierte en 10 segundos | Revertir |


> **Navegación:** [[00 - Índice]] · ← [[01 - UX y Flujo del Jugador]] · [[03 - Accesibilidad]] →
