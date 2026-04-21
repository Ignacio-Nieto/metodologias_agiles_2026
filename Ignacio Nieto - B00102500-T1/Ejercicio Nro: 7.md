# Ejercicio Nro: 7

## Enunciado
Dar un ejemplo de cada uno de los cuellos de botellas analizados anteriormente en el paper de Brooks.

## Resolución
En el paper *No Silver Bullet*, Brooks plantea que existen dificultades esenciales en el desarrollo de software, es decir, problemas que forman parte de la propia naturaleza del software y que no se eliminan fácilmente con nuevas herramientas o tecnologías. Entre esos principales cuellos de botella menciona la complejidad, la conformidad, la modificabilidad o cambio constante, y la invisibilidad del software. 

Un ejemplo de **complejidad** puede verse en un sistema bancario. Aunque parezca una sola aplicación, en realidad debe manejar cuentas, transferencias, préstamos, usuarios, permisos, movimientos, validaciones y medidas de seguridad. Cada parte se relaciona con otras, y un pequeño cambio puede afectar varias funciones del sistema. Brooks explica que esta complejidad es esencial porque el software crece en elementos diferentes y en interacciones no lineales, lo que vuelve difícil comprenderlo, probarlo y mantenerlo.

Un ejemplo de **conformidad** sería un sistema de facturación que debe adaptarse a normas impositivas, formatos legales, requisitos de organismos públicos y sistemas externos ya existentes. Muchas de esas condiciones no responden a una lógica técnica ideal, sino a reglas impuestas desde afuera. Brooks señala justamente que gran parte de la dificultad del software aparece porque debe ajustarse a interfaces, instituciones y reglas humanas arbitrarias. 

Un ejemplo de **modificabilidad**  puede verse en una app de delivery. Al principio puede servir solo para hacer pedidos, pero con el tiempo los usuarios piden seguimiento en tiempo real, nuevos medios de pago, promociones, calificaciones y compatibilidad con nuevos dispositivos. Brooks sostiene que todo software exitoso está sometido a presiones de cambio, tanto por nuevas necesidades de los usuarios como por cambios en el entorno donde funciona. 

Un ejemplo de **invisibilidad** aparece cuando un equipo intenta explicar toda la estructura interna de un sistema grande, como una plataforma de e-commerce. A diferencia de un edificio o una máquina, el software no tiene una forma física fácil de visualizar. Se pueden hacer diagramas, pero nunca muestran completamente todo lo que ocurre dentro del sistema. Brooks afirma que esta falta de representación clara dificulta el diseño y también la comunicación entre las personas del equipo. 

En conclusión, los cuellos de botella que plantea Brooks muestran que el problema del software no es solamente programar, sino lidiar con una realidad compleja, cambiante, dependiente de muchas reglas externas y difícil de visualizar. Por eso el desarrollo de software sigue siendo una actividad exigente, incluso con herramientas modernas. 
