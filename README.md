# Tutoría Fácil UTA · Prueba 02 IHC

**Universidad Técnica de Ambato · Facultad de Ingeniería en Sistemas, Electrónica e Industrial**  
**Carrera:** Ingeniería de Software · **Asignatura:** Interacción Humano Computador · **Nivel:** Quinto semestre  
**Grupo:** 6 · **Repositorio:** Grupo_6_Tutoria_Facil_UTA · **Fecha:** 30 de septiembre de 2026  

Repositorio oficial de la prueba práctica integradora del primer parcial: diseño desde cero de una aplicación web móvil para consultar disponibilidad, reservar, confirmar y reprogramar una tutoría académica.

---

## 1. Integrantes y roles

| Integrante | Usuario GitHub | Rol | Rama | Entrega principal |
| :--- | :--- | :--- | :--- | :--- |
| Emilio Abril | @EMILIOABRIL05 | Analista de interacción y evaluación | `feature/emilio-matriz-evaluacion` | `docs/01_matriz_ihc.pdf`, `evaluacion/prueba_iteracion.md` |
| Manuel Cusme | @ManuelCusme | Usabilidad y accesibilidad | `feature/manuel-usabilidad-pour` | `docs/02_usabilidad_accesibilidad.pdf` |
| Jonathan Gamboa | @Jonathan305g | Analista DCU y documentación | `feature/jonathan-dcu-readme` | `docs/03_dcu_contexto.pdf`, `README.md` |
| Pablo Lozada | @idk.Damian | Decisiones de diseño y guía de estilo | `feature/pablo-decisiones-guia` | `docs/04_decisiones_diseno.pdf` |
| William Martínez | @william-martinez5101 | Prototipado | `feature/william-prototipo` | `prototipo/` (capturas y enlace)|

> La asignación de un rol no limita la colaboración: todos los integrantes tienen issue, rama, commits y pull request propios.

---

## 2. Problema de diseño

La coordinación de tutorías se hace hoy con WhatsApp, hojas de cálculo y agendas personales. El estudiante escribe al docente, espera respuesta, propone horarios y solicita confirmación; para cambiar la cita debe iniciar otra conversación. Esa dispersión provoca confirmaciones ambiguas, intentos de elegir horarios ocupados, fechas olvidadas e información desactualizada (evidencias E3, E5, E6 y E7).

- **Pregunta de diseño:** ¿Cómo permitir que un estudiante reserve o reprograme una tutoría desde un teléfono, con claridad, bajo esfuerzo cognitivo, prevención de errores y acceso mediante teclado o tecnologías de apoyo?
- **Alcance:** Desde que el estudiante busca un horario hasta que recibe una confirmación con docente, fecha, hora y modalidad, incluyendo la ruta para reprogramar una cita existente. Quedan fuera autenticación, reportes y administración de usuarios.

---

## 3. Enlaces del proyecto

| Recurso | Enlace |
| :--- | :--- |
| Tablero FigJam (análisis) | Pendiente de incorporar |
| PDF del análisis DCU | [docs/](docs/) |
| Prototipo navegable (Figma Design / Penpot) | Pendiente de incorporar (ver [prototipo/enlace_prototipo.md](prototipo/enlace_prototipo.md)) |
| Registro de la prueba e iteración | [evaluacion/prueba_iteracion.md](evaluacion/prueba_iteracion.md) |

---

## 4. Estructura del repositorio

```text
Grupo_6_Tutoria_Facil_UTA/
├── README.md
├── docs/
│   ├── 01_matriz_ihc.pdf               # Matriz humano-sistema con E1 a E10
│   ├── 02_usabilidad_accesibilidad.pdf # 3 indicadores de usabilidad y 4 decisiones POUR
│   ├── 03_dcu_contexto.pdf             # Contexto, persona, escenario, journey map y 5 requisitos
│   └── 04_decisiones_diseno.pdf        # Metáforas, affordance, Gestalt y guía de estilo
├── prototipo/
│   ├── capturas/                       # Capturas de las 4 pantallas
│   └── enlace_prototipo.md             # Enlace navegable del prototipo
└── evaluacion/
    └── prueba_iteracion.md             # Tarea, participante, resultado, tiempo, hallazgo, antes y después
```

---

## 5. Resumen del análisis

**Persona principal:** Laura, estudiante de 20 años que consulta horarios desde el teléfono mientras viaja en bus (E1). Necesita reservar sin intercambiar varios mensajes y reconocer con claridad si su cita quedó confirmada. Como perfil complementario de accesibilidad, Carlos usa teclado, ampliación al 200 % y lector de pantalla (E2).

### Cinco requisitos de usuario

| ID | Requisito (resumen) | Evidencia | Pantalla |
| :--- | :--- | :--- | :--- |
| **R1** | Consultar horarios publicados de un docente desde el teléfono, sin intercambiar mensajes | E1, E4, E6, E8 | P1 y P2 |
| **R2** | Elegir un horario disponible distinguiendo los ocupados, con toque o teclado | E2, E3, E9 | P2 |
| **R3** | Revisar y corregir docente, fecha, hora y modalidad antes de confirmar | E3, E9, E10 | P3 → P2 |
| **R4** | Consultar la tarjeta de la tutoría confirmada para recordar los datos | E3, E5, E9 | P4 |
| **R5** | Seleccionar y confirmar un nuevo horario conservando la reserva anterior hasta finalizar | E7, E8, E10 | P4 → P2 → P3 → P4 |

### Indicadores de usabilidad (metas propuestas, aún no medidas)

| Dimensión | Indicador | Meta propuesta |
| :--- | :--- | :--- |
| **Efectividad** | Éxitos sin ayuda / participantes × 100 | ≥ 90 % en reserva y en reprogramación |
| **Eficiencia** | Tiempo y acciones hasta la confirmación | Reserva ≤ 120 s y ≤ 8 acciones; reprogramación ≤ 90 s y ≤ 6 acciones |
| **Satisfacción** | Escala de 1 a 7 tras la tarea | ≥ 6 |

- **Accesibilidad (POUR):** Estados con texto (Disponible, Ocupado, Seleccionado, Confirmada) y contraste mínimo 4,5:1; orden de foco lógico, foco visible y controles de al menos 44 × 44 px; etiquetas persistentes y errores que explican la corrección; nombre, rol y estado especificados para cada control.
- **Decisiones de diseño:** Metáforas de agenda, tarjeta de cita y recorrido guiado; horarios con borde y etiqueta como affordance; selección directa sobre el horario visible; retroalimentación de carga, selección, confirmación y error; un objetivo principal por pantalla; leyes Gestalt de proximidad, semejanza y figura-fondo; sin iconos aislados ni fechas numéricas ambiguas.

---

## 6. Prototipo

Cuatro pantallas móviles de 390 × 844 px, de fidelidad media, con datos ficticios (docente Ana Torres, jueves 1 de octubre de 2026, modalidad Presencial).

| Pantalla | Contenido |
| :--- | :--- |
| **P1 Inicio y búsqueda** | Propósito, botón *Reservar tutoría* y acceso a *Mis tutorías* |
| **P2 Docente y horario** | Docente, fecha completa y horarios *Disponible*, *Ocupado* y *Seleccionado* |
| **P3 Resumen y confirmación** | Docente, fecha, hora, modalidad, *Volver* y *Confirmar tutoría* |
| **P4 Confirmada y reprogramación** | Tarjeta con estado *Confirmada* y acceso a *Cambiar horario* |

**Recorridos:**  
- **Reserva:** P1 → P2 → P3 → P4  
- **Reprogramación:** P4 → P2 → P3 → P4  
- **Corrección:** P3 → P2  
- **Cancelar cambio:** P2 → P4  

---

## 7. Prueba cruzada e iteración

Una persona de otro equipo recibirá el prototipo sin explicaciones y se le pedirá: *«Reserve una tutoría para el jueves y luego cambie el horario»*. Se registrarán éxito, tiempo, acciones, dudas, errores y comentario final, y se aplicará una mejora concreta conservando la captura del antes y del después.

| Dato | Resultado |
| :--- | :--- |
| **Participante** | Pendiente de registrar |
| **Tarea** | Reservar una tutoría para el jueves y luego cambiar el horario |
| **Éxito sin ayuda** | Pendiente |
| **Tiempo y acciones** | Pendiente |
| **Hallazgo** | Pendiente |
| **Mejora aplicada (antes → después)** | Pendiente |

> El detalle completo se documenta en [evaluacion/prueba_iteracion.md](evaluacion/prueba_iteracion.md).

---

## 8. Flujo de trabajo en GitHub

1. **Planificar:** Un issue asignado a cada integrante.
2. **Desarrollar:** Una rama `feature/nombre-aporte` por integrante, con al menos dos commits vinculados a su issue.
3. **Revisar:** Un pull request por integrante, revisado por un compañero distinto.
4. **Integrar:** Aprobación y fusión de los cinco pull requests en `main`.

| Autor del PR | Revisor |
| :--- | :--- |
| Emilio | Manuel |
| Manuel | Jonathan |
| Jonathan | Pablo |
| Pablo | William |
| William | Emilio |

---

## 9. Estándares que fundamentan el trabajo

- **ISO 9241-11:** Calidad de uso mediante efectividad, eficiencia y satisfacción.
- **ISO 9241-210:** Proceso iterativo de diseño centrado en las personas.

> *Las metas de usabilidad son objetivos de diseño y no resultados de evaluación.*
