# Hardware

Directorio de documentación del montaje físico, diagramas, cableado y configuración de módulos. No almacenar planos como si estuvieran validados sin revisar contra el montaje real.

## Organización prevista

- `modules/`: fichas de módulos comerciales y revisiones exactas.
- `wiring/`: diagramas de interconexión, pinouts confirmados y listas de cables.
- `enclosure/`: distribución mecánica, riel DIN, conectores, etiquetado y ventilación.
- `photos/`: evidencia del montaje con fecha/versión.

Antes de agregar un esquema, incluir versión, autor, alcance, estado (borrador/revisado) y referencias. El montaje inicial no debe incluir PCB personalizada. Registrar el conjunto y la revisión de cada módulo en `../bom/components.csv`. No documentar conexiones de la válvula hasta verificar su pinout oficial.