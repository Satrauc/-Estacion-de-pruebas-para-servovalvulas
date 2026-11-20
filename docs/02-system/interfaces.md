# Interfaces y señales

Esta matriz captura objetivos conocidos y campos que deben completarse con documentación de fabricante. **No es un pinout ni una especificación de cableado.** No realizar conexiones basándose únicamente en esta tabla.

| Interfaz | Cantidad objetivo | Rango/medio objetivo | Datos por confirmar |
|---|---:|---|---|
| Entradas analógicas | 4–8 | Bipolar, ±10 V objetivo | Diferencial/single-ended, referencia, impedancia, tolerancia, ancho de banda, muestreo, protección y aislamiento |
| Salidas analógicas | 2–4 | Bipolar, ±10 V objetivo | Resolución, exactitud, velocidad de asentamiento, latencia, corriente/carga, SPI y compatibilidad 3.3 V |
| Sensor de corriente | 1 o más | Split-core, no invasivo | DC real, bidireccionalidad, rango mínimo/máximo, ancho de banda, sensibilidad, error y alimentación |
| Controlador-HMI | 1 | ESP32-P4, pantalla cercana a 7 in | Modelo exacto, pinout, buses compartidos, señales reservadas y secuencia de alimentación |
| Alimentación | Por definir | Conversión comercial; posibles rieles analógicos y digitales | Tensión de entrada, potencia, aislamiento, ruido, protección, disipación y disponibilidad |
| E-Stop/habilitación | Por definir | Circuito hardware independiente del MCU | Arquitectura, contactos, corte, estado por defecto, diagnóstico y criterios de reinicio |

## Registro de interfaces con la válvula

Para cada modelo/variante de servoválvula completar una copia de esta ficha con fuente:

- Fabricante, modelo exacto, revisión y número de parte:
- Documento oficial, revisión, URL y página:
- Tipo de conexión y pinout según fuente:
- Señales de mando: tipo, rango, impedancia, referencia, límites y polaridad:
- Señales de realimentación: tipo, rango, impedancia, referencia y capacidad de carga:
- Alimentación requerida y condiciones:
- Corriente de bobina o señales de corriente, método y límites:
- Protecciones, aislamiento y advertencias del fabricante:
- Ambigüedades/contradicciones:
- Responsable y fecha de verificación:
- Evidencia adicional de medición (equipo, calibración, configuración y resultados):

No introducir valores supuestos. Si un campo no está respaldado, registrar `Pendiente de confirmar`.

## Registro de buses del controlador

Para el modelo exacto de placa documentar: nombre de señal, conector/pin, dirección, nivel lógico, función compartida, periférico asociado, estado durante reset, límites absolutos y fuente. No asignar buses SPI/I2C hasta confirmar el esquema y el comportamiento de arranque.