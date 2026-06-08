# Ejercicio 13 - Extreme Programming XP

## 1. ¿Qué es Extreme Programming XP y cuál es su objetivo principal dentro de las metodologías ágiles?

**Extreme Programming**, también conocido como **XP**, es una metodología ágil de desarrollo de software que busca mejorar la calidad del producto y la capacidad de respuesta del equipo frente a los cambios del cliente.

Su objetivo principal es desarrollar software de manera rápida, flexible y con alta calidad, trabajando en ciclos cortos, con mucha comunicación, pruebas constantes y participación activa del cliente.

XP se enfoca en entregar software funcionando frecuentemente, recibir retroalimentación y mejorar el producto de forma continua.

---

## 2. ¿Cuáles son los cinco valores principales de XP? Explicá brevemente cada uno.

Los cinco valores principales de XP son:

### Comunicación

El equipo debe mantener una comunicación constante entre desarrolladores, cliente y demás participantes del proyecto. Esto evita malentendidos y ayuda a resolver problemas rápidamente.

### Simplicidad

Se busca desarrollar solo lo necesario, evitando agregar funcionalidades innecesarias o diseños demasiado complejos.

### Retroalimentación

El equipo recibe comentarios constantes del cliente, de las pruebas y del propio software funcionando. Esto permite corregir errores y mejorar el producto.

### Coraje

El equipo debe animarse a cambiar, corregir, refactorizar código y aceptar que algunas decisiones pueden modificarse si el proyecto lo necesita.

### Respeto

Todos los integrantes del equipo deben valorar el trabajo de los demás, colaborar y asumir responsabilidades de forma conjunta.

---

## 3. ¿Por qué XP considera que las pruebas son un elemento fundamental del desarrollo de software?

XP considera que las pruebas son fundamentales porque permiten detectar errores temprano y asegurar que el software funcione correctamente.

En XP las pruebas no se dejan solo para el final, sino que forman parte del desarrollo diario. Esto ayuda a:

* Evitar errores acumulados.
* Mejorar la calidad del código.
* Dar seguridad al hacer cambios.
* Comprobar que cada funcionalidad cumple con lo pedido.
* Reducir costos de corrección.

Por ejemplo, si se desarrolla una función para agregar productos a un inventario, se pueden crear pruebas para verificar que no se acepten productos sin nombre, con precio negativo o con código repetido.

---

## 4. ¿Qué es Test Driven Development TDD y cómo se relaciona con XP?

**Test Driven Development**, o **TDD**, significa desarrollo guiado por pruebas.

Consiste en escribir primero una prueba, luego desarrollar el código necesario para que esa prueba se cumpla y finalmente mejorar el código sin cambiar su funcionamiento.

El ciclo de TDD es:

1. Escribir una prueba que inicialmente falla.
2. Programar el código mínimo para que la prueba pase.
3. Refactorizar el código para mejorarlo.

TDD se relaciona con XP porque XP le da mucha importancia a las pruebas automáticas y a la calidad del software. TDD ayuda a construir software más confiable, mantenible y fácil de modificar.

---

## 5. ¿En qué consiste la práctica de Pair Programming? Mencioná dos ventajas y una posible dificultad.

**Pair Programming**, o programación en pareja, consiste en que dos programadores trabajen juntos en una misma computadora.

Uno escribe el código, llamado **driver**, y el otro revisa, analiza y propone mejoras, llamado **observer** o **navigator**. Luego pueden intercambiar roles.

### Ventajas

Una ventaja es que mejora la calidad del código, porque dos personas revisan la solución mientras se desarrolla.

Otra ventaja es que favorece el aprendizaje entre compañeros, ya que ambos comparten conocimientos, formas de resolver problemas y buenas prácticas.

### Posible dificultad

Una dificultad es que puede generar incomodidad o pérdida de ritmo si los integrantes no se comunican bien o tienen estilos de trabajo muy distintos.

---

## 6. ¿Qué son las historias de usuario en XP y por qué se prefieren frente a una especificación extensa de requisitos?

Las historias de usuario son descripciones simples y breves de una necesidad del usuario.

Generalmente se escriben con una estructura similar a:

“Como usuario, quiero realizar una acción para obtener un beneficio”.

Por ejemplo:

“Como encargado de inventario, quiero agregar nuevos productos para mantener actualizado el stock”.

XP prefiere las historias de usuario porque son más simples, fáciles de entender y permiten conversar con el cliente. En lugar de hacer documentos extensos desde el inicio, se trabaja con necesidades concretas que pueden cambiar y mejorarse durante el proyecto.

Esto permite mayor flexibilidad y adaptación a los cambios.

---

## 7. ¿Qué significa Continuous Integration en XP y qué beneficios aporta al equipo de desarrollo?

**Continuous Integration**, o integración continua, significa que los desarrolladores integran frecuentemente su código al proyecto principal.

Cada vez que se integra código, se ejecutan pruebas para verificar que el sistema siga funcionando correctamente.

### Beneficios

* Permite detectar errores rápidamente.
* Evita problemas grandes al integrar todo al final.
* Mejora la colaboración del equipo.
* Mantiene el software siempre en un estado funcional.
* Reduce riesgos durante el desarrollo.

Por ejemplo, si un desarrollador agrega la funcionalidad de “alta de producto” y otro trabaja en “consulta de stock”, ambos integran sus cambios frecuentemente para comprobar que el sistema completo sigue funcionando.

---

## 8. ¿Cómo se aplica el concepto de Weekly Cycle en un proyecto desarrollado con XP?

El **Weekly Cycle** en XP consiste en organizar el trabajo en ciclos semanales.

Al comienzo de cada semana, el equipo se reúne con el cliente o representante del cliente para definir qué historias de usuario se trabajarán durante esa semana.

Luego, el equipo planifica, desarrolla, prueba e integra esas funcionalidades. Al finalizar la semana, se revisa lo realizado y se obtiene retroalimentación.

Por ejemplo, en una semana el equipo puede decidir trabajar en:

* Agregar productos.
* Validar datos obligatorios.
* Consultar stock disponible.

Al final de la semana, esas funcionalidades deberían estar funcionando y listas para ser revisadas.

---

## 9. En XP se plantea que se fija el tiempo, el costo y la calidad, y se negocia el alcance. ¿Qué significa esta idea? Explicalo con un ejemplo.

Esta idea significa que en XP se intenta mantener estables tres elementos:

* El tiempo disponible.
* El costo del proyecto.
* La calidad del software.

Lo que se negocia es el **alcance**, es decir, la cantidad de funcionalidades que se desarrollarán.

En lugar de bajar la calidad o extender demasiado los tiempos, se decide qué funcionalidades son más importantes y cuáles pueden dejarse para después.

### Ejemplo

Supongamos que un equipo tiene dos semanas para desarrollar una aplicación de inventario.

El cliente pide:

* Alta de productos.
* Consulta de stock.
* Reportes.
* Alertas de stock mínimo.
* Exportación a PDF.

Si el tiempo no alcanza, no se reduce la calidad ni se entrega algo mal hecho. Se negocia el alcance y se prioriza:

Primera entrega:

* Alta de productos.
* Consulta de stock.
* Alertas básicas.

Segunda entrega:

* Reportes.
* Exportación a PDF.

De esta manera, se entrega software útil, funcionando y de calidad, aunque no tenga todas las funcionalidades desde el primer momento.

---

## 10. Elegí tres prácticas de XP y explicá cómo podrían aplicarse en un proyecto real de desarrollo de software.

Para un proyecto real, por ejemplo una aplicación web de inventario, se podrían aplicar las siguientes prácticas de XP:

### 1. Test Driven Development

Antes de programar la funcionalidad de agregar producto, el equipo escribe pruebas para validar que el producto tenga código, nombre, precio válido y stock correcto.

Luego se programa el código necesario para que esas pruebas pasen. Esto ayuda a evitar errores y mejora la calidad del sistema.

---

### 2. Pair Programming

Dos desarrolladores trabajan juntos en la funcionalidad de movimientos de stock.

Uno escribe el código y el otro revisa la lógica, detecta errores y propone mejoras. Esto permite construir una solución más sólida y compartir conocimiento entre los integrantes del equipo.

---

### 3. Continuous Integration

Cada vez que un desarrollador termina una funcionalidad, integra su código al proyecto principal.

Por ejemplo, cuando se termina el módulo de productos, se integra con el módulo de stock y se ejecutan pruebas automáticas para comprobar que nada se haya roto.

Esto permite detectar problemas rápidamente y mantener el sistema funcionando durante todo el desarrollo.


