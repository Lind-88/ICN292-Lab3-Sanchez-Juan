# ICN292-Lab3-Sanchez-Juan

**Estudiante:** Juan Sánchez González  
**RUT:** 21.749.266  
**Semilla:** S = 266  
**Fecha:** 23 de septiembre de 2026  

## Parámetros personales

A partir de la semilla personal se utilizaron los siguientes parámetros:

- **S = 266**
- **U = $46.000**
- **D = 21 días**

## Descripción

Este repositorio contiene los archivos correspondientes al Laboratorio N°3 de ICN292.

El trabajo implementa en n8n un MVP para la clasificación de solicitudes de devolución de AndesHogar SpA, incluyendo:

- Flujo principal de triage.
- Workflow emisor de solicitudes.
- Workflow programado de resumen.
- Registro de resultados mediante Data Tables.
- Consulta de la UF mediante una API pública.
- Manejo de errores y casos borde.
- Informe y evidencias de ejecución.

## Archivos incluidos

### `ICN292-Lab3-Sánchez-Juan-triage.json`

**Para abrirlo:**

1. Iniciar n8n.
2. Crear un nuevo workflow.
3. Seleccionar la opción **Import from File**.
4. Importar `ICN292-Lab3-Sánchez-Juan-triage.json`.
5. Configurar las credenciales necesarias antes de ejecutar.

---

### `ICN292-Lab3-Sánchez-Juan-emisor.json`

**Para reproducirlo:**

1. Crear un nuevo workflow.
2. Importar el archivo en n8n.
3. Verificar que el workflow de triage se encuentre publicado/activo.
4. Configurar en el nodo HTTP Request la Production URL del Webhook del workflow de triage.
5. Ejecutar el workflow.

---

### `ICN292-Lab3-Sánchez-Juan-resumen.json`

**Para reproducirlo:**

1. Crear un nuevo workflow.
2. Importar el archivo en n8n.
3. Verificar que exista la Data Table `registro_devoluciones`.
4. Configurar las credenciales de correo si corresponde.
5. Ejecutar manualmente para pruebas o activar el Schedule Trigger.

---

## Data Table requerida

Para ejecutar correctamente los workflows se debe disponer de una Data Table llamada:

`registro_devoluciones`

Con campos equivalentes a:

- `fecha_dia`
- `fecha_hora`
- `id_solicitud`
- `sku`
- `monto`
- `dias_desde_compra`
- `estado_producto`
- `email_cliente`
- `ruta`
- `motivo`
- `U`
- `D`
- `valor_uf`
- `monto_uf`
- `aprobacion_auto`

## Servicio externo utilizado

El workflow consulta la API pública:

`https://mindicador.cl/api`

De la respuesta se utiliza el campo:

`uf.valor`

para expresar el monto de las solicitudes en unidades de fomento.


```bash
Hola /*Prueba*/
