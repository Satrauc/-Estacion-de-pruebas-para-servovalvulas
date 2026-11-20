# Estación portátil de pruebas para servoválvulas electrohidráulicas

Repositorio de ingeniería para diseñar, documentar, construir y validar una estación portátil, modular y de bajo costo para visualizar, medir, controlar y caracterizar señales eléctricas asociadas a servoválvulas electrohidráulicas. El enfoque inicial es Rethox; la arquitectura deberá permitir evaluar otras marcas sin asumir compatibilidad no demostrada.

> **Estado del proyecto:** definición conceptual y prototipos preliminares de interfaz/BOM. A la fecha de esta revisión no se ha adquirido ni ensamblado hardware físico. Las selecciones de componentes siguen pendientes de verificación documental y ensayos.

## Objetivos

- Medir señales analógicas bipolares de hasta ±10 V y observar señales eléctricas de la servoválvula.
- Generar consignas analógicas estáticas y dinámicas con un estado seguro definido por hardware.
- Presentar mediciones, estados y controles en una HMI táctil.
- Mantener un diseño modular construido con módulos comerciales preensamblados; **no fabricar una PCB personalizada para el primer prototipo**.
- Documentar evidencia, compatibilidad, riesgos, pruebas y decisiones de forma trazable.
- Priorizar componentes documentados, disponibles y con envío viable a Colombia.

## Estado de subsistemas

| Subsistema | Estado actual | Siguiente evidencia necesaria |
|---|---|---|
| Requerimientos de servoválvulas Rethox | Abierto | Manuales, referencias exactas y perfil eléctrico confirmado |
| Controlador / HMI ESP32-P4 de 7 in | Candidato | Modelo exacto, esquema/pinout, buses expuestos y límites eléctricos |
| Entradas analógicas ±10 V | Candidato | Comparación de ADC, exactitud, aislamiento, protección y disponibilidad |
| Salidas analógicas ±10 V | **Bloqueador crítico** | DAC comercial, interfaz rápida, compatibilidad lógica 3.3 V y pruebas |
| Medición de corriente | Candidato | Confirmar medición DC bidireccional, rango y respuesta en corriente baja |
| Alimentación | Candidato | Datasheets, aislamiento, ruido, potencia, protecciones y montaje |
| Seguridad eléctrica / operacional | Abierto | Análisis de riesgos y arquitectura de E-Stop/habilitación independiente |
| Firmware | No iniciado | Arquitectura y pruebas de arranque, fallo y comunicaciones |
| Integración física | No iniciada | Prototipo de banco modular y plan de pruebas aprobado |

**Estados de evidencia obligatorios para cada componente:** `[VALIDADO]`, `[CANDIDATO]`, `[EXPERIMENTAL]` o `[NO COMPATIBLE]`. La clasificación debe enlazar a la evidencia que la sustenta. Un título de tienda, una imagen o una afirmación comercial no constituyen validación.

## Estructura del repositorio

```text
.
├── README.md
├── .gitignore
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── evaluacion-componente.yml
│       └── tarea-ingenieria.yml
├── bom/
│   ├── README.md
│   └── components.csv
├── docs/
│   ├── README.md
│   ├── 01-project/
│   │   ├── charter.md
│   │   └── requirements.md
│   ├── 02-system/
│   │   ├── architecture.md
│   │   └── interfaces.md
│   ├── 03-engineering/
│   │   └── component-validation.md
│   ├── 04-safety/
│   │   └── safety-plan.md
│   ├── 05-test-validation/
│   │   └── verification-plan.md
│   └── 06-decisions/
│       ├── README.md
│       └── ADR-0001-no-custom-pcb-first-prototype.md
├── firmware/README.md
├── hardware/README.md
├── hmi-prototype/README.md
├── safety/README.md
└── tests/README.md
```

## Documentación y navegación

- [Índice y reglas de documentación](docs/README.md)
- [Acta y alcance del proyecto](docs/01-project/charter.md)
- [Registro de requerimientos](docs/01-project/requirements.md)
- [Arquitectura de sistema](docs/02-system/architecture.md)
- [Interfaces y señales](docs/02-system/interfaces.md)
- [Proceso de validación de componentes](docs/03-engineering/component-validation.md)
- [Plan de seguridad](docs/04-safety/safety-plan.md)
- [Plan de verificación y pruebas](docs/05-test-validation/verification-plan.md)
- [Registro de decisiones (ADR)](docs/06-decisions/README.md)
- [BOM y estados de componentes](bom/README.md)
- [Hardware](hardware/README.md) · [Firmware](firmware/README.md) · [HMI](hmi-prototype/README.md) · [Seguridad](safety/README.md) · [Pruebas](tests/README.md)

## Hoja de ruta de ingeniería

1. Consolidar requerimientos y caracterizar eléctricamente servoválvulas Rethox.
2. Definir arquitectura electrónica: interfaces, pinout, aislamiento y alimentación.
3. Seleccionar componentes y verificar compra/envío a Colombia.
4. Ensamblar prototipo electrónico modular de banco, sin PCB propia.
5. Desarrollar firmware (ESP-IDF/FreeRTOS) y drivers necesarios.
6. Desarrollar HMI funcional (LVGL) para la pantalla seleccionada.
7. Integrar y probar con cargas controladas o simuladas.
8. Validar progresivamente con servoválvulas reales bajo procedimientos aprobados.
9. Integrar en gabinete portátil y completar documentación.

La hoja de ruta expresa orden de trabajo, no certificación ni autorización para operar equipos. Cada fase requiere criterios de entrada/salida y revisión de seguridad.

## Flujo de trabajo y trazabilidad

- Abrir una Issue por decisión técnica, componente por validar o tarea verificable.
- Registrar etapa, subsistema, responsable, dependencias, riesgo y criterio de aceptación.
- Asociar evidencia: datasheet/manual oficial, esquema, cálculo, medición, fotografía o resultado de prueba.
- Actualizar los requerimientos y la BOM cuando una decisión cambie.
- No marcar un componente `[VALIDADO]` sin evidencia de compatibilidad para el uso previsto.
- Registrar decisiones arquitectónicas relevantes como ADR numerados en `docs/06-decisions/`.
- Mantener el tablero GitHub Projects con estados acordados por el equipo; los Issues son el registro técnico trazable.

## Seguridad y límites de uso

Este repositorio es documentación de desarrollo, no un procedimiento de operación certificado. No conectar una servoválvula ni aplicar potencia hasta revisar los límites del equipo bajo prueba, el aislamiento, las protecciones, la parada de emergencia, el estado seguro de las salidas y el procedimiento de ensayo. No se debe asumir que el ESP32, el firmware o una interfaz gráfica pueden ser la única barrera de seguridad.

## Contribuciones

Antes de proponer cambios, revisar los documentos de requerimientos, seguridad y validación. Toda afirmación técnica nueva debe citar su fuente o marcarse explícitamente como pendiente de confirmación. Registrar unidades, condiciones de medida, versión del documento y fecha.

## Licencia y estado

El repositorio es el registro de ingeniería del proyecto. La licencia del código/documentación y la política de distribución de diseños se deben confirmar antes de publicar material reutilizable. La visibilidad del repositorio no implica que los diseños sean seguros, completos o aptos para fabricación.