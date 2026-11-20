# Plan de seguridad (borrador de ingeniería)

> **Advertencia:** este documento no es una evaluación de riesgos completa, un procedimiento de trabajo seguro ni una certificación. Debe ser revisado por personal competente antes de cualquier ensayo energizado. No conectar la estación a una válvula real hasta aprobar el diseño y los procedimientos aplicables.

## Principios

- La seguridad no depende exclusivamente del firmware, MCU, pantalla o comunicaciones.
- Las salidas deben permanecer inhibidas por defecto durante arranque, reset, pérdida de alimentación/control y fallos previsibles.
- La E-Stop debe actuar sobre una ruta hardware definida; su función, límites y necesidad de corte de energía se determinarán mediante análisis.
- Separar dominios y proteger interfaces conforme al análisis de tensión, energía, aislamiento y entorno.
- Empezar con cargas simuladas y límites de energía adecuados; definir transición progresiva a equipos reales.
- Etiquetar, proteger mecánicamente y verificar conexiones antes de energizar.

## Peligros a evaluar (lista inicial, no exhaustiva)

- Salida analógica inesperada, saturada o con polaridad incorrecta.
- Sobretensión, inversión, conexión equivocada o diferencia de potencial entre referencias.
- Fallo del DAC, ADC, amplificador, relé, módulo DC/DC o aislamiento.
- MCU bloqueado, arranque/reinicio, fallo de firmware, bus SPI atascado o salida GPIO indeterminada.
- Calentamiento, cortocircuito, sobrecorriente o descarga de energía almacenada.
- Actuación hidráulica/mecánica inesperada del equipo bajo prueba.
- Cable suelto, conector incompatible, error humano, E-Stop inaccesible o sin prueba funcional.

## Elementos que requieren diseño y evidencia

1. Identificación del peligro y estimación de riesgo acorde al contexto real de uso.
2. Límites de energía y tensiones/corrientes presentes por dominio.
3. E-Stop: acción esperada, elementos que desenergiza/inhibe, reinicio manual y verificación.
4. Habilitación de salida por hardware y comportamiento ante fallo de MCU/alimentación.
5. Estado de salida durante power-up, reset, desconexión de comunicaciones y fallo del DAC.
6. Protección de entradas/salidas, aislamiento, fusibles/limitación y puesta a tierra/referencia.
7. Descarga de energía, señalización, enclavamientos y accesibilidad.
8. Pruebas de fallo con carga simulada, límites y criterios de aprobación documentados.

## Puertas de revisión

- **Antes de alimentar módulos:** confirmar datos eléctricos, polaridad, límite de corriente y montaje.
- **Antes de conectar una carga simulada:** revisar esquema, límites, protección y estrategia de inhibición.
- **Antes de conectar una válvula real:** revisión formal del riesgo, manual de fabricante, procedimiento aprobado, E-Stop probada y supervisión competente.

Cada prueba debe tener responsable, condiciones de parada, método de verificación y registro. Mantener el plan sincronizado con `docs/05-test-validation/verification-plan.md` y `docs/02-system/architecture.md`.