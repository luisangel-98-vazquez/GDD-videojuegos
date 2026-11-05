# Datos y Persistencia

## Descripción de la sección

Esta sección define la información del estado de juego que debe conservarse entre sesiones, la estructura lógica de los datos guardados, el formato físico y la ubicación del archivo en el sistema de archivos del usuario, así como el mecanismo básico para gestionar cambios en la estructura de guardado durante el desarrollo.

## Datos persistentes

Las reglas de cuándo se guarda y cómo se reanuda están en [[04 - Guardado y Configuración]].

- **Progreso:**

    - Último nivel o zona del Mictlán alcanzada.

    - Punto de control (_checkpoint_) o punto de guardado activo dentro del nivel.

    - Si el juego se completó, es decir, si se derrotó al Señor del Mictlán y se terminó el epílogo.

- **Configuración:**

    - Volumen general de audio, música y efectos de sonido (SFX).

    - Modo de pantalla (pantalla completa o ventana) y resolución de video seleccionada.

    - Reducción de movimiento, reducción de destellos e indicaciones de control.

- **Inventario:**

    - Objetos consumibles o curativos recolectados durante la travesía. La espada y el escudo están disponibles desde el inicio y no se guardan.

- **Estadísticas:**

    - Salud actual y máxima del personaje principal.

    - Nivel de personaje y puntos de experiencia acumulados.

- **Desbloqueos:**

    - Recuerdos recuperados, que también se pueden volver a ver desde la pausa.

No se guardan la posición exacta del personaje, los enemigos derrotados ni los objetos recogidos en el nivel en curso: al cargar, el nivel se reconstruye desde su punto de guardado.

## Modelo de datos

- **`SaveData` (Contenedor del archivo de partida):**

    - Agrupa `dataVersion`, `PlayerData`, `ProgressData` e `InventoryData`.

- **`PlayerData` (Entidad principal):**

    - `currentHealth`, `maxHealth`, `attack`, `characterLevel` y `experience`.

- **`ProgressData` (Entidad secundaria):**

    - `currentLevelId`, `checkpointId`, `recoveredMemoryIds` (lista de identificadores) y `gameCompleted`.

- **`InventoryData` (Entidad secundaria):**

    - Mantiene una lista de identificadores de objetos (IDs) y sus respectivas cantidades (`ItemID`, `Quantity`). Se usa una lista serializable porque `JsonUtility` no admite diccionarios.

- **`SettingsData` (Entidad independiente):**

    - Guarda las preferencias de usuario relacionadas con audio, gráficos y accesibilidad para cargarlas de forma automática al iniciar el juego.

## Formato

**Formato de guardado:**

- **Formato de guardado:** **JSON (`.json`)** mediante la librería nativa `JsonUtility` de Unity, tanto para la partida como para la configuración. No se usa `PlayerPrefs`, para mantener un solo mecanismo de lectura, respaldo y restablecimiento.

- **Ubicación:** `Application.persistentDataPath`

- **Archivos:** `save.json` y su respaldo `save.bak.json` para la partida; `settings.json` para la configuración.

- **Escritura segura:** se escribe primero en un archivo temporal. Si la escritura termina bien, el archivo anterior pasa a ser el respaldo y el temporal se convierte en el nuevo guardado.

- **Versionado de datos:** Se incluye un campo entero llamado `dataVersion` (ej. `1`) dentro de la estructura de guardado para identificar la versión del esquema de datos utilizada por el archivo.

## Migraciones

- Al intentar cargar la partida, el script lee el campo `dataVersion`.

- Si la versión del archivo es anterior a la versión actual del ejecutable del juego, el sistema aplica valores predeterminados (_default values_) a las nuevas variables introducidas sin sobrescribir o perder los datos existentes del progreso del usuario.

- Si la versión del archivo es posterior a la del ejecutable, el archivo no se carga ni se modifica, y el jugador recibe un aviso.

- Todo cambio en la estructura incrementa `dataVersion` y añade un caso de prueba con un archivo de la versión anterior ([[02 - Pruebas]]).


> **Navegación:** [[00 - Índice]] · ← [[03 - Requisitos Técnicos]] · [[05 - Seguridad y Riesgos Técnicos]] →
