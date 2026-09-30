# 04 · Decisiones de Diseño, Leyes Gestalt y Guía de Estilo

**Proyecto:** Tutoría Fácil UTA · **Grupo 6** · **Asignatura:** Interacción Humano-Computador  
**Responsable:** Pablo · **Rama:** `feature/pablo-decisiones-guia`  

---

## 1. Principios de Interacción Humano-Computador (IHC)

El diseño del prototipo **Tutoría Fácil UTA** traduce los principios fundamentales de IHC en soluciones concretas de interfaz para la reserva y gestión de tutorías académicas presenciales:

| Principio IHC | Aplicación en el Prototipo | Justificación y Detalle de Diseño |
|---|---|---|
| **Metáfora** | Uso del calendario móvil y tarjeta de resumen como ticket/comprobante de cita | Se adopta el modelo mental de una agenda física y un ticket/comprobante de confirmación. La tarjeta final en la Pantalla 4 representa visualmente un pase digital de cita que el estudiante reconoce de inmediato. |
| **Affordance y Mapeo** | Botones con apariencia presionable, tarjetas de selección con bordes destacados y estados claros | Los botones poseen un radio de esquina de 8 px, relleno de color contrastante y bordes definidos que invitan al clic/toque. Los contenedores de horario (slots) usan borde `#64748B` e indican explícitamente su estado (*Disponible*, *Seleccionado*, *Ocupado*). |
| **Manipulación Directa** | Selección táctil de franjas horarias en la lista o calendario | El usuario interactúa tocando o haciendo clic directamente sobre las tarjetas de fecha y las franjas horarias de 30 minutos. La acción actualiza la selección de forma inmediata sin formularios emergentes o menús desplegables complejos. |
| **Retroalimentación** | Indicadores visuales al marcar horarios, mensajes de estado y banners de alerta | Al seleccionar un horario se muestra la etiqueta con check `✓ Seleccionado` en azul `#1D4ED8`. Durante el envío se despliega la pantalla de carga (*"Confirmando tutoría..."*) e impidiendo clics repetidos, junto con banners informativos o de error recuperable. |
| **Carga Cognitiva** | Formulario guiado paso a paso (pantalla por pantalla) con una sola acción principal | La reserva se divide en un flujo lineal progresivo (Inicio → Selección → Resumen → Confirmación). Cada vista tiene un único botón primario destacado y la pantalla de resumen agrupa toda la información relevante en una única tarjeta para su verificación antes de confirmar. |
| **Riesgo Cultural** | Lenguaje en español estándar sin jerga ambigua y formatos de fecha/hora claros | Se utiliza terminología comprensible y directa adecuada para el contexto de la Universidad Técnica de Ambato (UTA). Las fechas se escriben con formato extendido claro (ej. *"Jueves 1 de octubre de 2026"*) y los rangos de horas de 24h (*"10:00 a 10:30"*). |

---

## 2. Leyes de la Psicología de la Gestalt Justificadas

El prototipo aplica principios de la Psicología de la Gestalt para organizar la información y facilitar la comprensión visual rápida:

### 1. Ley de Proximidad
- **Aplicación:** Los datos clave de una tutoría (docente, fecha, hora asignada y modalidad presencial) se agrupan en proximidad dentro de un mismo contenedor o tarjeta (`.card.card-detail`).
- **Justificación:** Al mantener contiguos los atributos de la reserva, el estudiante los percibe como una única unidad conceptual sólida. De igual manera, el botón secundario *"🔄 Cambiar horario"* se sitúa inmediatamente debajo de la tarjeta de resumen contiguo a la hora asignada, indicando visualmente que su función aplica de forma directa sobre dicha cita.

### 2. Ley de Semejanza
- **Aplicación:** Todos los bloques o contenedores de horarios (*slot-item*) comparten una estructura visual equivalente (mismo radio de esquina, tamaño, espaciado interior padding de 12px/16px y altura mínima de 44 px).
- **Justificación:** El cerebro del usuario percibe que todos estos elementos pertenecen a la misma categoría y cumplen la misma función interactiva (seleccionar una franja horaria). Las variaciones de color de fondo y borde (azul para seleccionado, gris atenuado para ocupado) señalan el estado actual del elemento sin romper la semejanza de forma.

### 3. Ley de Figura-Fondo
- **Aplicación:** El diseño emplea un fondo neutro (pantalla en blanco `#FFFFFF` sobre marco contenedor `#F1F5F9`), tarjetas delimitadas con bordes `#64748B` o `#E2E8F0`, y botones de acción primaria en azul `#1D4ED8` de alto contraste.
- **Justificación:** Esta diferenciación cromática y de bordes establece una jerarquía clara donde los elementos interactivos primarios y la información relevante (figura) resaltan visiblemente sobre la superficie neutra de trabajo (fondo), reduciendo el tiempo de búsqueda visual.

---

## 3. Guía de Estilo Visual y Sistema de Diseño

Para garantizar la coherencia técnica y estética entre las maquetas de Figma y la implementación web, se definen los siguientes tokens y especificaciones:

### 3.1. Tipografía

Se adopta la fuente tipográfica **Inter** (Google Fonts) por su alta legibilidad en pantallas móviles de diversas resoluciones.

| Nivel / Rol | Fuente | Tamaño (`font-size`) | Altura de Línea (`line-height`) | Peso (`font-weight`) | Uso en Interfaz |
|---|---|---|---|---|---|
| **Título Principal (H1)** | Inter | `24 px` | `32 px` | Bold (`700`) | Encabezados principales de pantalla |
| **Subtítulo (H2)** | Inter | `18 px` | `24 px` | Semi-Bold (`600`) | Secciones secundarias y modales |
| **Cuerpo de Texto (Body)** | Inter | `16 px` | `22 px` | Regular (`400`) | Párrafos descriptivos e instrucciones |
| **Texto Auxiliar / Labels** | Inter | `14 px` | `20 px` | Semi-Bold (`600`) / Medium (`500`) | Etiquetas, badges, leyendas y captions (`#64748B`) |

---

### 3.2. Paleta de Colores

Los colores han sido seleccionados bajo criterios de accesibilidad (contraste WCAG AA) y significado cromático claro:

| Rol de Color | Código Hexadecimal | Muestra | Descripción y Aplicación |
|---|---|---|---|
| **Fondo Base** | `#FFFFFF` | ⚪ Blanco | Fondo principal de las pantallas del dispositivo |
| **Fondo Lienzo/Marco** | `#F1F5F9` | 🩶 Gris Claro | Fondo de integración exterior del prototipo |
| **Texto Principal** | `#111827` | ⬛ Negro Tintado | Títulos, valores de resumen y texto destacado |
| **Texto Secundario** | `#374151` | 🩶 Gris Oscuro | Cuerpo de texto y descripciones |
| **Texto Auxiliar / Caption** | `#64748B` | 🩶 Gris Medio | Subtítulos, horas deshabilitadas y bordes neutros |
| **Acción Primaria / Énfasis** | `#1D4ED8` | 🟦 Azul UTA | Botones principales, selecciones activas y bordes destacados |
| **Fondo Éxito** | `#F0FDF4` | 🟩 Verde Claro | Fondo de alertas y badges de confirmación |
| **Texto/Borde Éxito** | `#166534` / `#86EFAC` | 🟩 Verde Oscuro | Indicadores de cita confirmada o slot disponible |
| **Fondo Error / Ocupado** | `#FEF2F2` | 🟥 Rojo Claro | Fondo de alertas de error y horarios deshabilitados |
| **Texto/Borde Error** | `#991B1B` / `#FCA5A5` | 🟥 Rojo Oscuro | Indicador de franja horaria ocupada o fallo |

---

### 3.3. Componentes y Consistencia Visual

Todos los componentes reutilizables garantizan un área táctil adecuada (cumpliendo la pauta de área de toque mínima de **44 px** para dispositivos móviles):

1. **Botones Primarios (`.btn-primary`):**
   - Altura mínima: `48 px` (supera el estándar de 44 px).
   - Fondo: `#1D4ED8`, Texto: `#FFFFFF` (peso 600).
   - Bordes redondeados: `border-radius: 8px`.

2. **Botones Secundarios (`.btn-secondary`):**
   - Altura mínima: `48 px`.
   - Fondo: `#FFFFFF`, Texto y Borde: `#1D4ED8` (`1.5px solid`).
   - Variante de reprogramación: Borde punteado `border-style: dashed`.

3. **Tarjetas de Cita y Resumen (`.card`):**
   - Fondo: `#FFFFFF`, Borde: `1px solid #64748B`, Radio de esquina: `12 px`.
   - Relleno interno (*padding*): `16 px`.
   - Filas detalladas (`.detail-row`) divididas por líneas discontinuas `#E2E8F0`.

4. **Selectores de Horario (`.slot-item`):**
   - Altura mínima: `52 px`.
   - Estados:
     - *Disponible:* Borde `#64748B`, fondo `#FFFFFF`.
     - *Seleccionado:* Borde `2px solid #1D4ED8`, fondo `#EFF6FF`.
     - *Ocupado/Deshabilitado:* Borde `#CBD5E1`, fondo `#F1F5F9`, opacidad `0.6`, cursor `not-allowed`.

5. **Badges e Indicadores de Estado (`.badge-success` / `.badge-error`):**
   - Relleno interior: `4px 8px`, `border-radius: 4px`, tamaño de fuente: `14 px`.
   - Proporcionan feedback inmediato sin depender exclusivamente del color.
