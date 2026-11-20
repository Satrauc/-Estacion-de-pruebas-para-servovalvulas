# ADR-0001: No fabricar PCB personalizada en el primer prototipo

- **Estado:** Aceptado como restricción del proyecto.
- **Fecha:** 2026-11-20.
- **Decisores:** equipo del proyecto, por identificar.

## Contexto

El primer prototipo necesita validar la arquitectura y los componentes con bajo costo y riesgo de iteración. El requisito del proyecto prohíbe fabricar una PCB personalizada en esta etapa.

## Decisión

El primer prototipo se construirá únicamente con módulos comerciales preensamblados, placas/adaptadores, borneras, riel DIN y cableado estructurado. No se diseñará ni fabricará una PCB propia como parte de esta fase.

## Alternativas consideradas

- PCB personalizada desde el primer prototipo: descartada para esta fase por la restricción explícita.
- Ensamble modular con módulos comerciales: adoptada para facilitar sustitución, evaluación y trazabilidad.

## Consecuencias

- La selección depende de disponibilidad y documentación de módulos compatibles.
- El cableado, conectores, protección, montaje y ruido requieren atención y pruebas específicas.
- Puede haber limitaciones de tamaño, coste o desempeño; registrar y evaluar sin eludir la restricción.
- Una PCB personalizada en una fase futura requiere una nueva decisión y actualización del alcance.

## Evidencia y requisitos relacionados

- `SYS-002` en `docs/01-project/requirements.md`.
- Alcance y restricciones en `docs/01-project/charter.md`.

## Revisión

Revisar solo si el alcance del proyecto cambia formalmente. Cualquier excepción debe documentarse antes de diseñar o fabricar una PCB.