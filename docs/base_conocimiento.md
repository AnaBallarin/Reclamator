# AGENTS.md: reglas operativas para el agente de reclamaciones sanitarias

## Identidad operativa

Eres un agente de apoyo a la gestión sanitaria para elaborar respuestas formales a reclamaciones de pacientes.

Tu tarea no es valorar clínicamente los hechos ni emitir opiniones. Tu tarea es transformar una reclamación recibida en PDF en una respuesta institucional ajustada a los modelos disponibles.

---

## Principio rector

No debes inventar, deducir ni completar información no documentada.

Toda respuesta debe estar sustentada exclusivamente por:

1. El PDF de reclamación aportado por el usuario.
2. Los modelos de respuesta incluidos en la documentación del repositorio.
3. La plantilla institucional Word definida para la salida descargable.

---

## Flujo de trabajo

### 1. Lectura de la reclamación

Lee el PDF completo. Si contiene texto manuscrito o escaneado, interpreta únicamente lo que sea razonablemente legible.

Extrae, si constan:

- Datos del reclamante o paciente.
- Centro o dispositivo asistencial afectado.
- Fecha o periodo de los hechos.
- Motivo de la reclamación.
- Hechos descritos.
- Servicio, unidad, categoría profesional o profesional mencionado.
- Petición expresa del reclamante.

No inventes datos ausentes.

### 2. Selección del modelo

Busca en la documentación del repositorio el modelo que encaje mejor con la casuística.

Si no encuentras modelo adecuado, no redactes respuesta final.

### 3. Adaptación permitida

Puedes adaptar únicamente:

- Género y número.
- Fórmula de tratamiento.
- Centro o dispositivo.
- Fecha o periodo.
- Especialidad, prueba, derivación, tratamiento, cita o unidad implicada.
- Datos específicos presentes en la reclamación.

No puedes añadir nuevos párrafos ni modificar el sentido del modelo.

### 4. Salida inicial

La respuesta debe presentarse primero en formato editable si el entorno lo permite: lienzo, canvas, página editable o equivalente.

Si no existe esa función, debe mostrarse en el chat en formato Markdown claro.

### 5. Salida Word

Si el usuario solicita un documento descargable, utiliza la plantilla:

```text
plantillas/plantilla_respuesta_reclamacion.docx
```

No generes un Word desde cero si la plantilla existe.

---

## Formato de respuesta en chat

```markdown
**ASUNTO:**  
[Asunto]

**CUERPO DE LA RESPUESTA:**  
[Cuerpo de la respuesta]

**¿Desea que genere esta respuesta en un documento Word descargable?**
```

No incluyas análisis, justificaciones ni explicación del proceso salvo petición expresa del usuario.

---

## Formato de incidencia

Si no puedes continuar con seguridad, responde solo:

```markdown
**Incidencia detectada:**  
[Problema encontrado.]

**Información necesaria para continuar:**  
[Dato, modelo o aclaración necesaria.]
```

Si no hay modelo aplicable, responde:

```markdown
**Error de clasificación:** No existe un modelo preestablecido para esta casuística. Por favor, proporcione el modelo de referencia adecuado o indique las directrices de respuesta.
```

---

## Prohibiciones

- No usar conocimiento externo.
- No añadir normativa no documentada.
- No introducir valoraciones clínicas propias.
- No atribuir responsabilidades.
- No prometer actuaciones no recogidas en el modelo.
- No modificar el sentido del texto institucional.
- No rellenar campos ausentes con suposiciones.

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

# Índice de modelos de respuesta a reclamaciones

Este documento funciona como índice maestro para que el agente pueda clasificar una reclamación sanitaria y seleccionar el modelo de respuesta correspondiente.

El agente debe utilizar este índice como mapa de decisión, pero la redacción final de la respuesta debe construirse exclusivamente a partir del modelo concreto ubicado en la carpeta `modelos/` y de los datos explícitos contenidos en la reclamación.

---

## 1. Regla general de uso

Ante una reclamación en PDF, el agente debe seguir este orden:

1. Leer completamente la reclamación.
2. Identificar el motivo principal de la reclamación.
3. Consultar este índice.
4. Seleccionar el modelo aplicable dentro de la carpeta `modelos/`.
5. Adaptar únicamente las variables permitidas por el modelo.
6. Si no existe un modelo adecuado, detenerse y comunicar incidencia.

El agente no debe redactar una respuesta si no localiza un modelo aplicable.

---

## 2. Fuentes y prioridad documental

La prioridad de uso de documentos será la siguiente:

| Prioridad | Documento o carpeta | Uso |
|---|---|---|
| 1 | `modelos/` | Modelos definitivos para redactar la respuesta |
| 2 | `docs/modelos_respuesta_reclamaciones.md` | Índice para clasificar la reclamación y localizar el modelo |
| 3 | `AGENTS.md` | Reglas operativas del agente |
| 4 | `.github/copilot-instructions.md` | Instrucciones generales de Copilot para el repositorio |
| 5 | `docs/modelo_institucional_respuesta.md` | Formato institucional de la respuesta |
| 6 | `docs/plantilla_word_reclamaciones.md` | Reglas técnicas de la plantilla Word |
| 7 | `plantillas/plantilla_respuesta_reclamacion.docx` | Plantilla Word institucional para documento descargable |

Los documentos de `docs/`, `AGENTS.md`, `.github/copilot-instructions.md` y `README.md` son documentación de configuración. No deben utilizarse como modelos de respuesta salvo que así se indique expresamente.

---

## 3. Modelos disponibles

| ID | Categoría | Archivo | Estado | Uso principal |
|---|---|---|---|---|
| 01 | Accesibilidad telefónica | `modelos/01_accesibilidad_telefonica.md` | Disponible | Reclamaciones sobre dificultad de contacto telefónico, llamadas no atendidas, imposibilidad de comunicación con el centro o problemas de accesibilidad telefónica. |
| 02 | Demora en citaciones | `modelos/02_demora_citaciones.md` | Disponible | Reclamaciones sobre demora para obtener cita, tiempos de espera, dificultad para conseguir consulta o disconformidad con plazos de citación. |
| 03 | Desacuerdo con organización y normas | `modelos/03_desacuerdo_organizacion_y_normas.md` | Disponible | Reclamaciones relacionadas con disconformidad con normas organizativas, funcionamiento del centro, circuitos internos o criterios administrativos establecidos. |
| 04 | Pendiente de incorporar | `modelos/04_pendiente.md` | Pendiente | No disponible todavía. El agente no debe utilizar este ID hasta que exista el archivo definitivo. |
| 05 | Pendiente de incorporar | `modelos/05_pendiente.md` | Pendiente | No disponible todavía. El agente no debe utilizar este ID hasta que exista el archivo definitivo. |
| 06 | Pendiente de incorporar | `modelos/06_pendiente.md` | Pendiente | No disponible todavía. El agente no debe utilizar este ID hasta que exista el archivo definitivo. |
| 07 | Pendiente de incorporar | `modelos/07_pendiente.md` | Pendiente | No disponible todavía. El agente no debe utilizar este ID hasta que exista el archivo definitivo. |
| 08 | Pendiente de incorporar | `modelos/08_pendiente.md` | Pendiente | No disponible todavía. El agente no debe utilizar este ID hasta que exista el archivo definitivo. |
| 09 | Pendiente de incorporar | `modelos/09_pendiente.md` | Pendiente | No disponible todavía. El agente no debe utilizar este ID hasta que exista el archivo definitivo. |

---

## 4. Criterios de clasificación

### 4.1. Modelo 01 — Accesibilidad telefónica

Usar este modelo cuando la reclamación se refiera principalmente a:

- Dificultad para contactar telefónicamente con el centro.
- Llamadas no atendidas.
- Saturación o falta de respuesta telefónica.
- Problemas para solicitar cita por teléfono.
- Disconformidad con la accesibilidad telefónica del centro o dispositivo.

No utilizar este modelo si el motivo principal es una demora clínica, una disconformidad con la asistencia recibida o una queja sobre trato profesional, salvo que el modelo contemple expresamente esa situación.

---

### 4.2. Modelo 02 — Demora en citaciones

Usar este modelo cuando la reclamación se refiera principalmente a:

- Demora para obtener cita.
- Tiempo de espera excesivo para consulta.
- Dificultad para conseguir cita con medicina, enfermería u otro profesional.
- Disconformidad con la fecha asignada.
- Cancelación o reprogramación de cita, si el modelo lo contempla.

No utilizar este modelo si la reclamación se centra en el contenido clínico de la atención, el trato recibido o la organización general del centro, salvo que la demora sea el motivo principal.

---

### 4.3. Modelo 03 — Desacuerdo con organización y normas

Usar este modelo cuando la reclamación se refiera principalmente a:

- Disconformidad con normas organizativas del centro.
- Circuitos administrativos o asistenciales establecidos.
- Funcionamiento interno del centro.
- Criterios de organización de agendas, accesos, trámites o atención.
- Rechazo o desacuerdo con una norma aplicada al caso.

No utilizar este modelo si la reclamación corresponde claramente a una demora, un problema telefónico, una disconformidad clínica o una incidencia no cubierta por el modelo.

---

## 5. Regla de no invención

El agente no debe inventar modelos, categorías ni respuestas.

Si la reclamación no encaja claramente en ninguno de los modelos disponibles, debe responder:

```text
Error de clasificación: No existe un modelo preestablecido para esta casuística. Por favor, proporcione el modelo de referencia adecuado o indique las directrices de respuesta.
```

Si el modelo aplicable existe pero no puede acceder a su contenido, debe responder:

```text
Incidencia detectada: No es posible acceder o verificar el contenido del modelo de respuesta obligatorio.

Información necesaria para continuar:
Proporcione el enlace directo al archivo del modelo correspondiente o pegue el modelo de respuesta íntegramente en el chat.
```

---

## 6. Uso de modelos pendientes

Los modelos marcados como `Pendiente` no deben utilizarse.

Cuando se incorpore un nuevo modelo, deberá actualizarse:

1. La tabla de modelos disponibles.
2. Los criterios de clasificación.
3. El nombre exacto del archivo.
4. El estado, cambiándolo de `Pendiente` a `Disponible`.

El nombre del archivo en este índice debe coincidir exactamente con el nombre real del archivo en la carpeta `modelos/`.

---

## 7. Reglas para incorporar nuevos modelos

Cada nuevo modelo deberá guardarse en la carpeta `modelos/` con un nombre claro, numerado, en minúsculas, sin tildes y con extensión `.md`.

Formato recomendado:

```text
modelos/04_nombre_del_modelo.md
```

Cada documento de modelo debería incluir, como mínimo:

```markdown
# Título del modelo

## Cuándo usar este modelo

[Descripción de la casuística]

## Criterios de clasificación

- [Criterio 1]
- [Criterio 2]
- [Criterio 3]

## Modelo base de respuesta

[Texto institucional del modelo]

## Variables permitidas

- Centro o dispositivo asistencial
- Fecha, si consta en la reclamación
- Servicio o unidad implicada, si consta
- Género y número
- Fórmula de tratamiento

## Restricciones específicas

- [Restricción 1]
- [Restricción 2]
```

---

## 8. Control de calidad para el agente

Antes de redactar, el agente debe comprobar:

- Que ha leído la reclamación completa.
- Que ha identificado el motivo principal.
- Que ha localizado un modelo disponible.
- Que el modelo seleccionado encaja con la reclamación.
- Que no necesita mezclar varios modelos.
- Que la respuesta puede elaborarse sin añadir contenido no previsto.
- Que todos los datos adaptados proceden de la reclamación o del modelo.

Si cualquiera de estas comprobaciones falla, el agente debe detenerse y comunicar incidencia.

# ACCESIBILIDAD TELEFÓNICA

## Accesibilidad telefónica. Locución opción 1 y opción 9

Propósito:
Informar sobre el funcionamiento del sistema de atención telefónica con locución inicial y diferenciación entre la opción 1 y la opción 9, en respuesta a reclamaciones por dificultad de acceso telefónico.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera a dificultades para contactar telefónicamente con el Centro de Salud.
- Utilizar cuando sea necesario explicar expresamente el funcionamiento de la locución telefónica inicial.
- Utilizar cuando proceda diferenciar entre la opción 1, que deriva al Centro de Atención Telefónica, y la opción 9, que dirige la llamada al Centro de Salud.
- No utilizar como modelo genérico si la reclamación se centra exclusivamente en demora de cita, ausencia de médico asignado o atención urgente sin cita.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
Dirección Asistencial Oeste  
Gerencia Asistencial de Atención Primaria  
CONSEJERÍA DE SANIDAD  
Calle Alonso Cano, 8  
28993 Móstoles  
Tel. +34 91 648 91 71  
daoeste@salud.madrid.org  

D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

Estimada Sra.:

En relación con el escrito presentado con fecha [Fecha del escrito] de [Año] sobre la dificultad de acceso telefónico en su Centro de Salud, procedemos a informarle sobre el funcionamiento de nuestro sistema de citación y atención telefónica.

En primer lugar, queremos trasladarle que comprendemos la complejidad que supone gestionar la atención sanitaria de una enfermedad crónica y le agradecemos que nos haya hecho llegar su experiencia, ya que nos permite analizar y mejorar nuestros procedimientos.

Respecto al sistema de citación, le informamos de que, cuando un ciudadano contacta telefónicamente, la llamada es atendida a través de una locución inicial en la que se ofrecen dos opciones:

La opción 1 deriva la llamada al Centro de Atención Telefónica y la opción 9 dirige la llamada directamente al Centro de Salud.

Este sistema se implantó con el objetivo de mejorar la eficiencia, distribuir adecuadamente la carga de llamadas y garantizar que todas las solicitudes sean gestionadas de la forma más ágil posible.

Somos conscientes de que, en determinados momentos, puede resultar difícil contactar por vía telefónica debido al volumen de llamadas, especialmente en franjas horarias de mayor demanda. La accesibilidad de los ciudadanos a los servicios sanitarios es una prioridad para nosotros y, por ello, trabajamos de manera continua para optimizar los circuitos de atención y minimizar las incidencias que puedan producirse.

Le agradecemos su comprensión y colaboración, así como el hecho de que nos transmita su opinión y sus consideraciones, puesto que nos permiten profundizar en la información sobre determinados circuitos y procedimientos de trabajo implementados en aras de la mejor calidad del servicio prestado.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Dificultad de accesibilidad telefónica. Aumento de actividad telefónica

Propósito:
Responder a reclamaciones generales sobre dificultad de accesibilidad telefónica, explicando el aumento de la actividad telefónica y la disminución de accesibilidad en determinadas franjas horarias.

Condiciones de Aplicación:
- Utilizar cuando la reclamación sea una queja general por dificultad para contactar telefónicamente con el Centro de Salud.
- Utilizar cuando no sea necesario explicar circuitos específicos como opción 1/opción 9, aplicación móvil, falta de médico asignado o urgencia sin cita.
- Utilizar cuando el enfoque principal sea reconocer el aumento de demanda telefónica y trasladar compromiso de mejora.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
[Fecha de respuesta]

Estimada Sra. [Nombre]:

En relación con su escrito presentado el [Fecha del escrito] en el Centro de Salud [Centro de Salud], debo informarle de lo siguiente:

En estos últimos años nuestra actividad telefónica se ha visto notablemente aumentada, lo que ha provocado que, sobre todo en ciertas franjas horarias, la accesibilidad telefónica a los centros se haya visto disminuida.

La accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, y más si cabe en estos últimos tiempos. Compartimos su preocupación en este sentido y le aseguramos que estamos haciendo todo lo posible por paliar esta situación.

Lamentamos el malestar producido y le agradecemos su comprensión y colaboración, al tiempo que recogemos su información y opinión, que nos es de gran utilidad para seguir trabajando y conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Dificultad de acceso telefónico. Medidas de mejora de centralitas

Propósito:
Responder a reclamaciones por dificultad de acceso telefónico explicando el incremento de llamadas y las medidas adoptadas para mejorar el funcionamiento de centralitas y canales de atención.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se centre en la dificultad de acceso telefónico al Centro de Salud.
- Utilizar cuando proceda informar de medidas organizativas concretas de mejora, como revisión de centralitas, mejora de funcionamiento y Centralita Sanitarizada.
- No utilizar si la reclamación se centra en la locución opción 1/opción 9 o en un problema técnico de cita por aplicación.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
D. [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito presentado con fecha [Fecha del escrito] de [Año] relativo a la dificultad de acceso telefónico en su Centro de Salud, debo informarle de lo siguiente:

En los últimos años nuestra actividad telefónica se ha visto notablemente aumentada, lo que ha provocado que, sobre todo en ciertas franjas horarias, la accesibilidad telefónica se haya visto disminuida en la mayoría de los Centros de Salud.

Debe saber que, para mejorar este aspecto, se han articulado una serie de medidas para paliar esta situación, como la revisión de las centralitas de los centros con actuaciones para la mejora de su funcionamiento, la puesta en marcha de una Centralita Sanitarizada y de Información sobre trámites administrativos, y algunas otras medidas aún en estudio.

Le pedimos disculpas por el malestar generado y le agradecemos que nos haya hecho llegar su escrito, dado que su opinión y consideraciones nos son de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## No cogen el teléfono. Gestiones realizadas desde historia clínica

Propósito:
Responder a reclamaciones en las que el usuario refiere dificultad de contacto telefónico, pero consta que desde el Centro se han realizado intentos de llamada sin éxito.

Condiciones de Aplicación:
- Utilizar cuando se haya comprobado en el sistema o aplicación de llamadas que el Centro ha intentado contactar con la persona usuaria.
- Utilizar cuando consten varios intentos de llamada, incluso con mensaje en contestador.
- Utilizar cuando proceda recomendar al usuario la revisión de su dispositivo o configuración de recepción de llamadas.
- Mantener el número 913700000 cuando sea el teléfono institucional de salida de llamadas que debe reconocer el usuario.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito de fecha [Fecha del escrito] sobre la dificultad de acceso telefónico en su Centro de Salud, deseo explicarle que estos últimos años nuestra actividad telefónica se ha visto notablemente aumentada, lo que ha provocado que, sobre todo en ciertas franjas horarias, la accesibilidad telefónica a los centros se haya visto disminuida.

La accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, y más si cabe en estos últimos tiempos.

Tras pedir un informe a los profesionales para monitorizar la situación que describe en su escrito, en la aplicación de llamadas está registrado que se ha intentado contactar con usted durante varios días, sin éxito, dejando incluso un mensaje en su contestador.

Le recomendamos revisar su móvil para asegurarse de que las llamadas estén entrando correctamente. Es posible que haya algún problema con la recepción o configuración del dispositivo. El teléfono desde el que realizamos las llamadas es el 913700000.

Le pedimos disculpas por el malestar generado y le agradecemos que nos haga llegar su escrito, puesto que su opinión y consideraciones nos son de gran utilidad para conseguir un servicio de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## No cogen teléfono. Locución telefónica opción 1 y opción 9

Propósito:
Responder a reclamaciones por falta de accesibilidad telefónica en las que procede explicar el sistema de locución y derivación de llamadas.

Condiciones de Aplicación:
- Utilizar cuando el usuario manifieste que no le cogen el teléfono.
- Utilizar cuando proceda explicar que las llamadas pueden ser atendidas por el Centro de Atención Telefónica o por el propio Centro de Salud, según la opción marcada.
- Utilizar cuando se quiera reforzar que el sistema busca mejorar la eficiencia y la calidad de atención.
- No utilizar cuando haya constancia de intentos de llamada desde el Centro o cuando la dificultad se relacione con falta de médico asignado.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Fecha de reclamación]
- [Año]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su reclamación con fecha [Fecha de reclamación] de [Año], en la que expresa su insatisfacción por la falta de accesibilidad telefónica en el Centro de Salud [Centro de Salud], en primer lugar, queremos decirle que comprendemos su malestar y lamentamos las molestias que haya podido ocasionarle.

En segundo lugar, debe saber que, cuando un ciudadano llama para solicitar una cita, escuchará una locución donde se le informa de que será atendido marcando la opción 1 por el Centro de Atención Telefónica o bien por el propio Centro de Salud, si la opción marcada es la 9.

Este sistema ha sido implementado para mejorar la eficiencia y la calidad de nuestra atención, asegurando que todas las llamadas sean gestionadas de manera adecuada y rápida.

La accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, y más si cabe en estos últimos tiempos. Compartimos su preocupación en este sentido y le aseguramos que estamos haciendo todo lo posible por paliar esta situación.

Nuestro objetivo es mejorar continuamente la calidad de nuestro servicio. Lamentamos su malestar, al mismo tiempo que agradecemos su reclamación, pues su información y opinión nos son de gran utilidad para conseguir un servicio de calidad y de plena satisfacción para el ciudadano.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

Dirección Asistencial Oeste  
C/ Alonso Cano, 8  
28933 Móstoles - Madrid  
Tel.: 91 648 91 23 / 91 648 91 29  
Fax: 91 648 91 74  
e-mail: uapoeste@salud.madrid.org

## No me cogen el teléfono. Medidas articuladas por la Gerencia

Propósito:
Responder a reclamaciones por falta de accesibilidad telefónica, con énfasis en las medidas articuladas por la Gerencia para paliar la situación.

Condiciones de Aplicación:
- Utilizar como modelo breve cuando la reclamación se centre en que no contestan al teléfono.
- Utilizar cuando se quiera mencionar que la actividad telefónica se ha incrementado en los últimos años.
- Utilizar cuando proceda explicar medidas generales de mejora impulsadas por la Gerencia.
- Utilizar con estructura completa aunque el documento original sea fragmentario.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
En estos últimos años nuestra actividad telefónica se ha visto notablemente aumentada, lo que ha provocado que, sobre todo en ciertas franjas horarias, la accesibilidad telefónica a los centros se haya visto disminuida.

La accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, y más si cabe en estos últimos tiempos.

Por este motivo, desde la Gerencia de Atención Primaria se han articulado una serie de medidas para paliar esta situación, como la revisión de las centralitas de los centros con actuaciones para la mejora de su funcionamiento, la puesta en marcha de una Centralita Sanitarizada y de Información sobre trámites administrativos, y algunas otras medidas aún en estudio.

Esperamos que con estas acciones y algunas otras de índole organizativa consigamos mejorar este aspecto.

Le pedimos nuestras más sinceras disculpas por el malestar generado y le agradecemos que nos haga llegar su escrito, puesto que su opinión y consideraciones nos son de gran utilidad para conseguir un servicio de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## No puedo coger cita. Problema de accesibilidad y demora para médico de familia

Propósito:
Responder a reclamaciones mixtas sobre dificultad de accesibilidad y problemas para conseguir cita con el médico de familia.

Condiciones de Aplicación:
- Utilizar cuando la reclamación combine falta de accesibilidad con dificultad para obtener cita con el médico de familia.
- Utilizar cuando proceda explicar que la creciente demanda y la escasez de profesionales pueden producir demoras superiores a lo deseable.
- Utilizar cuando se quiera indicar que se garantiza la atención en el día a usuarios que no pueden esperar.
- No utilizar si la reclamación se limita exclusivamente a no poder contactar por teléfono.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Fecha de reclamación]

Contenido:
D. [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

Estimado Sr.:

En relación con su reclamación con fecha [Fecha de reclamación], en la que expresa su insatisfacción por la falta de accesibilidad y las dificultades para conseguir cita con su médico de familia, en primer lugar, queremos decirle que comprendemos su malestar y lamentamos las molestias que haya podido ocasionarle.

Le informamos de que, en ocasiones, debido a la creciente demanda de la población y a la escasez de profesionales que dificultan la cobertura de ausencias, la demora para obtener cita con su médico de familia puede ser mayor de lo deseable, garantizando siempre la atención en el día para aquellos usuarios que no puedan esperar.

También queremos decirle que trabajamos para intentar mejorar la accesibilidad a las consultas como un proyecto de mejora continua.

Nuestro objetivo es mejorar continuamente la calidad de nuestro servicio. Lamentamos su malestar, al mismo tiempo que agradecemos su reclamación, pues su información y opinión nos es de gran utilidad para conseguir un servicio de calidad y de plena satisfacción para el ciudadano.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

Dirección Asistencial Oeste  
C/ Alonso Cano, 8  
28933 Móstoles - Madrid  
Tel.: 91 648 91 23 / 91 648 91 29  
Fax: 91 648 91 74  
e-mail: uapoeste@salud.madrid.org

## Otra respuesta de accesibilidad telefónica. Mejora progresiva

Propósito:
Responder de forma general a reclamaciones por dificultad de acceso telefónico, destacando la prioridad de la accesibilidad y la implantación progresiva de medidas de mejora.

Condiciones de Aplicación:
- Utilizar cuando se requiera una respuesta general, clara y breve sobre accesibilidad telefónica.
- Utilizar cuando se quiera transmitir compromiso de mejora sin detallar medidas concretas como centralitas, locución u opción 1/opción 9.
- No utilizar cuando existan hechos específicos que exijan otro modelo, como intentos de llamada registrados o imposibilidad de cita por falta de médico asignado.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
D. [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito de fecha [Fecha del escrito] de [Año] sobre la dificultad de acceso telefónico en su Centro de Salud, deseo explicarle lo siguiente:

La accesibilidad para los ciudadanos a nuestros servicios es una prioridad para esta Gerencia, especialmente en los últimos tiempos, en los que la demanda ha aumentado de forma significativa.

Por este motivo, se están implantando diversas medidas destinadas a mejorar la capacidad de respuesta y agilizar la atención telefónica. Confiamos en que estas actuaciones, junto con otras de carácter organizativo, permitan mejorar de manera progresiva este aspecto del servicio.

Le pedimos nuestras más sinceras disculpas por el malestar generado y le agradecemos que nos haya hecho llegar su reclamación. Sus comentarios son de gran utilidad para identificar áreas de mejora y avanzar hacia un servicio que responda plenamente a las necesidades de la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Problema de accesibilidad. Dificultad para obtención de cita con valoración positiva de la asistencia

Propósito:
Responder a reclamaciones sobre dificultad para obtener cita en las que, además, la persona usuaria manifiesta satisfacción con la atención recibida por los profesionales.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera a dificultad para obtener cita, especialmente por accesibilidad telefónica.
- Utilizar cuando el escrito incluya una valoración positiva de la atención recibida por los profesionales del Centro de Salud.
- No utilizar cuando la reclamación sea exclusivamente negativa o no mencione satisfacción con la atención profesional.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
D. [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimado Sr.:

En relación con su escrito de fecha [Fecha del escrito] sobre la dificultad para la obtención de cita en su Centro de Salud, debo informarle de lo siguiente:

En estos últimos años nuestra actividad telefónica se ha visto notablemente aumentada, lo que ha provocado que, sobre todo en ciertas franjas horarias, la accesibilidad telefónica a los centros se haya visto disminuida.

La accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, y más si cabe en estos últimos tiempos. Compartimos su preocupación en este sentido y, por ello, se están implementando diversas medidas destinadas a reforzar y optimizar los canales de comunicación con los usuarios.

Valoramos mucho que haya manifestado su satisfacción con la atención recibida por los profesionales del Centro de Salud, y le agradecemos igualmente que nos haya hecho llegar sus consideraciones, pues su información y opinión nos son de gran utilidad para conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Accesibilidad telefónica y urgencia frente a atención sin cita

Propósito:
Responder a reclamaciones que combinan dificultad de accesibilidad telefónica con discrepancias sobre atención urgente, atención sin cita o gestión de citas.

Condiciones de Aplicación:
- Utilizar cuando la reclamación mencione dificultad de acceso telefónico y, además, discrepancia sobre atención urgente o atención sin cita.
- Utilizar cuando proceda explicar la diferencia entre una urgencia médica y un problema de salud que permite cierta demora.
- Utilizar cuando se quiera indicar que, si el cuadro clínico requiere atención inmediata, la actividad sanitaria se detiene para prestar asistencia.
- No utilizar para quejas exclusivamente telefónicas sin referencia a urgencia, cita ordinaria o atención sin cita.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito de fecha [Fecha del escrito] sobre la atención recibida en su Centro de Salud, en primer lugar, debo pedirle disculpas por la demora en la contestación a su escrito.

En segundo lugar, en cuanto a la accesibilidad telefónica, debo informarle de lo siguiente:

En estos últimos años nuestra actividad telefónica se ha visto notablemente aumentada, lo que ha provocado que, sobre todo en ciertas franjas horarias, la accesibilidad telefónica a los centros se haya visto disminuida.

La accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, y más si cabe en estos últimos tiempos. Compartimos su preocupación en este sentido y le aseguramos que estamos haciendo todo lo posible por paliar esta situación.

En cuanto a la gestión de las citas, debo explicarle que una urgencia médica es aquella situación clínica que, bien por la gravedad o por lo súbito de la aparición de los síntomas, requiere una intervención inmediata.

El resto de problemas de salud que, en general, permiten una cierta demora en su atención, es recomendable que sean atendidos con cita con un profesional sanitario. Por supuesto, si el cuadro clínico precisa una atención urgente y es necesario intervenir en el momento, toda la actividad sanitaria se detiene y se realiza la asistencia inmediata.

Lamentamos el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos son de gran utilidad para conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Accesibilidad. No cogen teléfono

Propósito:
Responder a reclamaciones breves sobre dificultad para solicitar citas, con disculpa institucional y referencia a medidas generales de mejora.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera a dificultad para solicitar citas o a que no contestan el teléfono.
- Utilizar como modelo genérico breve, sin necesidad de explicar locución telefónica, centralitas o aplicación.
- No utilizar si el caso requiere diferenciar opción 1/opción 9 o si existe falta de médico asignado.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
D. [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito de fecha [Fecha del escrito] de [Año] sobre la dificultad de petición de citas, deseo explicarle que la accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, y más si cabe en estos últimos tiempos, por lo que le pedimos disculpas por ello.

Por este motivo, desde la Gerencia de Atención Primaria se vienen articulando una serie de medidas para paliar esta situación. Esperamos que, con estas acciones y algunas otras de índole organizativa, consigamos mejorar este aspecto.

Le pedimos nuestras más sinceras disculpas por el malestar generado y le agradecemos que nos haga llegar su escrito, puesto que su opinión y consideraciones nos son de gran utilidad para conseguir un servicio de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Accesibilidad teléfono y aplicación. Imposibilidad de cita por falta de médico asignado

Propósito:
Responder a reclamaciones sobre dificultad para obtener cita cuando existe además una limitación técnica relacionada con la ausencia de médico de familia asignado en el sistema.

Condiciones de Aplicación:
- Utilizar cuando la persona usuaria no pueda obtener cita por canales telemáticos o aplicación.
- Utilizar cuando el motivo sea que no tiene médico de familia asignado o dicha asignación no consta correctamente registrada.
- Utilizar cuando la reclamación combine accesibilidad telefónica, dificultad de cita y limitación técnica de la aplicación.
- No utilizar para quejas genéricas de teléfono si no existe problema de asignación de profesional.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito presentado el [Fecha del escrito] de [Año] en relación con la dificultad para la obtención de cita en su Centro de Salud, debo informarle:

La accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, especialmente en estos últimos tiempos. Compartimos su preocupación y le aseguramos que estamos trabajando de forma continua para paliar esta situación y mejorar la capacidad de respuesta del centro.

En relación con la accesibilidad telefónica, debemos informarle de que en los últimos años la actividad por esta vía se ha incrementado de manera muy significativa. Este aumento ha provocado que, sobre todo en determinadas franjas horarias, la capacidad de respuesta telefónica se vea reducida, dificultando el acceso de algunos usuarios. Estamos adoptando medidas organizativas para mejorar este aspecto y minimizar las incidencias.

Por otro lado, es importante señalar que, cuando un usuario no tiene un médico de familia asignado, el sistema no permite gestionar una cita a través de la aplicación o de los canales telemáticos habituales. Esta limitación técnica impide que se puedan ofrecer citas hasta que la asignación del profesional quede correctamente registrada en el sistema.

Entendemos y compartimos su preocupación en este sentido y le aseguramos que estamos haciendo todo lo posible por paliar esta situación, no solo intentando dotar a los centros de los recursos humanos necesarios, sino también desde el punto de vista organizativo.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Accesibilidad telefónica. Locución telefónica

Propósito:
Informar sobre el funcionamiento general de la atención telefónica con locución inicial para solicitud de cita.

Condiciones de Aplicación:
- Utilizar cuando la reclamación requiera explicar el sistema de atención telefónica por locución.
- Utilizar cuando proceda indicar que la opción 1 corresponde al Centro de Atención Telefónica y la opción 9 al propio Centro de Salud.
- Utilizar como modelo general sobre locución telefónica sin elementos adicionales como enfermedad crónica, demora de cita o falta de médico asignado.
- No utilizar para casos en los que sea necesario responder sobre intentos de llamada realizados desde el Centro.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
Dirección Asistencial Oeste  
Gerencia Asistencial de Atención Primaria  
CONSEJERÍA DE SANIDAD  
Calle Alonso Cano, 8  
28993 Móstoles  
Tel. +34 91 648 91 71  
daoeste@salud.madrid.org  

D./D.ª [Nombre]

Estimado Sr./Estimada Sra.:

En relación con su escrito presentado el [Fecha del escrito] en su Centro de Salud, nos dirigimos a usted para informarle sobre el funcionamiento de nuestro sistema de atención telefónica.

Cuando un ciudadano llama para solicitar una cita, escuchará una locución donde se le informa de que será atendido marcando la opción 1 por el Centro de Atención Telefónica o bien por el propio Centro de Salud, si la opción marcada es la 9.

Este sistema ha sido implementado para mejorar la eficiencia y la calidad de nuestra atención al cliente, asegurando que todas las llamadas sean gestionadas de manera adecuada y rápida.

La accesibilidad de los ciudadanos a nuestros centros de salud es una prioridad para nosotros, y más si cabe en estos últimos tiempos. Compartimos su preocupación en este sentido y le aseguramos que estamos haciendo todo lo posible por paliar esta situación.

Le agradecemos su comprensión y colaboración, así como el hecho de que nos transmita su opinión y sus consideraciones, puesto que nos permiten profundizar en la información sobre determinados circuitos y procedimientos de trabajo implementados en aras de la mejor calidad del servicio prestado.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

# DEMORA CITACIONES

## Recursos y demora en obtención de cita

Propósito:
Responder a reclamaciones sobre demora en la obtención de cita en el Centro de Salud, explicando la dificultad para encontrar profesionales sustitutos y la existencia de circuitos para atención urgente o no demorable.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se centre en la demora para obtener cita en el Centro de Salud.
- Utilizar cuando proceda explicar que la demora se relaciona con la dificultad para encontrar profesionales sustitutos, especialmente médicos y pediatras.
- Utilizar cuando convenga recordar que existen circuitos para atender en el momento cuadros urgentes o valoraciones que no pueden demorarse más de 48-72 horas.
- No utilizar si la reclamación se centra exclusivamente en pruebas diagnósticas, resultados hospitalarios, laboratorio o atención sin cita no urgente.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra. [Nombre]:

En relación con su escrito presentado el [Fecha del escrito] en relación con la demora en la obtención de cita en el Centro de Salud [Centro de Salud], debo explicarle lo siguiente:

La dificultad actual para encontrar profesionales sustitutos, sobre todo en el caso de médicos y pediatras, hace que, especialmente en épocas de disfrute de ausencias legalmente establecidas y/o en momentos epidemiológicos de mayor carga asistencial, se produzcan demoras en la obtención de cita mayores de lo que nos gustaría.

Entendemos y compartimos su preocupación en este sentido y le aseguramos que estamos haciendo todo lo posible por paliar esta situación.

Debe saber también que en todos los centros hay circuitos establecidos mediante los cuales los pacientes que presentan un cuadro clínico urgente o cuya valoración no se puede demorar más de 48-72 horas son atendidos en el momento, aunque no tengan cita previa.

Lamentamos el malestar generado y le agradecemos que nos haga llegar su opinión y sus consideraciones, puesto que nos son de gran ayuda para continuar mejorando la atención que prestamos a nuestros ciudadanos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Sin cita. Solicitud de atención inmediata sin urgencia

Propósito:
Responder a reclamaciones en las que el usuario acude sin cita previa y solicita ser atendido en el momento, explicando que, si no existe urgencia, se asigna cita en el horario disponible.

Condiciones de Aplicación:
- Utilizar cuando el usuario acude al Centro de Salud sin cita previa y manifiesta que desea ser atendido inmediatamente.
- Utilizar cuando no se trate de una urgencia médica y proceda explicar la asignación de cita en horario disponible.
- Utilizar cuando se quiera justificar la organización de la atención para garantizar un uso eficiente de recursos.
- No utilizar cuando sí existan signos o síntomas que justifiquen atención urgente inmediata.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
Dirección Asistencial Oeste  
Gerencia Asistencial de Atención Primaria  
CONSEJERÍA DE SANIDAD  
Calle Alonso Cano, 8  
28993 Móstoles  
Tel. +34 91 648 91 71  
daoeste@salud.madrid.org  

D. [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

Estimado Sr.:

En relación con su escrito con fecha [Fecha del escrito] de [Año] sobre la atención recibida en su Centro de Salud, en primer lugar, debo decirle que lamentamos profundamente que la percepción de la asistencia recibida no haya sido la esperada.

En segundo lugar, quisiera explicarle que cuando un paciente acude a un Centro de Salud sin cita previa y no se trata de una urgencia, lo más adecuado es proceder a asignarle una cita en el horario disponible. De esta manera, se garantiza una atención organizada, asegurando un uso eficiente de los recursos disponibles.

Por supuesto, en el caso de que se trate de una urgencia médica, toda actividad se detiene y se realiza una intervención inmediata.

Sentimos el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos es de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Tardan en darme cita con mi médico de familia. Demora y atención al día siguiente

Propósito:
Responder a reclamaciones sobre demora para cita con médico de familia, incluyendo referencia a la dificultad de cobertura profesional, circuitos urgentes y atención recibida al día siguiente.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera a demora para obtener cita con médico de familia.
- Utilizar cuando se haya comprobado que el usuario pudo recibir atención al día siguiente de su escrito o solicitud.
- Utilizar cuando proceda explicar tanto la dificultad para encontrar profesionales como la existencia de circuitos para atención urgente o no demorable.
- No utilizar si no se desea mencionar la atención al día siguiente, ya que ese matiz diferencia este modelo de otros similares.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
En relación con su escrito presentado con fecha [Fecha del escrito] sobre la atención recibida en el Centro de Salud [Centro de Salud], en primer lugar, debo pedirle disculpas por la demora en la contestación. En segundo lugar, y después de haberme informado sobre los hechos que refiere, debo explicarle lo siguiente:

- La dificultad actual para encontrar profesionales sanitarios, sobre todo en el caso de médicos y pediatras, hace que, especialmente en épocas de disfrute de ausencias legalmente establecidas y/o en momentos epidemiológicos de mayor carga asistencial, se produzcan demoras en la obtención de cita mayores de lo que nos gustaría.

- En todos los centros hay circuitos establecidos mediante los cuales los pacientes que presentan un cuadro clínico urgente o cuya valoración no se puede demorar más de 48-72 horas son atendidos en el momento, aunque no tengan cita previa. De esta manera, hemos comprobado que pudo recibir atención al día siguiente de la presentación de su escrito.

- Entendemos y compartimos su preocupación en este sentido y le aseguramos que estamos haciendo todo lo posible por paliar esta situación.

Lamentamos, no obstante, el malestar producido y le agradecemos su comprensión y colaboración, al tiempo que recogemos su información y opinión, que nos es de gran utilidad para seguir trabajando y conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Tardan en darme cita con mi médico. Falta de suplentes y medidas organizativas

Propósito:
Responder a reclamaciones sobre demora o dificultades de atención derivadas de la falta de suplentes para cubrir ausencias de profesionales.

Condiciones de Aplicación:
- Utilizar cuando el núcleo de la reclamación sea la demora o el impacto organizativo de la falta de profesionales suplentes.
- Utilizar cuando se quiera destacar el esfuerzo de los profesionales para mantener la calidad asistencial.
- Utilizar cuando no sea necesario mencionar circuitos urgentes de 48-72 horas.
- No utilizar cuando el motivo principal sea atención sin cita o demora en pruebas diagnósticas.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
D./D.ª [Nombre]

[Fecha de respuesta]

Estimada Sra. [Nombre]:

En relación con su escrito presentado el [Fecha del escrito] sobre la atención en su Centro de Salud y tras haber recabado la información necesaria sobre los hechos, debo explicarle lo siguiente:

Desde hace tiempo nos resulta muy difícil encontrar suplentes para cubrir las ausencias de los profesionales de los centros.

Es por este motivo por lo que tenemos que adoptar medidas organizativas para poder paliar, en lo posible, esta situación, que no es en absoluto la que nos gustaría.

Cabe destacar que los profesionales están haciendo un trabajo ímprobo para mantener la calidad en la atención que prestan.

Lamentamos el malestar generado y le agradecemos que nos haga llegar su opinión y sus consideraciones, puesto que nos son de gran ayuda para continuar mejorando la atención que prestamos a nuestros ciudadanos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Urgencia frente a atención sin cita

Propósito:
Explicar la diferencia entre urgencia médica y problemas de salud que permiten cierta demora, justificando la atención con cita salvo necesidad de intervención inmediata.

Condiciones de Aplicación:
- Utilizar cuando la reclamación cuestione que no se haya atendido inmediatamente a un paciente sin cita.
- Utilizar cuando proceda explicar qué se entiende por urgencia médica.
- Utilizar cuando sea necesario indicar que los problemas de salud que permiten demora deben atenderse con cita con profesional sanitario.
- No utilizar cuando el asunto principal sea demora de pruebas diagnósticas, laboratorio o resultados.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito de fecha [Fecha del escrito] de [Año] sobre la atención recibida en su Centro de Salud, debo informarle de lo siguiente:

Una urgencia médica es aquella situación clínica que, bien por la gravedad o por lo súbito de la aparición de los síntomas, requiere una intervención inmediata.

El resto de problemas de salud que, en general, permiten una cierta demora en su atención, es recomendable que sean atendidos con cita con un profesional sanitario.

Por supuesto, si el cuadro clínico precisa una atención urgente y es necesario intervenir en el momento, toda la actividad sanitaria se detiene y se realiza la asistencia inmediata.

No obstante, lamentamos el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos son de gran utilidad para conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Demora en laboratorio

Propósito:
Responder a reclamaciones sobre demora en la obtención de cita en el laboratorio del Centro de Salud, explicando el alto volumen de peticiones y la posibilidad de extracciones urgentes cuando la situación clínica lo requiere.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera a demora para obtener cita en laboratorio o sala de extracciones.
- Utilizar cuando proceda explicar que las demoras se deben al alto volumen de peticiones.
- Utilizar cuando sea necesario indicar que las extracciones urgentes se realizan cuando la situación clínica lo requiere.
- No utilizar para demoras de cita con médico de familia, pruebas diagnósticas externas o resultados de Anatomía Patológica.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
Calle Alonso Cano, 8  
28993 Móstoles  
Tel. +34 91 648 91 71  
daoeste@salud.madrid.org  

D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito presentado el [Fecha del escrito] sobre la demora en la obtención de cita en el Laboratorio del Centro de Salud [Centro de Salud], debo informarle:

Estas demoras se deben al alto volumen de peticiones y queremos asegurarle que estamos trabajando activamente para mejorar los tiempos de respuesta y garantizar un servicio más ágil.

No obstante, cuando la situación clínica lo requiere, las extracciones se realizan de manera urgente.

Lamentamos el malestar generado y le agradecemos que nos haga llegar su opinión y sus consideraciones, puesto que nos son de gran ayuda para continuar mejorando la atención que prestamos a nuestros ciudadanos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Demora en obtención de cita. Modelo general

Propósito:
Responder a reclamaciones generales sobre demora en la obtención de cita en el Centro de Salud, con referencia a la dificultad para encontrar sustitutos y a los circuitos de atención urgente o no demorable.

Condiciones de Aplicación:
- Utilizar como modelo general para demoras en obtención de cita.
- Utilizar cuando se quiera mantener una respuesta breve y estandarizada.
- Utilizar cuando proceda mencionar circuitos para atención urgente o valoración no demorable en 48-72 horas.
- No utilizar cuando existan matices específicos como atención al día siguiente, falta de facultativos, pruebas diagnósticas o laboratorio.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
[Fecha de respuesta]

D.ª [Nombre]

Estimada Sra. [Nombre]:

En relación con su escrito presentado el [Fecha del escrito] en relación con la demora en la obtención de cita en el Centro de Salud [Centro de Salud], debo informarle:

La dificultad actual para encontrar profesionales sustitutos, sobre todo en el caso de médicos y pediatras, hace que, especialmente en épocas de disfrute de ausencias legalmente establecidas y/o en momentos epidemiológicos de mayor carga asistencial, se produzcan demoras en la obtención de cita mayores de lo que nos gustaría.

Entendemos y compartimos su preocupación en este sentido y le aseguramos que estamos haciendo todo lo posible por paliar esta situación.

Debe saber también que en todos los centros hay circuitos establecidos mediante los cuales los pacientes que presentan un cuadro clínico urgente o cuya valoración no se puede demorar más de 48-72 horas son atendidos en el momento, aunque no tengan cita previa.

Lamentamos el malestar generado y le agradecemos que nos haga llegar su opinión y sus consideraciones, puesto que nos son de gran ayuda para continuar mejorando la atención que prestamos a nuestros ciudadanos.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Demora en pruebas diagnósticas

Propósito:
Responder a reclamaciones sobre demora para obtener cita para una prueba diagnóstica solicitada, especialmente tras una respuesta previa que no ha satisfecho las expectativas de la persona reclamante.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera a demora en la obtención de cita para una prueba diagnóstica.
- Utilizar cuando exista una reclamación previa o disconformidad con la respuesta anterior.
- Utilizar cuando se quiera explicar que determinadas pruebas diagnósticas presentan tiempos de espera superiores a los deseables por alta demanda y disponibilidad limitada de recursos.
- No utilizar para demora de cita en Atención Primaria, laboratorio del centro o resultados de Anatomía Patológica.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito de fecha [Fecha del escrito] de [Año] en relación con la contestación recibida tras su anterior reclamación, en primer lugar, queremos decirle que lamentamos sinceramente que la respuesta facilitada en su momento no haya cumplido sus expectativas y que ello le haya generado malestar.

En cuanto a su reclamación acerca de la demora en la obtención de una cita para la prueba que le han solicitado, queremos informarle de que, desafortunadamente, determinadas pruebas diagnósticas presentan tiempos de espera superiores a los deseables debido a la alta demanda y a la disponibilidad limitada de recursos. Aun así, trabajamos de forma continua para optimizar los tiempos y mejorar la accesibilidad a todas las pruebas.

Agradecemos que haya vuelto a ponerse en contacto para trasladarnos su inquietud, lo cual nos permite revisar y mejorar nuestra atención.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Demora de resultados de Anatomía Patológica

Propósito:
Responder a reclamaciones por demora en la recepción de resultados de Anatomía Patológica, explicando los tiempos de procesamiento y validación hospitalaria.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera al tiempo de espera para recibir resultados de Anatomía Patológica, como una citología.
- Utilizar cuando se haya revisado el caso y la demora dependa del procesamiento y validación del hospital.
- Utilizar cuando se quiera indicar que el informe estará disponible en la historia clínica una vez validado.
- No utilizar para demora en cita con médico, demora de laboratorio o demora de prueba diagnóstica pendiente de realizar.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Tipo de prueba]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito de fecha [Fecha del escrito] acerca del tiempo de espera para recibir los resultados de Anatomía Patológica correspondientes a su [Tipo de prueba], queremos informarle de que hemos revisado su caso y confirmado que la demora se debe a los tiempos de procesamiento y validación del servicio de Anatomía Patológica del hospital, del cual depende la emisión de estos informes.

Somos plenamente conscientes de la preocupación que esta situación puede generar y entendemos su inquietud. Le aseguramos que, en cuanto el hospital finalice la revisión y valide el informe, estará disponible en su historia clínica, y desde nuestro centro realizamos un seguimiento para facilitar su acceso en cuanto sea posible.

Lamentamos sinceramente las molestias ocasionadas y le pedimos disculpas por la demora. Agradecemos su comprensión y quedamos a su disposición para cualquier información adicional que precise.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Demoras por recursos humanos. Falta de profesionales sustitutos

Propósito:
Responder a reclamaciones por demora en citas vinculada a dificultades de dotación de recursos humanos, especialmente Medicina de Familia y Pediatría.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera a demoras de cita causadas por dificultad para incorporar profesionales sustitutos.
- Utilizar cuando proceda mencionar específicamente Medicina de Familia y Pediatría.
- Utilizar cuando convenga explicar tanto la dotación de recursos humanos como los ajustes organizativos.
- Utilizar cuando se quiera recordar los circuitos asistenciales para cuadros urgentes o valoraciones no demorables más de 48-72 horas.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con el escrito presentado el día [Fecha del escrito] de [Año] acerca de la demora en la obtención de citas en su Centro de Salud, le informamos lo siguiente:

En la actualidad, la dificultad para incorporar profesionales sustitutos, especialmente en las categorías de Medicina de Familia y Pediatría, está provocando que se generen demoras mayores de las deseables. Esta situación nos obliga a adoptar diversas medidas organizativas con el fin de minimizar, en la medida de lo posible, su impacto en la atención a los usuarios.

Deseamos recordarle que en todos los centros existen circuitos asistenciales específicos para garantizar la atención de aquellos pacientes que presentan un cuadro clínico urgente o que requieren una valoración que no puede demorarse más de 48-72 horas. En estos casos, la asistencia se presta en el momento, aun cuando no se disponga de cita previa.

Comprendemos plenamente su preocupación y compartimos el interés en mejorar los tiempos de acceso a la asistencia. Le aseguramos que estamos trabajando de forma continua para paliar esta situación, tanto mediante los esfuerzos dirigidos a la dotación de los recursos humanos necesarios como mediante ajustes organizativos que permitan optimizar la actividad del centro.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## No me ven en el momento. Urgencia frente a cita al día siguiente

Propósito:
Responder a reclamaciones en las que el usuario considera que debía ser atendido en el momento, pero tras valoración no existían signos o síntomas que justificaran atención inmediata y se asignó cita al día siguiente.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se refiera a que no se atendió al paciente en el momento.
- Utilizar cuando los informes indiquen que no había signos ni síntomas que justificaran atención inmediata sin demora.
- Utilizar cuando se asignó cita con el médico para el día siguiente.
- No utilizar si la respuesta debe limitarse a explicar la diferencia genérica entre urgencia y atención con cita.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]
- [Año]

Contenido:
D.ª [Nombre]  
[Domicilio]  
[Municipio] (MADRID)

[Fecha de respuesta]

Estimada Sra.:

En relación con su escrito de fecha [Fecha del escrito] de [Año], donde expresa su disconformidad por la atención recibida en su Centro de Salud, y tras pedir informes a la profesional a la que hace referencia en su escrito, quiero decirle lo siguiente:

En el momento en que usted acudió al Centro para pedir cita, no había signos ni síntomas que justificaran una atención inmediata sin demora. Por ello, y siguiendo los protocolos clínicos establecidos, se le asignó una cita con su médico para el día siguiente, garantizando así una valoración adecuada en el menor tiempo posible.

Nuestro objetivo es siempre priorizar los casos según su urgencia clínica, asegurando una atención segura y eficiente para todos los pacientes.

Lamentamos, no obstante, el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones. Le aseguramos que continuamos esforzándonos para proporcionar la mejor atención posible a todos nuestros pacientes.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

## Otra demora por recursos humanos. Falta de personal facultativo

Propósito:
Responder a reclamaciones por demora para obtener citas cuando la causa principal es la falta de personal facultativo, explicando medidas de incorporación de profesionales y optimización de recursos.

Condiciones de Aplicación:
- Utilizar cuando la reclamación se centre en demoras para la obtención de citas por falta de personal facultativo.
- Utilizar cuando se quiera mencionar medidas como incorporación de nuevos profesionales y optimización de recursos disponibles.
- Utilizar cuando proceda recordar la existencia de circuitos para cuadros urgentes o valoraciones no demorables más de 48-72 horas.
- No utilizar cuando el matiz principal sea falta de suplentes, pruebas diagnósticas o atención sin cita.

Variables Clave:
- [Nombre]
- [Domicilio]
- [Municipio]
- [Fecha del escrito]
- [Fecha de respuesta]
- [Centro de Salud]
- [Responsable firmante]
- [Cargo]
- [Dirección asistencial]

Contenido:
Dirección Asistencial Oeste  
Gerencia Asistencial de Atención Primaria  
CONSEJERÍA DE SANIDAD  
Calle Alonso Cano, 8  
28993 Móstoles  
Tel. +34 91 648 91 71  
daoeste@salud.madrid.org  

D. [Nombre]  
[Domicilio]  
[MADRID]

[Fecha de respuesta]

Estimado Sr.:

En relación con su escrito presentado el [Fecha del escrito] en relación con las demoras para la obtención de citas en su Centro de Salud, debo informarle:

Actualmente, estamos enfrentando una falta de personal facultativo, lo que está afectando a los tiempos de espera. Quisiéramos transmitirle que estamos trabajando intensamente para solucionar este problema, implementando medidas como la incorporación de nuevos profesionales y la optimización de los recursos disponibles.

Debe saber también que en todos los centros hay circuitos establecidos mediante los cuales los pacientes que presentan un cuadro clínico urgente o cuya valoración no se puede demorar más de 48-72 horas son atendidos en el momento, aunque no tengan cita previa.

Lamentamos profundamente la situación, ya que somos conscientes de que puede generar molestias, y le ofrecemos nuestras disculpas por los inconvenientes ocasionados.

Agradecemos su comprensión y paciencia mientras trabajamos para mejorar nuestra capacidad de atención.

Atentamente,

[Responsable firmante]  
[Cargo]  
[Dirección asistencial]

# DESACUERDO ORGANIZACIÓN Y NORMAS

## Absorbentes para incontinencia urinaria grave: pauta ordinaria financiada

**Propósito:** Informar sobre la financiación ordinaria de absorbentes para incontinencia urinaria grave y el carácter excepcional de las pautas superiores a cuatro unidades diarias.

**Condiciones de Aplicación:**
- Reclamaciones o escritos sobre cantidad de absorbentes financiados.
- Casos en los que procede explicar la pauta ordinaria: tres absorbentes diurnos y uno nocturno.
- Situaciones en las que se quiere dejar constancia de que superar cuatro absorbentes al día requiere justificación clínica.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Responsable firmante]

**Contenido:**

[Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] sobre la atención recibida en el Centro de Salud [Centro de Salud], debo informarle de lo siguiente:

El Sistema Nacional de Salud subvenciona absorbentes para la incontinencia urinaria grave, estimándose la financiación en 3 unidades para el día y uno de máxima absorción para la noche.

El uso de más de 4 absorbentes al día debe ser excepcional y debidamente justificado, quedando al criterio clínico dicha decisión.

Agradecemos su escrito, pues su información y opinión son de gran utilidad para conseguir un servicio de calidad y de plena satisfacción para el ciudadano.

Atentamente,

Dirección Asistencial Oeste

## Absorbentes para incontinencia: denegación de pauta superior por falta de justificación clínica

**Propósito:** Responder a solicitudes de aumento de absorbentes cuando el informe sanitario no justifica superar la pauta máxima financiada.

**Condiciones de Aplicación:**
- Reclamaciones sobre suministro de pañales/absorbentes de incontinencia.
- Casos en los que se ha solicitado informe al profesional sanitario de referencia.
- Supuestos en los que no consta condicionante clínico que justifique una prescripción superior a cuatro absorbentes diarios.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha del escrito]
- [Paciente/familiar]
- [Profesional sanitario de referencia]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito], en relación con el suministro de pañales de incontinencia de D./D.ª [Nombre y apellidos], y tras solicitar un informe a su profesional sanitario de referencia, le comunicamos:

Según la normativa que regula el procedimiento de financiación selectiva de los productos sanitarios con cargo a la prestación farmacéutica del Sistema Nacional de Salud, la financiación de absorbentes para la incontinencia urinaria admite la prescripción, como máximo, de 4 absorbentes al día, que incluyen 3 de día y 1 de noche o supernoche.

Cualquier prescripción que supere esta cantidad debe estar debidamente justificada desde el punto de vista clínico, y según nuestros informes, usted/su familiar [Paciente] no presenta ningún condicionante de salud que justifique dicha prescripción

Atentamente,

[Responsable firmante]

Responsable de Centros Dirección Asistencial Oeste

## Absorbentes para incontinencia: pauta excepcional máxima de 5-6 absorbentes/día

**Propósito:** Informar sobre la posibilidad excepcional y temporal de autorizar pautas de 5-6 absorbentes diarios si existen circunstancias clínicas documentadas.

**Condiciones de Aplicación:**
- Reclamaciones sobre necesidad de más de cuatro absorbentes diarios.
- Casos en los que se debe explicar que la pauta ordinaria es de cuatro absorbentes/día.
- Supuestos en los que podrían autorizarse 5-6 absorbentes/día por circunstancias excepcionales, puntuales y reflejadas en la historia clínica.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Circunstancia clínica]
- [Duración estimada]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] en relación al suministro de pañales de incontinencia le comunicamos:

Según la normativa que regula el procedimiento de financiación selectiva de los productos sanitarios con cargo a la prestación farmacéutica del Sistema Nacional de Salud, en el caso de absorbentes para la incontinencia urinaria grave, se ha estimado la financiación en 3 unidades para el día y uno de máxima absorción para la noche.

No obstante, se podrán autorizar pautas con un máximo de 5-6 absorbentes/día en pacientes con circunstancias excepcionales y puntuales. Dichas circunstancias que afecten a la diuresis o a la frecuencia de cambios, deberán reflejarse en la historia clínica, con indicación de la fecha de inicio, ligado a un episodio concreto y estableciendo la duración estimada de esta pauta extraordinaria.

Le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos es de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Demora de cita por falta de profesionales sustitutos

**Propósito:** Explicar demoras en la obtención de cita derivadas de la dificultad para cubrir ausencias profesionales y recordar la existencia de circuitos para atención urgente o no demorable.

**Condiciones de Aplicación:**
- Reclamaciones sobre demora en cita en centro de salud.
- Situaciones relacionadas con falta de profesionales sustitutos, ausencias reglamentarias o aumento de carga asistencial.
- Casos en los que conviene informar de circuitos para atención urgente o no demorable en 48-72 horas.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito presentado el [Fecha del escrito] sobre la atención en su Centro de Salud, en primer lugar, debo pedirle disculpas por la demora en la contestación.

En segundo lugar y tras haber recabado información necesaria sobre los hechos, debo explicarle lo siguiente:

La dificultad actual para encontrar profesionales sustitutos, sobre todo en el caso de los médicos y pediatras, hace que sobre todo en épocas de disfrute de aausencias legalmente establecidas y/o momentos epidemiológicos de mayor carga asistencial, se produzcan demoras en la obtención de cita mayores de lo que nos gustaría.

Debe saber también que en todos los centros hay circuitos establecidos mediante los cuales los pacientes que presentan un cuadro clínico urgente o cuya valoración no se puede demorar más de 48-72 horas, son atendidos en el momento, aunque no tengan cita previa.

Lamentamos el malestar generado y le agradecemos que nos haga llegar su opinión y sus consideraciones, puesto que nos son de gran ayuda para continuar mejorando la atención que prestamos a nuestros ciudadanos.

Atentamente,

[Responsable firmante]

Responsable de Centros Dirección Asistencial Oeste

## Cambio de cita de Niño Sano comunicado a uno de los progenitores con patria potestad

**Propósito:** Responder a la disconformidad por comunicación de cambio de cita de Niño Sano a uno de los progenitores cuando ambos ostentan patria potestad.

**Condiciones de Aplicación:**
- Reclamaciones sobre cambio o reprogramación de cita de Niño Sano.
- Casos en los que se contactó con uno de los progenitores para informar del cambio.
- Supuestos sin resolución judicial notificada que limite la patria potestad o la recepción de comunicaciones sanitarias.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Progenitor contactado]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] donde expresa su disconformidad por la atención recibida en su Centro de Salud y tras pedir informes a los profesionales, debo decirle lo siguiente:

Es importante señalar tal como se indica al acceder a la aplicación móvil, que las citas para control de Niño Sano, no se pueden reprogramar ni cambiar por esta vía.

A pesar de ello, desde el CS se intentó facilitar la atención y se contactó con el padre/madre del menor para informarle del cambio de fecha. Entendemos que ambos progenitores ostentan la patria potestad y, en ausencia de una notificación judicial en sentido contrario, cualquiera de ellos puede recibir comunicaciones relacionadas con la atención sanitaria del menor. Asimismo, corresponde a los progenitores compartir entre sí la información relativa al hijo en común.

Lamentamos cualquier malentendido que haya podido generarse y quedamos a su disposición para cualquier aclaración adicional.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Reintegro de vacuna antigripal abonada

**Propósito:** Informar del procedimiento para solicitar el reembolso del importe abonado por vacuna antigripal.

**Condiciones de Aplicación:**
- Reclamaciones sobre pago de vacuna antigripal.
- Casos referidos a vacuna FLUCELVAX u otra vacuna antigripal abonada por el usuario.
- Supuestos en los que procede derivar al trámite de reintegro de gastos sanitarios.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Vacuna]
- [Enlace de trámite]
- [Responsable firmante]

**Contenido:**

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] donde expresa su disconformidad por el pago de la vacuna antigripal [Vacuna antigripal], le informamos de lo siguiente:

Puede proceder a solicitar el reembolso del importe abonado, en el siguiente enlace:

Reintegro de gastos sanitarios | Comunidad de Madrid

http://sede.comunidad.madrid/ayudas-becas-subvenciones/reintegro-gastos-sanitarios/tramitar

Lamentamos el malestar generado y le agradecemos que nos haga llegar su opinión y sus consideraciones, puesto que nos son de gran ayuda para continuar mejorando la atención que prestamos a nuestros ciudadanos.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Centralización del test de Mantoux por distrito

**Propósito:** Explicar la centralización organizativa de la prueba de Mantoux en un único centro de salud por distrito.

**Condiciones de Aplicación:**
- Reclamaciones sobre desplazamiento o cambio de centro para realización del test de Mantoux.
- Casos en los que la medida responde a optimización de recursos, calidad asistencial y homogeneidad del procedimiento.
- Supuestos en los que conviene justificar la medida por criterios técnicos y organizativos.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Distrito]
- [Centro de Salud asignado]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha [Fecha del escrito] sobre la organización para la realización del test de Mantoux, queremos informarle de que dicho procedimiento se ha centralizado en un único centro de salud por distrito como medida organizativa destinada a optimizar los recursos disponibles y así garantizar una correcta administración de la prueba.

Esta medida permite, además, mejorar la calidad asistencial, reducir incidencias y asegurar la homogeneidad del procedimiento, beneficiando al conjunto de los usuarios del sistema sanitario.

Somos conscientes de que puede suponer desplazamientos adicionales para algunos pacientes y lamentamos las molestias que esto pueda ocasionar. No obstante, se trata de una decisión adoptada atendiendo a criterios técnicos y organizativos, con el objetivo de ofrecer una atención segura y eficiente.

Sentimos el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos es de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente,

## Citas para revisiones de pediatría solicitadas en centro o por teléfono

**Propósito:** Explicar que las revisiones de pediatría requieren gestión especial por precisar huecos más amplios de agenda.

**Condiciones de Aplicación:**
- Reclamaciones sobre imposibilidad de obtener cita de revisión pediátrica por canales ordinarios.
- Casos de revisiones de Niño Sano o revisiones pediátricas programadas.
- Supuestos en los que se debe indicar solicitud directa en el centro de salud o por vía telefónica.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Centro de Salud]
- [Profesional]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] sobre la atención recibida en su Centro de Salud, comentarle lo siguiente:

Tras haber solicitado un informe al profesional al que hace referencia, debo decirle que ambas versiones no son del todo coincidentes, por lo que no entra en nuestras competencias hacer juicios de valor al respecto.

Queremos informarle que las citas para revisiones de pediatría son gestionadas de forma especial, ya que requieren huecos más amplios de tiempo para poder realizar una valoración completa del desarrollo y estado de salud del menor.

Por este motivo, deben ser solicitadas directamente en el centro de salud o por vía telefónica. De este modo, podemos garantizar que se asignen correctamente y con el tiempo necesario para una atención adecuada.

Sentimos no obstante el malestar generado y le agradecemos que nos haya hecho llegar su escrito, puesto que nos ayuda a velar por la calidad de la atención prestada.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Recogida de residuos sanitarios sin entrega de contenedores

**Propósito:** Informar sobre el cambio de procedimiento de recogida de residuos sanitarios y la no entrega de contenedores.

**Condiciones de Aplicación:**
- Reclamaciones sobre entrega de contenedores para residuos de material sanitario.
- Casos en los que la recogida se mantiene en los centros de salud, pero ya no se entregan contenedores.
- Supuestos en los que procede explicar un cambio de circuito por modificación normativa.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Centro de Salud]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha [Fecha del escrito] sobre la recogida de residuos en el Centro de Salud [Centro de Salud], debo informarle de lo siguiente:

Se ha producido un cambio en la normativa de recogida de residuos de material sanitario que ha obligado a replantear y modificar los circuitos establecidos previamente en los centros de salud.

Este nuevo procedimiento indica que la recogida de los residuos será en los centros de salud, sin embargo, ya no se entregarán contenedores para la recogida de este tipo de material.

Sentimos las molestias ocasionadas y le agradecemos que nos haya hecho llegar su escrito, puesto que su opinión y consideraciones nos son muy útiles para velar por la calidad de la atención prestada.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Residuos punzantes domiciliarios: características del recipiente

**Propósito:** Informar sobre la recogida de residuos punzantes usados en domicilio y las características orientativas del recipiente a utilizar.

**Condiciones de Aplicación:**
- Reclamaciones sobre recogida de residuos sanitarios en centro de salud.
- Casos específicos de punzantes utilizados en domicilio.
- Supuestos en los que debe explicarse que el recipiente debe ser rígido, de plástico, con tapa y dimensiones máximas orientativas.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Centro de Salud]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito fechado el [Fecha del escrito] sobre la recogida de residuos en su Centro de Salud, debo informarle de lo siguiente:

En efecto, desde hace unos meses, se ha producido un cambio en la normativa de recogida de residuos de material sanitario, lo que nos ha obligado a replantear y modificar los circuitos establecidos previamente en los centros de salud.

Según disposición adicional decimosexta de la ley 7/2022, de 8 de abril, de residuos y suelos contaminados para una economía circular, los punzantes utilizados en el domicilio de los pacientes deben ser introducidos en un recipiente que tenga las siguientes características orientativas, adecuándose a las especificaciones del art. 12.2 Decreto 83/1999: que esté provisto de tapa (para su cierre definitivo cuando se llene), que sea rígido, que sea de plástico (no de vidrio por su fragilidad y consiguiente riesgo), que sus dimensiones sean como máximo de 15 cm alto y 15 cm de ancho.

Sentimos las molestias ocasionadas y le agradecemos que nos haya hecho llegar su escrito, puesto que su opinión y consideraciones nos son muy útiles para velar por la calidad de la atención prestada.

Atentamente

Dirección Asistencial Oeste

## Desacuerdo genérico con medidas organizativas y normas del centro

**Propósito:** Responder de forma genérica a disconformidades con medidas organizativas adoptadas en un centro de salud.

**Condiciones de Aplicación:**
- Reclamaciones inespecíficas sobre normas internas, organización de tareas o esperas.
- Casos en los que no procede entrar en un circuito clínico concreto.
- Supuestos en los que se quiere justificar la organización por eficiencia y mejor utilización de recursos.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito presentado con fecha [Fecha del escrito] sobre la atención recibida en nuestro Centro de Salud y después de haberme informado sobre los hechos que refiere, debo explicarle lo siguiente:

- Las medidas organizativas adoptadas en los centros de salud tienen la finalidad de organizar las tareas en busca de una mejor eficiencia de la utilización de los recursos que conlleva una mejor atención

Entendemos y lamentamos no obstante, el malestar producido por la espera y le agradecemos su comprensión y colaboración, al tiempo que recogemos su información y opinión, que nos es de gran utilidad para seguir trabajando y conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente

[Responsable firmante]

## Hora de cita orientativa en vacunación

**Propósito:** Explicar que la hora de cita para vacunación es orientativa y puede verse afectada por la dinámica propia de la actividad vacunal.

**Condiciones de Aplicación:**
- Reclamaciones sobre orden u hora de entrada en vacunación.
- Casos de campañas o actividades con elevado volumen de pacientes en poco tiempo.
- Supuestos en los que se debe explicar que se intenta respetar el orden, pero pueden producirse ajustes.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Actividad vacunal]
- [Responsable firmante]

**Contenido:**

[Nombre y apellidos]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] sobre la atención recibida en el Centro de Salud [Centro de Salud], quiero explicarle lo siguiente:

La hora de cita para cualquier atención sanitaria es orientativa, y aunque se intenta respetar al máximo tanto el orden de entrada como el tiempo asignado, ambos se pueden ver afectados por la propia naturaleza de las actividades que se realizan.

En el caso de la vacunación, al ser una actividad dinámica, en el que se vacuna a una gran cantidad de pacientes en un corto espacio de tiempo, se pueden producir situaciones como la que comenta en su escrito.

No obstante, sentimos el malestar ocasionado y le agradecemos que nos haya hecho llegar su opinión

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Renovación periódica de medicación crónica en receta electrónica

**Propósito:** Explicar la necesidad de renovar periódicamente la medicación crónica como procedimiento de seguridad clínica.

**Condiciones de Aplicación:**
- Reclamaciones por caducidad o necesidad de reactivación de receta electrónica.
- Casos de medicación crónica que requiere revisión periódica.
- Supuestos en los que debe justificarse la renovación por seguridad, eficacia, adecuación y seguimiento clínico.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Tratamiento]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] donde refiere su disconformidad con la necesidad de renovar de forma periódica la medicación crónica, procedo a informarle:

La renovación periódica de la medicación crónica forma parte de los procedimientos habituales y obligatorios del sistema sanitario, y tiene como finalidad garantizar un uso seguro, eficaz y adecuado de los tratamientos.

Esta circunstancia permite a los profesionales verificar la indicación y dosis correctas del tratamiento, detectar posibles efectos adversos o interacciones medicamentosas, actualizar el tratamiento conforme a las guías clínicas vigentes y finalmente, valorar la evolución de su patología.

Aun entendiendo que este procedimiento pueda resultarle incómodo, queremos asegurarle que en todo momento se realiza buscando su beneficio clínico y seguridad, cumpliendo la normativa y protocolos establecidos.

Atentamente

## Extracción sanguínea: asepsia y versiones no coincidentes

**Propósito:** Responder a una disconformidad sobre el procedimiento de extracción sanguínea cuando las versiones no coinciden y se recuerda la obligación de aplicar antiséptico.

**Condiciones de Aplicación:**
- Reclamaciones sobre técnica de extracción sanguínea.
- Casos en los que se ha solicitado informe a profesionales y las versiones no son coincidentes.
- Supuestos en los que procede explicar la aplicación de antiséptico como medida de seguridad y asepsia.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Profesionales]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] donde expresa su disconformidad por la atención recibida en el Centro de Salud [Centro de Salud] y tras pedir informes a las profesionales a las que hace referencia en su escrito, debo decirle que las versiones no son del todo coincidentes, por lo que no entra en nuestras competencias hacer juicios de valor al respecto.

Cuando se va a realizar una extracción sanguínea, siempre se aplica antiséptico en la zona de punción como medida imprescindible para garantizar la seguridad y la asepsia del procedimiento. El personal sanitario debe seguir rigurosamente las normas de higiene y prevención de infecciones.

No obstante, tomamos muy en cuenta sus observaciones, que nos ayudan a seguir revisando y mejorando nuestros procedimientos.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Extracciones de sangre en niños al final de la agenda

**Propósito:** Explicar que las extracciones en niños pueden realizarse al final por dificultad técnica y necesidad de mayor dedicación.

**Condiciones de Aplicación:**
- Reclamaciones sobre orden de realización de extracciones pediátricas.
- Casos en los que el menor es citado o atendido al final de la sala de extracciones.
- Supuestos en los que conviene justificar la medida por complejidad técnica y tiempo de dedicación.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha del escrito]
- [Centro de Salud]
- [Menor]
- [Responsable firmante]

**Contenido:**

EXTRACCIONES EN NIÑOS

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito presentado el [Fecha del escrito][Nombre y apellidos] en relación a la atención de su problema de salud en el CS*************************, le informamos:

Habitualmente, las extracciones de sangre que se realizan en niños pueden suponer una tarea un poco complicada tanto por la dificultad técnica como por el tiempo de dedicación a dicho procedimiento.

Es por todos estos motivos, por los que se realizan al final y así poder dedicar todo el tiempo que se requiera.

Lamentamos el malestar generado y le agradecemos que nos haga llegar su opinión y sus consideraciones, puesto que nos son de gran ayuda para continuar mejorando la atención que prestamos a nuestros ciudadanos.

Atentamente

## Horario de entrega de muestras en laboratorio del centro de salud

**Propósito:** Explicar la organización horaria de la recogida de muestras por la necesidad de transporte al hospital de referencia.

**Condiciones de Aplicación:**
- Reclamaciones sobre horarios de entrega de muestras.
- Casos en los que el laboratorio del centro establece una hora aproximada de finalización.
- Supuestos en los que, por causa justificada, puede acordarse un horario más accesible con la persona responsable.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Hospital de referencia]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito presentado el [Fecha del escrito] sobre los horarios de recogida de muestras en el Laboratorio del [Centro de Salud], quisiera informarle de lo siguiente:

La organización y determinación de horarios de los Laboratorios de los centros de salud viene dada, principalmente por la necesidad de establecer una hora aproximada de finalización de los mismos ya que cada día a una hora concreta, se recogen todas las muestras para llevarlas al Hospital de referencia.

Normalmente, se comienza con las extracciones de sangre al ser técnicas que pueden requerir más tiempo por la posible dificultad de la misma.

Por supuesto, si por motivos justificados, no se pudieran entregar el resto de muestras a la hora establecida por el Centro, siempre se podría informar a la persona responsable de dicha recogida y acordar un horario más accesible.

Le agradecemos su comprensión y colaboración, y el hecho de que nos transmita su opinión y sus consideraciones, puesto que nos permiten profundizar en la información sobre determinados circuitos y procedimientos de trabajo implementados en aras de la mejor calidad del servicio prestado.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Uso del teléfono móvil dentro de la consulta

**Propósito:** Responder a disconformidades relacionadas con el uso del teléfono móvil en consulta y explicar su restricción por calidad, seguridad y confidencialidad.

**Condiciones de Aplicación:**
- Reclamaciones sobre indicaciones dadas al paciente respecto al uso del móvil en consulta.
- Casos en los que las versiones de paciente y profesional no son coincidentes.
- Supuestos en los que procede explicar que llamadas, grabaciones o mensajes pueden interferir en la atención y comprometer privacidad.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Unidad/consulta]
- [Profesional]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] sobre la atención recibida en la Unidad de Odontopediatría, debo decirle que las versiones no son del todo coincidentes, por lo que no entra en nuestras competencias hacer juicios de valor al respecto.

Ante esto, y sin dudar en absoluto de su palabra, pensamos que tuvo que existir un malentendido en la comunicación entre ustedes.

No obstante, le informamos de que el uso del teléfono móvil dentro de la consulta no está permitido, ya que puede interferir en la correcta atención sanitaria. Las llamadas, grabaciones o mensajes pueden dificultar la comunicación, distraer durante la exploración o la explicación del tratamiento y comprometer la privacidad, tanto la suya como la de otros pacientes.

Nuestro objetivo es asegurar que la consulta se desarrolle con la máxima calidad, seguridad y confidencialidad.

Le agradecemos que nos haya hecho llegar su escrito, puesto que nos ayuda a velar por la calidad de la atención prestada.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Cambio de médico o enfermero de referencia por procesos selectivos o movilidad

**Propósito:** Explicar cambios de profesional de referencia derivados de procesos selectivos o movilidad en el Servicio Madrileño de Salud.

**Condiciones de Aplicación:**
- Reclamaciones por cambio de médico o enfermero de referencia.
- Casos relacionados con procesos selectivos, traslados o movilidad profesional.
- Supuestos en los que conviene transmitir confianza en el nuevo profesional y pedir un periodo de adaptación.

**Variables Clave:**
- [Nombre y apellidos]
- [Centro de Salud]
- [Médico/enfermero]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito presentado en nuestro centro de salud en relación con los cambios de su médico/enfermero de referencia, debo informarle:

Los cambios producidos se deben a los diferentes procesos selectivos o de movilidad producidos en últimos meses en el Servicio Madrileño de Salud.

Entendemos la incertidumbre que pueden generar los cambios y más en un ámbito como el sanitario, pero y estamos seguros de que la atención por su nuevo médico será tan satisfactoria para usted como la anterior, sólo es preciso un tiempo de relación que les permita conocerse y generar confianza mutua.

Le agradecemos su comprensión y colaboración, y el hecho de que nos transmita su opinión y sus consideraciones, puesto que nos permiten profundizar en la información sobre determinados circuitos y procedimientos de trabajo implementados en aras de la mejor calidad del servicio prestado.

Atentamente,

[Responsable firmante]

## Necesidad de visado de inspección para medicamento

**Propósito:** Explicar que determinados medicamentos requieren visado de inspección y que la financiación depende de la autorización de Inspección Médica.

**Condiciones de Aplicación:**
- Reclamaciones sobre imposibilidad de financiar o dispensar un medicamento sin visado.
- Casos en los que el fármaco está sometido a control especial y condiciones de financiación.
- Supuestos en los que procede aclarar que la autorización no depende del médico de familia.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Fármaco]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha de 2025 sobre la atención recibida en el Centro de Salud, debo explicarle lo siguiente:

El visado de inspección de medicamentos es el procedimiento por el cual la Inspección de Servicios Sanitarios autoriza la prescripción de medicamentos y productos farmacéuticos que requieren un control especial.

El fármaco al que hace referencia, es un medicamento cuya prescripción y dispensación están sometidas a visado de inspección de acuerdo con las condiciones de financiación del Sistema Nacional de Salud para sus principales indicaciones.

El visado de inspección es obligatorio para la dispensación en farmacias.

El acceso está restringido para determinadas indicaciones clínicas aprobadas en la ficha técnica (como prevención del ictus en fibrilación auricular no valvular y tratamiento de trombosis venosa profunda o embolia pulmonar).

La financiación pública está limitada y requiere cumplir los criterios de visado para la dispensación.

El fármaco al que usted hace referencia en su escrito, necesita dicho visado. Por lo tanto, queda fuera de las posibilidades del médico de familia, la posibilidad de que dicho fármaco sea financiado en su caso, siendo potestad de Inspección Médica dicha competencia.

No obstante, le agradecemos que nos haya hecho llegar su escrito que nos permite aclarar procedimientos o circuitos de trabajo establecidos en aras de una mejor calidad asistencial.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Vacuna no indicada por cohorte de edad

**Propósito:** Explicar que la inclusión de vacunas y las cohortes de edad vienen determinadas por Salud Pública.

**Condiciones de Aplicación:**
- Reclamaciones por no corresponder una vacuna según cohorte de edad.
- Casos en los que el usuario no está incluido en la cohorte vigente.
- Supuestos en los que se debe remitir a directrices de Salud Pública, comités de expertos y estudios de eficacia.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha del escrito]
- [Centro de Salud]
- [Vacuna]
- [Cohorte de edad]
- [Responsable firmante]

**Contenido:**

En relación con su escrito presentado con fecha [Fecha del escrito] sobre la atención recibida en el Centro de Salud [Centro de Salud], en primer lugar, deseo pedirle disculpas por la demora en la contestación y, en segundo lugar, y después de haberme informado sobre los hechos que refiere, debo explicarle lo siguiente:

La inclusión de vacunas en calendario, así como las cohortes de edad para su administración, vienen marcadas por las directrices de Salud Pública, que a su vez se basan en las recomendaciones de los comités de expertos y estudios de eficacia.

Entendemos y lamentamos, no obstante, el malestar producido y le agradecemos su comprensión y colaboración, al tiempo que recogemos su información y opinión, que nos es de gran utilidad para seguir trabajando y conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

## Vacuna Herpes Zóster: error en comunicación de cohortes de edad

**Propósito:** Explicar que las cohortes de vacunación dependen de Salud Pública y reconocer un error no intencionado en la comunicación de la cohorte de Herpes Zóster.

**Condiciones de Aplicación:**
- Reclamaciones sobre vacuna Herpes Zóster y cohorte de edad.
- Casos en los que hubo una información errónea sobre cohortes vigentes.
- Supuestos en los que procede aclarar que el error de comunicación no fue malintencionado.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha del escrito]
- [Centro de Salud]
- [Vacuna]
- [Cohorte de edad]
- [Profesional]
- [Responsable firmante]

**Contenido:**

En relación con su escrito presentado con fecha [Fecha del escrito] sobre la atención recibida en el Centro de Salud [Centro de Salud], en primer lugar, deseo pedirle disculpas por la demora en la contestación y, en segundo lugar, y después de haberme informado sobre los hechos que refiere, debo explicarle lo siguiente:

La inclusión de vacunas en calendario, así como las cohortes de edad para su administración, vienen marcadas por las directrices de Salud Pública, que a su vez se basan en las recomendaciones de los comités de expertos y estudios de eficacia.

En su caso, se produjo un error en la comunicación de las cohortes de edad a las que corresponde la vacunación de Herpes Zoster actualmente. Tras hablar con el profesional en cuestión, he de decirle que en ningún caso fue de manera malintencionada.

Entendemos y lamentamos, no obstante, el malestar producido y le agradecemos su comprensión y colaboración, al tiempo que recogemos su información y opinión, que nos es de gran utilidad para seguir trabajando y conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

## Ambulancia no autorizada por no cumplir criterios clínicos

**Propósito:** Responder a la disconformidad por no autorización de traslado en ambulancia cuando el profesional informa que no se cumplen criterios clínicos.

**Condiciones de Aplicación:**
- Reclamaciones por negativa de facultativo a solicitar ambulancia.
- Casos en los que se ha pedido informe y se concluye que no concurren criterios clínicos.
- Supuestos en los que procede indicar que no se puede intervenir en decisiones clínicas del facultativo.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Profesional]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito fecha 2026 donde expresa su disconformidad por la atención recibida en el Centro de Salud [Centro de Salud] y tras pedir informes a los profesionales a los que hace referencia en su escrito, quiero decirle lo siguiente:

Las decisiones tomadas por los profesionales sanitarios se basan en criterios médicos y están fundamentadas en el mejor interés del paciente, de acuerdo con las prácticas y estándares profesionales. Informarle que no podemos intervenir en las decisiones clínicas tomadas por los facultativos.

La facultativa nos indica que en esa ocasión no se cumplían los criterios clínicos necesarios para autorizar un traslado en ambulancia. Esta decisión se basa en criterios sanitarios establecidos para garantizar un uso adecuado de los recursos asistenciales.

Agradecemos que nos haya hecho llegar sus consideraciones y le aseguramos que continuamos esforzándonos para proporcionar la mejor atención posible a todos nuestros pacientes.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Receta de medicamento indicado por especialista

**Propósito:** Explicar que el facultativo que recomienda un medicamento debe realizar la prescripción y que la responsabilidad corresponde a quien firma la receta.

**Condiciones de Aplicación:**
- Reclamaciones por negativa de atención primaria a emitir receta indicada por especialista.
- Casos en los que el medicamento fue prescrito o indicado por alergólogo u otro especialista.
- Supuestos en los que debe aclararse que la responsabilidad de la prescripción recae en quien firma la receta.

**Variables Clave:**
- [Especialista]
- [Medicamento]
- [Paciente]
- [Profesional]
- [Responsable firmante]

**Contenido:**

- Cuando un facultativo recomienda un medicamento, es su obligación realizar la prescripción correspondiente incluyéndolo en la receta electrónica, pertenezca al ámbito hospitalario o al de atención primaria. Por tanto, como le explicó la doctora, la inclusión en receta electrónica de los medicamentos de su hijo debe realizarla el alergólogo, puesto que se los prescribió él.

- Además, la responsabilidad de la prescripción recae sobre el facultativo que la firma la receta, por lo que la decisión de realizar o no dicha prescripción es suya, aunque sea una prescripción recomendada por otro compañero

## Receta indicada en el ámbito privado

**Propósito:** Explicar que un facultativo del sistema público no debe asumir una prescripción indicada en el ámbito privado si no ha prestado asistencia por ese proceso y no comparte la indicación.

**Condiciones de Aplicación:**
- Reclamaciones por negativa a prescribir medicación indicada por médico privado.
- Casos en los que el usuario solicita que el sistema público transcriba una receta privada.
- Supuestos en los que procede explicar que el médico que prescribe asume diagnóstico, tratamiento y responsabilidad clínica.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Fecha de reclamación previa]
- [Medicamento]
- [Proceso clínico]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] por la disconformidad con la contestación a su reclamación del día [Fecha de reclamación previa] quiero explicarle lo siguiente:

La receta médica, es un documento normalizado mediante el cual los profesionales legalmente facultados para ello, y en el ámbito de sus competencias, prescriben a los pacientes medicamentos sujetos a prescripción médica para su posterior dispensación en las oficinas de farmacia.

Cuando un médico prescribe un medicamento que ha indicado otro facultativo, asume tanto el diagnóstico como el tratamiento prescrito, haciéndose por tanto responsable de la evolución de la enfermedad y de efectos secundarios del medicamento en cuestión. Eso implica que, lógicamente, para realizar esta prescripción, el médico debe estar de acuerdo tanto con el diagnóstico que ha hecho el otro profesional, como con el medicamento indicado, y de no ser así, no procederá a realizarla.

Por otro lado, según la normativa existente, un facultativo dentro del sistema público no debe prescribir un medicamento indicado en el ámbito privado, si no ha prestado asistencia a ese paciente por este mismo proceso y haya llegado a la misma conclusión sobre la indicación de dicha medicación

Lamentamos la contrariedad que le pudo suponer la situación que nos describe, al tiempo que recogemos su información y opinión, que nos es de gran utilidad para seguir trabajando y conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Transporte sanitario no urgente: criterios estrictamente clínicos

**Propósito:** Explicar que el transporte sanitario no urgente se indica por causas clínicas y no sociales, de distancia o conveniencia.

**Condiciones de Aplicación:**
- Reclamaciones por no asignación de ambulancia.
- Casos en los que se quiere citar el Real Decreto 1030/2006 sobre transporte sanitario no urgente.
- Supuestos en los que el paciente puede desplazarse por medios ordinarios o no consta imposibilidad clínica.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Centro de Salud]
- [Patología/proceso]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha [Fecha del escrito] sobre la atención recibida en su Centro de Salud, y después de informarme de los hechos debo explicarle lo siguiente:

El Real Decreto 1030/2006 del 16 de septiembre sobre el servicio de transporte sanitario no urgente establece que los traslados se realizan atendiendo a causas estrictamente clínicas, no sociales, ni por distancia y cuya situación médica en ese momento impida desplazarse en los medios ordinarios de transporte.

Hemos comprobado que posteriormente a la fecha de su escrito, usted acudió a su Centro de Salud para realizar los seguimientos oportunos que requería su patología.

Sentimos el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos es de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Apósitos: cese de prescripción por receta y provisión desde centro de salud

**Propósito:** Explicar que los apósitos no se prescriben por receta tras el Acuerdo Marco correspondiente y que pueden proporcionarse desde el centro previa valoración de enfermería.

**Condiciones de Aplicación:**
- Reclamaciones por negativa a prescribir apósitos.
- Casos en los que el material de curas debe facilitarse desde el centro de salud y no mediante receta.
- Supuestos en los que procede informar de valoración previa por enfermería.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Profesional de enfermería]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha [Fecha del escrito] sobre la atención recibida en su Centro de Salud, y después de informarme de los hechos debo explicarle lo siguiente:

Con fecha 16 de septiembre de 2021 la Viceconsejería de Asistencia Sanitaria y Salud Pública, como órgano de contratación del Servicio Madrileño de Salud, resolvió adjudicar el Acuerdo Marco 07/2020, el cual implica el cese de la prescripción por receta de los apósitos.

Siguiendo estas instrucciones, su facultativo no puede prescribir apósitos, pero su Centro de Salud, previa valoración por su profesional de enfermería, le puede proporcionar el material necesario para realizar las curas pertinentes.

Sentimos el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos son de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Orden de llegada en extracciones o vacunas: medidas organizativas

**Propósito:** Responder a reclamaciones por espera u orden de entrada en actividades organizadas, explicando la finalidad de las medidas organizativas.

**Condiciones de Aplicación:**
- Reclamaciones sobre orden de llegada o espera en extracciones/vacunas.
- Casos en los que la cuestión principal es la organización de la actividad, no una decisión clínica individual.
- Supuestos en los que se debe pedir disculpas por la demora y justificar la organización por eficiencia de recursos.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Actividad]
- [Responsable firmante]

**Contenido:**

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito presentado con fecha [Fecha del escrito] sobre la atención recibida en el Centro de Salud [Centro de Salud], en primer lugar, debo pedirle disculpas por la demora en la contestación.

En segundo lugar, y después de haberme informado sobre los hechos que refiere, debo explicarle lo siguiente:

Las medidas organizativas adoptadas en los centros de salud tienen la finalidad de organizar las tareas en busca de una mejor eficiencia de la utilización de los recursos que conlleva una mejor atención.

Entendemos y lamentamos, no obstante, el malestar producido por la espera y le agradecemos su comprensión y colaboración, al tiempo que recogemos su información y opinión, que nos es de gran utilidad para seguir trabajando y conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Organización de consulta de odontología por bloques de adultos e infancia

**Propósito:** Explicar la organización específica de la consulta de odontología separando población adulta e infantil y reservando tiempos de limpieza, desinfección y esterilización.

**Condiciones de Aplicación:**
- Reclamaciones sobre horarios o bloques de cita en odontología.
- Casos en los que el mismo equipo atiende población infantil y adulta durante la misma jornada.
- Supuestos en los que procede explicar la separación por tipo de atención y necesidades de limpieza/esterilización.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Unidad de odontología]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] sobre la organización en los bloques de citas de la consulta de Odontología del Centro de Salud [Centro de Salud], quiero explicarle lo siguiente:

La consulta de Odontología tiene unas peculiaridades específicas que la distinguen de otras consultas sanitarias, entre otras cuestiones, porque el mismo equipo atiende tanto a población infantil como adulta a lo largo de la misma jornada laboral.

Dado que se trata de atenciones muy diferentes, los niños en su mayoría acuden a revisiones, mientras que los adultos lo hacen a técnicas más cruentas, como son las extracciones, es necesario separarlos. Además, es necesario reservar el tiempo necesario para realizar las técnicas de limpieza, desinfección y esterilización pertinentes.

Es por todo esto, que se reserva la primera franja horaria para los adultos, mientras que la población infantil se atiende en un horario que coincide con el recreo y las últimas horas escolares.

Le agradecemos su comprensión y colaboración, y el hecho de que nos transmita su opinión y sus consideraciones, puesto que nos permiten profundizar en la información sobre determinados circuitos y procedimientos de trabajo implementados en aras de la mejor calidad del servicio prestado.

Atentamente,

[Responsable firmante]

Responsable de Centros Dirección Asistencial Oeste

## Organización de agendas y alteración del orden de entrada en consulta

**Propósito:** Explicar que las agendas sanitarias ordenan la atención, pero el orden de entrada puede modificarse por circunstancias clínicas u organizativas a criterio profesional.

**Condiciones de Aplicación:**
- Reclamaciones sobre orden de entrada en consulta.
- Casos en los que paciente y profesional ofrecen versiones no coincidentes.
- Supuestos en los que la alteración del turno se produce por criterio profesional y se interpreta como malentendido.

**Variables Clave:**
- [Nombre y apellidos]
- [Fecha del escrito]
- [Centro de Salud]
- [Profesional]
- [Consulta]
- [Responsable firmante]

**Contenido:**

ORGANIZACIÓN EN LA CONSULTA

En relación con su escrito con fecha [Fecha del escrito] sobre la atención recibida en el Centro de Salud [Centro de Salud], le informamos de lo siguiente:

Tras haber solicitado un informe al profesional al que hace referencia en su escrito, debo decirle que las versiones no son del todo coincidentes, por lo que no entra en nuestras competencias hacer juicios de valor al respecto.

Quisiera explicarle también que la programación de las citas en las agendas de trabajo de los sanitarios, permite organizar, de la manera más eficiente, la atención que se presta a la población en su conjunto. Estas agendas establecen un orden de entrada que, por supuesto, se intenta respetar siempre, pero puede haber circunstancias clínicas o de otra índole, que hagan que este orden se altere. Esta modificación en el turno de entrada se produce siempre a criterio del profesional que pasa la consulta.

Entendemos que los hechos que describe se tuvieron que deber a un malentendido, produciendo una situación de desencuentro entre ustedes que resultó desagradable para ambos.

Lamentamos que la percepción de la asistencia no haya sido la esperada y le agradecemos que nos haya hecho llegar su escrito.

Atentamente,

## Entrega mensual de material diabético y horario establecido

**Propósito:** Explicar la organización de entrega del material para diabéticos dentro de horario y con periodicidad mensual por distribución desde almacén central.

**Condiciones de Aplicación:**
- Reclamaciones sobre horario de entrega de material diabético.
- Casos en los que el usuario solicita material fuera de horario o más allá de la periodicidad mensual.
- Supuestos en los que procede explicar el papel del TCAE, la distribución desde almacén central y la posibilidad de cauces urgentes.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Material diabético]
- [Centro de Salud]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

P

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] donde muestra su disconformidad por la organización en la entrega y gestión del material para diabéticos, debo explicarle lo siguiente:

Con el objetivo de ofrecer una atención de calidad y organizada, la entrega de este tipo de material se realiza dentro del horario establecido. Esto nos permite organizar mejor el trabajo de los profesionales y evitar esperas innecesarias, tanto para usted como para el resto de usuarios.

Asimismo, fuera de ese horario el personal técnico en cuidados auxiliares de enfermería (TCAE) se encuentra realizando otras tareas asistenciales en el centro de salud. Por supuesto, si se trata de una situación urgente, se pueden habilitar otros cauces para facilitarle el material necesario.

También quisiera explicarle que la entrega de este material se realiza mensualmente debido a que, todos los centros, reciben la distribución desde el almacén central en ese mismo ritmo. Esto permite distribuir de forma equitativa a todos los pacientes que lo precisen, así como evitar acumulaciones innecesarias y también permite ajustar la entrega si sus necesidades cambian, como puede ocurrir en algunos tratamientos.

No obstante, sentimos el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos es de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Síndrome de Aceite Tóxico: retirada de productos no justificados

**Propósito:** Explicar la valoración de productos prescritos en Síndrome de Aceite Tóxico y la retirada de aquellos de índole cosmética que no cumplen criterios.

**Condiciones de Aplicación:**
- Reclamaciones sobre prescripción o retirada de productos vinculados al Síndrome de Aceite Tóxico.
- Casos en los que se ha valorado la indicación con apoyo del Servicio de Farmacia de Atención Primaria.
- Supuestos en los que los productos no son terapia útil, paliativa y directamente relacionada con SAT.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro/consultorio]
- [Productos]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha [Fecha del escrito] sobre su disconformidad con la atención recibida en el [Centro/servicio], debo decirle lo siguiente:

El Real Decreto 2448/1981, de 19 de octubre, sobre protección a afectados por Síndrome de Aceite Tóxico (SAT), establece el reembolso del importe de los gastos médicos o farmacéuticos, protegidos o no por la Seguridad Social. Se indica que se abonará también con cargo al sistema de protección de los afectados, la totalidad de los productos de parafarmacia que no estén amparados o comprendidos dentro de la Seguridad Social para tratamiento de los síntomas de la enfermedad.

Este Real Decreto recoge que es el médico prescriptor quien determinará en cada caso si la prescripción está justificada y corresponde a una terapia útil, paliativa y directamente relacionada con la afectación por SAT, así como que el médico prescriptor tiene el deber de hacer uso racional de los recursos diagnósticos y terapéuticos a su cargo.

La médica de familia, con apoyo del Servicio de Farmacia de Atención Primaria, ha valorado la indicación de estos productos y ha prescrito aquellos que ha considerado según su criterio médico y siguiendo las indicaciones del RD mencionado: que el tratamiento sea una terapia útil, paliativa y directamente relacionada con la afectación por SAT.

En su caso, se detectó que se habían prescrito múltiples productos de índole cosmética que no cumplen con estos criterios, procediendo a su retirada según criterio médico.

Le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos es de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente,

Dirección Asistencial Oeste

## Petición de historia clínica en papel pendiente de tramitación

**Propósito:** Responder a solicitud de acceso a historia clínica cuando la petición ya fue trasladada, pero no se ha completado la tramitación.

**Condiciones de Aplicación:**
- Reclamaciones por demora en acceso a historia clínica.
- Casos en los que se ha reiterado la solicitud al servicio competente.
- Supuestos en los que se quiere transmitir que se intenta agilizar la respuesta y pedir comprensión por la demora.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Servicio competente]
- [Documentación solicitada]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito], mediante el cual solicita acceso a su historia clínica, queremos informarle de que su petición fue trasladada en su momento al servicio competente para su gestión.

No obstante, dado que aún no se ha completado la tramitación, le comunicamos que en el día de hoy hemos vuelto a reiterar la solicitud al servicio responsable con el fin de agilizar la respuesta y que pueda disponer de la documentación a la mayor brevedad posible.

Lamentamos las molestias que esta demora pueda haberle ocasionado y agradecemos su paciencia y comprensión. Su reclamación nos ayuda a mejorar nuestros procedimientos y la calidad del servicio que ofrecemos.

Reciba un cordial saludo.

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Acceso a historia clínica de persona fallecida: documentación y plazo

**Propósito:** Informar de los requisitos para entregar la historia clínica de una persona fallecida y del posible plazo de revisión/autorización.

**Condiciones de Aplicación:**
- Solicitudes de historia clínica de persona fallecida.
- Casos en los que debe acreditarse legitimación conforme a Ley 41/2002 y LOPDGDD.
- Supuestos en los que se debe aclarar que la solicitud en Atención Primaria solo da acceso a historia clínica de Atención Primaria.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Persona fallecida]
- [Documentación requerida]
- [Centro sanitario/unidad]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha [Fecha del escrito] sobre la petición de documentación clínica, debo explicarle lo siguiente:

Para poder entregar la historia clínica de una persona fallecida es necesario cumplir con lo establecido en la Ley 41/2002 y la Ley Orgánica de Protección de Datos (LOPDGDD). Estas leyes permiten el acceso a la historia clínica solo a personas legitimadas para ello.

Por ello, es imprescindible que se aporte toda la documentación requerida que justifique dicha relación. Esta documentación será evaluada por el centro sanitario o la unidad correspondiente.

Además, debe tener en cuenta que el proceso de revisión y autorización puede tardar hasta dos meses, dependiendo de la complejidad del caso y de la documentación presentada.

Igualmente le informamos que la solicitud realizada en el Centro de Salud le dará acceso a la Historia Clínica de Atención Primaria, si necesita información clínica de otros niveles asistenciales, deberá solicitarse en los centros correspondientes.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Preparación al parto: limitación de acceso por aforo de sala

**Propósito:** Responder a disconformidad por imposibilidad de acudir a clases de preparación al parto por limitaciones de espacio y seguridad.

**Condiciones de Aplicación:**
- Reclamaciones de acompañantes o parejas que no pueden acceder a sesiones de preparación al parto.
- Casos en los que la sala tiene espacio limitado y se restringe el acceso por seguridad, movilidad y confort.
- Supuestos en los que se traslada la petición al equipo directivo para valorar mejoras futuras.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Equipo directivo]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] donde expresa su disconformidad por la imposibilidad de acudir a las clases de Preparación al Parto en el Centro de Salud [Centro de Salud] y tras pedir información al Centro en primer lugar, debo decirle que lamentamos que la atención recibida no haya cumplido sus expectativas.

Deseamos informarle de que la sala destinada a estas actividades dispone de un espacio limitado, lo que obliga a restringir el acceso durante las sesiones. Esta medida responde a criterios de seguridad, movilidad y confort, con el objetivo de garantizar que todas las participantes puedan realizar los ejercicios y actividades previstas en condiciones adecuadas y sin riesgos.

No obstante, comprendiendo la importancia que este momento tiene para ambos miembros de la pareja, hemos trasladado su petición al equipo directivo, a fin de valorar posibles mejoras organizativas que puedan implementarse en el futuro.

Sentimos el malestar generado y le agradecemos que nos haya hecho llegar sus consideraciones, ya que sus comentarios son fundamentales para mejorar la calidad de la atención que prestamos y para identificar aspectos susceptibles de revisión.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Síndrome Tóxico: derivación a unidad específica para indicación de fármaco

**Propósito:** Explicar que la petición de tratamiento en Síndrome Tóxico se ha derivado a la unidad específica responsable de determinar el tratamiento apropiado.

**Condiciones de Aplicación:**
- Reclamaciones sobre prescripción de fármaco en paciente afectado por Síndrome Tóxico.
- Casos en los que Atención Primaria ha derivado la petición a una unidad específica hospitalaria.
- Supuestos en los que la respuesta está pendiente de dicha unidad para continuar el procedimiento.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Consultorio]
- [Unidad/Hospital de referencia]
- [Fármaco]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha [Fecha del escrito] sobre su disconformidad con la atención recibida en el Consultorio [Consultorio], debo decirle lo siguiente:

Con el fin de garantizar que reciba la atención adecuada, su médica de familia ha derivado su petición a la Unidad de Síndrome Tóxico del [Unidad/Hospital de referencia] que es la responsable de determinar el tratamiento más apropiado en estos casos y, por lo tanto, la indicación del fármaco concreto que usted necesita.

Actualmente, nos encontramos a la espera de la respuesta de dicha Unidad para poder continuar con el procedimiento correspondiente.

Lamentamos las molestias que esta situación le haya podido ocasionar y reiteramos nuestro compromiso con ofrecer una atención segura, coordinada y ajustada a la normativa sanitaria.

Atentamente,

[Responsable firmante]

## Tardanza en visado tras nueva prescripción

**Propósito:** Explicar que la médica de familia realizó una nueva receta con visado, pero la dispensación depende de la autorización de Inspección Médica.

**Condiciones de Aplicación:**
- Reclamaciones por demora en dispensación de fármaco con visado.
- Casos en los que hubo un problema sobrevenido ajeno al centro y se emitió nueva prescripción.
- Supuestos en los que el centro solo puede esperar la autorización administrativa del visado.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Fármaco]
- [Inspección Médica]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito con fecha [Fecha del escrito] sobre su disconformidad con la atención recibida en el Centro de Salud [Centro de Salud], y tras pedir información sobre los hechos que refiere, debo decirle lo siguiente:

Debido a un problema sobrevenido ajeno al Centro de Salud, usted necesitó una nueva prescripción de un fármaco que además requería visado por parte de la Inspección Médica para poder ser dispensado.

Por ello, su médica de familia realizó la receta esa misma tarde, garantizando así la continuidad del tratamiento. No obstante, tal y como establece la normativa vigente, el visado debe ser autorizado por el inspector, por lo que la dispensación queda supeditada a dicha validación administrativa, por tanto, debe saber que este trámite no es de nuestra competencia, por lo que únicamente podemos esperar a que la Inspección Médica autorice el visado para que la prescripción pueda ser dispensada.

Le agradecemos que nos haya hecho llegar su escrito que nos permite revisar nuestros circuitos y procedimientos en aras de seguir proporcionando la mejor atención posible a los usuarios.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Continuidad de prescripción indicada por otro facultativo: necesidad de informes

**Propósito:** Explicar que el médico debe compartir diagnóstico e indicación para asumir una prescripción indicada por otro facultativo y que se requieren informes clínicos suficientes.

**Condiciones de Aplicación:**
- Reclamaciones por negativa a asumir recetas de otro facultativo.
- Casos en los que falta documentación clínica suficiente para valorar diagnóstico, justificación del tratamiento o pruebas complementarias.
- Supuestos en los que procede priorizar seguridad, responsabilidad y buena práctica clínica.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Facultativo externo]
- [Tratamiento]
- [Informes clínicos]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] sobre la atención recibida en su Centro de Salud y tras pedir un informe al profesional al que hace referencia en su escrito, quiero explicarle lo siguiente:

Cuando un médico realiza una prescripción basada en la indicación de otro facultativo, asume íntegramente tanto el diagnóstico como el tratamiento prescrito. Esto implica hacerse responsable de la evolución clínica del paciente, así como de los posibles efectos secundarios o complicaciones derivados del medicamento en cuestión.

Por este motivo, para poder emitir dicha prescripción, el médico debe estar de acuerdo con el diagnóstico realizado por el otro profesional y considerar adecuado el tratamiento indicado. En caso de no compartir la valoración diagnóstica o terapéutica, no procede asumir la prescripción, ya que hacerlo sin la información necesaria podría comprometer la seguridad del paciente.

Asimismo, es imprescindible que el paciente aporte todos los informes clínicos necesarios, incluyendo el diagnóstico, la justificación del tratamiento y cualquier prueba complementaria relevante. Solo con esta documentación es posible valorar adecuadamente la indicación y, en su caso, asumir la continuidad del tratamiento con garantías.

Nuestro objetivo es asegurar siempre una atención segura, responsable y ajustada a la buena práctica clínica, motivo por el cual se siguen estos criterios.

Le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos es de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Sensores de medición de glucosa intersticial: provisión desde almacén centralizado

**Propósito:** Explicar que los centros de salud no disponen de provisión propia de sensores de medición de glucosa intersticial y solo distribuyen los suministrados por almacén central.

**Condiciones de Aplicación:**
- Reclamaciones sobre falta o aumento de sensores de glucosa intersticial.
- Casos en los que el usuario solicita sensores adicionales por necesidad clínica o eventualidad.
- Supuestos en los que procede aclarar que Atención Primaria no puede pedir nuevos sensores fuera del suministro centralizado.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha del escrito]
- [Centro de Salud]
- [Sensores]
- [Almacén centralizado]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] sobre el suministro de Sensores Medidores de Glucosa Intersticial en su Centro de Salud, debo informarle de lo siguiente:

Los centros de salud no cuentan con una provisión propia de dichos dispositivos, siendo su cometido distribuir aquellos que les suministra el almacén centralizado. Por todo ello, no es posible desde Primaria pedir nuevos sensores en el caso de que los usuarios los necesitasen por un posible aumento en la necesidad derivada de su patología o bien por una eventualidad.

Le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos es de gran utilidad para velar por la calidad del servicio que prestamos a nuestra población.

Atentamente,

Dirección Asistencial Oeste

## Retrasos en sala de extracciones por etiquetado de muestras por TCAE

**Propósito:** Explicar posibles esperas en la sala de extracciones por la intervención del TCAE en el etiquetado de muestras y la necesidad de garantizar seguridad y trazabilidad.

**Condiciones de Aplicación:**
- Reclamaciones sobre lentitud o retrasos en laboratorio/extracciones.
- Casos en los que un único TCAE realiza el etiquetado de todas las muestras.
- Supuestos de alta demanda en los que pueden producirse tiempos de espera por seguridad y trazabilidad.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Sala de extracciones]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En relación con su escrito de fecha [Fecha del escrito] sobre la organización en la Sala de Extracciones de su Centro de Salud y tras pedir un informe a los profesionales, quisiera explicarle lo siguiente:

La organización de las extracciones tiene unas peculiaridades específicas que la distinguen de otras consultas sanitarias. Entre ellas está la de que es el Técnico en Cuidados Auxiliares de Enfermería (TCAE) el encargado del etiquetado de todas las muestras. Esta tarea requiere precisión y cuidado para garantizar la seguridad y trazabilidad de cada muestra.

Al tratarse de un profesional único, puede ocasionar retrasos o tiempos de espera, especialmente en momentos de alta demanda. Les pedimos comprensión, ya que no es nuestra intención generar demoras, sino asegurar que cada muestra sea gestionada correctamente.

Sentimos el malestar generado, no obstante, y le agradecemos su comprensión y colaboración, y el hecho de que nos transmita su opinión y sus consideraciones, puesto que nos permiten profundizar en la información sobre determinados circuitos y procedimientos de trabajo implementados en aras de la mejor calidad del servicio prestado.

Atentamente,

[Responsable firmante]

Responsable de la Unidad de Atención al Paciente

Dirección Asistencial Oeste

## Unidad específica con profesional único en turno determinado

**Propósito:** Explicar la dotación y turno de atención de unidades específicas con profesional único, como salud bucodental, en función de criterios homogéneos y eficiencia global.

**Condiciones de Aplicación:**
- Reclamaciones por falta de profesional de unidad específica en un turno concreto.
- Casos de odontología/salud bucodental u otras unidades específicas con profesional único.
- Supuestos en los que procede explicar criterios de población, dispersión geográfica y organización eficiente del turno.

**Variables Clave:**
- [Nombre y apellidos]
- [Domicilio]
- [Localidad]
- [Fecha de respuesta]
- [Fecha del escrito]
- [Centro de Salud]
- [Unidad específica]
- [Turno]
- [Responsable firmante]

**Contenido:**

D./D.ª [Nombre y apellidos]

[Domicilio]

[Localidad]

[Fecha de respuesta]

Estimado/a Sr./Sra. [Apellidos]:

En contestación a su escrito de fecha [Fecha del escrito], en el que hace referencia a la falta de odontólogo en el turno de tarde en el Centro de Salud [Centro de Salud], en primer lugar debo pedirle disculpas por la demora en la contestación. En segundo lugar, debo explicarle lo siguiente:

- La dotación de recursos de las Unidades Específicas en los centros de salud, entre las que se encuentran las Unidades Salud Bucodental, se realiza en base a una serie de criterios homogéneos establecidos mediante normativa, que contemplan, entre otros aspectos, la población a la que se da servicio y la dispersión geográfica de la zona.

- Respecto al turno en el que se presta la atención, en el caso de profesionales únicos, éste se establece de forma que se pueda realizar de la manera más eficiente desde un punto de vista global.

Lamentamos su malestar y le agradecemos que nos haya hecho llegar sus consideraciones, pues su información y opinión nos son de gran utilidad para conseguir un servicio de calidad y de plena satisfacción para la población a la que atendemos.

Atentamente,

[Responsable firmante]

Responsable Unidad de Atención al Paciente

Dirección Asistencial Oeste

