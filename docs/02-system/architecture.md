# Arquitectura del sistema (línea base conceptual)

Este documento establece bloques funcionales a investigar; no es un esquema de conexión ni una autorización de montaje. Ninguna referencia de componente aquí se considera seleccionada o compatible por el solo hecho de aparecer en el contexto inicial.

## Bloques propuestos

```text
                    ┌─────────────────────────────────────┐
                    │ ESP32-P4 + pantalla táctil (candidato)│
                    │ HMI / lógica / adquisición / registro │
                    └──────────┬──────────────────┬─────────┘
                               │ buses digitales   │ estado/mandos
                 ┌─────────────┴──────┐       ┌───┴────────────────┐
                 │ ADC(s) ±10 V        │       │ DAC(s) + etapa ±10 V│
                 │ 4–8 canales objetivo│       │ 2–4 canales objetivo│
                 └─────────────┬──────┘       └───┬────────────────┘
                               │                   │
             Entradas/feedback ┴── Servoválvula / carga de prueba ─┘
                               │                   │
                         sensor de corriente   corte/habilitación
                                                   hardware
                    Alimentaciones, E-Stop, aislamiento y protección
```

La figura es conceptual: no define pinout, topología, aislamiento, conexiones a la válvula ni nivel de seguridad.

## Dominios a analizar

- **Digital:** controlador, pantalla, lógica de control y comunicaciones.
- **Analógico:** adquisición y generación de señales; evaluar ±15 V u otros rieles solo según necesidad demostrada.
- **Interfaz bajo prueba:** señales hacia/desde válvula y sensor de corriente. Definir referencia eléctrica y aislamiento a partir de los manuales de la válvula.
- **Seguridad:** E-Stop, habilitación física de salidas, relé/dispositivo de corte seleccionado, estado por defecto y realimentación de estado.

La necesidad de aislamiento galvánico, el número de fuentes, la secuencia de encendido y el presupuesto de potencia permanecen abiertos hasta analizar interfaces y riesgos.

## Decisiones y preguntas abiertas

1. ¿Cuál es el modelo y variante exactos de la placa ESP32-P4 y su esquema/pinout oficial?
2. ¿Qué señales eléctricas exige/entrega cada servoválvula Rethox objetivo (referencia, rango, corriente, impedancia, frecuencia, protección)?
3. ¿Qué ADC satisface simultáneamente rango, canales, muestreo, exactitud e interfaz? AD7606 y SC1467 son candidatos a estudiar, no selecciones.
4. ¿Qué DAC comercial proporciona salida bipolar ±10 V con SPI y niveles compatibles con 3.3 V? Es el bloqueador actual.
5. ¿Cómo evitar que un fallo de MCU, firmware, bus o fuente habilite una salida peligrosa?
6. ¿Qué corriente y ancho de banda debe medir el sensor Hall? Las referencias HSTS016L y QNHCK2-16 son candidatos no verificados.
7. ¿Qué restricciones de alimentación, aislamiento térmico/eléctrico y montaje aplican al prototipo?

## Secuencia de integración

1. Revisar requisitos y documentación de la válvula sin conectar hardware.
2. Verificar pinout, niveles lógicos y alimentación de los módulos elegidos individualmente.
3. Probar adquisición/generación con fuentes, cargas y simuladores seguros, limitados y documentados.
4. Validar mecanismos hardware de inhibición y estados de falla antes de conectar cargas externas.
5. Realizar integración de banco con revisión del plan de seguridad.
6. Planificar cualquier ensayo con válvula real por separado, con procedimiento aprobado y supervisión.

## Control de cambios

Un cambio de controlador, ADC/DAC, rango, referencia eléctrica, aislamiento o dispositivo de seguridad requiere revisar `requirements.md`, `interfaces.md`, BOM, riesgos y pruebas; las decisiones importantes se registran como ADR.