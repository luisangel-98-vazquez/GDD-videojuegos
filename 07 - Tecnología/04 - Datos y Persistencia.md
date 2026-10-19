# Datos y Persistencia

## Descripción de la sección

Esta sección define la información del estado de juego que debe conservarse entre sesiones, la estructura lógica de los datos guardados, el formato físico y la ubicación del archivo en el sistema de archivos del usuario, así como el mecanismo básico para gestionar cambios en la estructura de guardado durante el desarrollo.
## Datos persistentes

- **Progreso:**
    
    - Último nivel o zona del Mictlán alcanzada.
        
    - Punto de control (_checkpoint_) o punto de guardado activo dentro del nivel.
        
    - Estado de derrota o victoria frente a jefes o minijefes.
        
- **Configuración:**
    
    - Volumen general de audio, música y efectos de sonido (SFX).
        
    - Modo de pantalla (pantalla completa o ventana) y resolución de video seleccionada.
        
- **Inventario:**
    
    - Objetos consumibles o curativos recolectados durante la travesía.
        

        
- **Estadísticas:**
    
    - Salud actual y máxima del personaje principal.
        
    - Puntos de experiencia o recursos acumulados (si aplica en el sistema de combate).
        
- **Desbloqueos:**
    
    - Habilidades o mejoras adquiridas por el jugador.
        
    - Niveles o entradas del lore cultural del Mictlán desbloqueadas en el menú principal.

## Modelo de datos

- **`PlayerData` (Entidad principal):**
    
    - Contiene variables simples para la salud, nivel actual, posición en el mapa y estadísticas generales.
        
- **`InventoryData` (Entidad secundaria):**
    
    - Mantiene una lista de identificadores de objetos (IDs) y sus respectivas cantidades (`ItemID`, `Quantity`).
        
- **`SettingsData` (Entidad independiente):**
    
    - Guarda las preferencias de usuario relacionadas con audio y gráficos para cargarlas de forma automática al iniciar el juego.

## Formato

**Formato de guardado:**
- **Formato de guardado:** **JSON (`.json`)** mediante la librería nativa `JsonUtility` de Unity (o formato clave-valor con `PlayerPrefs` para la configuración rápida de opciones de video y sonido).
    
- **Ubicación:** `Application.persistentDataPath`
    
- **Versionado de datos:** Se incluye un campo entero llamado `dataVersion` (ej. `1`) dentro de la estructura de guardado para identificar la versión del esquema de datos utilizada por el archivo.



## Migraciones

- Al intentar cargar la partida, el script lee el campo `dataVersion`.
    
- Si la versión del archivo es anterior a la versión actual del ejecutable del juego, el sistema aplica valores predeterminados (_default values_) a las nuevas variables introducidas sin sobrescribir o perder los datos existentes del progreso del usuario.


> **Navegación:** [[00 - Índice]] · ← [[03 - Requisitos Técnicos]] · [[05 - Seguridad y Riesgos Técnicos]] →
