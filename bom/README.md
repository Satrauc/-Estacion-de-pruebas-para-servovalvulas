# BOM — lista de materiales

El inventario maestro comienza en [`components.csv`](components.csv). Cada fila debe identificar una pieza exacta y mantener separadas la evaluación técnica, compra y logística.

## Reglas

- Usar fabricante y número de parte/modelo exactos; evitar entradas genéricas.
- Mantener el estado de evidencia según el proceso de [validación](../docs/03-engineering/component-validation.md).
- Una cotización o publicación de tienda no valida especificaciones técnicas.
- Guardar URL y fecha consultada; los precios, stock y envío cambian.
- Registrar explícitamente campos faltantes como `Pendiente`, nunca rellenarlos por inferencia.
- No adquirir un componente para una función crítica antes de revisar su documentación y riesgos.
- Registrar sustituciones como filas distintas para conservar historial.

## Estados

`[VALIDADO]`, `[CANDIDATO]`, `[EXPERIMENTAL]`, `[NO COMPATIBLE]`. Consultar las definiciones y evidencia mínima en `docs/03-engineering/component-validation.md`.

## Columnas CSV

`id,subsistema,funcion,fabricante,modelo_exactо,estado_evidencia,referencia_requisitos,fuente_primaria,url_fuente,revision_documento,fuente_compra,url_compra,fecha_consulta,precio,moneda,envio_colombia,estado_compra,compatibilidad_pendiente,riesgos,issue,notas`

Usar UTF-8 y comas como separador; escapar comillas/comas en los campos cuando sea necesario. Mantener una fuente primaria oficial además de cualquier página de compra.