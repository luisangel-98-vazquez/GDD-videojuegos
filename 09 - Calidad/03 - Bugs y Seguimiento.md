# Bugs y Seguimiento

## Descripción de la sección

Registra problemas encontrados durante las pruebas y permite darles seguimiento.

## Proceso

Los bugs se reportan como Issues en el repositorio del proyecto, con la plantilla de esta sección. El registro siguiente resume los severos para las revisiones de hito.

```text
Abierto → En progreso → Resuelto → Cerrado
```

1. Quien lo encuentra lo reporta con los pasos para reproducirlo y evidencia.
2. Esther, como coordinación de QA, confirma la severidad y asigna responsable.
3. El responsable lo corrige en una rama propia y lo marca como **Resuelto**.
4. Una persona distinta lo prueba en una compilación y lo marca como **Cerrado**. Si persiste, vuelve a **Abierto**.

## Severidad

| Severidad | Significado | Ejemplo | Atención |
| --------- | ----------- | ------- | -------- |
| Crítica | Impide jugar o pierde datos. | Cierre al cargar un nivel, guardado inservible. | Inmediata; bloquea el hito. |
| Alta | Afecta gravemente una función principal y no tiene alternativa razonable. | Un enemigo se vuelve invulnerable, el jefe no ataca. | Antes del siguiente hito. |
| Media | Función afectada con alternativa, o error molesto. | Un menú no recuerda la selección, una colisión imprecisa. | Según la capacidad del equipo. |
| Baja | Detalle visual o de sonido sin efecto en el juego. | Texto desalineado, efecto con volumen alto. | Si hay tiempo. |

Para llegar a la versión candidata (H6) no puede haber bugs críticos ni altos abiertos.

## Reporte de bug

**Título:** <!-- Qué falla y dónde -->

**Versión:** <!-- Compilación o commit -->

**Nivel / escena:**

**Pasos para reproducir:**

1.
2.
3.

**Resultado esperado:**

**Resultado actual:**

**Frecuencia:** Siempre / A veces / Rara vez

**Severidad:** Crítica / Alta / Media / Baja

**Evidencia:** <!-- Captura, video y Player.log; para errores de guardado, también save.json -->

**Estado:** Abierto / En progreso / Resuelto / Cerrado

## Registro

Sin bugs registrados: la implementación aún no inicia.

| ID | Bug | Severidad | Responsable | Estado |
|---|---|---|---|---|
| | | | | |


> **Navegación:** [[00 - Índice]] · ← [[02 - Pruebas]] · [[04 - Criterios de Aceptación]] →
