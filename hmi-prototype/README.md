# Prototipo HMI

El proyecto cuenta con un prototipo visual/conceptual de HMI en HTML. Aún no es una HMI funcional conectada a hardware. Mantener el prototipo separado del firmware embebido y señalar claramente las funciones simuladas.

## Organización prevista

- `index.html`: punto de entrada, si se versiona el prototipo aquí.
- `assets/`: estilos, imágenes e iconografía con licencias registradas.
- `docs/`: capturas, flujo de pantallas, supuestos y decisiones.

## Criterios de documentación

- Identificar las pantallas y controles simulados.
- No mostrar valores como mediciones reales si son datos ficticios.
- Documentar estados: deshabilitado, habilitado, alarma y comunicación perdida.
- Validar accesibilidad/legibilidad en la resolución y dispositivo realmente seleccionados.
- La interfaz no es una barrera de seguridad; indicar claramente el estado físico de habilitación.

El código HTML/CSS/JS de interfaz inicial puede incorporarse aquí cuando esté disponible en el repositorio, preservando autoría y dependencias.