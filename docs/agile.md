# Metodologías de desarrollo: Agile, Scrum y Kanban

## ¿Qué es Agile y cuál es su objetivo en el desarrollo de software?

**Agile** (ágil) no es un único método con pasos fijos, sino un **enfoque** y un conjunto de **valores y principios** para desarrollar software de forma iterativa e incremental. Nació como reacción a planes rígidos de meses o años que a menudo entregaban productos que ya no encajaban con lo que el negocio o los usuarios necesitaban.

Su **objetivo central** es **entregar valor de forma continua y temprana**, adaptándose al cambio en lugar de combatirlo. Se prioriza la colaboración con el cliente, equipos autoorganizados, software funcionando como medida de progreso y la mejora constante del proceso. El Manifiesto Ágil resume ideas como: individuos e interacciones sobre procesos y herramientas; software funcionando sobre documentación extensa; colaboración con el cliente sobre negociación contractual; y respuesta al cambio sobre seguir un plan fijo.

En la práctica, Agile se materializa mediante **marcos concretos** (como Scrum o Kanban) o combinaciones híbridas que respetan esos principios.

---

## ¿Qué es Scrum y sus conceptos principales?

**Scrum** es un **marco de trabajo** dentro del mundo ágil, muy estructurado, pensado para equipos que desarrollan productos complejos en ciclos cortos y predecibles.

### Roles principales

- **Product Owner (dueño del producto):** representa intereses de negocio y usuarios. Define y ordena el trabajo según valor; es quien toma decisiones sobre *qué* construir y en qué prioridad.
- **Scrum Master:** facilita el marco Scrum, ayuda a quitar impedimentos y protege al equipo de interrupciones que rompen el foco. No es un “jefe de proyecto” tradicional: orienta al proceso y a la mejora.
- **Equipo de desarrollo:** profesionales que construyen el incremento del producto; suelen ser multifuncionales y autoorganizados.

### Sprints

Un **sprint** es un **periodo de tiempo fijo** (típicamente de una a cuatro semanas) en el que el equipo se compromete a completar un conjunto de trabajo seleccionado desde el backlog. Al final del sprint debe haber un **incremento potencialmente entregable** del producto. Los sprints se repiten uno tras otro, con la misma duración habitualmente.

### Backlog

El **Product Backlog** es la lista ordenada de todo lo que podría hacerse en el producto: funcionalidades, mejoras, correcciones, deuda técnica, etc. El Product Owner la mantiene priorizada. Durante la planificación del sprint, el equipo elige **elementos del backlog** que cree poder terminar en ese sprint; esa selección forma el **Sprint Backlog**, el plan del sprint.

### Reviews y otros eventos habituales

- **Sprint Review (revisión del sprint):** al terminar el sprint, el equipo muestra lo construido a interesados y recoge feedback. Sirve para inspeccionar el producto y adaptar el backlog si hace falta.
- **Sprint Retrospective:** el equipo reflexiona sobre *cómo* trabajó el proceso y busca mejoras para el siguiente sprint.
- **Daily Scrum (reunión diaria):** sincronización breve del equipo sobre el progreso y los impedimentos del día.

También suele existir **planificación del sprint** al inicio y, a veces, refinamiento del backlog entre sprints.

---

## ¿Qué es Kanban y cómo se usa para organizar tareas?

**Kanban** es un método de gestión del flujo de trabajo que enfatiza **visualizar el trabajo**, **limitar el trabajo en curso (WIP)** y **mejorar de forma continua** sin imponer necesariamente ciclos de tiempo fijos como los sprints.

### Cómo se usa para organizar tareas

1. **Tablero visual:** las tareas se representan como tarjetas que se mueven por **columnas** que reflejan estados del flujo (por ejemplo: Por hacer, En progreso, En revisión, Hecho). Todo el mundo ve qué hay en cada etapa.
2. **Límites de WIP:** cada columna (o el conjunto de “en progreso”) tiene un **máximo** de ítems permitidos. Eso evita multitarea excesiva, reduce colas y obliga a terminar antes de empezar demasiadas cosas nuevas.
3. **Políticas explícitas:** se acuerdan reglas claras sobre cuándo una tarjeta puede pasar de una columna a otra (definición de “hecho”, criterios de calidad, etc.).
4. **Flujo continuo:** el trabajo entra cuando hay capacidad; no hace falta esperar a una “fecha de inicio de iteración” global. Se prioriza el flujo estable hacia “terminado”.

Kanban puede aplicarse a equipos de software, soporte, operaciones o mezcla de tipos de trabajo; es muy flexible en ceremonias y roles formales.

---

## Diferencias entre Scrum y Kanban

| Aspecto | Scrum | Kanban |
|--------|--------|--------|
| **Ritmo** | Ciclos fijos (sprints) con inicio y fin definidos. | Flujo continuo; no exige sprints. |
| **Roles** | Roles definidos (Product Owner, Scrum Master, equipo). | No prescribe roles obligatorios; el equipo adapta gobernanza. |
| **Compromiso** | El equipo se compromete con un conjunto de trabajo por sprint. | Se limita trabajo en curso; el “compromiso” es más por capacidad y WIP que por caja de tiempo. |
| **Cambios mid-sprint** | Se desaconseja cambiar el alcance del sprint en curso; los cambios entran al backlog para el siguiente. | Se pueden repriorizar o entrar tareas nuevas respetando límites de WIP y políticas acordadas. |
| **Métricas / foco** | Velocidad, burndown, incremento al cierre del sprint. | Tiempo de ciclo, throughput, cuellos de botella en el tablero. |
| **Ceremonias** | Eventos prescritos (planificación, daily, review, retrospectiva). | Mínimo prescrito; reuniones según necesidad (p. ej. replenishment, retrospectivas de flujo). |

Ambos pueden usar tableros visuales; la diferencia no es solo el tablero, sino **reglas de ritmo, roles y cambio**.

---

## En qué situaciones usar cada metodología

### Scrum suele encajar bien cuando:

- El producto se evoluciona por **entregas discretas** que quieren mostrarse a stakeholders al cerrar cada ciclo.
- El equipo y la organización valoran **ritmo estable**, **roles claros** y **ceremonias** que estructuran la colaboración.
- Hay un **Product Owner** disponible para priorizar y aclarar requisitos.
- El dominio permite **planificar** un bloque de trabajo de 1–4 semanas con objetivo común.

### Kanban suele encajar bien cuando:

- Hay **mucho trabajo entrante impredecible** (incidencias, peticiones variadas, soporte).
- Se necesita **flexibilidad** para cambiar prioridades sin esperar al siguiente sprint.
- El objetivo es **reducir tiempo de espera** y suavizar cuellos de botella en un flujo ya existente.
- El equipo prefiere **evolucionar el proceso** sin adoptar todo el ritual de Scrum de golpe.

### Nota práctica

Muchas organizaciones usan **híbridos** (por ejemplo Scrum con límites WIP en el tablero, o Kanban con retrospectivas periódicas). Lo importante es que el marco sirva al **flujo de valor** y a la **realidad del equipo**, no al revés.

---



