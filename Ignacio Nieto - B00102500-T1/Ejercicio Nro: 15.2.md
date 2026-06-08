# Ejercicios de Scrum

# EJERCICIOS CONCEPTUALES

---

# Ejercicio 1: Identificación de Roles

## Objetivo

Reconocer los roles de Scrum y sus responsabilidades.

## Consigna

Para cada situación, se identifica qué rol de Scrum debería actuar y se justifica la respuesta.

---

## a) Un stakeholder quiere agregar una nueva funcionalidad urgente durante el Sprint

**Rol que debería actuar:** Product Owner.

**Justificación:**

El Product Owner es el responsable de gestionar el Product Backlog y ordenar las prioridades del producto. Si un stakeholder quiere agregar una funcionalidad urgente, no debería interrumpir directamente al Development Team durante el Sprint.

El Product Owner debe analizar si esa funcionalidad realmente aporta valor, evaluar su urgencia y decidir si se incorpora al Product Backlog. En Scrum, durante un Sprint no se deberían agregar cambios que afecten el Sprint Goal, salvo que sea algo realmente crítico.

---

## b) El equipo no entiende claramente un requisito del Product Backlog

**Rol que debería actuar:** Product Owner.

**Justificación:**

El Product Owner es quien debe aclarar las historias de usuario, requisitos, prioridades y criterios de aceptación. Si el equipo de desarrollo no entiende un requisito, debe consultar al Product Owner para evitar desarrollar algo incorrecto.

También puede participar el Scrum Master facilitando la comunicación, pero la responsabilidad principal de explicar el valor y el alcance del ítem corresponde al Product Owner.

---

## c) Hay conflictos entre desarrolladores sobre la implementación técnica

**Rol que debería actuar:** Development Team, con ayuda del Scrum Master.

**Justificación:**

El Development Team es responsable de decidir cómo implementar técnicamente las funcionalidades. Por lo tanto, el equipo debe conversar y llegar a un acuerdo técnico.

Si el conflicto afecta el trabajo o la colaboración, el Scrum Master debe intervenir como facilitador, ayudando a resolver el problema y promoviendo una comunicación sana dentro del equipo.

---

## d) Se necesita decidir el orden de prioridad de las User Stories

**Rol que debería actuar:** Product Owner.

**Justificación:**

El Product Owner es responsable de ordenar y priorizar el Product Backlog. Su tarea es decidir qué historias de usuario tienen mayor valor para el cliente o negocio.

El equipo puede aportar información técnica, como complejidad o riesgos, pero la decisión final de prioridad corresponde al Product Owner.

---

## e) El equipo está teniendo problemas para cumplir con la Definition of Done

**Rol que debería actuar:** Development Team y Scrum Master.

**Justificación:**

El Development Team es responsable de construir incrementos que cumplan con la Definition of Done. Si no lo logra, debe revisar su forma de trabajo, sus tareas y la calidad de lo entregado.

El Scrum Master debe ayudar al equipo a detectar impedimentos, mejorar el proceso y respetar las reglas de Scrum.

---

# Ejercicio 2: Artefactos de Scrum

## Objetivo

Comprender el propósito y contenido de cada artefacto.

| Artefacto       | ¿Qué SÍ contiene?                                                                                                                                                                        | ¿Qué NO debería contener?                                                                                                                                                                            |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Product Backlog | Lista priorizada de funcionalidades, mejoras, errores, requisitos técnicos e historias de usuario del producto. También puede incluir criterios de aceptación, estimaciones y prioridad. | No debería contener tareas técnicas demasiado detalladas del Sprint, decisiones internas del equipo o elementos que no aporten valor al producto. Tampoco debería estar desordenado o sin prioridad. |
| Sprint Backlog  | Historias seleccionadas para el Sprint, tareas necesarias para completarlas, objetivo del Sprint y plan de trabajo del Development Team.                                                 | No debería contener historias no comprometidas para el Sprint, pedidos externos agregados sin análisis ni tareas que no estén relacionadas con el Sprint Goal.                                       |
| Increment       | Resultado funcional y terminado del Sprint. Incluye las funcionalidades completadas que cumplen con la Definition of Done.                                                               | No debería contener funcionalidades incompletas, código sin probar, tareas a medio hacer o elementos que no cumplan con la Definition of Done.                                                       |

---

# Ejercicio 3: Eventos de Scrum - Verdadero o Falso

## 1. La Sprint Planning puede durar hasta 8 horas para un Sprint de 4 semanas

**Respuesta:** Verdadero.

**Justificación:**

Para un Sprint de un mes o 4 semanas, la Sprint Planning puede durar hasta 8 horas. Si el Sprint es más corto, normalmente la duración también es menor.

---

## 2. En la Daily Scrum cada miembro debe reportar al Scrum Master

**Respuesta:** Falso.

**Justificación:**

En la Daily Scrum los miembros del Development Team no reportan al Scrum Master. La reunión es para que el equipo inspeccione el avance hacia el Sprint Goal y coordine el trabajo del día.

El Scrum Master puede participar, pero no es una reunión de reporte jerárquico.

---

## 3. La Sprint Review es solo para demostrar el producto al Product Owner

**Respuesta:** Falso.

**Justificación:**

La Sprint Review no es solamente para el Product Owner. También pueden participar stakeholders, usuarios, cliente y equipo Scrum.

El objetivo es inspeccionar el incremento, recibir feedback y adaptar el Product Backlog si es necesario.

---

## 4. En la Sprint Retrospective se puede modificar el Sprint Backlog

**Respuesta:** Falso.

**Justificación:**

La Sprint Retrospective se realiza al finalizar el Sprint. En ese momento el Sprint Backlog del Sprint que terminó ya no se modifica.

Lo que sí puede hacerse es identificar mejoras para aplicar en el próximo Sprint.

---

## 5. El Sprint puede cancelarse solo por decisión del Development Team

**Respuesta:** Falso.

**Justificación:**

El Sprint puede cancelarse solamente por decisión del Product Owner, generalmente si el Sprint Goal deja de tener sentido o cambia una condición importante del negocio.

---

# EJERCICIOS DE APLICACIÓN

---

# Ejercicio 4: Creación de Product Backlog

## Contexto

Una empresa quiere desarrollar una aplicación móvil para delivery de comida.

## Product Backlog con User Stories

| Prioridad | User Story                                                                                                 | Story Points |
| --------- | ---------------------------------------------------------------------------------------------------------- | ------------ |
| 1         | Como usuario, quiero registrarme en la aplicación para poder realizar pedidos de comida.                   | 3            |
| 2         | Como usuario, quiero buscar restaurantes cercanos para elegir dónde comprar comida.                        | 5            |
| 3         | Como usuario, quiero agregar productos al carrito para armar mi pedido.                                    | 5            |
| 4         | Como usuario, quiero pagar mi pedido con tarjeta o medios digitales para finalizar la compra.              | 8            |
| 5         | Como usuario, quiero ver el estado de mi pedido para saber si está en preparación o camino a mi domicilio. | 8            |
| 6         | Como restaurante, quiero recibir pedidos en tiempo real para prepararlos rápidamente.                      | 13           |
| 7         | Como repartidor, quiero ver la dirección de entrega para llevar el pedido al cliente.                      | 5            |
| 8         | Como administrador, quiero generar reportes de ventas para analizar el rendimiento de la aplicación.       | 13           |

---

## Criterios de aceptación de las 3 historias de mayor prioridad

## Historia 1: Registro de usuario

**User Story:**

Como usuario, quiero registrarme en la aplicación para poder realizar pedidos de comida.

**Criterios de aceptación:**

* El sistema debe permitir ingresar nombre, email, contraseña y teléfono.
* El sistema debe validar que el email tenga formato correcto.
* El sistema debe validar que la contraseña tenga al menos 6 caracteres.
* El sistema no debe permitir registrar dos usuarios con el mismo email.
* Al finalizar el registro, el sistema debe mostrar un mensaje de confirmación.

---

## Historia 2: Buscar restaurantes cercanos

**User Story:**

Como usuario, quiero buscar restaurantes cercanos para elegir dónde comprar comida.

**Criterios de aceptación:**

* El sistema debe mostrar una lista de restaurantes disponibles.
* El usuario debe poder buscar por nombre del restaurante.
* El usuario debe poder filtrar por tipo de comida.
* El sistema debe mostrar información básica: nombre, dirección, calificación y tiempo estimado de entrega.
* Si no hay restaurantes disponibles, debe mostrar un mensaje claro.

---

## Historia 3: Agregar productos al carrito

**User Story:**

Como usuario, quiero agregar productos al carrito para armar mi pedido.

**Criterios de aceptación:**

* El usuario debe poder seleccionar un producto de un restaurante.
* El sistema debe permitir indicar la cantidad.
* El sistema debe agregar el producto al carrito.
* El sistema debe calcular el subtotal.
* El usuario debe poder eliminar productos del carrito.
* El usuario debe poder modificar la cantidad antes de confirmar el pedido.

---

# Ejercicio 5: Planning Poker Simulation

## Objetivo

Practicar la estimación colaborativa mediante Planning Poker.

## User Stories a estimar

| User Story                                                        | Estimación propuesta | Justificación                                                                                                                     |
| ----------------------------------------------------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Como usuario, quiero registrarme con email y contraseña           | 3 puntos             | Es una funcionalidad simple, común y de baja complejidad. Requiere formulario, validaciones básicas y guardado de usuario.        |
| Como usuario, quiero recuperar mi contraseña olvidada             | 5 puntos             | Tiene complejidad media porque requiere envío de email, generación de token o enlace de recuperación y validaciones de seguridad. |
| Como administrador, quiero generar reportes de ventas mensuales   | 8 puntos             | Requiere consultas, filtros por fecha, cálculos y posiblemente gráficos o exportación. Tiene más lógica que un formulario simple. |
| Como usuario, quiero pagar con tarjeta de crédito de forma segura | 13 puntos            | Es una funcionalidad compleja porque implica integración con pasarela de pagos, seguridad, validaciones y manejo de errores.      |

---

## Simulación del proceso

### Primera ronda de estimación

| Historia                        | Estimaciones del equipo | Resultado                                        |
| ------------------------------- | ----------------------- | ------------------------------------------------ |
| Registro con email y contraseña | 3, 3, 5, 3              | Se discute la diferencia y se acuerda 3          |
| Recuperar contraseña            | 5, 5, 8, 5              | Se discute el envío de email y se acuerda 5      |
| Reportes mensuales              | 8, 8, 13, 8             | Se aclara alcance del reporte y se acuerda 8     |
| Pago con tarjeta                | 13, 21, 13, 13          | Se considera integración externa y se acuerda 13 |

---

## Conclusión

El Planning Poker permite que todo el equipo participe en la estimación. Cuando aparecen diferencias importantes, se discuten los motivos y se llega a un consenso más realista.

---

# Ejercicio 6: Sprint Planning Práctico

## Contexto

Sprint de 2 semanas.
Equipo de 5 desarrolladores.
Velocidad promedio: 40 Story Points.

## Product Backlog disponible

| Historia   | Puntos | Prioridad |
| ---------- | ------ | --------- |
| Historia A | 8      | Alta      |
| Historia B | 13     | Alta      |
| Historia C | 5      | Media     |
| Historia D | 8      | Media     |
| Historia E | 3      | Baja      |
| Historia F | 21     | Media     |

---

## 1. Selección de historias para el Sprint Backlog

Se seleccionan historias hasta acercarse a la velocidad del equipo, sin superar demasiado los 40 puntos.

| Historia seleccionada | Puntos | Prioridad |
| --------------------- | ------ | --------- |
| Historia A            | 8      | Alta      |
| Historia B            | 13     | Alta      |
| Historia C            | 5      | Media     |
| Historia D            | 8      | Media     |
| Historia E            | 3      | Baja      |

**Total:** 37 puntos.

No se selecciona la Historia F porque tiene 21 puntos y haría que el Sprint supere demasiado la velocidad promedio del equipo.

---

## 2. Descomposición de la historia de mayor prioridad

Se toma como historia de mayor prioridad la **Historia A**.

## Historia A: Registro de usuario

**Tareas específicas:**

| Tarea                                 | Responsable      |
| ------------------------------------- | ---------------- |
| Diseñar pantalla de registro          | Frontend         |
| Crear modelo de usuario               | Backend          |
| Crear endpoint para registrar usuario | Backend          |
| Validar email y contraseña            | Backend          |
| Conectar formulario con backend       | Frontend         |
| Guardar usuario en base de datos      | Backend          |
| Crear pruebas unitarias               | Tester / Backend |
| Probar registro desde la interfaz     | Tester           |
| Revisar criterios de aceptación       | Product Owner    |

---

## 3. Sprint Goal

El objetivo del Sprint es:

**Desarrollar las funcionalidades iniciales del sistema que permitan al usuario registrarse, acceder a funcionalidades básicas y avanzar en las historias principales de mayor prioridad.**

Otra forma más concreta:

**Al finalizar el Sprint, el sistema deberá permitir registrar usuarios y completar las funcionalidades principales seleccionadas, cumpliendo con los criterios de aceptación definidos.**

---

## 4. Posibles impedimentos y riesgos

| Riesgo o impedimento                        | Impacto                        | Acción preventiva                               |
| ------------------------------------------- | ------------------------------ | ----------------------------------------------- |
| Requisitos poco claros                      | Puede generar retrabajo        | Consultar al Product Owner antes de desarrollar |
| Historia B más compleja de lo estimado      | Puede afectar el Sprint Goal   | Dividir la historia en tareas más pequeñas      |
| Falta de disponibilidad de un desarrollador | Reduce la capacidad del equipo | Reorganizar tareas                              |
| Errores de integración                      | Puede retrasar pruebas         | Integrar frecuentemente                         |
| Dependencias técnicas                       | Puede bloquear una tarea       | Identificar dependencias desde la planificación |

---

# Ejercicio 7: Simulación de Daily Scrum

## Objetivo

Practicar la dinámica de la reunión diaria.

## Escenario

Día 5 de un Sprint de 10 días.
Participan 5 desarrolladores y un Scrum Master.

---

## Participantes

| Participante | Rol                      |
| ------------ | ------------------------ |
| Integrante 1 | Scrum Master             |
| Integrante 2 | Desarrollador Backend    |
| Integrante 3 | Desarrollador Frontend   |
| Integrante 4 | Tester                   |
| Integrante 5 | Desarrollador Full Stack |
| Integrante 6 | Desarrollador Backend    |

---

## Simulación de respuestas

## Desarrollador 1

**¿Qué hice ayer?**
Terminé la tarea de login.

**¿Qué haré hoy?**
Hoy trabajaré en el registro de usuarios.

**¿Qué impedimentos tengo?**
No tengo impedimentos.

---

## Desarrollador 2

**¿Qué hice ayer?**
Ayer tuve problemas con la base de datos.

**¿Qué haré hoy?**
Hoy intentaré avanzar con la conexión entre el backend y la base de datos.

**¿Qué impedimentos tengo?**
Necesito ayuda del DBA para revisar la configuración.

---

## Desarrollador 3

**¿Qué hice ayer?**
Completé las pruebas unitarias.

**¿Qué haré hoy?**
Hoy empiezo con las pruebas de integración.

**¿Qué impedimentos tengo?**
No tengo impedimentos.

---

## Desarrollador 4

**¿Qué hice ayer?**
Ayer avancé con la integración del sistema de pagos.

**¿Qué haré hoy?**
Hoy continuaré con la pantalla de pago.

**¿Qué impedimentos tengo?**
Estoy bloqueado esperando la API del sistema de pagos.

---

## Desarrollador 5

**¿Qué hice ayer?**
Terminé antes de lo esperado la tarea asignada.

**¿Qué haré hoy?**
Puedo ayudar a otro integrante del equipo.

**¿Qué impedimentos tengo?**
No tengo impedimentos.

---

## Acciones del Scrum Master

| Impedimento                | Acción del Scrum Master                                             |
| -------------------------- | ------------------------------------------------------------------- |
| Problema con base de datos | Contactar al DBA y coordinar ayuda                                  |
| Espera de API de pagos     | Consultar fecha de disponibilidad y buscar una alternativa temporal |
| Integrante libre           | Reasignarlo para ayudar en tareas bloqueadas o atrasadas            |

---

# Ejercicio 8: Sprint Review y Retrospective

## Parte A - Sprint Review

## Situación

El equipo completó 35 de 40 Story Points comprometidos.

## Duración

2 horas.

---

## Agenda de la Sprint Review

| Tiempo     | Actividad                                  |
| ---------- | ------------------------------------------ |
| 10 minutos | Bienvenida y objetivo de la reunión        |
| 15 minutos | Presentación del Sprint Goal               |
| 30 minutos | Demostración de funcionalidades terminadas |
| 20 minutos | Presentación de métricas                   |
| 25 minutos | Feedback de stakeholders                   |
| 10 minutos | Revisión de historias no completadas       |
| 10 minutos | Próximos pasos                             |
| 10 minutos | Cierre de la reunión                       |

---

## Métricas a presentar

| Métrica                    | Resultado |
| -------------------------- | --------- |
| Story Points comprometidos | 40        |
| Story Points completados   | 35        |
| Porcentaje de cumplimiento | 87,5%     |
| Historias completadas      | 4 de 5    |
| Historias no completadas   | 1         |
| Defectos encontrados       | 3         |
| Defectos corregidos        | 2         |
| Tareas bloqueadas          | 2         |

---

## Preguntas para los stakeholders

* ¿Las funcionalidades entregadas cumplen con sus expectativas?
* ¿Qué cambios o mejoras sugieren?
* ¿Hay alguna funcionalidad que debería priorizarse para el próximo Sprint?
* ¿El producto entregado aporta valor al negocio?
* ¿Algún requisito cambió desde la última reunión?

---

## Plan para historias no completadas

La historia no completada no se considera terminada y no forma parte del Increment.

Acciones:

1. Revisar qué faltó para completarla.
2. Identificar si hubo problemas de estimación.
3. Dividirla en tareas más pequeñas si es necesario.
4. Volver a colocarla en el Product Backlog.
5. El Product Owner decidirá si se prioriza para el próximo Sprint.

---

## Parte B - Sprint Retrospective

## Técnica utilizada: Start, Stop, Continue

---

## Start - Qué debe empezar a hacer el equipo

* Empezar a dividir mejor las tareas grandes.
* Empezar a detectar riesgos al inicio del Sprint.
* Empezar a registrar impedimentos apenas aparecen.
* Empezar a validar cambios de requisitos con el Product Owner antes de trabajar en ellos.
* Empezar a revisar estimaciones cuando una tarea parece demasiado grande.

---

## Stop - Qué debe dejar de hacer el equipo

* Dejar de aceptar cambios de último momento sin analizarlos.
* Dejar de trabajar en tareas poco claras.
* Dejar de depender de una sola persona para tareas críticas.
* Dejar de esperar al final del Sprint para probar.
* Dejar de asumir que una tarea está terminada sin revisar la Definition of Done.

---

## Continue - Qué debe continuar haciendo el equipo

* Continuar mejorando la colaboración entre frontend y backend.
* Continuar realizando reuniones diarias breves.
* Continuar revisando el avance del Sprint.
* Continuar ayudándose cuando alguien queda bloqueado.
* Continuar mostrando avances funcionales a los stakeholders.

---

## Situaciones analizadas

| Situación                                      | Análisis                                               | Acción de mejora                         |
| ---------------------------------------------- | ------------------------------------------------------ | ---------------------------------------- |
| Algunas tareas tomaron más tiempo del estimado | Puede haber mala estimación o tareas demasiado grandes | Dividir tareas y revisar estimaciones    |
| Un miembro estuvo enfermo 3 días               | Afectó la capacidad del equipo                         | No depender de una sola persona          |
| Hubo cambios de último momento                 | Afectaron la planificación                             | Canalizar cambios mediante Product Owner |
| Mejoró la colaboración frontend/backend        | Fue positivo para el avance                            | Mantener esa práctica                    |

---

# Ejercicio 9: Manejo de Impedimentos

## Situación 1: El Product Owner no está disponible para aclarar dudas

**Tipo de impedimento:** Comunicación / disponibilidad.

**Estrategias de resolución:**

* Definir horarios fijos de consulta con el Product Owner.
* Documentar dudas en el Product Backlog.
* Designar un representante temporal si el Product Owner no puede asistir.

**Quién debería actuar:** Scrum Master y Product Owner.

**Plan de seguimiento:**

El Scrum Master revisará diariamente si las dudas fueron respondidas y si hay historias bloqueadas por falta de información.

---

## Situación 2: Un desarrollador senior está sobrecargado y se convierte en cuello de botella

**Tipo de impedimento:** Organización del equipo / dependencia de una persona.

**Estrategias de resolución:**

* Distribuir el conocimiento mediante pair programming.
* Reasignar tareas a otros desarrolladores.
* Documentar decisiones técnicas importantes.
* Dividir tareas complejas en partes más pequeñas.

**Quién debería actuar:** Development Team y Scrum Master.

**Plan de seguimiento:**

Revisar en la Daily Scrum si las tareas críticas siguen dependiendo de una sola persona.

---

## Situación 3: Las herramientas de desarrollo fallan constantemente

**Tipo de impedimento:** Técnico / infraestructura.

**Estrategias de resolución:**

* Reportar fallas al área técnica.
* Usar herramientas alternativas temporalmente.
* Revisar versiones, permisos y configuraciones.
* Priorizar la solución porque afecta a todo el equipo.

**Quién debería actuar:** Scrum Master, Development Team y soporte técnico.

**Plan de seguimiento:**

Registrar los incidentes y verificar si se reducen luego de aplicar las correcciones.

---

## Situación 4: Hay conflictos interpersonales en el equipo

**Tipo de impedimento:** Humano / comunicación.

**Estrategias de resolución:**

* Realizar una reunión facilitada por el Scrum Master.
* Establecer acuerdos de trabajo y comunicación.
* Separar el problema técnico del problema personal.
* Fomentar el respeto y la colaboración.

**Quién debería actuar:** Scrum Master y Development Team.

**Plan de seguimiento:**

Revisar en la retrospectiva si mejoró la comunicación y si los conflictos disminuyeron.

---

## Situación 5: Un stakeholder presiona para agregar funcionalidades no planificadas

**Tipo de impedimento:** Gestión de alcance / presión externa.

**Estrategias de resolución:**

* Derivar el pedido al Product Owner.
* Evaluar el valor de negocio de la nueva funcionalidad.
* Agregarla al Product Backlog si corresponde.
* Evitar interrumpir el Sprint actual si afecta el Sprint Goal.

**Quién debería actuar:** Product Owner y Scrum Master.

**Plan de seguimiento:**

El Product Owner revisará el pedido y decidirá si se prioriza para el próximo Sprint.

---

# Ejercicio 10: Definition of Done

## Contexto

Equipo desarrollando una aplicación web de e-commerce.

## Objetivo

Crear criterios compartidos que permitan definir cuándo una historia de usuario está realmente terminada.

---

# Definition of Done

Una historia de usuario se considera terminada cuando cumple con todos los siguientes criterios:

---

## 1. Criterios técnicos

* El código fue desarrollado y funciona correctamente.
* El código fue integrado a la rama principal del proyecto.
* No existen errores de compilación.
* No quedan comentarios innecesarios ni código duplicado.
* La funcionalidad está conectada correctamente con la base de datos o servicios necesarios.
* La funcionalidad está desplegada en un ambiente de testing.

---

## 2. Criterios de calidad

* El código fue revisado por al menos otro miembro del equipo.
* Se ejecutaron pruebas unitarias.
* Se ejecutaron pruebas de integración si corresponde.
* No se detectaron errores críticos.
* La funcionalidad cumple con los criterios de aceptación.
* El comportamiento fue probado con datos válidos e inválidos.

---

## 3. Criterios de documentación

* La historia de usuario tiene criterios de aceptación claros.
* Se documentaron decisiones técnicas importantes.
* Se actualizó la documentación técnica si hubo cambios.
* Se registraron endpoints, campos o reglas de negocio nuevas.
* Se actualizaron instrucciones de uso si la funcionalidad afecta al usuario final.

---

## 4. Criterios de validación

* El Product Owner revisó y aceptó la funcionalidad.
* La funcionalidad cumple con el objetivo de la historia.
* La funcionalidad aporta valor al producto.
* Se validó que no afecte negativamente funcionalidades existentes.
* Los stakeholders pueden visualizar la funcionalidad si corresponde.

---

## 5. Criterios de performance

* La funcionalidad responde en un tiempo aceptable.
* Las consultas a la base de datos son eficientes.
* No genera demoras importantes en la carga de la página.
* No consume recursos innecesarios.

---

## 6. Criterios de accesibilidad

* La interfaz es clara y fácil de usar.
* Los botones y formularios tienen textos comprensibles.
* Los mensajes de error son visibles y entendibles.
* La navegación puede realizarse correctamente desde distintos dispositivos.
* Se consideran contrastes, etiquetas y estructura clara en los formularios.

---

## 7. Criterios de seguridad

* Se validan los datos ingresados por el usuario.
* No se exponen datos sensibles.
* Se respetan permisos de usuario.
* Las operaciones críticas requieren autenticación.
* Se evita el ingreso de datos maliciosos.
* Los pagos y datos personales se manejan de forma segura.

