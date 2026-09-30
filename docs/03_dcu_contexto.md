# 03 · Comprender el contexto con Diseño Centrado en el Usuario (DCU)

**Proyecto:** Tutoría Fácil UTA · **Grupo 6** · **Asignatura:** Interacción Humano Computador
**Responsable:** Jonathan Gamboa · **Rama:** `feature/jonathan-dcu-readme`

Las referencias **E1 a E10** identifican las evidencias del caso. Cada elemento de este documento indica la evidencia que lo respalda.

---

## 1. Contexto de uso

| Aspecto | Descripción | Evidencia |
|---|---|---|
| **Usuarios** | Estudiantes con experiencia digital diversa; uso táctil, teclado, ampliación y lector de pantalla. Docentes y secretaría participan indirectamente. | E1, E2, E6, E7 |
| **Tareas** | Consultar disponibilidad, seleccionar un horario, revisar datos, confirmar y cambiar una cita. | E3, E5, E10 |
| **Entorno** | Uso móvil durante desplazamientos, atención dividida y conectividad variable; acceso alternativo mediante teclado. | E1, E2, E8 |
| **Restricciones** | Espacio reducido, respuestas lentas, fechas que pueden olvidarse, horarios ocupados y datos que pueden quedar desactualizados. | E3, E5, E7, E8 |

## 2. Persona principal

**Laura**, estudiante de 20 años.

| Elemento | Contenido |
|---|---|
| **Objetivo** | Reservar una tutoría sin intercambiar varios mensajes. |
| **Comportamiento** | Consulta horarios desde su teléfono mientras viaja en bus; revisa la información en periodos breves. |
| **Condición relevante** | Atención dividida y conectividad variable durante el trayecto. |
| **Frustración** | Esperar respuestas y no saber con claridad si una cita está confirmada. |
| **Necesidad** | Un recorrido corto, datos visibles y posibilidad de corregir una selección. |

Fundamento: E1; E3, E4, E5 y E8 describen necesidades del contexto que orientan el diseño.

### Condición de accesibilidad relevante

**Carlos** representa un perfil complementario: utiliza teclado, ampliación al 200 % y lector de pantalla. E2 exige que la disponibilidad no dependa de un calendario visual sin etiquetas. Su condición se incorpora mediante nombres descriptivos, alternativas en lista, orden de foco y anotaciones semánticas, sin atribuir estas capacidades a Laura.

## 3. Escenario del proceso actual

| Elemento | Descripción |
|---|---|
| **Situación** | Durante el trayecto a la universidad, Laura identifica que necesita una tutoría para el jueves. |
| **Contexto** | Usa el teléfono en el bus, con conexión variable. |
| **Desencadenante** | Necesita una tutoría para el jueves. |
| **Objetivo** | Obtener una cita clara y conservar la información vigente. |
| **Dificultad actual** | Consulta al docente por WhatsApp, espera la disponibilidad, propone un horario, recibe mensajes y solicita confirmación. Si necesita cambiar la hora, debe recuperar la conversación y volver a coordinar. La conexión variable retrasa las respuestas y la confirmación puede quedar mezclada con otros mensajes. |

Evidencias relacionadas: E1, E4, E5, E8 y E10. El escenario describe el proceso anterior a la solución.

## 4. Ciclo de diseño (ISO 9241-210)

El contexto y las evidencias originan los requisitos; estos guían las decisiones y las cuatro pantallas. La prueba cruzada permite contrastar el recorrido con las metas, registrar una dificultad y modificar el diseño, aplicando el proceso iterativo de ISO 9241-210.

---

## 5. Journey map del proceso actual

Las cinco etapas representan el recorrido anterior a la aplicación. Los pensamientos y emociones son interpretaciones de diseño derivadas del caso; no son citas ni testimonios recogidos en entrevistas.

| Etapa | Acción | Pensamiento | Emoción | Problema | Oportunidad |
|---|---|---|---|---|---|
| **1 Buscar** | Identificar la necesidad de tutoría y revisar cómo contactar. | Necesito conocer los horarios. | Duda | La disponibilidad no está reunida. (E1, E6) | Mostrar fechas y horarios publicados. |
| **2 Contactar** | Enviar mensaje y esperar respuesta. | ¿Cuándo me responderá? | Ansiedad | Esperas y mensajes sucesivos. (E4, E8) | Consultar disponibilidad sin conversación previa. |
| **3 Acordar** | Proponer hora y negociar alternativas. | ¿Este horario estará libre? | Molestia | Se intentan elegir horarios ocupados. (E3) | Distinguir y bloquear horarios ocupados. |
| **4 Confirmar** | Buscar el mensaje que confirma la cita. | ¿Ya quedó reservada y a qué hora? | Duda | Confirmación ambigua o perdida. (E3, E5) | Tarjeta con estado y datos completos. |
| **5 Cambiar** | Iniciar otra conversación para modificar la hora. | ¿Sigue vigente la cita anterior? | Inquietud | Cambios manuales y datos desactualizados. (E7, E10) | Reprogramar con revisión previa y cita vigente visible. |

### Prioridades identificadas

La mayor fricción está en **acordar** y **confirmar**, donde el usuario debe interpretar respuestas y verificar disponibilidad. La oportunidad principal es hacer visible el estado de cada horario y reunir los datos de la cita. Para cambiarla, el diseño debe indicar con claridad cuándo se reemplaza la reserva anterior y permitir cancelar antes de confirmar.

### Transformación del recorrido

- **Buscar** y **contactar** se traducen en el acceso a disponibilidad.
- **Acordar** se convierte en seleccionar un horario visible.
- **Confirmar** se divide en una revisión previa y una tarjeta final.
- **Cambiar** reutiliza selección y revisión, con el modo *Reprogramar tutoría* y el mensaje final *Horario actualizado*.

---

## 6. Cinco requisitos verificables de usuario

Cada requisito expresa una acción, una condición y un resultado. **P1** corresponde a Inicio y búsqueda; **P2** a Docente y horario; **P3** a Resumen y confirmación; **P4** a Confirmada y reprogramación.

| ID | Requisito de usuario | Evidencia | Pantalla y aceptación |
|---|---|---|---|
| **R1** | El estudiante debe poder consultar horarios publicados de un docente, desde el teléfono y con conexión variable, para identificar una opción disponible sin intercambiar mensajes. | E1, E4, E6, E8 | **P1 y P2.** Ver docente, fecha y disponibilidad; mostrar carga sin borrar la elección. |
| **R2** | El estudiante debe poder elegir un horario disponible, distinguiendo los ocupados y usando toque o teclado, para evitar una reserva inválida. | E2, E3, E9 | **P2.** Estados con texto, foco visible y horarios ocupados sin selección. |
| **R3** | El estudiante debe poder revisar y corregir docente, fecha, hora y modalidad antes de confirmar, para detectar una elección incorrecta sin reiniciar el recorrido. | E3, E9, E10 | **P3** y retorno a **P2.** Volver conserva la selección; confirmar muestra el resultado final. |
| **R4** | El estudiante debe poder consultar una tarjeta de su tutoría confirmada, después de reservar, para reconocer el estado y recordar los datos acordados. | E3, E5, E9 | **P4** y acceso desde **P1.** Estado *Confirmada* y datos completos, sin depender del color. |
| **R5** | El estudiante debe poder seleccionar y confirmar un nuevo horario de una cita existente, conservando la reserva anterior hasta finalizar el cambio, para reprogramar sin ambigüedad. | E7, E8, E10 | **P4 → P2 → P3 → P4.** Comparar antes y después; cancelar conserva la cita original; confirmar muestra *Horario actualizado*. |

### Reglas de operación

- Un horario ocupado se informa pero no puede seleccionarse. Antes de confirmar, el sistema comprueba de nuevo la disponibilidad; el prototipo representa este caso con una variante de error.
- Elegir otro horario reemplaza únicamente la selección provisional. *Volver* no borra los datos y *Cancelar cambio* conserva la cita vigente.
- Mientras se procesa la confirmación, la acción no puede enviarse repetidamente. Si falla, se explica el problema y se conserva la información para reintentar.
- El cambio sustituye la cita anterior solo tras una confirmación exitosa. No se muestran dos reservas vigentes para la misma tutoría.