# Gestión de Cambios

## Descripción de la sección

El diseño de un videojuego cambia. Esta sección evita que las modificaciones importantes se pierdan o aparezcan sin evaluar sus consecuencias.

## Proceso

1. Quien propone el cambio llena la solicitud y evalúa si refuerza un [[04 - Pilares de Diseño|pilar]].
2. El responsable del área afectada estima el costo y el impacto.
3. Joel, como responsable del proyecto, aprueba o rechaza. Si afecta el alcance, se decide con todo el equipo.
4. Si se aprueba, se actualizan el GDD, el backlog y el [[03 - Registro de Decisiones]].

Se requiere solicitud para cambiar el alcance, una mecánica, el formato de guardado, la versión de Unity o una fecha de hito. Las correcciones menores no la requieren. A partir de la versión candidata (H6) solo se aceptan cambios que corrijan errores.

## Solicitud de cambio

### CC-01 — Control de mando y versión Web

**Fecha:** 2026-11-05

**Cambio propuesto:** dejar fuera de la versión objetivo el control de mando y la versión Web, como elementos deseables.

**Motivo:** [[03 - Público y Plataforma]] menciona ambos, mientras que [[03 - Requisitos Técnicos]] define PC con teclado y mouse, sin gamepads en esta fase.

**Beneficio esperado:** reduce las pruebas y permite concentrarse en la plataforma principal.

**Costo estimado:** bajo. Solo se actualiza la documentación, y Input System permite añadir el control después.

**Impacto en otros sistemas:** controles, UI, pruebas y requisitos. La tabla de plataforma de la sección 1 debe actualizarse.

**Decisión:** Pendiente.

**Responsable:** Joel

## Registro

| ID | Fecha | Cambio | Motivo | Impacto | Estado |
|---|---|---|---|---|---|
| CC-01 | 2026-11-05 | Control de mando y Web pasan a deseables. | Contradicción entre [[03 - Público y Plataforma]] y [[03 - Requisitos Técnicos]]. | Bajo: documentación, controles y pruebas. | Pendiente |
| CC-02 | 2026-11-05 | Retirar sigilo y decisiones de las características principales, o añadirlos al contenido. | [[02 - Visión del Juego]] los incluye, pero [[02 - Niveles]] no los contempla. | Bajo si se retiran; alto si se implementan. Esta sección asume que se retiran. | Pendiente |
| CC-03 | 2026-11-05 | Actualizar la duración total a 25 minutos, o recortar 5 minutos de niveles. | [[03 - Público y Plataforma]] indica 20 minutos, y los nueve niveles suman 25. | Bajo: documentación y pruebas. Las pruebas aceptan de 20 a 30 minutos. | Pendiente |
| CC-04 | 2026-11-05 | Usar un solo nombre para el jefe final: Señor del Mictlán. | [[01 - Estructura del Contenido]] lo llama también Custodio del Umbral. | Bajo: documentación. Esta sección usa Señor del Mictlán. | Pendiente |
| CC-05 | 2026-11-05 | Ajustar los datos guardados: añadir recuerdos y configuración de accesibilidad; quitar posición exacta, minijefes, habilidades y lore. | Los datos no coincidían con [[01 - Estructura del Contenido]] ni con [[02 - Niveles]]. | Medio: define el esquema inicial, antes de implementar. | Aplicado en [[04 - Datos y Persistencia]], por validar |
| CC-06 | 2026-11-05 | Reaparecer con vida completa y revertir experiencia y curativos del intento fallido. | Evita bloqueos en puntos de guardado y acumular recursos muriendo. | Medio: guardado, balance y futura sección de reglas. | Aplicado en [[04 - Guardado y Configuración]], por validar |
| CC-07 | 2026-11-05 | Añadir carpetas de scripts `Core`, `Items`, `Narrative` y de datos `Data`. | La arquitectura necesita ubicar sistemas sin carpeta asignada. | Bajo: estructura inicial del proyecto. | Aplicado en [[02 - Motor y Herramientas]], por validar |


> **Navegación:** [[00 - Índice]] · ← [[04 - Backlog del Proyecto]] · [[01 - Criterios de Calidad]] →
