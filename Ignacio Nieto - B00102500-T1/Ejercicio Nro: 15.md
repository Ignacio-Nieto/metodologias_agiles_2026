# Ejercicio 15

## Plan de trabajo basado en Scrum

## Tema del proyecto

Sistema informático para la gestión de presupuestos de construcción de galpones.

---

# 1. Objetivo del plan de trabajo

El objetivo del plan de trabajo es organizar al equipo mediante la metodología **Scrum** para desarrollar historias de usuario relacionadas con un sistema de presupuesto para construcción de galpones.

El sistema permitirá crear presupuestos detallados, incluir etapas de construcción, realizar seguimiento del presupuesto, generar informes y visualizar el estado económico de la obra.

---

# 2. Equipo Scrum

El equipo estará formado por entre 3 y 5 integrantes.

## Roles propuestos

| Rol Scrum            | Responsable          | Función                                                                                      |
| -------------------- | -------------------- | -------------------------------------------------------------------------------------------- |
| Product Owner        | Integrante 1         | Define prioridades, representa las necesidades del cliente y valida las historias de usuario |
| Scrum Master         | Integrante 2         | Facilita el trabajo del equipo, elimina obstáculos y controla que se respete Scrum           |
| Equipo de desarrollo | Integrantes 3, 4 y 5 | Analizan, redactan, revisan y presentan las historias de usuario                             |

---

# 3. Producto a desarrollar

## Nombre del sistema

**GalpónPresupuestos**

## Descripción

GalpónPresupuestos será un sistema web destinado a empresas constructoras que necesitan elaborar, controlar y presentar presupuestos para la construcción de galpones.

El sistema permitirá:

* Cargar datos del cliente.
* Registrar características del galpón.
* Crear presupuestos por etapas.
* Calcular materiales, mano de obra y costos adicionales.
* Realizar seguimiento del presupuesto durante la obra.
* Generar informes para el cliente.

---

# 4. Product Backlog inicial

El **Product Backlog** es la lista de funcionalidades o necesidades del sistema.

| Prioridad | Ítem del backlog                  | Descripción                                             |
| --------- | --------------------------------- | ------------------------------------------------------- |
| Alta      | Crear presupuesto                 | Permite generar un nuevo presupuesto para un galpón     |
| Alta      | Cargar datos del cliente          | Registra información básica del cliente                 |
| Alta      | Agregar etapas de construcción    | Permite dividir el presupuesto en etapas                |
| Alta      | Calcular costo total              | Calcula el total del presupuesto                        |
| Media     | Generar informe                   | Permite generar un informe del presupuesto              |
| Media     | Consultar presupuestos            | Permite buscar presupuestos ya cargados                 |
| Media     | Actualizar estado del presupuesto | Permite indicar si está pendiente, aprobado o rechazado |
| Baja      | Exportar presupuesto a PDF        | Permite descargar el presupuesto                        |
| Baja      | Registrar observaciones           | Permite agregar notas adicionales                       |

---

# 5. Sprint propuesto

## Duración del Sprint

Se propone realizar un Sprint de **1 semana**.

## Objetivo del Sprint

Crear al menos **3 historias de usuario claras, concisas y completas**, con sus respectivos criterios de aceptación, para el sistema de presupuesto de construcción de galpones.

---

# 6. Sprint Planning

En la reunión de planificación, el equipo selecciona los ítems más importantes del Product Backlog.

## Historias seleccionadas para el Sprint

1. Crear un presupuesto de construcción.
2. Agregar etapas al presupuesto.
3. Generar informe del presupuesto.

---

# 7. Historias de usuario

## Historia de usuario 1: Crear presupuesto

**Como** empleado administrativo de la empresa constructora,
**quiero** crear un presupuesto para la construcción de un galpón,
**para** estimar el costo total de la obra y presentarlo al cliente.

### Criterios de aceptación

* El sistema debe permitir ingresar los datos del cliente.
* El sistema debe permitir ingresar las características del galpón.
* El sistema debe permitir cargar medidas como largo, ancho y altura.
* El sistema debe permitir ingresar el tipo de estructura.
* El sistema debe guardar el presupuesto con estado “Pendiente”.
* El sistema debe mostrar un mensaje de confirmación al guardar.

### Ejemplo de datos

```text
Cliente: Metalúrgica Norte
Largo: 30 metros
Ancho: 15 metros
Altura: 6 metros
Tipo de estructura: Metálica
Estado: Pendiente
```

---

## Historia de usuario 2: Agregar etapas de construcción

**Como** encargado de obra,
**quiero** dividir el presupuesto en etapas de construcción,
**para** poder calcular y controlar los costos de cada parte del proyecto.

### Criterios de aceptación

* El sistema debe permitir agregar una o más etapas al presupuesto.
* Cada etapa debe tener nombre, descripción y costo estimado.
* El sistema debe permitir etapas como movimiento de suelo, estructura, cerramientos, techo, instalación eléctrica y terminaciones.
* El sistema debe calcular el subtotal de cada etapa.
* El sistema debe actualizar el costo total del presupuesto al agregar una etapa.
* El sistema debe permitir modificar o eliminar etapas antes de aprobar el presupuesto.

### Ejemplo de etapas

```text
Etapa 1: Movimiento de suelo
Etapa 2: Estructura metálica
Etapa 3: Cerramientos laterales
Etapa 4: Cubierta de techo
Etapa 5: Instalación eléctrica
```

---

## Historia de usuario 3: Generar informe del presupuesto

**Como** gerente de la empresa constructora,
**quiero** generar un informe del presupuesto,
**para** entregárselo al cliente de forma clara y profesional.

### Criterios de aceptación

* El sistema debe mostrar los datos del cliente.
* El sistema debe mostrar las características del galpón.
* El sistema debe listar las etapas de construcción.
* El sistema debe mostrar el costo de cada etapa.
* El sistema debe mostrar el costo total del presupuesto.
* El sistema debe mostrar el estado del presupuesto.
* El informe debe poder visualizarse antes de ser enviado o impreso.

---

# 8. Tablero Scrum

Para organizar el trabajo se propone usar un tablero con las siguientes columnas:

```text
Product Backlog → Sprint Backlog → En proceso → En revisión → Terminado
```

## Tareas del Sprint

| Tarea                                 | Responsable     | Estado     |
| ------------------------------------- | --------------- | ---------- |
| Definir contexto del sistema          | Product Owner   | Terminado  |
| Redactar historia “Crear presupuesto” | Desarrollo      | En proceso |
| Redactar historia “Agregar etapas”    | Desarrollo      | En proceso |
| Redactar historia “Generar informe”   | Desarrollo      | En proceso |
| Revisar criterios de aceptación       | Scrum Master    | Pendiente  |
| Preparar presentación final           | Equipo completo | Pendiente  |

---

# 9. Daily Scrum

Durante el Sprint se realizará una reunión breve diaria.

Cada integrante responderá:

1. ¿Qué hice ayer?
2. ¿Qué voy a hacer hoy?
3. ¿Tengo algún impedimento?

## Ejemplo

```text
Ayer redacté la historia de usuario para crear presupuesto.
Hoy voy a revisar los criterios de aceptación.
No tengo impedimentos.
```

---

# 10. Sprint Review

Al finalizar el Sprint, el equipo presentará las historias de usuario al resto de la clase.

En la presentación se explicará:

* Contexto del sistema.
* Necesidad del cliente.
* Historias de usuario seleccionadas.
* Criterios de aceptación.
* Por qué esas historias aportan valor al sistema.

---

# 11. Sprint Retrospective

Luego de la presentación, el equipo realizará una retrospectiva para mejorar.

## Preguntas de retrospectiva

* ¿Qué hicimos bien?
* ¿Qué podríamos mejorar?
* ¿Qué problemas tuvimos al redactar las historias?
* ¿Los criterios de aceptación fueron claros?
* ¿Todos participaron en la actividad?

## Mejoras posibles

| Problema detectado                         | Acción de mejora                 |
| ------------------------------------------ | -------------------------------- |
| Historias demasiado generales              | Hacerlas más concretas           |
| Criterios de aceptación incompletos        | Agregar condiciones verificables |
| Falta de participación de algún integrante | Distribuir mejor las tareas      |
| Dudas sobre el alcance del sistema         | Consultar al Product Owner       |

---

# 12. Definition of Done

Una historia de usuario se considerará terminada cuando:

* Está redactada en formato “Como…, quiero…, para…”.
* Tiene título claro.
* Tiene descripción comprensible.
* Tiene criterios de aceptación verificables.
* Está relacionada con el sistema de presupuesto de galpones.
* Fue revisada por el equipo.
* Puede ser presentada oralmente al resto de la clase.

---

# 13. Conclusión

Mediante Scrum, el equipo puede organizar el trabajo de forma colaborativa, dividiendo la actividad en tareas pequeñas y priorizadas. El Product Backlog permite identificar las funcionalidades del sistema, el Sprint permite enfocarse en un objetivo concreto y las reuniones Scrum ayudan a revisar el avance y mejorar la comunicación.

Las historias de usuario creadas permiten representar necesidades reales de un sistema de presupuesto de construcción de galpones, considerando funcionalidades como la creación de presupuestos, la división por etapas y la generación de informes.
