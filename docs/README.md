# Documentación del proyecto

Este directorio contiene la fuente de verdad para alcance, requerimientos, arquitectura, validación, seguridad, pruebas y decisiones. La documentación se versiona junto con el hardware, firmware y HMI para preservar trazabilidad.

## Convenciones

1. **No inventar especificaciones.** Citar la fuente primaria (fabricante, manual, datasheet o medición propia reproducible). Marcar lo desconocido como `Pendiente`.
2. **Separar hecho, supuesto y decisión.** Los supuestos deben tener responsable y plan de cierre; las decisiones arquitectónicas relevantes se registran como ADR.
3. **Usar estados uniformes de componentes:** `[VALIDADO]`, `[CANDIDATO]`, `[EXPERIMENTAL]`, `[NO COMPATIBLE]`. Incluir evidencia y fecha de revisión.
4. **Trazar requisitos.** Asignar ID estable (`SYS-`, `AI-`, `AO-`, `SAFE-`, etc.) y enlazarlo con Issue, diseño y prueba.
5. **Registrar unidades y condiciones.** Indicar rango, tolerancia, referencia, ancho de banda/frecuencia cuando aplique, método e incertidumbre conocida.
6. **No considerar una compra como validación.** La disponibilidad, compatibilidad eléctrica y desempeño se verifican por separado.
7. **Revisar seguridad antes de pruebas energizadas.** Las pruebas con equipo real requieren procedimiento, revisión de riesgos y autorización del responsable técnico.

## Documentos

| Documento | Propósito |
|---|---|
| [Acta del proyecto](01-project/charter.md) | Objetivo, alcance, exclusiones, entregables y estado |
| [Requerimientos](01-project/requirements.md) | Requerimientos identificados y trazables |
| [Arquitectura](02-system/architecture.md) | Bloques funcionales y decisiones pendientes |
| [Interfaces](02-system/interfaces.md) | Señales, buses y límites por confirmar |
| [Validación de componentes](03-engineering/component-validation.md) | Método de evaluación y evidencia mínima |
| [Plan de seguridad](04-safety/safety-plan.md) | Peligros, barreras y revisiones necesarias |
| [Plan de verificación](05-test-validation/verification-plan.md) | Estrategia de pruebas y criterios de salida |
| [Registro ADR](06-decisions/README.md) | Índice de decisiones de arquitectura |

## Mantenimiento

Actualizar la documentación en el mismo cambio que altera una interfaz, requerimiento, componente, riesgo o decisión. Incluir en las revisiones: impacto sobre requisitos, BOM, seguridad, firmware y plan de pruebas. No sobrescribir conclusiones históricas: registrar revisiones con fecha y motivo.