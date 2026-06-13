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
