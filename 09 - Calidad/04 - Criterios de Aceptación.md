# Criterios de Aceptación

## Descripción de la sección

Los criterios de aceptación permiten decidir objetivamente si una característica está lista.

## Criterios por característica

### Movimiento y plataformas

**Dado que:** el protagonista está sobre una plataforma.

**Cuando:** el jugador se mueve y salta hacia otra plataforma al alcance.

**Entonces:** el personaje aterriza en ella, cambia de animación y no atraviesa suelos ni paredes.

### Combate

**Dado que:** un enemigo está al alcance y de frente.

**Cuando:** el jugador ataca.

**Entonces:** el enemigo pierde vida con respuesta visual y sonora; al llegar a cero desaparece y otorga experiencia una sola vez.

### Bloqueo

**Dado que:** el jugador mantiene el bloqueo de frente a un ataque cuerpo a cuerpo o a un proyectil.

**Cuando:** el ataque impacta.

**Entonces:** no se recibe daño y se muestra la respuesta de bloqueo. Un ataque por la espalda sí causa daño.

### Muerte y reaparición

**Dado que:** el jugador tiene un punto de guardado activo.

**Cuando:** su vida llega a cero o cae en un peligro mortal.

**Entonces:** la pantalla de derrota muestra la causa y Reintentar lo devuelve al punto de guardado con vida completa, sin conservar lo obtenido después de guardar.

### Progresión

**Dado que:** al jugador le falta poca experiencia para subir de nivel.

**Cuando:** derrota a un enemigo y alcanza el valor requerido.

**Entonces:** sube de nivel, mejoran sus estadísticas automáticamente y el HUD lo indica.

### Curativos

**Dado que:** el jugador tiene al menos un curativo y ha recibido daño.

**Cuando:** pulsa la tecla de curar, sin abrir ningún menú.

**Entonces:** recupera vida y el contador baja en uno. Sin existencias o con la vida completa no se consume nada.

### Interacción y xolo

**Dado que:** el jugador se acerca al xolo, al alma en pena o a una salida.

**Cuando:** aparece el indicador y pulsa interactuar.

**Entonces:** se muestra el diálogo o se activa el acceso. Hablar con el alma en pena es opcional para avanzar.

### Recuerdos

**Dado que:** el jugador llega a un fragmento en los niveles 3, 6 o 9.

**Cuando:** lo recoge.

**Entonces:** se muestra la escena y, al pasar el siguiente punto de guardado, el recuerdo queda guardado de forma permanente.

### Peligros del entorno

**Dado que:** el jugador se acerca a agua, vacío, obsidiana, bloques o trampas.

**Cuando:** observa el peligro antes de tocarlo.

**Entonces:** puede distinguirlo del fondo y evitarlo; siempre existe una forma de pasar sin recibir daño.

### Jefe final

**Dado que:** el jugador entra a la arena del Señor del Mictlán.

**Cuando:** el jefe ejecuta el golpe frontal o la onda.

**Entonces:** cada ataque muestra su señal previa, el golpe se puede bloquear y la onda se evita saltando. Al derrotarlo se pasa al epílogo, y si el jugador muere repite el combate sin ver el recuerdo.

### Guardado

**Dado que:** el jugador entra a un nivel y aparece el icono de guardado.

**Cuando:** cierra el juego y elige Continuar.

**Entonces:** aparece en ese punto con los mismos datos. Un archivo dañado se recupera según [[05 - Seguridad y Riesgos Técnicos]], sin cerrar el juego.

### Pausa y menús

**Dado que:** el jugador está en un nivel o en un diálogo.

**Cuando:** pulsa Esc.

**Entonces:** el mundo se detiene, los menús se pueden usar con teclado y con mouse, y las acciones destructivas piden confirmación ([[02 - UI y Menús]]).

### Configuración

**Dado que:** el jugador cambia una opción de [[04 - Guardado y Configuración]].

**Cuando:** la aplica y reinicia el juego.

**Entonces:** la opción sigue activa. Restablecer recupera el valor predeterminado sin afectar la partida.

## Criterios del proyecto

- [ ] El bucle principal funciona.
- [ ] Las condiciones de victoria y derrota funcionan.
- [ ] El progreso puede guardarse.
- [ ] Los sistemas principales están integrados.
- [ ] Las pruebas críticas están aprobadas.
- [ ] El rendimiento cumple el objetivo definido.
- [ ] No existen errores bloqueantes conocidos.
- [ ] Se pueden recorrer las nueve regiones del Mictlán hasta el epílogo.
- [ ] Escenarios, personajes y criaturas representan la mitología mexica de forma coherente.
- [ ] El ejecutable funciona en Windows sin Unity instalado y sin conexión.

Las pruebas críticas están en [[02 - Pruebas]] y los objetivos de rendimiento en [[01 - Criterios de Calidad]]. Las casillas permanecen sin marcar hasta verificarse en la compilación final.


> **Navegación:** [[00 - Índice]] · ← [[03 - Bugs y Seguimiento]] · [[01 - Glosario]] →
