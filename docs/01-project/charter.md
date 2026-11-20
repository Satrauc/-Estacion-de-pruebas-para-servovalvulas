# Acta del proyecto

## Identificación

- **Nombre:** Estación portátil de pruebas, diagnóstico y caracterización de servoválvulas electrohidráulicas.
- **Enfoque inicial:** servoválvulas Rethox; extensible a otras marcas tras verificar compatibilidad.
- **Estado:** definición conceptual; no se ha adquirido ni ensamblado hardware físico.
- **Responsable / equipo:** por asignar en el repositorio.
- **Última actualización:** 2026-11-20.

## Propósito

Desarrollar una estación portátil, modular y económica para observar, medir, generar y registrar señales eléctricas relacionadas con servoválvulas electrohidráulicas. La estación debe permitir caracterización progresiva con cargas simuladas antes de cualquier ensayo con válvulas reales.

## Alcance inicial

- Controlador/HMI basado en una plataforma ESP32-P4 con pantalla táctil IPS cercana a 7 pulgadas y resolución objetivo aproximada de 1024 × 600; modelo exacto pendiente de selección.
- 4 a 8 entradas analógicas bipolares con rango de diseño objetivo ±10 V; preferencia por medición diferencial y protección frente a sobretensión/error de conexión.
- 2 a 4 salidas analógicas bipolares con rango objetivo ±10 V, respuesta adecuada a consignas dinámicas y estado seguro independiente del software.
- Medición de corriente no invasiva mediante sensor de núcleo dividido, con capacidad de medir DC/pulsante y corriente bidireccional, sujeto a validar el rango.
- Alimentación por módulos DC/DC comerciales con dominios y filtrado definidos por análisis.
- E-Stop física, habilitación hardware de salidas y aislamiento entre dominios cuando el análisis lo requiera.
- Prototipo con módulos comerciales preensamblados, adaptadores, borneras, riel DIN y cableado estructurado.
- Documentación de ingeniería, BOM, firmware, HMI, pruebas y gabinete.

## Exclusiones y restricciones

- **No fabricar PCB personalizada para el primer prototipo.** Cualquier cambio futuro requiere nueva decisión registrada.
- No asumir compatibilidad a partir de títulos de venta o fichas incompletas.
- No conectar o probar con válvulas reales hasta validar límites, seguridad, procedimiento y supervisión.
- La estación no se considera equipo certificado ni instrumento metrológico hasta completar la evaluación correspondiente.
- La compra/envío a Colombia es un criterio de viabilidad, no evidencia de idoneidad técnica.

## Entregables esperados

1. Especificación de requisitos y perfil eléctrico de válvulas objetivo.
2. Arquitectura funcional y de seguridad con interfaces documentadas.
3. BOM trazable con estado de evidencia, fuentes, costos/precios fechados y logística.
4. Prototipo de banco modular y cableado documentado.
5. Firmware y HMI con pruebas unitarias/integración adecuadas.
6. Procedimientos y resultados de pruebas con cargas simuladas y, posteriormente, válvulas reales.
7. Ensamblaje mecánico portátil y documentación final.

## Criterios de éxito preliminares

- Requisitos y límites de las válvulas de referencia respaldados por documentación primaria o medición reproducible.
- ADC/DAC y cadenas analógicas seleccionados con rangos, exactitud, interfaz, protección y compatibilidad demostrados.
- Salidas pasan a un estado seguro definido ante arranque, reinicio, pérdida de firmware y E-Stop, verificado por prueba.
- Prototipo ensamblado sin PCB propia y probado inicialmente con simuladores/cargas controladas.
- Resultados repetibles, trazables y revisados antes de operar con válvulas reales.

Estos criterios son objetivos iniciales, no valores de aceptación cuantificados. Deben convertirse en requisitos verificables con límites numéricos cuando existan datos suficientes.

## Registro de cambios

| Fecha | Cambio |
|---|---|
| 2026-11-20 | Primera línea base documental, basada en el contexto inicial del proyecto. |