# Alcance

## Descripción de la sección

Define qué se va a construir y, sobre todo, qué queda fuera del proyecto.

## Alcance de la versión objetivo

### Incluido

- Versión para PC (Windows), para un jugador y sin conexión, con teclado y mouse.
- Prólogo, tres capítulos con las nueve regiones de [[02 - Niveles]] y epílogo, en una ruta lineal.
- Movimiento, salto, ataque, bloqueo, interacción y uso de curativos.
- Dos tipos de enemigos (guerrero caído y alma errante) y un jefe final con dos patrones de ataque.
- Peligros del entorno: agua, vacío, obsidiana, bloques móviles y trampas de flechas.
- Progresión con experiencia, subida de nivel y mejora automática de estadísticas.
- Inventario de espada, escudo y curativos.
- Tres recuerdos coleccionables, xolo guía y alma en pena.
- Menús de [[02 - UI y Menús]], HUD, guardado automático de una ranura y las opciones incluidas en [[03 - Accesibilidad]].
- Arte 2D, animaciones, música y efectos propios de las nueve regiones.

### No incluido

- Multijugador o funciones en línea.
- Consolas o dispositivos móviles.
- Mundo abierto o contenido generado aleatoriamente.
- Misiones secundarias.
- Sistema de sigilo. Las regiones que evitan el combate se resuelven observando el entorno, como Tépetl Monamictlán y Paniecatacoyan.
- Decisiones que ramifiquen la historia o finales alternativos. El desenlace es único.
- Tienda, moneda o árbol de habilidades.
- Dificultad seleccionable, doblaje y localización a otros idiomas.

### Deseable

Solo se aborda si el juego base y sus pruebas críticas ya están terminados:

- Compatibilidad con control de mando.
- Versión Web.
- Reasignación de controles y tamaño de texto.

> [!warning] Decisiones por validar
> [[01 - Ficha del Proyecto]], [[02 - Visión del Juego]] y [[03 - Público y Plataforma]] mencionan elementos que esta lista deja fuera o como deseables: control de mando, Web, sigilo y decisiones. El motivo es que [[03 - Requisitos Técnicos]] y [[02 - Niveles]] no los contemplan. El equipo debe resolverlos en [[05 - Gestión de Cambios]].

## MVP

El **Producto Mínimo Viable** debe contener únicamente lo necesario para demostrar que la experiencia principal funciona.

**MVP del proyecto:** el capítulo 1 jugable de principio a fin con arte provisional. Incluye:

- Itzcuintlán, Tépetl Monamictlán e Itztépetl conectados.
- Movimiento, salto, ataque y bloqueo.
- Guerrero caído con patrulla, detección y ataque.
- Vida, daño, muerte, experiencia y subida de nivel.
- Un curativo y el primer recuerdo.
- Guardado automático, Continuar y HUD básico.

Valida el bucle de explorar, combatir, progresar y descubrir, que sostiene los tres [[04 - Pilares de Diseño|pilares]]. Si este tramo no resulta entretenido, se corrige antes de construir el resto.

## Vertical Slice

¿Qué parte del juego debe estar completamente terminada para demostrar la calidad y dirección del producto?

**Itztépetl, la montaña de obsidiana.** Se termina con arte, animación, audio, HUD y efectos finales, porque en 3 minutos reúne plataformas, combate, bloqueo, peligros del entorno y un recuerdo narrativo. También sirve como referencia de calidad, memoria y rendimiento para los otros ocho niveles.

## Criterios de recorte

Si el tiempo o los recursos son insuficientes, ¿Qué se elimina primero?
- variación de enemigos
- niveles mas adelante


| Orden | Se recorta | Efecto |
| ----- | ---------- | ------ |
| 1 | Todo lo deseable: control de mando, Web, reasignación y tamaño de texto | Ninguno en la experiencia base |
| 2 | Menú Recuerdos y animación de retratos | Los recuerdos solo se ven al obtenerlos |
| 3 | Fondos con parallax, partículas y variaciones de sonido | Menor pulido visual y sonoro |
| 4 | Conversación con el alma en pena y objetivos secundarios | Menos narrativa opcional |
| 5 | Longitud de Itzehecayan, Teocoyohuehualoyan e Izmictlán Apochcalolca, que no introducen mecánicas | Partida más corta |
| 6 | Trampas de flechas, reutilizando solo los proyectiles de las almas errantes | Timiminaloayan con menos variedad |

**No se recorta sin una solicitud de cambio aprobada:** las nueve regiones, el combate, los tres recuerdos, el jefe final, el epílogo y el guardado. Forman parte del [[01 - Ficha del Proyecto|criterio de éxito del proyecto]].


> **Navegación:** [[00 - Índice]] · ← [[05 - Seguridad y Riesgos Técnicos]] · [[02 - Roles y Responsabilidades]] →
