# Agente de respuesta a reclamaciones sanitarias

Este repositorio contiene la documentación mínima para configurar un agente capaz de leer reclamaciones sanitarias en PDF y generar respuestas institucionales basadas exclusivamente en modelos autorizados.

---

## Estructura recomendada del repositorio

```text
.github/
  copilot-instructions.md

AGENTS.md
README.md

docs/
  modelo_institucional_respuesta.md
  modelos_respuesta_reclamaciones.md
  plantilla_word_reclamaciones.md

plantillas/
  plantilla_respuesta_reclamacion.docx
```

---

## Función de cada archivo

### `.github/copilot-instructions.md`

Contiene las instrucciones generales para Copilot dentro del repositorio.

Define:

- Rol del agente.
- Fuentes autorizadas.
- Flujo de trabajo.
- Restricciones críticas.
- Formato de respuesta.
- Uso obligatorio de la plantilla Word institucional.

### `AGENTS.md`

Contiene reglas operativas para agentes compatibles con este archivo.

Resume el comportamiento esperado y las prohibiciones principales.

### `docs/modelo_institucional_respuesta.md`

Describe la estructura formal del documento institucional observado:

- Encabezado.
- Destinatario.
- Fecha.
- Saludo.
- Cuerpo.
- Despedida.
- Firma.
- Pie de página.

### `docs/modelos_respuesta_reclamaciones.md`

Archivo destinado a incorporar los modelos textuales de respuesta a reclamaciones.

Cada modelo debe tener identificador, categoría, ámbito de aplicación, texto base y variables permitidas.

### `docs/plantilla_word_reclamaciones.md`

Define cómo debe estar preparada la plantilla Word para que el agente pueda generar documentos descargables.

Incluye los marcadores recomendados:

```text
{{DESTINATARIO_TRATAMIENTO}}
{{DESTINATARIO_NOMBRE}}
{{DESTINATARIO_DIRECCION}}
{{DESTINATARIO_CP}}
{{DESTINATARIO_MUNICIPIO}}
{{FECHA}}
{{SALUDO}}
{{CUERPO_RESPUESTA}}
{{DESPEDIDA}}
{{FIRMA_NOMBRE}}
{{FIRMA_CARGO}}
{{FIRMA_DIRECCION}}
```

### `plantillas/plantilla_respuesta_reclamacion.docx`

Documento Word institucional que debe usarse como base para generar la respuesta descargable.

Debe conservar logotipos, encabezados, pies, márgenes, estilos, firma y distribución visual.

---

## Flujo recomendado de uso

1. Añadir los modelos reales de respuesta en `docs/modelos_respuesta_reclamaciones.md`.
2. Crear o adaptar la plantilla Word institucional con los marcadores definidos.
3. Subir una reclamación en PDF al agente.
4. El agente analiza el PDF y selecciona el modelo aplicable.
5. El agente muestra la respuesta primero en formato editable, si el entorno lo permite.
6. Si el usuario lo solicita, el agente genera un Word descargable usando la plantilla institucional.

---

## Regla esencial

El agente no debe inventar contenido.

Si no puede responder con los modelos disponibles, debe detenerse y solicitar el modelo o la aclaración necesaria.
