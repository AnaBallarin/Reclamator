# Especificación técnica de la plantilla Word institucional para respuestas a reclamaciones

Este documento define cómo debe prepararse y utilizarse la plantilla Word institucional para que el agente pueda generar respuestas descargables a reclamaciones sanitarias sin alterar el formato oficial.

El archivo esperado es:

```text
plantillas/plantilla_respuesta_reclamacion.docx
```

---

## 1. Objetivo

La plantilla Word debe funcionar como documento base institucional para generar respuestas formales a reclamaciones sanitarias.

El agente debe utilizar esta plantilla cuando el usuario solicite una respuesta en documento Word descargable.

La finalidad de la plantilla es permitir que el agente inserte únicamente el contenido variable de cada respuesta, conservando la apariencia institucional del documento original:

- Logotipos.
- Cabecera.
- Pie de página.
- Márgenes.
- Tipografías.
- Alineaciones.
- Firma institucional.
- Distribución visual del documento.
- Sello o distintivo institucional, si existe.

El agente no debe crear un documento Word desde cero si existe una plantilla institucional disponible.

---

## 2. Ubicación obligatoria de la plantilla

La plantilla Word institucional debe guardarse en la siguiente ruta del repositorio:

```text
plantillas/plantilla_respuesta_reclamacion.docx
```

Opcionalmente, puede conservarse una copia editable o de trabajo para revisión interna:

```text
plantillas/plantilla_respuesta_reclamacion_EDITABLE.docx
```

La plantilla definitiva que debe utilizar el agente será siempre:

```text
plantillas/plantilla_respuesta_reclamacion.docx
```

---

## 3. Principio de funcionamiento

La plantilla debe contener marcadores textuales simples, escritos exactamente igual en el documento Word.

Cada marcador identifica un campo variable que será sustituido por el agente o por el script de generación documental.

Ejemplo de marcador:

```text
{{CUERPO_RESPUESTA}}
```

El agente debe buscar ese texto exacto dentro del documento y sustituirlo por el contenido correspondiente.

Los marcadores deben insertarse directamente en el cuerpo editable del Word, no como imágenes, cuadros no editables ni elementos decorativos.

---

## 4. Reglas generales para crear marcadores

Los marcadores deben cumplir estas reglas:

1. Deben escribirse entre dobles llaves.
2. Deben usar mayúsculas.
3. No deben contener tildes.
4. No deben contener eñes.
5. No deben contener espacios.
6. No deben dividirse entre varias líneas.
7. No deben estar fragmentados por estilos distintos.
8. No deben insertarse dentro de imágenes.
9. No deben colocarse en zonas no editables.
10. Deben escribirse exactamente igual en el Word y en la documentación técnica.

Ejemplo correcto:

```text
{{CUERPO_RESPUESTA}}
```

Ejemplos incorrectos:

```text
{{CUERPO_
RESPUESTA}}
```

```text
{{CUERPO RESPUESTA}}
```

```text
{{CUERPO_RESPUESTA }}
```

```text
{{DIRECCIÓN_DESTINATARIO}}
```

---

## 5. Marcadores obligatorios recomendados

La plantilla debe contener, como mínimo, los siguientes marcadores.

### 5.1. Destinatario

```text
{{DESTINATARIO_NOMBRE}}
{{DESTINATARIO_DIRECCION}}
{{DESTINATARIO_CP}}
{{DESTINATARIO_MUNICIPIO}}
```

Uso previsto:

```text
{{DESTINATARIO_NOMBRE}}
{{DESTINATARIO_DIRECCION}}
{{DESTINATARIO_CP}} {{DESTINATARIO_MUNICIPIO}} (MADRID)
```

Estos campos deben utilizarse para completar el bloque de destinatario situado en la parte superior derecha del documento.

Si el modelo institucional mantiene la fórmula `D/Dª`, puede sustituirse por un marcador específico:

```text
{{DESTINATARIO_TRATAMIENTO}}
```

Ejemplo:

```text
{{DESTINATARIO_TRATAMIENTO}} {{DESTINATARIO_NOMBRE}}
```

Valores posibles:

```text
D.
D.ª
D./D.ª
```

Si no consta con seguridad el tratamiento, debe utilizarse una fórmula neutra o solicitar aclaración, según las reglas del agente.

---

### 5.2. Fecha

```text
{{FECHA}}
```

Este marcador debe sustituirse por la fecha de emisión de la respuesta.

Formato recomendado:

```text
Móstoles, 12 de junio de 2026
```

Si se prefiere no incluir municipio en la fecha:

```text
12 de junio de 2026
```

El formato debe ser homogéneo en todos los documentos generados.

---

### 5.3. Saludo

```text
{{SALUDO}}
```

Este marcador debe sustituirse por la fórmula de saludo correspondiente.

Ejemplos:

```text
Estimada señora:
```

```text
Estimado señor:
```

```text
Estimado/a paciente:
```

Si no puede determinarse con seguridad el género o tratamiento del destinatario, debe utilizarse una fórmula neutra institucional o solicitar aclaración, según el grado de obligatoriedad del dato.

---

### 5.4. Cuerpo de la respuesta

```text
{{CUERPO_RESPUESTA}}
```

Este es el marcador principal de la plantilla.

Debe sustituirse por la respuesta formal elaborada a partir del modelo de respuesta seleccionado y de los datos explícitos contenidos en la reclamación.

El contenido insertado en este marcador debe cumplir las reglas generales del agente:

- No inventar información.
- No añadir hechos no presentes en la reclamación.
- No añadir párrafos nuevos que no existan en el modelo base.
- No modificar el sentido del modelo utilizado.
- No introducir explicaciones clínicas, administrativas o legales no incluidas en la documentación de referencia.
- Mantener tono formal, institucional y prudente.

---

### 5.5. Despedida

```text
{{DESPEDIDA}}
```

Este marcador debe sustituirse por la fórmula de cierre prevista en el modelo o por la fórmula fija institucional si así se decide.

Ejemplo:

```text
Atentamente,
```

Si la despedida es siempre la misma, puede dejarse como texto fijo en la plantilla y no utilizar este marcador.

---

## 6. Marcadores opcionales

Los siguientes marcadores son opcionales y solo deben incluirse si el circuito de trabajo los necesita.

### 6.1. Asunto

```text
{{ASUNTO}}
```

Solo debe incluirse si la plantilla institucional contiene un campo visible de asunto.

Si la plantilla no contempla asunto, no debe añadirse artificialmente.

---

### 6.2. Número de expediente o referencia

```text
{{NUMERO_EXPEDIENTE}}
```

Debe utilizarse únicamente si la reclamación o el sistema de gestión aporta un número de expediente o referencia.

No debe inventarse ni generarse automáticamente salvo que exista una regla técnica externa validada para ello.

---

### 6.3. Centro o dispositivo asistencial

```text
{{CENTRO_SALUD}}
```

Puede utilizarse cuando el modelo de respuesta necesite mencionar el centro o dispositivo implicado.

Ejemplos de valores:

```text
Centro de Salud Francia
Punto de Atención Continuada de Móstoles
Equipo de Soporte de Atención Paliativa Domiciliaria
Unidad de Atención a Residencias
```

Este campo solo puede completarse si el centro o dispositivo consta en la reclamación o en la documentación asociada.

---

### 6.4. Firma variable

Si la firma puede cambiar según la unidad, responsable o circuito, pueden usarse los siguientes marcadores:

```text
{{FIRMA_NOMBRE}}
{{FIRMA_CARGO}}
{{FIRMA_DIRECCION}}
```

Ejemplo:

```text
{{FIRMA_NOMBRE}}
{{FIRMA_CARGO}}
{{FIRMA_DIRECCION}}
```

Si la firma institucional es siempre la misma, se recomienda dejarla como texto fijo en la plantilla.

Firma fija recomendada según el modelo institucional aportado:

```text
Elena Aguilar Hurtado
Responsable de la Unidad de Atención al Paciente
Dirección Asistencial Oeste
```

---

## 7. Texto fijo institucional

La plantilla debe mantener como texto fijo todos los elementos institucionales que no deban cambiar.

Según el modelo aportado, deben conservarse como contenido fijo:

```text
Dirección Asistencial Oeste
Gerencia Asistencial de Atención Primaria
CONSEJERÍA DE SANIDAD
```

También debe conservarse el bloque de pie de página:

```text
Calle Alonso Cano, 8
28993 Móstoles
Tel. +34 91 648 91 71
daoeste@salud.madrid.org
```

Y, si procede, la firma institucional:

```text
Elena Aguilar Hurtado
Responsable de la Unidad de Atención al Paciente
Dirección Asistencial Oeste
```

Estos elementos no deben ser modificados por el agente salvo que el usuario indique expresamente que hay una nueva versión institucional de la plantilla.

---

## 8. Estructura visual recomendada de la plantilla

La plantilla debe conservar la distribución visual del modelo institucional.

La zona editable del documento puede estructurarse del siguiente modo:

```text
[Logotipo Comunidad de Madrid]                      [Dirección Asistencial Oeste]
                                                    [Gerencia Asistencial de Atención Primaria]
                                                    [CONSEJERÍA DE SANIDAD]

                                                    {{DESTINATARIO_TRATAMIENTO}} {{DESTINATARIO_NOMBRE}}
                                                    {{DESTINATARIO_DIRECCION}}
                                                    {{DESTINATARIO_CP}} {{DESTINATARIO_MUNICIPIO}} (MADRID)

                                                    {{FECHA}}


{{SALUDO}}

{{CUERPO_RESPUESTA}}


{{DESPEDIDA}}

                                  Elena Aguilar Hurtado
                                  Responsable de la Unidad de Atención al Paciente
                                  Dirección Asistencial Oeste


[Calle Alonso Cano, 8...]                                      [Sello o distintivo institucional]
```

Si se opta por firma variable, el bloque de firma debe ser:

```text
                                  {{FIRMA_NOMBRE}}
                                  {{FIRMA_CARGO}}
                                  {{FIRMA_DIRECCION}}
```

---

## 9. Campos críticos y campos opcionales

No todos los marcadores tienen la misma importancia.

### 9.1. Campos críticos

Se consideran campos críticos aquellos sin los cuales no debería generarse una respuesta formal completa:

```text
{{DESTINATARIO_NOMBRE}}
{{FECHA}}
{{SALUDO}}
{{CUERPO_RESPUESTA}}
```

Si falta alguno de estos datos y no puede completarse de forma segura, el agente debe solicitar aclaración antes de generar el Word, salvo que exista una regla institucional que permita usar una fórmula neutra.

### 9.2. Campos administrativos importantes

Se consideran campos administrativos importantes:

```text
{{DESTINATARIO_DIRECCION}}
{{DESTINATARIO_CP}}
{{DESTINATARIO_MUNICIPIO}}
{{NUMERO_EXPEDIENTE}}
```

Si no constan en la reclamación, no deben inventarse.

Según el circuito de trabajo, el agente deberá:

- Solicitar aclaración.
- Dejar el marcador sin sustituir.
- Sustituirlo por una fórmula neutra previamente validada.
- Omitir la línea si el procedimiento técnico lo permite y no altera la estructura formal.

La opción concreta debe estar definida en las instrucciones operativas del agente.

### 9.3. Campos opcionales

Se consideran campos opcionales:

```text
{{ASUNTO}}
{{CENTRO_SALUD}}
{{FIRMA_NOMBRE}}
{{FIRMA_CARGO}}
{{FIRMA_DIRECCION}}
```

Solo deben utilizarse si la plantilla o el modelo de respuesta los contempla.

---

## 10. Reglas de sustitución

El agente o el script que genere el Word debe seguir este procedimiento:

1. Cargar la plantilla existente desde:

```text
plantillas/plantilla_respuesta_reclamacion.docx
```

2. Localizar todos los marcadores definidos.

3. Sustituir cada marcador por el texto correspondiente.

4. Mantener el estilo del párrafo donde se encuentra cada marcador.

5. Mantener encabezados, pies de página, logotipos, sellos y elementos institucionales.

6. No alterar márgenes, orientación, tamaño de página ni distribución.

7. No crear una plantilla nueva desde cero.

8. Guardar una copia como documento nuevo.

9. No sobrescribir la plantilla original.

Nombre recomendado para el documento generado:

```text
respuesta_reclamacion_{{FECHA}}.docx
```

Si existe número de expediente:

```text
respuesta_reclamacion_{{NUMERO_EXPEDIENTE}}.docx
```

---

## 11. Tratamiento de campos no disponibles

Si un campo no está disponible en la reclamación o en la documentación asociada:

- No debe inventarse.
- No debe deducirse.
- No debe completarse por aproximación.
- No debe obtenerse de conocimiento externo.
- No debe sustituirse por contenido no validado.

El agente debe actuar según la importancia del campo.

### 11.1. Si el campo es crítico

Debe detener el proceso y solicitar aclaración.

Formato de incidencia:

```text
Incidencia detectada:
No consta [campo necesario] para completar la plantilla institucional.

Información necesaria para continuar:
Indique [dato concreto necesario] o proporcione una versión de la reclamación/documentación donde conste.
```

### 11.2. Si el campo es administrativo importante

Debe aplicar la regla definida por el circuito de trabajo.

Si no existe regla definida, debe solicitar aclaración.

### 11.3. Si el campo es opcional

Puede omitirse únicamente si la plantilla lo permite sin alterar la coherencia formal del documento.

---

## 12. Reglas específicas sobre el cuerpo de respuesta

El contenido de `{{CUERPO_RESPUESTA}}` debe proceder exclusivamente de:

1. El modelo de respuesta seleccionado.
2. Los datos explícitos contenidos en la reclamación.
3. La documentación de configuración del agente.

El cuerpo de respuesta no puede incluir:

- Hechos nuevos.
- Suposiciones.
- Valoraciones no previstas.
- Párrafos añadidos por cortesía.
- Información clínica no incluida en el modelo.
- Información legal no incluida en el modelo.
- Explicaciones administrativas no previstas en el modelo.
- Afirmaciones de comprobación, revisión o actuación si no constan en el modelo o en la documentación.

Si el modelo no permite responder adecuadamente a la reclamación, el agente debe detenerse y comunicar incidencia.

---

## 13. Reglas de formato dentro del Word

Al sustituir los marcadores, debe conservarse el formato institucional de la plantilla.

Reglas recomendadas:

- El texto insertado debe adoptar el estilo del párrafo donde estaba el marcador.
- El cuerpo debe conservar separación lógica entre párrafos.
- No deben introducirse tablas salvo que el modelo institucional las contemple.
- No deben insertarse imágenes nuevas.
- No deben modificarse logotipos ni sellos existentes.
- No deben cambiarse márgenes.
- No debe alterarse el tamaño de página.
- No deben modificarse encabezados ni pies.
- No deben eliminarse líneas en blanco que tengan función visual en el modelo, salvo regla técnica validada.
- No debe quedar texto superpuesto, desplazado fuera de página o con cortes anómalos.

---

## 14. Control de calidad antes de entregar el Word

Antes de entregar el documento generado, debe comprobarse:

- La plantilla original no ha sido sobrescrita.
- El documento generado conserva la cabecera institucional.
- El documento generado conserva el pie de página.
- El documento generado conserva logotipos y sellos.
- No quedan marcadores sin sustituir, salvo decisión expresa.
- Los campos sustituidos son correctos.
- No se ha inventado información.
- El cuerpo de respuesta procede del modelo seleccionado.
- No se han añadido párrafos no incluidos en el modelo base.
- El saludo concuerda con el tratamiento.
- La fecha tiene formato correcto.
- La firma institucional se mantiene.
- La respuesta es coherente con la reclamación.
- El documento final puede abrirse correctamente en Word.

---

## 15. Versión mínima recomendada de la plantilla

Para una primera implantación estable, se recomienda utilizar únicamente estos marcadores:

```text
{{DESTINATARIO_NOMBRE}}
{{DESTINATARIO_DIRECCION}}
{{DESTINATARIO_CP}}
{{DESTINATARIO_MUNICIPIO}}
{{FECHA}}
{{SALUDO}}
{{CUERPO_RESPUESTA}}
```

Y dejar como texto fijo:

```text
Atentamente,
```

```text
Elena Aguilar Hurtado
Responsable de la Unidad de Atención al Paciente
Dirección Asistencial Oeste
```

Esta configuración reduce errores y evita que el agente modifique elementos institucionales que previsiblemente serán estables.
