# Idea de proyecto: evaluación de rendimiento de empleados (construcción)

## Problema que intenta resolver

La empresa familiar de **construcción** paga a sus empleados de una forma concreta, pero **no tiene una forma clara y repetible** de contrastar ese coste con el **valor económico** que aporta el trabajo de cada persona en un periodo determinado. Sin esa visión, es difícil saber si el gasto en mano de obra **se corresponde** con el resultado (obras entregadas, márgenes, productividad percibida, etc.).

La aplicación intenta resolver ese vacío actuando como una **calculadora de apoyo a la decisión**: centraliza **empleados**, **horas trabajadas** y **parámetros de cálculo** (por ejemplo porcentajes o ratios acordados con el negocio) para **estimar o comparar el rendimiento económico** frente al esfuerzo registrado y ayudar a **valorar** si alguien encaja como **buen activo** para la empresa, siempre dentro de los límites de lo que se pueda medir con los datos disponibles.

> **Nota:** Periodo de análisis (diario / semanal / mensual), fórmula exacta y reglas de negocio pueden seguir en definición tras reunión con el cliente.

---

## Usuario objetivo

| Perfil | Descripción |
|--------|-------------|
| **Principal** | El **dueño o responsable** de la empresa de construcción (o quien delegue en gestión de personal y costes) que necesita una herramienta **sencilla**, en **un solo lugar**, para registrar horas y obtener **indicadores comparativos** sin depender de hojas de cálculo dispersas. |
| **Secundario** | Cualquier **administrativo** autorizado que cargue datos de jornadas y mantenga la ficha de empleados, si el cliente decide separar roles más adelante. |

El usuario no tiene por qué ser técnico: la interfaz debe priorizar **claridad** sobre complejidad estadística.

---

## Stack de persistencia previsto (sin base de datos propia)

Para la primera versión **no es obligatorio** usar servidor con base de datos:

- **LocalStorage del navegador** para guardar empleados, registros de horas y configuración local del cliente.
- **API** (endpoints propios o servicios públicos de demo) para **generar o cargar datos de ejemplo**, facilitar pruebas y demostraciones sin introducir datos reales a mano.

Esto reduce coste e infraestructura y encaja con un uso **táctico en oficina o obra** desde un navegador.

---

## Funcionalidades principales

1. **Alta, edición y listado de empleados** (datos mínimos acordados con el cliente: nombre, tipo de contrato o tarifa si aplica, etc.).
2. **Registro de horas trabajadas** por empleado y por fecha (la granularidad final —día / semana / mes— se alineará con el cliente).
3. **Parámetros de cálculo configurables** (por ejemplo porcentajes, coste hora objetivo o factores definidos en reunión) para no hardcodear reglas de negocio.
4. **Vista de resultado / “calculadora”** que combine horas, coste estimado y criterios acordados para mostrar un **indicador de rendimiento** o comparación frente a un umbral.
5. **Persistencia local** con LocalStorage: los datos sobreviven al cerrar el navegador en ese equipo.
6. **Carga o generación de datos de ejemplo** vía API para vaciar o poblar el estado y probar flujos sin captura manual larga.

---

## Funcionalidades opcionales

1. **Exportación** a CSV o PDF de resúmenes por empleado o por periodo.
2. **Filtros por rango de fechas** y comparación entre dos periodos consecutivos.
3. **Notas o etiquetas** por empleado (obra asignada, especialidad) si el cliente lo necesita.
4. **Modo oscuro** o ajustes de accesibilidad (tamaño de texto, contraste).
5. **Recordatorios** (solo UI) para “falta registrar horas esta semana”, sin obligar a notificaciones push.
6. **Importación** desde un CSV plantilla si en el futuro migran desde Excel.

---

## Posibles mejoras futuras

- Definir con el cliente **indicadores de negocio** más allá de horas (metros cuadrados, partidas de obra, facturación asignada) si los datos existen.
- **Historial de versiones** de reglas de cálculo para auditar cambios de porcentajes.
- **Multi-usuario** con autenticación si varias personas gestionan datos y se requiere trazabilidad.
- **Sincronización en la nube** o app móvil nativa si el registro debe hacerse en obra con poca conectividad.
- Integración con **software de nóminas** o ERP cuando el volumen y la formalidad lo justifiquen.

---

## Valoración de una posible base de datos (cuando aún no hay consultas definidas)

Hoy **no conoces las consultas concretas** que hará el negocio; aun así se puede anticipar el **tipo** de necesidades que suelen aparecer y si merece invertir en BD.

**Cuándo LocalStorage (y quizá un JSON estático en API) sigue siendo suficiente**

- Pocos empleados y pocos meses de historial.
- Un solo dispositivo o navegador por responsable.
- Información **no crítica** desde el punto de vista legal (la nómina oficial sigue en otro sistema).
- No necesitas informes complejos cruzando años, obras y costes reales desde servidor.

**Cuándo empezar a plantear base de datos (relacional o documental)**

- **Varios usuarios** escribiendo al mismo tiempo o acceso desde PC y tablet con **los mismos datos**.
- **Consultas recurrentes** que hoy imaginas como: totales por empleado y mes, ranking, medias móviles, comparación obra vs obra, detección de anomalías (picos de horas sin output esperado).
- **Respaldo centralizado**, auditoría y permisos.
- Volumen que haga **lenta o frágil** la app si todo vive en el navegador.

**Enfoque pragmático sin conocer aún el SQL exacto**

- Empieza modelando **entidades mentales**: `Empleado`, `RegistroHoras`, `Periodo`, `ParametroCalculo`, `ResultadoEvaluacion`. Casi cualquier BD relacional (PostgreSQL, SQLite con backend ligero) encajará con consultas del estilo *agrupar por empleado y mes*, *sumar horas*, *filtrar por fechas*.
- Si más adelante las consultas son sobre todo **documentos por empleado** sin joins complejos, una **BD documental** también puede valer; si prevés **reportes tabulares y integridad referencial**, lo habitual es **SQL relacional**.

**Conclusión:** para prototipo y uso interno acotado, **LocalStorage + API de demo** es coherente. Valora BD cuando tengas claros **quién escribe**, **desde cuántos sitios** y **qué preguntas** quieres que la app responda en una sola pantalla o informe; en ese momento las “consultas específicas” se deducen del negocio y el modelo de datos casi se escribe solo.

---

*Documento vivo: actualizar tras reuniones con el cliente.*
