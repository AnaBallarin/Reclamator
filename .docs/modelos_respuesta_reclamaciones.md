# Modelos de respuesta a reclamaciones sanitarias

Este archivo debe recoger los modelos textuales que el agente puede utilizar para responder reclamaciones.

Cada modelo debe estar identificado de forma clara para facilitar la clasificación de la reclamación y evitar respuestas improvisadas.

---

## Instrucciones de uso de este archivo

Para cada modelo, utiliza la siguiente estructura:

```markdown
## MODELO-[ID]: [Título del modelo]

### Categoría
[Categoría de reclamación: demora, trato, cita, derivación, información, asistencia, documentación, etc.]

### Ámbito de aplicación
[Centro de Salud, PAC, ESAPD, Unidad de Residencias u otro dispositivo.]

### Cuándo utilizar este modelo
[Condiciones que deben cumplirse para usar el modelo.]

### Cuándo no utilizar este modelo
[Situaciones en las que este modelo no debe usarse.]

### Variables permitidas
- {{CENTRO}}
- {{FECHA_HECHOS}}
- {{ESPECIALIDAD}}
- {{SERVICIO}}
- {{PROFESIONAL}}
- {{TRATAMIENTO}}
- {{OTRA_VARIABLE}}

### Texto base del modelo
[Incluir aquí el texto literal del modelo institucional.]

### Adaptaciones permitidas
[Indicar qué partes pueden adaptarse sin alterar el sentido del modelo.]
```

---

## Reglas obligatorias

- El agente debe utilizar siempre uno de los modelos incluidos en este archivo o en la documentación de configuración equivalente.
- El agente no puede crear modelos nuevos.
- El agente no puede mezclar párrafos de distintos modelos salvo que esté expresamente permitido.
- El agente no puede añadir párrafos no incluidos en el modelo base.
- El agente solo puede sustituir variables autorizadas.
- Si ningún modelo encaja, debe detenerse y emitir error de clasificación.

---

## Plantilla para añadir modelos

Copia y completa el siguiente bloque para cada nuevo modelo institucional.

```markdown
## MODELO-XXX: [Título]

### Categoría
[Indicar categoría]

### Ámbito de aplicación
[Indicar ámbito]

### Cuándo utilizar este modelo
[Indicar supuestos de uso]

### Cuándo no utilizar este modelo
[Indicar exclusiones]

### Variables permitidas
- {{CENTRO}}
- {{FECHA_HECHOS}}
- {{SERVICIO}}
- {{ESPECIALIDAD}}

### Texto base del modelo
[Texto literal del modelo]

### Adaptaciones permitidas
[Indicar adaptaciones posibles]
```
