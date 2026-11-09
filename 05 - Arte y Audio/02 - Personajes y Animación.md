# Personajes y Animación

## Descripción de la sección

Documenta cómo deben verse y comportarse visualmente los personajes.

## Requisitos por personaje

| Personaje                   | Modelo/Sprite                                                                                   | Animaciones                                                                     | VFX                                                                           | Estado     |
| --------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ---------- |
| **Yaotl (protagonista)**    | Guerrero mexica 2D con vestimenta ceremonial, espada y escudo.                                  | Idle, caminar, saltar, caer, agacharse, atacar, bloquear, recibir daño y morir. | Golpes de espada, impactos, bloqueo y recuperación de salud.                  | terminado. |
| **Quetzalli (sacerdotisa)** | [[SACERDOTISTA.svg]]                                                                            | Idle, caminar, expresiones, interacción y animaciones narrativas.               | ninguno                                                                       | terminado  |
| **Xólotl (compañero)**      | Xoloitzcuintle 2D con elementos sobrenaturales y apariencia caricaturesca.                      | Idle, caminar, correr, detenerse y reaccionar.                                  | Resplandor espiritual y partículas turquesas.                                 | terminado  |
| **Guerrero caído**          | [[guerrero caido.svg]]                                                                          | Idle, patrullar, caminar, perseguir, atacar, recibir daño y morir.              | Impactos, señales de ataque y desaparición.                                   | terminado  |
| **Gólem de Obsidiana**      | Criatura gigante formada por rocas de obsidiana morada, grietas luminosas y ornamentos dorados. | Idle, caminar, golpe descendente, barrido, recibir daño y derrumbarse.          | Grietas moradas luminosas, impactos de roca, partículas y temblores visuales. | terminado  |
| **Alma en pena**            | [[alma en pena.svg]]                                                                            | Flotar, esperar, reaccionar, interactuar y desaparecer.                         | Brillo espiritual y partículas luminosas.                                     | terminado  |
| **Murciélago del Mictlán**  | [[murcielago.svg]]                                                                              | Flotar, volar, atacar, recibir daño y morir.                                    | Estelas de movimiento, impactos y desaparición espiritual.                    | terminado  |
| **Jaguar del Mictlán**      | Criatura felina 2D de apariencia amenazante y elementos visuales mexicas.                       | Idle, caminar, correr, saltar, atacar, recibir daño y morir.                    | Zarpazos e impactos.                                                          | terminado  |
| **Espíritu del viento**     | [[espiritu del viento.svg]]                                                                     | Flotar, desplazarse, atacar, reaccionar y desvanecerse.                         | Ráfagas, remolinos y partículas espirituales.                                 | terminado  |
| **Alma errante**            | [[alma errante.svg]]                                                                            | Idle, flotar, atacar, recibir daño y desaparecer.                               | Llamas espectrales y partículas turquesas.                                    | terminado  |
| **Segador del Mictlán**     | Entidad sobrenatural de apariencia oscura y amenazante.                                         | Idle, desplazarse, atacar, recibir daño y morir.                                | Energía oscura y efectos de ataque.                                           | terminado  |
| **Señor del Mictlán**       | [[segador.svg]]                                                                                 | Idle, caminar, gesticular, ataque espiritual y reacciones.                      | Energía espiritual morada, partículas y efectos sobrenaturales.               | terminado  |
| **Guía del Mictlán**        | Personaje esquelético con penacho, manto ceremonial y bastón.                                   | Idle, caminar, interactuar y gesticular.                                        | Resplandor del bastón y partículas turquesas.                                 | terminado  |

**Nota de alcance:** El desarrollo principal contempla un número limitado de enemigos, NPC y jefes. Las propuestas adicionales de personajes no implican su incorporación automática a los niveles. Su participación deberá confirmarse antes de producir las animaciones definitivas.

## Animaciones

### Movimiento

**Idle (espera):** Animación que se reproduce cuando el personaje permanece quieto. Incluye movimientos ligeros del cuerpo, respiración, cabello, vestimenta o energía espiritual según corresponda.

**Caminar:** Secuencia de desplazamiento horizontal, con movimiento coordinado de piernas, brazos y accesorios. Debe adaptarse a la velocidad de movimiento del personaje.

**Correr:** Animación de desplazamiento rápido con pasos más amplios y movimiento dinámico del cuerpo. Se utilizará únicamente en personajes que tengan esta acción habilitada.

**Saltar:** Animación que representa el impulso del personaje al despegar del suelo. La postura debe permitir identificar claramente el inicio del salto.

**Caer:** Animación utilizada durante el descenso después de un salto o una caída desde una plataforma. Se diferencia de la animación de salto mediante la posición del cuerpo y las extremidades.

**Agacharse:** Animación del protagonista que reduce visualmente su altura y permite atravesar espacios bajos cuando la mecánica está habilitada.

Para criaturas voladoras y espíritus, las animaciones de caminar y correr se sustituyen por movimientos de vuelo, flotación o desplazamiento sobrenatural.

### Interacción

Las animaciones de interacción permiten representar visualmente las acciones de los personajes con los elementos del escenario.

- **Interactuar:** Movimiento breve utilizado al activar objetos o elementos del entorno.
- **Recoger objetos:** Animación para obtener elementos disponibles durante la exploración.
- **Abrir cofres:** Secuencia visual de apertura y obtención de recompensas.
- **Dialogar:** Gestos o cambios de expresión durante las conversaciones con NPC.
- **Interactuar con almas:** Animación y efecto espiritual utilizados durante las decisiones de ayudar o absorber.
- **Reaccionar:** Movimientos breves de sorpresa, atención o respuesta ante eventos del nivel.

### Combate

Las animaciones de combate deben comunicar con claridad el inicio, desarrollo y finalización de cada acción.

**Ataque con espada:** Animación de Yaotl al realizar un golpe, mostrando el recorrido del arma y su efecto de impacto.

**Bloqueo con escudo:** Postura defensiva en la que el protagonista coloca el escudo frente a su cuerpo para protegerse de ataques frontales.

**Ataque enemigo:** Movimiento utilizado por enemigos comunes para ejecutar sus ataques. Debe mostrar una preparación visible antes del impacto.

**Ataque del Gólem de Obsidiana:** Incluye movimientos de barrido y golpes descendentes. Sus ataques deben presentar señales visuales que permitan anticipar el daño.

**Efectos de combate:** Estelas de ataque, impactos, partículas y destellos breves. Los efectos no deben ocultar al personaje ni dificultar la identificación de peligros.

### Daño

**Recibir daño:** Animación breve que representa la reacción del personaje al ser golpeado, mediante un retroceso o cambio de postura.

**Impacto visual:** Destello temporal o partículas que indican que el personaje ha recibido daño.

**Daño mortal:** Se representa mediante la transición hacia la animación de muerte o derrota, seguida del reinicio desde el punto de guardado correspondiente.

Los efectos deben mantener la legibilidad de las acciones y evitar animaciones excesivamente largas.

### Muerte / derrota

**Muerte del protagonista:** Yaotl reproduce una animación de derrota antes de reiniciarse desde el punto de guardado del nivel.

**Muerte de enemigos comunes:** Los enemigos realizan una animación de caída, derrumbe o desaparición antes de retirarse del escenario.

**Derrota del Gólem de Obsidiana:** Su cuerpo se fragmenta en rocas y partículas de obsidiana morada, representando su destrucción.

**Desaparición de espíritus:** Las entidades sobrenaturales se desvanecen mediante efectos de energía y partículas.

Las animaciones de muerte no deben interferir con el reinicio del nivel ni con el funcionamiento de las colisiones.

## Convenciones

### Nombres de archivos

Se utilizará una nomenclatura uniforme para facilitar la organización de recursos en Unity 2D.

**Formato:**

`NombrePersonaje_Accion_Numero.png`

**Ejemplos:**

- `Yaotl_Idle_01.png`
- `Yaotl_Walk_01.png`
- `Yaotl_Jump_01.png`
- `Yaotl_Attack_01.png`
- `Yaotl_Block_01.png`
- `GuerreroCaido_Attack_01.png`
- `GolemObsidiana_Death_01.png`
- `Quetzalli_Idle_01.png`
- `Xolotl_Walk_01.png`

### Formatos y resolución

- **Formato de imagen:** svg con fondo transparente.
- **Color:** RGBA, con canal alfa.
- **Sprites:** Recursos individuales o agrupados en spritesheets.
- **Resolución:** Se definirá según el tamaño del personaje y su representación dentro de la escena.
- **Proporciones:** Deben conservarse durante todas las animaciones del mismo personaje.
- **Orientación:** Vista lateral para el desplazamiento principal del videojuego.

Las ilustraciones originales se conservarán en alta resolución para permitir modificaciones sin afectar los recursos utilizados dentro del motor.

### Animación y rigging

Se podrán utilizar animaciones cuadro por cuadro (*frame-by-frame*).



### Organización de archivos

```text
Assets/
└── Art/
    └── Characters/
        ├── Yaotl/
        ├── Quetzalli/
        ├── Xolotl/
        ├── GuerreroCaido/
        ├── GolemObsidiana/
        └── Otros/
```

Cada carpeta podrá incluir los sprites, animaciones, controladores y efectos necesarios para el personaje correspondiente.

### Reglas de consistencia

1. Todos los sprites deben conservar la misma identidad visual, proporciones y paleta de colores de su diseño aprobado.
2. Las animaciones deben utilizar el mismo punto de referencia del personaje para evitar desplazamientos involuntarios entre fotogramas.
3. Los efectos visuales deben ser reconocibles y coherentes con las reglas de color establecidas en la sección de Dirección de Arte.
4. Las ilustraciones conceptuales deberán adaptarse a sprites optimizados para Unity 2D sin perder los rasgos principales del personaje.
5. Las animaciones deben priorizar la claridad y la funcionalidad sobre el exceso de detalles.



> **Navegación:** [[00 - Índice]] · ← [[01 - Dirección de Arte]] · [[03 - Entornos]] →
