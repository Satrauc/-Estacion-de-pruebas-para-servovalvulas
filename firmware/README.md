# Firmware

El firmware se desarrollará para el controlador seleccionado, inicialmente considerando ESP-IDF/FreeRTOS. La selección de versión y placa está pendiente; no asumir que toda placa ESP32-P4 ofrece los mismos periféricos, pines o soporte de pantalla.

## Organización prevista

- `main/`: aplicación y máquinas de estado.
- `components/`: drivers y componentes desacoplados.
- `test/`: pruebas host/target y simuladores de periféricos.
- `docs/`: configuración, versiones, protocolo e interfaces.

## Principios

- Mantener salidas inhibidas por defecto en reset, arranque y fallos.
- El firmware no sustituye la habilitación/interrupción hardware.
- Separar adquisición, control, HMI, comunicaciones y registro.
- Controlar tiempos de espera y errores de SPI/I2C; no habilitar salidas ante datos inválidos.
- Definir límites, rangos y unidades mediante requisitos aprobados, no constantes implícitas.
- Documentar versión ESP-IDF, placa, configuración, compilación y resultado de pruebas.

No implementar generación de consignas hacia una válvula real antes de validar DAC, interfaces y plan de seguridad.