# Plan de verificación y validación

## Enfoque

La verificación demuestra que el diseño implementa los requisitos; la validación demuestra que satisface la necesidad de uso definida. La ejecución se divide en etapas con evidencia retenida. Los límites cuantitativos de aceptación se definirán desde fuentes de válvula y requisitos aprobados; no se inventan en este plan.

## Niveles de prueba

| Nivel | Alcance | Condición de entrada |
|---|---|---|
| V0 — Revisión documental | Datasheets, pinout, requisitos, análisis y trazabilidad | Identidad de componente y fuentes disponibles |
| V1 — Módulo aislado | Alimentación y señales de cada módulo individual | Límites eléctricos y procedimiento revisados |
| V2 — Simulación de señales | ADC/DAC y firmware con instrumentos/cargas limitadas | Plan y límites de prueba aprobados |
| V3 — Integración de banco | Subsistemas integrados, comunicación, fallos y E-Stop | Diseño de seguridad revisado; cargas simuladas |
| V4 — Carga representativa | Comportamiento con carga controlada/representativa | Criterios, riesgos y supervisión aprobados |
| V5 — Válvula real | Caracterización progresiva del modelo documentado | Revisión formal, procedimiento específico y autorización |

No saltar niveles por conveniencia. Una prueba fallida requiere registrar condición, resultado, impacto y corrección antes de repetirse.

## Matriz inicial de verificación

| Requisito | Método previsto | Criterio de aceptación |
|---|---|---|
| SYS-002: sin PCB propia en primer prototipo | Inspección de BOM y montaje | Solo módulos comerciales preensamblados/adaptadores; documentar excepciones |
| HMI-002: pinout y buses | Revisión de fuentes y prueba de continuidad/función apropiada | Coincidencia con documentación oficial y asignación registrada |
| AI-001/002 | Inyección de señales controladas y medición de referencia | Pendiente de límites de error, rango, protección y configuración aprobados |
| AO-001/002 | Medición de salida con carga/instrumentación adecuada | Pendiente de exactitud, linealidad, respuesta y límites aprobados |
| AO-003 / SAFE-001 | Pruebas de arranque, reset, fallo y E-Stop con carga simulada | Definir estado seguro observable y criterio formal antes del ensayo |
| CUR-001 | Comparación con referencia en corriente DC/pulsante y bidireccional | Pendiente de rango, error y ancho de banda requeridos |
| PWR-001 | Medición de rieles, ruido, aislamiento y transitorios pertinentes | Criterios según componentes y análisis de seguridad |

## Registro de resultados

Por prueba guardar: ID, versión de diseño/firmware, fecha, responsable, objetivo, requisitos cubiertos, instrumentos y calibración, configuración, límites, procedimiento, datos originales, resultado, desviaciones, fotos/esquemas pertinentes y revisión. No publicar datos sensibles ni ocultar fallos.

Plantillas y resultados de ejecución se organizarán en `tests/`. Una prueba con válvula real debe contar además con procedimiento específico y aprobación de seguridad; este plan general no reemplaza esos documentos.