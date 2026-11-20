# Validación de componentes

## Estados de evidencia

- **`[VALIDADO]`**: datasheet/manual oficial revisado y compatibilidad del requisito demostrada por análisis y/o prueba reproducible. Indicar exactamente qué aspectos están validados; no generalizar a otros modelos o condiciones.
- **`[CANDIDATO]`**: existe documentación plausible, pero queda una o más comprobaciones técnicas o de logística.
- **`[EXPERIMENTAL]`**: incertidumbre técnica alta, documentación insuficiente o se requiere ensayo exploratorio controlado.
- **`[NO COMPATIBLE]`**: incumple un requisito obligatorio o se descartó con evidencia. Registrar razón y no reutilizar como selección activa sin revisión.

El estado debe reflejar evidencia y fecha, no opinión ni disponibilidad comercial. Se puede añadir detalle sobre qué atributo fue verificado, por ejemplo, interfaz lógica o rango, sin cambiar el significado del estado global.

## Flujo de evaluación

1. **Identificar:** fabricante, número de parte exacto, revisión y variante. Evitar referencias genéricas.
2. **Obtener fuente primaria:** datasheet, manual, esquema oficial y, cuando aplique, declaración del fabricante.
3. **Extraer límites:** condiciones recomendadas, absolutos, interfaz, alimentación, temperatura, tolerancias, aislamiento y protección.
4. **Mapear requisitos:** enlazar cada especificación con IDs de `docs/01-project/requirements.md`.
5. **Analizar compatibilidad:** incluir niveles lógicos, rango, referencia, temporización, potencia, disipación, seguridad y conexiones.
6. **Revisar disponibilidad:** proveedor, precio con fecha/moneda, envío a Colombia, impuestos/tiempos y trazabilidad del SKU. No sustituir análisis técnico por precio.
7. **Definir ensayo seguro:** instrumentos, conexiones, límites, criterio de aceptación y riesgos antes de alimentar el componente.
8. **Registrar resultado:** BOM, evidencia, responsable, estado, limitaciones y próxima acción.
9. **Revisar cambios:** repetir evaluación si cambia variante, fuente documental, requisito o configuración de uso.

## Evidencia mínima

- Link y versión de datasheet/manual oficial, más páginas relevantes.
- Modelo exacto/variante y fecha de consulta.
- Matriz requisito → especificación → análisis/medición → conclusión.
- Esquema de prueba, equipos utilizados y estado de calibración cuando aplique.
- Resultados originales (no solo captura resumida), condiciones, limitaciones y revisión técnica.
- Decisión de compra separada de decisión de compatibilidad.

## Registro

La plantilla de evaluación está disponible al crear una Issue mediante `.github/ISSUE_TEMPLATE/evaluacion-componente.yml`. El inventario controlado reside en `bom/components.csv`. No colocar credenciales, cotizaciones confidenciales ni datos personales en Issues públicos.