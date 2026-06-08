1. Análisis de Requerimientos
Ejercicio 1: Requisitos funcionales y no funcionales
Sistema: Aplicación web para gestionar inventario

El cliente solicita una aplicación web que permita administrar productos, controlar stock, registrar movimientos y consultar información del inventario.

Requisitos funcionales

Los requisitos funcionales indican qué debe hacer el sistema.

RF1 - Iniciar sesión

El sistema debe permitir que los usuarios ingresen con usuario y contraseña.

RF2 - Gestionar productos

El sistema debe permitir:

Agregar productos.
Modificar productos.
Eliminar o dar de baja productos.
Consultar productos registrados.
RF3 - Registrar datos del producto

De cada producto se debe registrar:

Código del producto.
Nombre.
Descripción.
Categoría.
Precio.
Cantidad en stock.
Stock mínimo.
Proveedor.
RF4 - Controlar stock

El sistema debe permitir consultar la cantidad disponible de cada producto.

RF5 - Registrar entradas de mercadería

El sistema debe permitir registrar ingresos de productos al inventario.

Ejemplo: compra a proveedor o reposición de stock.

RF6 - Registrar salidas de mercadería

El sistema debe permitir registrar egresos de productos.

Ejemplo: venta, pérdida, rotura o devolución.

RF7 - Generar alertas de stock mínimo

El sistema debe avisar cuando un producto tenga una cantidad menor o igual al stock mínimo definido.

RF8 - Buscar productos

El sistema debe permitir buscar productos por:

Código.
Nombre.
Categoría.
Proveedor.
RF9 - Generar reportes

El sistema debe permitir generar reportes de:

Productos disponibles.
Productos con bajo stock.
Movimientos de entrada y salida.
Productos más vendidos o más utilizados.
RF10 - Gestionar usuarios

El sistema debe permitir crear usuarios y asignarles permisos.

Ejemplo:

Administrador.
Encargado de depósito.
Usuario de consulta.
Requisitos no funcionales

Los requisitos no funcionales indican cómo debe funcionar el sistema.

RNF1 - Seguridad

El sistema debe proteger el acceso mediante usuario y contraseña.

RNF2 - Rendimiento

El sistema debe responder rápidamente a las consultas de productos y stock.

RNF3 - Disponibilidad

El sistema debe estar disponible para los usuarios durante el horario laboral.

RNF4 - Usabilidad

La interfaz debe ser clara, simple y fácil de usar.

RNF5 - Compatibilidad

El sistema debe poder utilizarse desde navegadores web como Chrome, Edge o Firefox.

RNF6 - Mantenibilidad

El sistema debe estar diseñado de forma ordenada para permitir futuras modificaciones.

RNF7 - Integridad de datos

El sistema debe evitar inconsistencias, por ejemplo, que el stock quede en valores negativos.

RNF8 - Escalabilidad

El sistema debe permitir agregar nuevas funcionalidades en el futuro, como ventas, compras o facturación.

RNF9 - Respaldo de información

El sistema debe permitir realizar copias de seguridad de la base de datos.

RNF10 - Control de errores

El sistema debe mostrar mensajes claros cuando ocurra un error.

Ejemplo: “No hay stock suficiente para realizar la salida”.


Ejercicio 2: Caso de uso “Agregar un nuevo producto”
Caso de uso: Agregar nuevo producto
<img width="714" height="303" alt="image" src="https://github.com/user-attachments/assets/4136c86d-ddef-4bbf-af7d-2a9c9fae01e5" />


Curso normal
El usuario ingresa al sistema con su usuario y contraseña.
El sistema muestra la pantalla principal.
El usuario selecciona la opción Productos.
El sistema muestra el listado de productos.
El usuario selecciona la opción Agregar nuevo producto.
El sistema muestra un formulario vacío.
El usuario completa los datos del producto:
Código.
Nombre.
Descripción.
Categoría.
Precio.
Stock inicial.
Stock mínimo.
Proveedor.
El usuario presiona el botón Guardar.
El sistema valida los datos ingresados.
El sistema registra el producto en la base de datos.
El sistema muestra un mensaje de confirmación:
“Producto agregado correctamente”.
Flujos alternativos
A1 - Datos incompletos
El usuario deja campos obligatorios vacíos.
El sistema detecta la falta de datos.
El sistema muestra un mensaje de error:
“Debe completar todos los campos obligatorios”.
El usuario completa los datos faltantes.
El caso de uso continúa desde el paso 8.
A2 - Código de producto repetido
El usuario ingresa un código de producto que ya existe.
El sistema valida el código.
El sistema muestra un mensaje de error:
“Ya existe un producto con ese código”.
El usuario modifica el código.
El caso de uso continúa desde el paso 8.
A3 - Precio o stock inválido
El usuario ingresa un precio negativo o un stock menor a cero.
El sistema detecta el error.
El sistema muestra un mensaje:
“El precio y el stock deben ser valores válidos”.
El usuario corrige los datos.
El caso de uso continúa desde el paso 8.

2. Diseño del Sistema
Ejercicio 3: Diagrama de Flujo de Datos

Un Diagrama de Flujo de Datos, también llamado DFD, muestra cómo circula la información dentro del sistema.
<img width="1122" height="1402" alt="image" src="https://github.com/user-attachments/assets/42dfafc6-492b-4dad-a0bf-c16694919353" />


Explicación

El usuario interactúa con el sistema cargando productos, registrando entradas y salidas, consultando stock y solicitando reportes. El sistema responde con información, mensajes de confirmación y alertas.


<img width="1122" height="1402" alt="image" src="https://github.com/user-attachments/assets/feb52096-4c6b-45d7-9c6b-c365a639d208" />

<img width="701" height="620" alt="image" src="https://github.com/user-attachments/assets/bacc8c03-1cfd-4025-8152-7ba70afc0625" />


Ejercicio 4: Diseño de interfaz de usuario para pantalla de Inicio
Pantalla de Inicio

La pantalla de inicio debe ser simple y mostrar las opciones principales del sistema.

Diseño propuesto

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/024f34e2-ef87-4cc8-8c34-00045dceb160" />

Elementos de la pantalla
Encabezado

Contiene el nombre del sistema y la opción para cerrar sesión.

Menú principal

Contiene accesos a las principales funcionalidades:

Productos.
Stock.
Movimientos.
Reportes.
Proveedores.
Usuarios.
Área de bienvenida

Muestra un mensaje inicial para el usuario.

Alertas

Muestra avisos importantes, por ejemplo productos con bajo stock.

3. Diseño del Programa
Ejercicio 5: Arquitectura adecuada para la aplicación web

Para esta aplicación se propone utilizar una arquitectura en tres capas.

Arquitectura en tres capas

<img width="1122" height="1402" alt="image" src="https://github.com/user-attachments/assets/469d4893-0311-4ce3-aaef-4437431563a2" />


Justificación

Se elige esta arquitectura porque permite separar responsabilidades.

La capa de presentación se encarga de mostrar las pantallas al usuario.

La capa de lógica de negocio contiene las reglas principales del sistema, por ejemplo:

Validar que el stock no quede negativo.
Controlar si un producto está por debajo del stock mínimo.
Registrar correctamente las entradas y salidas.
Validar los datos obligatorios.

La capa de datos se encarga de guardar y recuperar la información de la base de datos.

Ventajas de esta arquitectura
Es ordenada.
Facilita el mantenimiento.
Permite modificar la interfaz sin afectar la base de datos.
Permite reutilizar la lógica del sistema.
Es adecuada para aplicaciones web.
Facilita futuras ampliaciones del sistema.
Ejercicio 6: Diseño de la base de datos

Para la aplicación web de inventario se propone una base de datos relacional.

Entidades principales
Usuario

Guarda los usuarios que acceden al sistema.

Rol

Guarda los tipos de usuarios o permisos.

Producto

Guarda la información de cada producto.

Categoría

Permite clasificar los productos.

Proveedor

Guarda los datos de los proveedores.

Movimiento

Registra las entradas y salidas de mercadería.

Modelo de base de datos propuesto

ROL
- idRol PK
- nombreRol

USUARIO
- idUsuario PK
- nombreUsuario
- contraseña
- nombreCompleto
- idRol FK

CATEGORIA
- idCategoria PK
- nombreCategoria
- descripcion

PROVEEDOR
- idProveedor PK
- nombreProveedor
- telefono
- email
- direccion

PRODUCTO
- idProducto PK
- codigoProducto
- nombreProducto
- descripcion
- precio
- stockActual
- stockMinimo
- idCategoria FK
- idProveedor FK

MOVIMIENTO
- idMovimiento PK
- fechaMovimiento
- tipoMovimiento
- cantidad
- motivo
- idProducto FK
- idUsuario FK

Relaciones entre tablas
ROL 1 ─────── N USUARIO

CATEGORIA 1 ─────── N PRODUCTO

PROVEEDOR 1 ─────── N PRODUCTO

PRODUCTO 1 ─────── N MOVIMIENTO

USUARIO 1 ─────── N MOVIMIENTO

Ejercicio 6: Diseño de la base de datos
Aplicación web de gestión de inventario

La base de datos debe permitir registrar productos, categorías, proveedores, usuarios y movimientos de stock.
Script SQL
CREATE DATABASE InventarioWeb;
GO

USE InventarioWeb;
GO

CREATE TABLE Rol (
    idRol INT PRIMARY KEY IDENTITY(1,1),
    nombreRol VARCHAR(50) NOT NULL
);

CREATE TABLE Usuario (
    idUsuario INT PRIMARY KEY IDENTITY(1,1),
    nombreUsuario VARCHAR(50) NOT NULL,
    contraseña VARCHAR(100) NOT NULL,
    nombreCompleto VARCHAR(100) NOT NULL,
    idRol INT NOT NULL,
    FOREIGN KEY (idRol) REFERENCES Rol(idRol)
);

CREATE TABLE Categoria (
    idCategoria INT PRIMARY KEY IDENTITY(1,1),
    nombreCategoria VARCHAR(100) NOT NULL,
    descripcion VARCHAR(200)
);

CREATE TABLE Proveedor (
    idProveedor INT PRIMARY KEY IDENTITY(1,1),
    nombreProveedor VARCHAR(100) NOT NULL,
    telefono VARCHAR(30),
    email VARCHAR(100),
    direccion VARCHAR(150)
);

CREATE TABLE Producto (
    idProducto INT PRIMARY KEY IDENTITY(1,1),
    codigoProducto VARCHAR(30) NOT NULL UNIQUE,
    nombreProducto VARCHAR(100) NOT NULL,
    descripcion VARCHAR(200),
    precio DECIMAL(10,2) NOT NULL,
    stockActual INT NOT NULL,
    stockMinimo INT NOT NULL,
    estado VARCHAR(20) NOT NULL,
    idCategoria INT NOT NULL,
    idProveedor INT NOT NULL,
    FOREIGN KEY (idCategoria) REFERENCES Categoria(idCategoria),
    FOREIGN KEY (idProveedor) REFERENCES Proveedor(idProveedor)
);

CREATE TABLE MovimientoStock (
    idMovimiento INT PRIMARY KEY IDENTITY(1,1),
    fechaMovimiento DATETIME NOT NULL,
    tipoMovimiento VARCHAR(20) NOT NULL,
    cantidad INT NOT NULL,
    motivo VARCHAR(100),
    idProducto INT NOT NULL,
    idUsuario INT NOT NULL,
    FOREIGN KEY (idProducto) REFERENCES Producto(idProducto),
    FOREIGN KEY (idUsuario) REFERENCES Usuario(idUsuario)
);

Ejercicio 7: Implementar la funcionalidad “Agregar un nuevo producto”
1. Diagrama de Dominio

El diagrama de dominio muestra las entidades principales del sistema, sus atributos y relaciones.
<img width="1122" height="1402" alt="image" src="https://github.com/user-attachments/assets/4f2513c5-7d49-4769-b4eb-291e63453580" />

2. Diagrama de Robustez

<img width="586" height="235" alt="image" src="https://github.com/user-attachments/assets/03e0d3b2-6e78-4e67-8b95-960b4196d2cc" />

<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/cc54c1ac-0e12-43c9-a6db-eb593d9a3422" />

3. Prototipo de pantalla
Pantalla: Agregar nuevo producto
<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/dc467ae4-d8fe-4882-b1b3-009136e2808b" />
4. Diagrama de Secuencia

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0bdc25d2-f1f3-44ea-90a2-37b83e6354c5" />

5.Diagrama de clases
<img width="1076" height="413" alt="image" src="https://github.com/user-attachments/assets/5a4b7235-903f-4d1a-98a0-b2cf43fe6194" />

Ejercicio 8: Implementar la lógica de negocio para “Agregar un nuevo producto”

La lógica de negocio define las reglas que debe cumplir el sistema antes de guardar el producto.

Reglas de negocio
RN1 - El código del producto es obligatorio

No se puede registrar un producto sin código.

RN2 - El código del producto no puede repetirse

Cada producto debe tener un código único.

RN3 - El nombre del producto es obligatorio

No se puede registrar un producto sin nombre.

RN4 - El precio debe ser mayor a cero

El sistema no debe aceptar productos con precio cero o negativo.

RN5 - El stock actual no puede ser negativo

No puede cargarse un producto con stock menor a cero.

RN6 - El stock mínimo no puede ser negativo

El stock mínimo debe ser cero o mayor.

RN7 - El producto debe tener una categoría

Todo producto debe estar clasificado.

RN8 - El producto debe tener un proveedor

Todo producto debe estar asociado a un proveedor.

RN9 - El producto se registra con estado activo

Cuando se agrega un producto nuevo, su estado inicial debe ser Activo.

# 5. Pruebas

## Ejercicio 9: Pruebas unitarias para “Agregar un nuevo producto”

Las pruebas unitarias sirven para verificar que una parte específica del sistema funcione correctamente. En este caso, se prueba la lógica de negocio de la funcionalidad **Agregar un nuevo producto**.

La funcionalidad debe validar que los datos ingresados sean correctos antes de guardar el producto.

---

## Casos de prueba unitarios

| N.º | Caso de prueba            | Datos de entrada                                               | Resultado esperado                                                |
| --- | ------------------------- | -------------------------------------------------------------- | ----------------------------------------------------------------- |
| 1   | Agregar producto válido   | Código, nombre, precio, stock, categoría y proveedor correctos | Producto agregado correctamente                                   |
| 2   | Código vacío              | Código sin completar                                           | El sistema muestra error: “El código es obligatorio”              |
| 3   | Nombre vacío              | Nombre sin completar                                           | El sistema muestra error: “El nombre es obligatorio”              |
| 4   | Precio negativo           | Precio menor a 0                                               | El sistema muestra error: “El precio debe ser mayor a cero”       |
| 5   | Precio igual a 0          | Precio = 0                                                     | El sistema muestra error: “El precio debe ser mayor a cero”       |
| 6   | Stock negativo            | StockActual menor a 0                                          | El sistema muestra error: “El stock no puede ser negativo”        |
| 7   | Stock mínimo negativo     | StockMinimo menor a 0                                          | El sistema muestra error: “El stock mínimo no puede ser negativo” |
| 8   | Categoría no seleccionada | idCategoria = 0                                                | El sistema muestra error: “Debe seleccionar una categoría”        |
| 9   | Proveedor no seleccionado | idProveedor = 0                                                | El sistema muestra error: “Debe seleccionar un proveedor”         |
| 10  | Código repetido           | Código ya existente en el sistema                              | El sistema muestra error: “Ya existe un producto con ese código”  |

---

## Ejemplo de prueba unitaria en C#

```csharp
[TestClass]
public class ProductoServiceTest
{
    [TestMethod]
    public void AgregarProducto_ProductoValido_DeberiaAgregarCorrectamente()
    {
        // Arrange
        ProductoService service = new ProductoService();

        Producto producto = new Producto
        {
            CodigoProducto = "PROD001",
            NombreProducto = "Mouse inalámbrico",
            Descripcion = "Mouse óptico USB",
            Precio = 15000,
            StockActual = 10,
            StockMinimo = 3,
            IdCategoria = 1,
            IdProveedor = 1
        };

        // Act
        string resultado = service.AgregarProducto(producto);

        // Assert
        Assert.AreEqual("Producto agregado correctamente.", resultado);
    }

    [TestMethod]
    public void AgregarProducto_CodigoVacio_DeberiaMostrarError()
    {
        // Arrange
        ProductoService service = new ProductoService();

        Producto producto = new Producto
        {
            CodigoProducto = "",
            NombreProducto = "Teclado",
            Precio = 20000,
            StockActual = 5,
            StockMinimo = 2,
            IdCategoria = 1,
            IdProveedor = 1
        };

        // Act
        string resultado = service.AgregarProducto(producto);

        // Assert
        Assert.AreEqual("El código del producto es obligatorio.", resultado);
    }

    [TestMethod]
    public void AgregarProducto_PrecioNegativo_DeberiaMostrarError()
    {
        // Arrange
        ProductoService service = new ProductoService();

        Producto producto = new Producto
        {
            CodigoProducto = "PROD002",
            NombreProducto = "Monitor",
            Precio = -5000,
            StockActual = 4,
            StockMinimo = 1,
            IdCategoria = 1,
            IdProveedor = 1
        };

        // Act
        string resultado = service.AgregarProducto(producto);

        // Assert
        Assert.AreEqual("El precio debe ser mayor a cero.", resultado);
    }
}
```

---

## Conclusión del ejercicio 9

Las pruebas unitarias permiten comprobar que la funcionalidad **Agregar nuevo producto** cumple con las reglas de negocio definidas. Estas pruebas ayudan a detectar errores antes de integrar el módulo con el resto del sistema.

---

# Ejercicio 10: Pruebas de integración para “Agregar un nuevo producto”

Las pruebas de integración verifican que varias partes del sistema funcionen correctamente en conjunto.

En este caso, se prueba la integración entre:

* Pantalla de agregar producto.
* Controlador de producto.
* Lógica de negocio.
* Repositorio.
* Base de datos.

---

## Objetivo de la prueba de integración

Comprobar que un producto ingresado desde la interfaz web sea validado, procesado y guardado correctamente en la base de datos.

---

## Componentes que intervienen

| Componente         | Función                               |
| ------------------ | ------------------------------------- |
| Interfaz web       | Permite cargar los datos del producto |
| ProductoController | Recibe los datos desde la pantalla    |
| ProductoService    | Aplica las reglas de negocio          |
| ProductoRepository | Se comunica con la base de datos      |
| Base de datos      | Guarda el producto                    |

---

## Caso de prueba de integración 1: Alta correcta de producto

### Datos de entrada

```text
Código: PROD001
Nombre: Mouse inalámbrico
Descripción: Mouse óptico USB
Precio: 15000
Stock actual: 10
Stock mínimo: 3
Categoría: Periféricos
Proveedor: Logitech
```

### Pasos

1. El usuario ingresa al sistema.
2. Selecciona la opción **Productos**.
3. Hace clic en **Agregar nuevo producto**.
4. Completa el formulario.
5. Presiona el botón **Guardar**.
6. El sistema valida los datos.
7. El sistema guarda el producto en la base de datos.
8. El sistema muestra el mensaje:
   “Producto agregado correctamente”.

### Resultado esperado

El producto queda registrado correctamente en la base de datos.

---

## Caso de prueba de integración 2: Código repetido

### Datos de entrada

```text
Código: PROD001
Nombre: Mouse inalámbrico
Precio: 15000
Stock actual: 10
Stock mínimo: 3
Categoría: Periféricos
Proveedor: Logitech
```

### Pasos

1. El usuario intenta cargar un producto con un código ya existente.
2. El sistema consulta la base de datos.
3. El sistema detecta que el código ya está registrado.
4. El sistema muestra un mensaje de error.

### Resultado esperado

El producto no se guarda y se muestra el mensaje:
“Ya existe un producto con ese código”.

---

## Caso de prueba de integración 3: Datos inválidos

### Datos de entrada

```text
Código: PROD002
Nombre: Teclado
Precio: -1000
Stock actual: 5
Stock mínimo: 2
Categoría: Periféricos
Proveedor: Logitech
```

### Resultado esperado

El sistema no guarda el producto y muestra el mensaje:
“El precio debe ser mayor a cero”.

---

## Conclusión del ejercicio 10

Las pruebas de integración permiten comprobar que las distintas capas del sistema trabajan correctamente juntas. En este caso, se verifica que los datos ingresados desde la pantalla lleguen al controlador, pasen por la lógica de negocio y finalmente se guarden en la base de datos.

---

# 6. Despliegue del Programa

## Ejercicio 11: Plan de despliegue para la aplicación web

El despliegue consiste en instalar y poner en funcionamiento la aplicación web en un servidor para que pueda ser utilizada por los usuarios finales.

---

## Objetivo del plan de despliegue

Publicar la aplicación web de inventario en un ambiente de producción de manera segura, controlada y ordenada.

---

## Etapas del plan de despliegue

### 1. Preparación del ambiente

Se debe preparar el servidor donde se instalará la aplicación.

El servidor debe contar con:

* Sistema operativo actualizado.
* Servidor web instalado.
* Motor de base de datos.
* Conexión a internet o red interna.
* Certificado SSL para seguridad.
* Permisos de acceso configurados.

---

### 2. Preparación de la base de datos

Se debe crear la base de datos de producción.

Actividades:

* Crear la base de datos InventarioWeb.
* Ejecutar los scripts de creación de tablas.
* Crear usuarios de base de datos.
* Configurar permisos.
* Cargar datos iniciales, como roles, categorías y proveedores.

---

### 3. Publicación de la aplicación

Se genera la versión final de la aplicación.

Actividades:

* Compilar el proyecto.
* Generar los archivos de publicación.
* Copiar los archivos al servidor.
* Configurar la conexión a la base de datos.
* Configurar variables del sistema.

---

### 4. Pruebas en producción

Antes de habilitar el sistema a todos los usuarios, se realizan pruebas básicas.

Pruebas:

* Iniciar sesión.
* Agregar producto.
* Consultar productos.
* Registrar entrada de stock.
* Registrar salida de stock.
* Verificar alertas de stock mínimo.
* Generar reportes.

---

### 5. Capacitación a usuarios

Se capacita a los usuarios principales del sistema.

Usuarios a capacitar:

* Administrador.
* Encargado de inventario.
* Operarios.
* Usuarios de consulta.

---

### 6. Puesta en marcha

Cuando las pruebas sean correctas, el sistema queda disponible para su uso real.

Actividades:

* Informar a los usuarios.
* Habilitar accesos.
* Supervisar el funcionamiento inicial.
* Registrar errores detectados.

---

### 7. Plan de respaldo

Antes del despliegue se debe realizar una copia de seguridad.

También se deben programar respaldos periódicos de la base de datos.

Ejemplo:

* Backup diario automático.
* Backup semanal completo.
* Almacenamiento externo o en la nube.

---

## Responsables del despliegue

| Rol                              | Responsabilidad                                |
| -------------------------------- | ---------------------------------------------- |
| Administrador del sistema        | Configura servidor y permisos                  |
| Desarrollador                    | Publica la aplicación                          |
| DBA o encargado de base de datos | Crea y revisa la base de datos                 |
| Tester                           | Verifica que el sistema funcione correctamente |
| Usuario clave                    | Valida que el sistema cumpla con lo pedido     |

---

## Conclusión del ejercicio 11

El plan de despliegue permite poner en producción la aplicación web de inventario de forma ordenada, reduciendo errores y asegurando que el sistema esté listo para ser utilizado.

---

# Ejercicio 12: Despliegue de la aplicación web en un servidor de producción

Para este ejercicio se describe cómo se realizaría el despliegue de la aplicación web en un servidor de producción.

---

## Servidor de producción elegido

Se utilizará un servidor web con las siguientes características:

```text
Sistema operativo: Windows Server
Servidor web: IIS
Base de datos: SQL Server
Aplicación: ASP.NET / C#
```

---

## Pasos para desplegar la aplicación

### Paso 1: Compilar la aplicación

Desde Visual Studio se compila el proyecto para verificar que no existan errores.

```text
Compilar → Compilar solución
```

---

### Paso 2: Publicar la aplicación

Desde Visual Studio se selecciona la opción:

```text
Clic derecho sobre el proyecto → Publicar
```

Luego se elige la carpeta de destino donde se generarán los archivos de publicación.

---

### Paso 3: Configurar el servidor IIS

En el servidor de producción se abre IIS y se crea un nuevo sitio web.

Datos del sitio:

```text
Nombre del sitio: InventarioWeb
Ruta física: C:\inetpub\wwwroot\InventarioWeb
Puerto: 443
Protocolo: HTTPS
```

---

### Paso 4: Copiar archivos al servidor

Se copian los archivos publicados a la carpeta configurada en IIS.

```text
C:\inetpub\wwwroot\InventarioWeb
```

---

### Paso 5: Configurar la base de datos

En SQL Server se crea la base de datos y se ejecutan los scripts correspondientes.

```sql
CREATE DATABASE InventarioWeb;
```

Luego se ejecutan los scripts de tablas, claves primarias y claves foráneas.

---

### Paso 6: Configurar la cadena de conexión

Se configura la conexión entre la aplicación y la base de datos.

Ejemplo:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=SERVIDOR;Database=InventarioWeb;User Id=usuario;Password=contraseña;"
}
```

---

### Paso 7: Probar el sistema

Se ingresa a la URL del sistema:

```text
https://servidor/InventarioWeb
```

Se prueban las funcionalidades principales:

* Inicio de sesión.
* Alta de producto.
* Consulta de stock.
* Registro de movimientos.
* Generación de reportes.

---

### Paso 8: Habilitar usuarios

Se crean los usuarios que utilizarán el sistema y se asignan sus roles.

Ejemplo:

* Administrador.
* Encargado de inventario.
* Usuario de consulta.

---

## Resultado esperado

La aplicación queda publicada en el servidor de producción y disponible para los usuarios autorizados.

---

## Conclusión del ejercicio 12

El despliegue permite que la aplicación web de inventario pase del ambiente de desarrollo al ambiente real de trabajo. Una vez instalada en el servidor, los usuarios pueden acceder al sistema mediante un navegador web.

---

# 7. Mantenimiento

## Ejercicio 13: Plan de mantenimiento para la aplicación web

El mantenimiento consiste en realizar mejoras, correcciones y controles sobre el sistema una vez que ya está en funcionamiento.

---

## Objetivo del plan de mantenimiento

Asegurar que la aplicación web de inventario funcione correctamente a lo largo del tiempo, corrigiendo errores, mejorando funcionalidades y protegiendo la información.

---

## Tipos de mantenimiento

### 1. Mantenimiento correctivo

Se realiza cuando se detecta un error en el sistema.

Ejemplo:

* El sistema permite guardar productos con precio negativo.
* No se actualiza correctamente el stock.
* No aparece una alerta de stock mínimo.

---

### 2. Mantenimiento preventivo

Busca evitar problemas futuros.

Ejemplo:

* Realizar copias de seguridad.
* Revisar el rendimiento de la base de datos.
* Actualizar librerías y componentes.
* Controlar espacio en disco del servidor.

---

### 3. Mantenimiento adaptativo

Se realiza cuando el sistema debe adaptarse a nuevos cambios.

Ejemplo:

* Cambios en el servidor.
* Cambios en el motor de base de datos.
* Nuevas políticas de seguridad.
* Nuevos navegadores o dispositivos.

---

### 4. Mantenimiento perfectivo

Busca mejorar el sistema agregando nuevas funcionalidades.

Ejemplo:

* Agregar exportación de reportes a PDF.
* Mejorar los filtros de búsqueda.
* Agregar gráficos de stock.
* Incorporar notificaciones por correo electrónico.

---

## Actividades del plan de mantenimiento

| Actividad                           | Frecuencia         | Responsable               |
| ----------------------------------- | ------------------ | ------------------------- |
| Revisión de errores reportados      | Semanal            | Desarrollador             |
| Copia de seguridad de base de datos | Diaria             | Administrador del sistema |
| Revisión de rendimiento             | Mensual            | Administrador / DBA       |
| Actualización de seguridad          | Mensual            | Administrador             |
| Revisión de usuarios y permisos     | Mensual            | Administrador del sistema |
| Mejoras solicitadas por usuarios    | Según necesidad    | Analista / Desarrollador  |
| Pruebas después de cambios          | Cada actualización | Tester                    |

---

## Procedimiento ante errores

1. El usuario informa el problema.
2. Se registra el incidente.
3. Se analiza la causa.
4. Se clasifica la prioridad.
5. Se corrige el error.
6. Se realizan pruebas.
7. Se publica la corrección.
8. Se informa al usuario.

---

## Conclusión del ejercicio 13

El plan de mantenimiento permite que la aplicación siga siendo útil, segura y confiable después de su puesta en marcha. Además, ayuda a organizar las correcciones y mejoras futuras.

---

# Ejercicio 14: Corrección de errores detectados

## Problema detectado

Durante el uso del sistema se detectó que la aplicación permite agregar productos con **stock mínimo mayor al stock actual**.

Ejemplo:

```text
Stock actual: 5
Stock mínimo: 10
```

Esto puede generar alertas incorrectas desde el momento en que el producto se crea.

---

## Análisis del problema

El error ocurre porque la lógica de negocio valida que el stock no sea negativo, pero no compara el stock mínimo con el stock actual.

Actualmente valida:

* Que el stock actual no sea negativo.
* Que el stock mínimo no sea negativo.

Pero falta validar:

```text
El stock mínimo no debe ser mayor que el stock actual al momento de crear el producto.
```

---

## Corrección propuesta

Agregar una validación en la clase `ProductoService`.

---

## Código antes de la corrección

```csharp
if (producto.StockActual < 0)
{
    return "El stock actual no puede ser negativo.";
}

if (producto.StockMinimo < 0)
{
    return "El stock mínimo no puede ser negativo.";
}
```

---

## Código corregido

```csharp
if (producto.StockActual < 0)
{
    return "El stock actual no puede ser negativo.";
}

if (producto.StockMinimo < 0)
{
    return "El stock mínimo no puede ser negativo.";
}

if (producto.StockMinimo > producto.StockActual)
{
    return "El stock mínimo no puede ser mayor al stock actual.";
}
```

---

## Clase corregida

```csharp
public class ProductoService
{
    private ProductoRepository productoRepository;

    public ProductoService()
    {
        productoRepository = new ProductoRepository();
    }

    public string AgregarProducto(Producto producto)
    {
        string resultadoValidacion = ValidarProducto(producto);

        if (resultadoValidacion != "OK")
        {
            return resultadoValidacion;
        }

        if (productoRepository.ExisteCodigo(producto.CodigoProducto))
        {
            return "Ya existe un producto con ese código.";
        }

        producto.Estado = "Activo";

        productoRepository.Guardar(producto);

        return "Producto agregado correctamente.";
    }

    private string ValidarProducto(Producto producto)
    {
        if (producto == null)
        {
            return "El producto no puede ser nulo.";
        }

        if (string.IsNullOrWhiteSpace(producto.CodigoProducto))
        {
            return "El código del producto es obligatorio.";
        }

        if (string.IsNullOrWhiteSpace(producto.NombreProducto))
        {
            return "El nombre del producto es obligatorio.";
        }

        if (producto.Precio <= 0)
        {
            return "El precio debe ser mayor a cero.";
        }

        if (producto.StockActual < 0)
        {
            return "El stock actual no puede ser negativo.";
        }

        if (producto.StockMinimo < 0)
        {
            return "El stock mínimo no puede ser negativo.";
        }

        if (producto.StockMinimo > producto.StockActual)
        {
            return "El stock mínimo no puede ser mayor al stock actual.";
        }

        if (producto.IdCategoria <= 0)
        {
            return "Debe seleccionar una categoría.";
        }

        if (producto.IdProveedor <= 0)
        {
            return "Debe seleccionar un proveedor.";
        }

        return "OK";
    }
}
```

---

## Prueba de la corrección

### Caso de prueba

```text
Código: PROD010
Nombre: Auriculares
Precio: 25000
Stock actual: 5
Stock mínimo: 10
Categoría: Periféricos
Proveedor: Logitech
```

### Resultado esperado

El sistema no debe guardar el producto y debe mostrar el mensaje:

```text
El stock mínimo no puede ser mayor al stock actual.
```

---

## Conclusión del ejercicio 14

La corrección mejora la lógica de negocio y evita inconsistencias en el inventario. Además, permite que las alertas de stock mínimo funcionen de manera más precisa.

---

# 8. Nos preparamos para nuevos retos

## Ejercicio 15: Equipo de trabajo y roles para un futuro dominio relacionado con inteligencia artificial generativa

Para futuros proyectos relacionados con **inteligencia artificial generativa**, se propone formar un equipo de trabajo multidisciplinario. Este equipo deberá encargarse del análisis, diseño, desarrollo, prueba, despliegue y mantenimiento del sistema.

---

## Dominio de aplicación propuesto

Se propone desarrollar una aplicación web basada en inteligencia artificial generativa para ayudar a empresas a crear descripciones automáticas de productos para sus catálogos digitales.

El sistema permitiría ingresar datos básicos de un producto y generar automáticamente:

* Descripciones comerciales.
* Textos para publicaciones.
* Resúmenes técnicos.
* Sugerencias de palabras clave.
* Traducciones a otros idiomas.

---

## Nombre tentativo del sistema

```text
GeneraCatalog IA
```

---

## Objetivo del sistema

Desarrollar una aplicación web que utilice inteligencia artificial generativa para asistir en la creación automática de contenido relacionado con productos, mejorando la rapidez y calidad de la carga de información en catálogos digitales.

---

## Equipo de trabajo propuesto

| Rol                                | Responsabilidades                                                              |
| ---------------------------------- | ------------------------------------------------------------------------------ |
| Jefe de proyecto                   | Organiza el trabajo, controla tiempos y coordina al equipo                     |
| Analista funcional                 | Releva requerimientos, define casos de uso y documenta necesidades del cliente |
| Diseñador UX/UI                    | Diseña las pantallas y mejora la experiencia de usuario                        |
| Desarrollador backend              | Programa la lógica del sistema, servicios y conexión con base de datos         |
| Desarrollador frontend             | Implementa la interfaz web que usa el usuario                                  |
| Especialista en IA generativa      | Integra el modelo de IA y define cómo se generan los textos                    |
| Administrador de base de datos     | Diseña y mantiene la base de datos                                             |
| Tester / QA                        | Realiza pruebas unitarias, integración, sistema y aceptación                   |
| DevOps / Administrador de servidor | Realiza el despliegue y controla el ambiente de producción                     |
| Usuario clave                      | Valida que el sistema cumpla con las necesidades reales del negocio            |

---

## Distribución de tareas según etapas de cascada

### 1. Análisis de requerimientos

Responsables:

* Analista funcional.
* Jefe de proyecto.
* Usuario clave.
* Especialista en IA generativa.

Actividades:

* Definir funcionalidades principales.
* Identificar usuarios del sistema.
* Especificar casos de uso.
* Definir requisitos funcionales y no funcionales.
* Determinar límites éticos y de seguridad del uso de IA.

---

### 2. Diseño del sistema

Responsables:

* Analista funcional.
* Diseñador UX/UI.
* Desarrollador backend.
* Administrador de base de datos.
* Especialista en IA generativa.

Actividades:

* Crear diagramas de dominio.
* Crear diagramas de robustez.
* Diseñar prototipos.
* Diseñar diagramas de secuencia.
* Diseñar diagramas de clases.
* Definir cómo se conectará el sistema con el modelo de IA.

---

### 3. Diseño del programa

Responsables:

* Desarrollador backend.
* Desarrollador frontend.
* Administrador de base de datos.
* Especialista en IA generativa.

Actividades:

* Definir arquitectura del sistema.
* Diseñar la base de datos.
* Diseñar servicios de generación de contenido.
* Definir validaciones.
* Definir permisos de usuario.

---

### 4. Implementación

Responsables:

* Desarrollador backend.
* Desarrollador frontend.
* Especialista en IA generativa.

Actividades:

* Programar la interfaz web.
* Programar la lógica de negocio.
* Integrar el modelo de IA generativa.
* Programar la gestión de usuarios.
* Programar el historial de textos generados.

---

### 5. Pruebas

Responsables:

* Tester / QA.
* Desarrolladores.
* Usuario clave.

Actividades:

* Realizar pruebas unitarias.
* Realizar pruebas de integración.
* Realizar pruebas de seguridad.
* Probar resultados generados por la IA.
* Validar que los textos generados sean correctos y útiles.

---

### 6. Despliegue

Responsables:

* DevOps.
* Desarrollador backend.
* Administrador de base de datos.

Actividades:

* Configurar servidor.
* Publicar la aplicación.
* Configurar base de datos.
* Configurar claves de acceso a la IA.
* Probar el sistema en producción.

---

### 7. Mantenimiento

Responsables:

* Jefe de proyecto.
* Desarrolladores.
* Tester.
* Especialista en IA generativa.
* Administrador de servidor.

Actividades:

* Corregir errores.
* Mejorar prompts de IA.
* Actualizar funcionalidades.
* Revisar seguridad.
* Controlar rendimiento.
* Atender solicitudes de usuarios.

---

## Requisitos iniciales para el sistema con IA generativa

### Requisitos funcionales

* El sistema debe permitir cargar un producto.
* El sistema debe generar una descripción automática del producto.
* El sistema debe permitir editar el texto generado.
* El sistema debe guardar el historial de generaciones.
* El sistema debe permitir copiar o exportar el texto generado.
* El sistema debe permitir seleccionar el tono del texto: formal, comercial o técnico.
* El sistema debe permitir generar palabras clave relacionadas.

### Requisitos no funcionales

* El sistema debe responder en pocos segundos.
* El sistema debe proteger los datos cargados.
* El sistema debe permitir controlar usuarios y permisos.
* El sistema debe ser fácil de usar.
* El sistema debe estar disponible desde un navegador web.
* El sistema debe evitar generar contenido ofensivo, falso o inapropiado.

---

## Conclusión del ejercicio 15

Para desarrollar un futuro sistema relacionado con inteligencia artificial generativa, es necesario formar un equipo con roles bien definidos. Además de los roles tradicionales como analista, desarrollador, tester y administrador, se incorpora un especialista en IA generativa, encargado de integrar y controlar el uso del modelo de inteligencia artificial.

El trabajo debe organizarse siguiendo las etapas de la metodología en cascada: análisis, diseño, implementación, pruebas, despliegue y mantenimiento. De esta forma, el proyecto puede desarrollarse de manera ordenada, documentada y controlada.

