# Economía y Recursos

## Descripción de la sección

Documenta cualquier recurso cuantificable: dinero, vida, energía, munición, experiencia, materiales, tiempo, puntos, etc.

## Recursos

| Recurso | Obtención | Uso | Límite | Pérdida |
|---|---|---|---|---|
| Vida | Inicio, subir de nivel, equipo y curativos | Sobrevivir al daño | Base 100; 0 reinicia desde checkpoint local con vida completa | No se pierde como dato permanente al morir |
| Experiencia | Derrotar enemigos y subjefe; recompensa única | Define nivel del personaje | Umbral para nivel n: `20 × n × (n − 1)` | Se conserva al reintentar |
| Puntos de atributo | 2 por cada nivel alcanzado | Vitalidad, fuerza o espíritu | Se asignan en menú del personaje (Tab) | Persisten; no se pierden al morir |
| Curativos | Recogidas en regiones | Restauran 40 de vida base; no se consumen con vida completa | Cantidad según recogidas | Cantidad y consumo se guardan; no se devuelve al morir |
| Humanidad | Empieza en 50; ayudar aumenta, absorber y ataque espiritual reducen | Relación con Xólotl y condiciones de finales | 0–100; 0 termina el viaje | Persistente |
| Poder espiritual | Absorber almas | Ataque espiritual y condición de desenlaces | Se desbloquea con 12; no se gasta al atacar | Persistente |
| Equipo | Cofres y hallazgos | Modifica atributos del personaje | Un arma, un escudo, un amuleto | Persistente |

## Fuentes y sumideros

**Fuentes:** XP por enemigos; objetos y equipo en cofres; humanidad o poder según decisiones con almas; recuerdos en puntos narrativos.

**Sumideros:** curativos consumidos; vida perdida por daño; humanidad gastada al absorber almas o ejecutar ataque espiritual; puntos de atributo asignados.

## Reglas

Las recompensas de enemigos y objetos llevan identificadores únicos para que no se dupliquen al reintentar. El nivel de personaje se calcula por XP; cada nivel entrega dos puntos. La curación base es 40, con +50 % si humanidad ≥70, +5 % por punto de espíritu y bonificaciones de amuleto. El ataque espiritual hace `20 + poder espiritual + 4 × puntos de espíritu`, cuesta 1 humanidad y tiene enfriamiento de 5 s.

## Balance

Explorar, aprender los patrones, elegir entre humanidad y poder, y gastar curativos con intención.

Farmear enemigos repetidos, duplicar recompensas, consumir curativos con la vida completa o usar poder espiritual sin considerar el coste narrativo.


> **Navegación:** [[00 - Índice]] · ← [[05 - Progresión]] · [[07 - Reglas y Estados del Juego]] →
