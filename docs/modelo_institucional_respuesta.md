# Modelo institucional de respuesta a reclamaciones sanitarias

Este documento describe la estructura visual y textual que debe respetarse al generar respuestas institucionales a reclamaciones sanitarias.

La plantilla formal de salida se encuentra en:

```text
plantillas/plantilla_respuesta_reclamacion.docx
```

La plantilla Word debe conservarse como documento base para generar respuestas descargables.

---

## 1. Estructura general del documento

El documento institucional tiene una sola página base con la siguiente estructura:

1. Encabezado institucional.
2. Bloque de destinatario alineado hacia la zona superior derecha.
3. Fecha bajo el bloque de destinatario.
4. Saludo inicial.
5. Cuerpo de la respuesta.
6. Despedida.
7. Firma institucional centrada.
8. Datos de contacto en el pie izquierdo.
9. Sello o distintivo institucional en el pie derecho.

---

## 2. Encabezado institucional

El encabezado contiene:

- Logotipo de la Comunidad de Madrid en la zona superior izquierda.
- Texto institucional en la zona superior derecha:

```text
Dirección Asistencial Oeste
Gerencia Asistencial de Atención Primaria
CONSEJERÍA DE SANIDAD
```

Estos elementos deben mantenerse sin modificación salvo que se actualice oficialmente la plantilla.

---

## 3. Bloque de destinatario

El bloque de destinatario aparece en la zona superior derecha del cuerpo del documento.

Estructura visual esperada:

```text
D/Dª
C/
(CP) (Municipio) (MADRID)
```

Marcadores recomendados:

```text
{{DESTINATARIO_TRATAMIENTO}}
{{DESTINATARIO_NOMBRE}}
{{DESTINATARIO_DIRECCION}}
{{DESTINATARIO_CP}}
{{DESTINATARIO_MUNICIPIO}}
```

Uso recomendado:

```text
{{DESTINATARIO_TRATAMIENTO}} {{DESTINATARIO_NOMBRE}}
{{DESTINATARIO_DIRECCION}}
{{DESTINATARIO_CP}} {{DESTINATARIO_MUNICIPIO}} (MADRID)
```

Si los datos del destinatario no constan en la reclamación, no deben inventarse.

---

## 4. Fecha

La fecha aparece bajo el bloque de destinatario.

Marcador recomendado:

```text
{{FECHA}}
```

Formato sugerido:

```text
Madrid, [día] de [mes] de [año]
```

Si el agente no tiene instrucción explícita sobre la fecha que debe utilizarse, debe solicitar confirmación o conservar el marcador.

---

## 5. Saludo

El saludo aparece alineado a la izquierda.

Ejemplo base observado:

```text
Estimada:
```

Marcador recomendado:

```text
{{SALUDO}}
```

Adaptaciones permitidas:

- `Estimado:`
- `Estimada:`
- `Estimado señor:`
- `Estimada señora:`
- Otra fórmula solo si está prevista en el modelo de respuesta o en las instrucciones institucionales.

No debe inferirse el género si no consta con claridad.

---

## 6. Cuerpo de la respuesta

El cuerpo de la respuesta sustituye el marcador:

```text
{{CUERPO_RESPUESTA}}
```

Debe elaborarse exclusivamente a partir del modelo de respuesta seleccionado y de los datos explícitos de la reclamación.

No se deben añadir párrafos nuevos que no existan en el modelo base.

---

## 7. Despedida

La despedida observada en la plantilla es:

```text
Atentamente,
```

Debe mantenerse salvo que el modelo institucional aplicable indique otra fórmula.

Marcador opcional:

```text
{{DESPEDIDA}}
```

Valor por defecto:

```text
Atentamente,
```

---

## 8. Firma institucional

La firma institucional aparece centrada en la zona inferior-media del documento.

Texto base observado:

```text
Elena Aguilar Hurtado
Responsable de la Unidad de Atención al Paciente
Dirección Asistencial Oeste
```

Marcadores recomendados:

```text
{{FIRMA_NOMBRE}}
{{FIRMA_CARGO}}
{{FIRMA_DIRECCION}}
```

Valores por defecto, salvo indicación contraria:

```text
Elena Aguilar Hurtado
Responsable de la Unidad de Atención al Paciente
Dirección Asistencial Oeste
```

Si la firma institucional cambia, debe actualizarse la plantilla Word y este documento.

---

## 9. Pie de página

El pie izquierdo contiene datos de contacto institucionales:

```text
Calle Alonso Cano, 8
28993 Móstoles
Tel. +34 91 648 91 71
daoeste@salud.madrid.org
```

El pie derecho contiene el distintivo institucional o sello gráfico existente en la plantilla.

Estos elementos deben conservarse en el Word descargable.

---

## 10. Reglas de generación del Word

Al generar una respuesta en documento Word:

1. Abrir la plantilla `plantillas/plantilla_respuesta_reclamacion.docx`.
2. Sustituir únicamente los marcadores definidos.
3. Mantener encabezados, pies, logos, márgenes, estilos y distribución.
4. No reconstruir visualmente el documento desde cero.
5. No eliminar elementos gráficos institucionales.
6. No insertar contenido fuera de las zonas previstas.
7. Guardar el documento generado con un nombre claro, por ejemplo:

```text
respuesta_reclamacion_[fecha]_[centro].docx
```

Si la plantilla no contiene marcadores editables o el agente no puede insertar el texto con seguridad, debe detenerse y solicitar instrucciones.
