# Enemigos y NPC

## Descripción de la sección

Documenta las entidades controladas por el juego y su comportamiento.

## Plantilla de enemigo

### Guerrero caído

**Nombre:** Guerrero caído.

**Rol de combate:**

Enemigo común que aparece en los niveles 1 al 4. Su función es atacar a Yaotl y dificultar su avance por los escenarios.

El nivel 5 no tiene guerreros caídos: su dificultad proviene de los saltos y de las piedras que ruedan. Su presencia en los niveles 6 al 9 está pendiente de definir.

**Comportamiento:**

El guerrero caído patrulla una zona determinada. Cuando detecta a Yaotl, comienza a perseguirlo hasta encontrarse a una distancia adecuada para atacar.

Si Yaotl se aleja demasiado o sale de su rango de detección, el enemigo deja de perseguirlo y puede regresar a su zona de patrullaje.

En los niveles 2 y 3 los guerreros son más hábiles: buscan a Yaotl en el último lugar donde lo vieron, esquivan algunos golpes, encadenan dos ataques y cambian el ritmo antes de golpear.

**Vida:**

60 puntos en los niveles 2 y 3.

**Daño:**

18 por golpe en los niveles 1, 2 y 4; 16 en el nivel 3.

**Defensas:**

La mayoría no tiene una defensa especial y recibe daño de los ataques de Yaotl.

Algunos guerreros del nivel 3 llevan un escudo que detiene los golpes de frente. El escudo solo baja durante su recuperación.

**Velocidad:**

- Patrullaje: 1.1 m/s.
- Persecución: 2.5 m/s en los niveles 1 y 4; 3 m/s en el nivel 2 y 3.1 m/s en el nivel 3.

**Rango de detección:**

Detecta a Yaotl a 7 metros en los niveles 1 y 4, y a 8 metros en los niveles 2 y 3.

**Ataques:**

- Ataque cuerpo a cuerpo cuando Yaotl está dentro de su alcance (1.6 metros).
- Embestida: algunos guerreros se lanzan hacia Yaotl desde lejos después de un aviso.
- Lanzamiento: algunos guerreros arrojan un proyectil a distancia.

**Debilidades:**

- Tiene un alcance de ataque limitado.
- Puede recibir daño mientras se encuentra dentro del alcance de Yaotl.
- Sus movimientos y ataques pueden ser reconocidos por el jugador.
- Después de atacar tiene un momento de recuperación en el que puede recibir daño.
- El escudo de Yaotl bloquea sus golpes frontales.

**Recompensa:**

20 puntos de experiencia al derrotarlo.

**Estados de IA:**

1. **Patrullar:** recorre una zona establecida.
2. **Detectar:** identifica a Yaotl dentro de su rango.
3. **Perseguir:** se desplaza hacia Yaotl.
4. **Atacar:** ejecuta su ataque cuando está suficientemente cerca.
5. **Buscar:** intenta localizar nuevamente a Yaotl cuando lo pierde, durante unos 2.5 segundos.
6. **Regresar:** vuelve a su zona de patrullaje si no encuentra al jugador.
7. **Morir:** se reproduce su animación de muerte cuando su vida llega a cero.

```text
Patrullar → Detectar → Perseguir → Atacar
                ↓
         Perder objetivo
                ↓
              Buscar
                ↓
       Regresar a patrullar

Vida = 0 → Morir
```

### Gigante de Obsidiana

**Nombre:** Gigante de Obsidiana.

**Rol de combate:**

Subjefe que aparece en el nivel 3, Itztépetl. Representa un enfrentamiento de mayor dificultad que los guerreros caídos.

**Comportamiento:**

Permanece en una zona específica del escenario y comienza el combate cuando Yaotl entra en el área del enfrentamiento.

Sus ataques siguen patrones que el jugador debe reconocer para encontrar oportunidades de atacar.

**Vida:**

250 puntos.

**Daño:**

22 por cada barrido.

**Defensas:**

Su cuerpo está cubierto de obsidiana. No tiene una defensa adicional: recibe daño cuando Yaotl lo golpea.

**Velocidad:**

No persigue a Yaotl. Permanece en su zona y ataca desde ahí.

Al perder la mitad de su vida pasa a una segunda fase en la que se recupera más rápido entre ataques.

**Rango de detección:**

El enfrentamiento comienza cuando Yaotl entra en la zona del subjefe.

**Ataques:**

- **Barrido:** golpe horizontal anunciado por un aviso. Se bloquea con el escudo.
- **Golpe al suelo:** genera una onda baja que avanza por el piso. Se esquiva saltando.

**Debilidades:**

El jugador debe observar sus movimientos y aprovechar los momentos en que pueda atacarlo sin recibir daño.

Después de cada ataque se recupera durante un momento, marcado por una grieta amarilla, en el que Yaotl puede contraatacar.

**Recompensa:**

- 150 puntos de experiencia.
- Permite recuperar el primer recuerdo en el altar y continuar el recorrido del nivel 3.

Al ser derrotado, el gigante parece reconocer a Yaotl: «Tú no deberías estar aquí». Antes de deshacerse en fragmentos añade: «Ya moriste una vez antes».

**Estados de IA:**

1. **Esperar:** permanece en su zona antes del combate.
2. **Detectar:** reconoce la entrada de Yaotl.
3. **Atacar:** utiliza sus ataques contra el jugador.
4. **Recibir daño:** reacciona cuando Yaotl consigue golpearlo.
5. **Morir:** termina el enfrentamiento cuando su vida llega a cero.

```text
Esperar → Detectar → Atacar
                        ↓
                  Recibir daño
                        ↓
                 Continuar combate

Vida = 0 → Morir
```

### Alma furiosa

**Nombre:** Alma furiosa.

**Rol de combate:**

Enemigo que aparece en los niveles 2 y 3. Es un alma que flota dentro de una zona y ataca a Yaotl con embestidas.

**Comportamiento:**

Recorre su zona flotando. Cuando ve a Yaotl, se acerca y se mantiene a cierta distancia. Antes de atacar brilla y marca la dirección de su embestida. Poco antes de lanzarse fija esa dirección, por lo que el jugador puede apartarse.

Si ve venir un golpe de espada, puede esquivarlo. Cuando ha perdido la mitad de su vida, encadena una segunda embestida más rápida.

**Vida:**

50 puntos.

**Daño:**

16 por embestida.

**Defensas:**

No tiene defensa especial. Puede esquivar algunos golpes mientras no está atacando.

**Velocidad:**

Embestida rápida (8 m/s). Fuera del ataque se mueve despacio.

**Rango de detección:**

Detecta a Yaotl a 7.5 metros, siempre que esté dentro de su zona y no haya paredes entre ambos.

**Ataques:**

- Embestida en línea recta después de un aviso.

**Debilidades:**

- El aviso muestra la dirección del ataque.
- Durante la embestida y la recuperación no puede esquivar.
- Después de embestir queda expuesta durante un momento.

**Recompensa:**

10 o 25 puntos de experiencia, según el alma.

**Estados de IA:**

1. **Patrullar:** flota dentro de su zona.
2. **Acechar:** se acerca a Yaotl y se mantiene a distancia.
3. **Aviso:** marca la dirección de su embestida.
4. **Embestir:** se lanza en línea recta.
5. **Recuperarse:** queda expuesta a los ataques.
6. **Esquivar:** se aparta de un golpe de espada.
7. **Morir:** desaparece cuando su vida llega a cero.

```text
Patrullar → Acechar → Aviso → Embestir → Recuperarse
                                              ↓
                                           Acechar

Golpe de espada cercano → Esquivar
Vida = 0 → Morir
```

### Entidad ancestral

**Nombre:** Entidad ancestral.

**Rol de combate:**

Jefe final del videojuego. Aparece en el nivel 9, Chicunamictlán, donde Yaotl debe enfrentarla para liberar el alma de Quetzalli.

**Comportamiento:**

El combate comienza después de la conversación en la que la entidad revela su verdadero plan.

Durante el enfrentamiento utiliza dos ataques principales. El jugador debe reconocer sus movimientos, evitar recibir daño y atacar cuando encuentre una oportunidad.

**Vida:**

Pendiente de definir.

**Daño:**

Pendiente de definir.

**Defensas:**

Pendiente de definir según el diseño del jefe final.

**Velocidad:**

Pendiente de definir.

**Rango de detección:**

El jefe se activa cuando comienza el enfrentamiento final dentro de su área de combate.

**Ataques:**

- Ataque principal 1: pendiente de especificar.
- Ataque principal 2: pendiente de especificar.

**Debilidades:**

- Sus ataques siguen patrones que el jugador puede reconocer.
- Presenta momentos en los que puede recibir daño.
- Puede ser derrotada utilizando las habilidades de combate de Yaotl.

**Recompensa:**

- Liberación del alma de Quetzalli.
- Acceso a la decisión que determina el final de la historia.

**Estados de IA:**

1. **Esperar:** permanece inactiva hasta que termina la conversación previa.
2. **Iniciar combate:** comienza el enfrentamiento.
3. **Atacar:** ejecuta uno de sus dos ataques.
4. **Recibir daño:** registra los golpes de Yaotl.
5. **Continuar combate:** vuelve a ejecutar sus patrones mientras tenga vida.
6. **Morir:** termina el combate y activa la secuencia narrativa final.

```text
Esperar → Iniciar combate
                ↓
              Atacar
                ↓
           Recibir daño
                ↓
        Continuar combate

Vida = 0 → Derrota del jefe
                ↓
       Liberación de Quetzalli
                ↓
           Decisión final
```

## Plantilla de NPC

### Xólotl — Guía espiritual

**Nombre:** Xólotl.

**Función:**

Es el xoloitzcuintle que acompaña a Yaotl durante su recorrido por el Mictlán.

Su función principal es guiar al protagonista y proporcionarle información sobre el inframundo. También observa sus decisiones para comprobar si conserva sus recuerdos y humanidad.

**Ubicación:**

Aparece desde el nivel 1, Itzcuintlán, y acompaña a Yaotl durante su viaje por las nueve regiones.

**Interacción:**

El jugador puede avanzar sus conversaciones cuando se activan las escenas narrativas.

Después de la escena 1, el jugador también puede hablar con Xólotl en cualquier momento, acercándose a él o desde el menú del personaje. En cada nivel puede preguntarle cómo avanzar y qué es lo que no le está diciendo.

Xólotl es controlado por el sistema y no puede ser manejado directamente por el jugador.

Camina delante de Yaotl, lo espera si se detiene y regresa con él si se aleja. Cuando detecta un peligro cercano, como un guerrero, un alma furiosa, las montañas que se cierran o el Gigante, muestra una alerta y avisa al jugador.

**Diálogos:**

Sus conversaciones principales se presentan en:

- **Nivel 1:** explica a Yaotl que está muerto y que Quetzalli todavía puede salvarse.
- **Niveles 1 al 5:** responde preguntas sobre cada región y avisa de los peligros cercanos.
- **Nivel 8:** revela que su misión también consistía en observar las decisiones de Yaotl.
- **Nivel 9:** participa en la conversación posterior al combate final y en los desenlaces correspondientes.

Los diálogos completos se encuentran en la sección *04 - Diálogos y Narrativa*.

**Condiciones:**

Sus intervenciones narrativas se activan al llegar a los puntos correspondientes de la historia.

No participa directamente en los combates ni resuelve los obstáculos por el jugador.

Su actitud depende de la humanidad de Yaotl y de la confianza entre ambos:

- Si la humanidad es alta (70 o más) y la confianza no es negativa, una vez por intento cura a Yaotl cuando está a punto de caer.
- Si la humanidad es baja (menos de 30) o la confianza es negativa, camina lejos de Yaotl y no lo ayuda.

La confianza aumenta o disminuye según lo que Yaotl le responda en las conversaciones.

**Recompensas / información:**

- Información sobre el Mictlán.
- Orientación durante el recorrido.
- Revelación de su misión en el nivel 8.
- Información relacionada con la decisión final.
- Avisos de peligro durante el recorrido.
- Curación ocasional si Yaotl conserva su humanidad.

### Alma en pena

**Nombre:** Alma en pena.

**Función:**

NPC que permite conocer las consecuencias de perder los recuerdos y la identidad dentro del Mictlán.

**Ubicación:**

Nivel 5 — Paniecatacoyan, en una plataforma estable del camino suspendido.

**Interacción:**

Yaotl puede acercarse al alma y activar una conversación. La interacción es opcional, por lo que también puede continuar sin hablar con ella.

**Diálogos:**

El alma explica que ha olvidado su nombre y parte de su pasado.

Durante la conversación, le pregunta a Yaotl si todavía recuerda quién es y le advierte sobre el riesgo de perder sus recuerdos.

El diálogo completo se encuentra en la escena 4 de *04 - Diálogos y Narrativa*.

**Condiciones:**

- Yaotl debe acercarse a la zona donde se encuentra el NPC.
- El jugador debe activar la interacción.
- La conversación no es obligatoria para completar el nivel.

**Recompensas / información:**

Proporciona información sobre la pérdida de recuerdos y la importancia de conservar la identidad.

No se ha establecido una recompensa de experiencia, objetos o poder espiritual por esta conversación.

### Almas del recorrido

**Nombre:** Almas del recorrido.

**Función:**

NPC que representan a los muertos que no han podido avanzar. Permiten que el jugador decida si ayuda a cada alma o absorbe su energía.

**Ubicación:**

- Nivel 1 — Itzcuintlán: un alma.
- Nivel 2 — Tépetl Monamictlán: dos almas.
- Nivel 3 — Itztépetl: tres almas.
- Nivel 4 — Itzehecayan: dos almas.

**Interacción:**

Yaotl puede acercarse y escuchar al alma. Después elige entre ayudarla, absorber su energía o dejarla por ahora. Ayudar y absorber piden una confirmación porque la decisión es permanente.

**Diálogos:**

Cada alma muestra una frase breve sobre su situación. Por ejemplo: «Esta alma repite un nombre que ya no sabe si es el suyo».

Si la humanidad de Yaotl es alta, el alma confía en él y le da una pista. Si ha absorbido muchas almas, las demás le temen.

**Condiciones:**

- Yaotl debe acercarse al alma y activar la interacción.
- Cada alma solo puede recibir una decisión, que no se repite al morir.
- La interacción no es obligatoria para completar el nivel.

**Recompensas / información:**

- Ayudar: aumenta la humanidad. Por ejemplo, el alma del nivel 1 da +8.
- Absorber: aumenta el poder espiritual y reduce la humanidad. Por ejemplo, el alma del nivel 1 da +12 de poder y −10 de humanidad.
- Si Yaotl ha absorbido muchas almas, ayudar le devuelve la mitad de la humanidad.
- Si una absorción deja la humanidad en cero, el viaje termina.

### Guerrero consciente

**Nombre:** Guerrero consciente.

**Función:**

Guerrero caído que todavía puede hablar. Advierte a Yaotl sobre el riesgo de olvidar por qué vino.

**Ubicación:**

Nivel 2 — Tépetl Monamictlán.

**Interacción:**

Yaotl puede acercarse y hablar con él. Puede preguntarle quién es o si vio pasar a una mujer. Después elige entre ayudarlo a descansar, tomar su energía o dejarlo y seguir.

**Diálogos:**

El guerrero ya no recuerda su nombre ni por qué peleaba. Le cuenta a Yaotl que vio un alma arrastrada hacia abajo que no caminaba como las demás, porque seguía viva.

**Condiciones:**

- Yaotl debe acercarse al guerrero y activar la interacción.
- La conversación no es obligatoria para completar el nivel.

**Recompensas / información:**

- Ayudarlo a descansar: +6 de humanidad y +20 de experiencia.
- Tomar su energía: +10 de poder espiritual, −8 de humanidad y +20 de experiencia.
- Información sobre el paso del alma de Quetzalli.


> **Navegación:** [[00 - Índice]] · ← [[02 - Niveles]] · [[04 - Objetos y Coleccionables]] →
