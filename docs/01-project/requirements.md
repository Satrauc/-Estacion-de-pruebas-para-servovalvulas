# Registro de requerimientos

Los valores en esta tabla son objetivos de diseño derivados del contexto inicial, no especificaciones confirmadas de una válvula. Convertirlos en requisitos cuantitativos de aceptación después de obtener manuales y referencias exactas de los equipos bajo prueba.

| ID | Requerimiento | Verificación prevista | Estado |
|---|---|---|---|
| SYS-001 | La estación será modular y portátil, con subsistemas reemplazables. | Inspección de arquitectura y prototipo | Abierto |
| SYS-002 | El primer prototipo usará exclusivamente módulos comerciales preensamblados; no incluirá PCB personalizada. | Inspección de BOM y montaje | Aceptado como restricción |
| SYS-003 | Componentes y compras priorizarán documentación verificable y disponibilidad de envío a Colombia. | Revisión de fuentes/logística | Abierto |
| SYS-004 | Cada componente tendrá uno de los estados de evidencia definidos en `bom/README.md`. | Auditoría BOM | Abierto |
| HMI-001 | Evaluar plataforma ESP32-P4 con pantalla táctil IPS de aproximadamente 7 in y resolución objetivo aproximada 1024 × 600. | Datasheet, pinout y prueba de interfaz | Candidato |
| HMI-002 | Identificar GPIO y buses SPI/I2C realmente disponibles, reservados y accesibles en el modelo seleccionado. | Revisión de esquema/manual y prueba | Abierto |
| AI-001 | Diseñar una configuración de 4–8 entradas analógicas bipolares; rango objetivo ±10 V. | Revisión de diseño y ensayo calibrado | Objetivo, no validado |
| AI-002 | Evaluar medición diferencial y protecciones frente a sobretensión y conexión incorrecta. | Análisis y ensayo seguro | Abierto |
| AI-003 | Documentar exactitud, resolución, frecuencia de muestreo, aislamiento, impedancia y límites absolutos de cada canal. | Datasheet/cálculo/medición | Abierto |
| AO-001 | Diseñar 2–4 salidas analógicas bipolares; rango objetivo ±10 V. | Revisión de diseño y ensayo | Objetivo, no validado |
| AO-002 | Seleccionar un DAC/módulo comercial con interfaz de latencia adecuada, preferentemente SPI, y compatibilidad lógica con 3.3 V. | Datasheet y prueba de comunicación | Bloqueador crítico |
| AO-003 | Definir un estado seguro por hardware independiente del ESP32 y probarlo ante condiciones de falla. | Análisis y ensayo de fallos | Abierto |
| CUR-001 | Evaluar sensor split-core no invasivo para corriente DC/pulsante y bidireccional. | Datasheet y comparación contra referencia | Abierto |
| PWR-001 | Diseñar dominios de alimentación analógico/digital con aislamiento y filtrado definidos por análisis. | Revisión de arquitectura y medición | Abierto |
| SAFE-001 | Incorporar E-Stop física y una ruta de corte/habilitación hardware de las salidas. | Inspección y pruebas de fallo | Abierto |
| SAFE-002 | Definir límites de conexión, puesta en marcha, pruebas simuladas y progresión a válvulas reales. | Revisión de plan/procedimientos | Abierto |
| DOC-001 | Mantener trazabilidad entre requisito, decisión, componente, Issue y evidencia de prueba. | Revisión documental | Abierto |

## Mantenimiento del registro

- No borrar IDs retirados; marcar su estado y documentar motivo.
- Añadir columna de responsable, fuente, Issue y resultado de prueba cuando se asigne el trabajo.
- Los límites de seguridad y aceptación requieren revisión técnica antes de usarse en ensayos.
- Para cada cambio, indicar fecha y enlace a la revisión correspondiente.