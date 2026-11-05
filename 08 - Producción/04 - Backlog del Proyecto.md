# Backlog del Proyecto

## Descripción de la sección

El backlog contiene el trabajo necesario para convertir el diseño en un videojuego funcional.

## Formato de tarea

### T-05 — Controlador del protagonista

**Descripción:** implementar caminar, saltar, detección de suelo y colisiones.

**Responsable:** Luis

**Prioridad:** Alta

**Dependencias:** T-04

**Criterio de aceptación:** el personaje recorre una escena de prueba, salta entre plataformas y no atraviesa paredes ni suelos.

**Estado:** Pendiente

## Backlog

Todas las tareas tienen estado **Pendiente** hasta marcarse como terminadas. Los responsables siguen la propuesta de [[02 - Roles y Responsabilidades]]. Cada línea indica responsable, prioridad, dependencias y criterio de aceptación.

### Preproducción: H1 y H2

- [ ] **T-01 Integrar Diseño.** Esther · Alta · Sin dependencias · El contenido de `feact/02-diseño` está en la rama principal. Esa rama no comparte historial con las demás, así que debe copiarse o fusionarse con cuidado.
- [ ] **T-02 Resolver contradicciones.** Joel · Alta · Sin dependencias · CC-01 a CC-04 de [[05 - Gestión de Cambios]] tienen decisión y la sección 1 está actualizada.
- [ ] **T-03 Completar el GDD.** Luis y Esther · Alta · T-01 · Las secciones 2, 3, 4 y 5 no tienen plantillas vacías, e incluyen valores de vida, daño y experiencia.
- [ ] **T-04 Crear proyecto de Unity.** Josué · Alta · Sin dependencias · Con 2022.3 LTS, URP 2D, Input System, carpetas de [[02 - Motor y Herramientas]] y `.gitignore`; otra persona lo clona y lo abre sin errores.
- [ ] **T-05 Controlador del protagonista.** Luis · Alta · T-04 · Ver el formato de tarea.
- [ ] **T-06 Combate base.** Luis · Alta · T-05 · Atacar, bloquear, recibir daño y morir funcionan contra un objetivo de prueba.
- [ ] **T-07 Guerrero caído.** Luis · Alta · T-06 · Patrulla, detecta y ataca cuerpo a cuerpo con señal previa.
- [ ] **T-08 Guía de estilo y personaje provisional.** Ramón · Alta · Sin dependencias · Define límites de tamaño de los sprites y paleta aplicada, a partir de [[01 - Dirección de Arte]].

### Producción: H3 y H4

- [ ] **T-09 Estado global y carga de escenas.** Josué · Alta · T-04 · Menú, carga, juego y pausa funcionan y la carga dura menos de 5 segundos.
- [ ] **T-10 Sistema de guardado.** Josué · Alta · T-09 · Guarda, carga y se recupera según [[04 - Datos y Persistencia]]; aprueba CP-01, CP-02 y CP-03.
- [ ] **T-11 Progresión.** Luis · Alta · T-06, T-03 · Los enemigos dan experiencia y las estadísticas suben al alcanzar el nivel.
- [ ] **T-12 Inventario y curativos.** Luis · Alta · T-06 · Recoger y usar curativos cambia la vida y el contador; no se usan con la vida completa.
- [ ] **T-13 Interacción y diálogos.** Josué · Alta · T-05 · Se puede hablar con el xolo y activar las salidas con el indicador de tecla.
- [ ] **T-14 Recuerdos.** Josué y Esther · Alta · T-13, T-10 · Se activa la escena, se registra el recuerdo y queda guardado.
- [ ] **T-15 HUD y menús base.** Josué · Alta · T-09 · Pantallas de [[02 - UI y Menús]] navegables con teclado y con mouse.
- [ ] **T-16 Peligros del entorno.** Luis · Alta · T-06 · Agua, vacío, obsidiana y bloques móviles causan el daño o la muerte definidos.
- [ ] **T-17 Niveles 1, 2 y 3 con arte provisional.** Joel · Alta · T-07, T-12, T-13, T-16 · El capítulo 1 se completa de principio a fin (hito H3).
- [ ] **T-18 Medir rendimiento en equipo de prueba.** Josué · Alta · T-17 · Se registran FPS, memoria y carga, también en un equipo cercano al mínimo.
- [ ] **T-19 Arte final de protagonista y guerrero caído.** Ramón · Alta · T-08 · Sprites integrados sin superar el límite de memoria.
- [ ] **T-20 Animaciones de protagonista y guerrero caído.** Kevin · Alta · T-19 · Hay animaciones de reposo, caminar, saltar, atacar, bloquear, recibir daño y morir.
- [ ] **T-21 Entorno, audio y pulido de Itztépetl.** Ramón y Kevin · Alta · T-17, T-20 · El nivel cumple los criterios de calidad (hito H4).

### Producción: H5

- [ ] **T-22 Alma errante y proyectiles.** Luis · Alta · T-07 · Lanza proyectiles bloqueables y usa el mismo sistema que las flechas.
- [ ] **T-23 Niveles 4, 5 y 6.** Joel · Alta · T-21, T-22 · Se completa el capítulo 2, con coberturas y trampas de flechas.
- [ ] **T-24 Niveles 7 y 8.** Joel · Alta · T-23 · Se limita a dos enemigos activos por encuentro y el río es legible con niebla.
- [ ] **T-25 Señor del Mictlán y arena.** Luis · Alta · T-22 · Golpe bloqueable, onda saltable y señales previas; el combate se puede repetir tras morir.
- [ ] **T-26 Nivel 9 y flujo final.** Joel · Alta · T-25, T-14 · Recuerdo, guardado, combate, epílogo, finalización y créditos funcionan en orden.
- [ ] **T-27 Guion e imágenes de narrativa.** Esther y Ramón · Alta · T-03 · Prólogo, tres recuerdos, diálogos y epílogo integrados y revisados.
- [ ] **T-28 Arte de enemigos, jefe y regiones restantes.** Ramón · Alta · T-19 · Las nueve regiones son distinguibles y los peligros destacan sobre el fondo.
- [ ] **T-29 Animaciones de alma errante, jefe y xolo.** Kevin · Media · T-28 · Las señales previas del jefe se reconocen visualmente.
- [ ] **T-30 Música y efectos.** Kevin · Media · T-09 · Cada acción de [[01 - UX y Flujo del Jugador]] tiene sonido y funcionan los tres volúmenes.
- [ ] **T-31 Configuración y accesibilidad.** Josué · Media · T-15, T-10 · Se aplican y guardan las opciones de [[04 - Guardado y Configuración]].

### Pruebas y entrega: H6 y H7

- [ ] **T-32 Ejecutar casos de prueba.** Esther · Alta · T-26 · Todos los casos de [[02 - Pruebas]] tienen resultado registrado.
- [ ] **T-33 Pruebas de usabilidad.** Esther · Alta · T-26 · Al menos 5 personas ajenas al equipo juegan y se documentan los hallazgos.
- [ ] **T-34 Balance final.** Luis · Alta · T-33 · La dificultad sigue la curva de [[02 - Niveles]] y el jefe se puede vencer sin ayuda externa.
- [ ] **T-35 Corregir errores críticos y altos.** Josué · Alta · T-32 · No quedan errores críticos ni altos abiertos.
- [ ] **T-36 Compilación final para Windows.** Josué · Alta · T-35 · El ejecutable funciona en un equipo sin Unity instalado.
- [ ] **T-37 Actualizar GDD y preparar entrega.** Esther y Joel · Alta · T-36 · Decisiones, versiones y presentación están al día, y el repositorio queda etiquetado.

### Deseable

- [ ] **T-38 Control de mando.** Josué · Baja · T-36 · Todas las acciones y menús se pueden usar con control.
- [ ] **T-39 Versión Web.** Josué · Baja · T-36 · El juego carga y guarda en un navegador de escritorio.
- [ ] **T-40 Reasignación de controles y tamaño de texto.** Josué · Baja · T-31 · Los cambios se conservan al reiniciar.

## Priorización

Prioriza aquello que desbloquea otras tareas o valida primero las partes más riesgosas del proyecto.

1. **Decisiones y base técnica (T-01 a T-04):** desbloquean todo lo demás.
2. **Movimiento y combate (T-05 a T-07):** son el mayor riesgo de diversión y la base de los nueve niveles.
3. **Guardado y flujo (T-09, T-10):** afectan a todos los sistemas, por lo que cuesta más añadirlos después.
4. **MVP y vertical slice (T-17, T-21):** validan la experiencia, la calidad y la memoria antes de producir el resto del arte.
5. **Resto del contenido:** se construye sobre sistemas ya probados.


> **Navegación:** [[00 - Índice]] · ← [[03 - Roadmap]] · [[05 - Gestión de Cambios]] →
