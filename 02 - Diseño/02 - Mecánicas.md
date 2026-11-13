# Mecánicas

## Descripción de la sección

Una mecánica es una regla o interacción mediante la cual el jugador puede actuar dentro del sistema del juego.

Documenta cada mecánica con suficiente detalle para que otro integrante pueda implementarla.

## Plantilla de mecánica

### Nombre de la mecánica

**Propósito:**  
¿Qué aporta a la experiencia?

**Activación:**  
¿Qué debe hacer el jugador?

**Reglas:**  
¿Qué puede y qué no puede ocurrir?

**Entrada:**  
¿Qué botón, gesto o acción la activa?

**Estado inicial:**

**Estado final:**

**Recursos utilizados:**

**Recompensa:**

**Penalización:**

**Interacciones con otras mecánicas:**

**Casos límite:**  
¿Qué ocurre en situaciones poco comunes?

## Mecánicas principales

### Mecánica 01 — Movimiento y plataformas

**Propósito:** recorrer las nueve regiones y leer peligros. **Activación:** A/D o flechas mueven; Mayús corre; Ctrl/S/↓ agacha; Espacio salta. **Reglas:** caminar 4.2, correr 7.5, agacharse 2.5 unidades/s; impulso de salto 10.3; colisiones 2D. El salto variable usa buffer 0.14 s y tolerancia de borde 0.12 s. **Estado inicial/final:** suelo o aire → suelo, aire o checkpoint tras peligro mortal. **Recursos:** ninguno. **Recompensa:** avance seguro. **Penalización:** muerte y reintento con vida completa. **Interacciones:** plataformas, trituradoras, derrumbe y zonas letales. **Casos límite:** no puede ponerse de pie bajo techo; checkpoint intermedio se conserva durante la sesión.

### Mecánica 02 — Espada y escudo

**Propósito:** derrotar enemigos y defenderse. **Activación:** J para espada; mantener K para bloquear. **Reglas:** espada hace 25 de daño base, alcance 1.55; preparación 0.16 s, impacto 0.12 s, recuperación 0.32 s. El escudo bloquea ataques compatibles al frente y reduce movimiento a 40 %; no se puede levantar durante las fases del golpe. **Estado inicial/final:** listo → preparación → impacto → recuperación → listo; bloqueo mientras se mantiene K. **Recursos:** vida del enemigo. **Recompensa:** XP por recompensa única. **Penalización:** daño recibido; invulnerabilidad normal 0.65 s. **Interacciones:** equipo, armadura, peligros, almas y jefes. **Casos límite:** el golpe no atraviesa paredes; el escudo no bloquea daño mortal ni ataques por la espalda.

### Mecánica 03 — Decisiones y progresión RPG

**Propósito:** dar consecuencias a la búsqueda y permitir desarrollar a Yaotl. **Activación:** E abre interacción; 1 ayuda, 2 absorbe y Enter confirma; Tab abre personaje. **Reglas:** ayudar/absorber modifica humanidad y poder espiritual y la decisión se guarda una vez. XP calcula nivel con umbral `20 × n × (n − 1)`; cada nivel entrega 2 puntos para vitalidad, fuerza o espíritu. **Estado inicial/final:** alma disponible → elección permanente; nivel alcanzado → puntos sin asignar/asignados. **Recursos:** XP, humanidad, poder espiritual, atributos y equipo. **Recompensa:** progreso, equipo y acceso a desenlaces. **Penalización:** absorber y usar ataque espiritual reducen humanidad; en cero, termina el viaje. **Interacciones:** Xólotl, cofres, curativos, recuerdos y finales. **Casos límite:** un mismo ID no da recompensas duplicadas al reintentar.

## Mecánicas secundarias

Recoger curativos con E y usarlos con H (40 de curación base); equipar armas, escudos y amuletos; recuperar tres recuerdos; usar ataque espiritual con L (se desbloquea a 12 de poder, cuesta 1 humanidad y tiene 5 s de enfriamiento); conversar y pausar con Esc.


> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
