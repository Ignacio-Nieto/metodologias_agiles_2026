# Mejora del Ejercicio 8 aplicando conceptos del Proceso Unificado

## Ejercicio 8: Implementar la lógica de negocio para la funcionalidad “Agregar un nuevo producto”

A partir de los conceptos aprendidos del **Proceso Unificado**, se propone mejorar el desarrollo de la funcionalidad **Agregar un nuevo producto**. La mejora consiste en no pensar la funcionalidad solamente como una parte del código, sino como un caso de uso que debe ser analizado, diseñado, implementado, probado y mantenido de forma iterativa.

El Proceso Unificado se caracteriza por ser:

* Iterativo e incremental.
* Centrado en casos de uso.
* Centrado en la arquitectura.
* Orientado a la reducción de riesgos.

Por lo tanto, la funcionalidad “Agregar un nuevo producto” debe desarrollarse considerando estos aspectos.

---

# 1. Caso de uso mejorado

## Nombre del caso de uso

Agregar nuevo producto.

## Actor principal

Administrador o encargado de inventario.

## Objetivo

Permitir que un usuario autorizado registre un nuevo producto en el sistema de inventario.

## Precondiciones

* El usuario debe haber iniciado sesión.
* El usuario debe tener permisos para gestionar productos.
* Deben existir categorías cargadas.
* Deben existir proveedores registrados.

## Postcondiciones

* El producto queda registrado en la base de datos.
* El producto queda con estado “Activo”.
* El sistema registra quién realizó la operación.
* El producto queda disponible para futuras consultas y movimientos de stock.

---

# 2. Flujo principal

1. El usuario ingresa al sistema.
2. El sistema valida sus credenciales.
3. El usuario selecciona la opción “Productos”.
4. El usuario elige “Agregar nuevo producto”.
5. El sistema muestra el formulario de carga.
6. El usuario completa los datos del producto.
7. El usuario presiona el botón “Guardar”.
8. El sistema valida los datos ingresados.
9. El sistema verifica que el código del producto no esté repetido.
10. El sistema registra el producto en la base de datos.
11. El sistema guarda el usuario que realizó la operación.
12. El sistema muestra el mensaje: “Producto agregado correctamente”.

---

# 3. Flujos alternativos

## A1 - Datos obligatorios incompletos

1. El usuario deja uno o más campos obligatorios vacíos.
2. El sistema detecta el error.
3. El sistema muestra un mensaje indicando qué campo falta completar.
4. El usuario corrige la información.
5. El caso de uso continúa desde el paso 7.

---

## A2 - Código de producto repetido

1. El usuario ingresa un código de producto ya existente.
2. El sistema consulta la base de datos.
3. El sistema detecta que el código ya está registrado.
4. El sistema muestra el mensaje: “Ya existe un producto con ese código”.
5. El usuario modifica el código.
6. El caso de uso continúa desde el paso 7.

---

## A3 - Precio inválido

1. El usuario ingresa un precio menor o igual a cero.
2. El sistema valida el dato.
3. El sistema muestra el mensaje: “El precio debe ser mayor a cero”.
4. El usuario corrige el precio.
5. El caso de uso continúa desde el paso 7.

---

## A4 - Stock inválido

1. El usuario ingresa un stock negativo.
2. El sistema valida el dato.
3. El sistema muestra el mensaje: “El stock no puede ser negativo”.
4. El usuario corrige el stock.
5. El caso de uso continúa desde el paso 7.

---

## A5 - Usuario sin permisos

1. El usuario intenta acceder a la opción “Agregar producto”.
2. El sistema verifica sus permisos.
3. El sistema detecta que no tiene autorización.
4. El sistema muestra el mensaje: “No posee permisos para realizar esta acción”.
5. El caso de uso finaliza.

---

# 4. Reglas de negocio mejoradas

La lógica de negocio de la funcionalidad debe cumplir las siguientes reglas:

## RN1 - Código obligatorio

Todo producto debe tener un código identificatorio.

## RN2 - Código único

No pueden existir dos productos con el mismo código.

## RN3 - Nombre obligatorio

Todo producto debe tener un nombre.

## RN4 - Precio válido

El precio debe ser mayor a cero.

## RN5 - Stock actual válido

El stock actual no puede ser negativo.

## RN6 - Stock mínimo válido

El stock mínimo no puede ser negativo.

## RN7 - Stock mínimo coherente

El stock mínimo no debe ser mayor al stock actual al momento de crear el producto.

## RN8 - Categoría obligatoria

Todo producto debe pertenecer a una categoría.

## RN9 - Proveedor obligatorio

Todo producto debe estar asociado a un proveedor.

## RN10 - Estado inicial

Todo producto nuevo se registra con estado “Activo”.

## RN11 - Registro de auditoría

El sistema debe registrar qué usuario realizó el alta del producto y en qué fecha.

---

# 5. Mejora desde el Proceso Unificado

## Enfoque iterativo e incremental

En lugar de desarrollar toda la funcionalidad completa de una sola vez, se propone dividirla en iteraciones.

### Iteración 1

Alta básica de producto.

Incluye:

* Código.
* Nombre.
* Precio.
* Stock actual.

### Iteración 2

Validaciones de negocio.

Incluye:

* Código único.
* Precio mayor a cero.
* Stock no negativo.
* Campos obligatorios.

### Iteración 3

Relaciones con otras entidades.

Incluye:

* Categoría.
* Proveedor.
* Estado del producto.

### Iteración 4

Control de permisos y auditoría.

Incluye:

* Usuario autorizado.
* Registro de fecha de alta.
* Usuario que realizó la operación.

De esta manera, la funcionalidad se construye por partes, permitiendo revisar y corregir antes de avanzar.

---

# 6. Riesgos detectados

Aplicando el Proceso Unificado, también se deben identificar riesgos tempranos.

| Riesgo                            | Impacto                                  | Solución propuesta                            |
| --------------------------------- | ---------------------------------------- | --------------------------------------------- |
| Código de producto repetido       | Genera duplicación de datos              | Validar código único antes de guardar         |
| Stock negativo                    | Produce inconsistencias en el inventario | Validar que el stock sea mayor o igual a cero |
| Usuario sin permisos              | Riesgo de seguridad                      | Controlar permisos antes de permitir el alta  |
| Datos incompletos                 | Producto mal registrado                  | Validar campos obligatorios                   |
| Error al guardar en base de datos | El producto no queda registrado          | Manejar excepciones y mostrar mensaje claro   |
| Falta de auditoría                | No se sabe quién cargó el producto       | Registrar usuario y fecha de operación        |

---

# 7. Arquitectura propuesta

Para mejorar el diseño se mantiene una arquitectura en capas:

```text
Pantalla Agregar Producto
        ↓
ProductoController
        ↓
ProductoService
        ↓
ProductoRepository
        ↓
Base de Datos
```

## Capa de presentación

Contiene el formulario donde el usuario ingresa los datos del producto.

## Controlador

Recibe los datos desde la pantalla y los envía a la lógica de negocio.

## Servicio

Contiene las reglas de negocio y validaciones.

## Repositorio

Se encarga de guardar y consultar productos en la base de datos.

## Base de datos

Almacena la información del producto.

---

# 8. Diagrama de clases mejorado

```text
┌────────────────────────────┐
│         Producto           │
├────────────────────────────┤
│ - idProducto: int          │
│ - codigoProducto: string   │
│ - nombreProducto: string   │
│ - descripcion: string      │
│ - precio: decimal          │
│ - stockActual: int         │
│ - stockMinimo: int         │
│ - estado: string           │
│ - idCategoria: int         │
│ - idProveedor: int         │
│ - fechaAlta: DateTime      │
│ - idUsuarioAlta: int       │
└────────────────────────────┘

┌────────────────────────────┐
│      ProductoService       │
├────────────────────────────┤
│ + agregarProducto()        │
│ + validarProducto()        │
│ + verificarCodigoUnico()   │
│ + asignarEstadoInicial()   │
└────────────────────────────┘

┌────────────────────────────┐
│    ProductoRepository      │
├────────────────────────────┤
│ + guardar()                │
│ + existeCodigo()           │
│ + buscarPorCodigo()        │
└────────────────────────────┘

┌────────────────────────────┐
│      AuditoriaService      │
├────────────────────────────┤
│ + registrarAltaProducto()  │
└────────────────────────────┘
```

---

# 9. Lógica de negocio mejorada en pseudocódigo

```text
Inicio

Recibir datos del producto y usuario actual

Verificar si el usuario tiene permiso para agregar productos

Si el usuario no tiene permiso
    Mostrar "No posee permisos para realizar esta acción"
    Finalizar
Fin Si

Validar que el código no esté vacío

Validar que el nombre no esté vacío

Validar que el precio sea mayor a cero

Validar que el stock actual no sea negativo

Validar que el stock mínimo no sea negativo

Validar que el stock mínimo no sea mayor al stock actual

Validar que se haya seleccionado una categoría

Validar que se haya seleccionado un proveedor

Verificar que el código del producto no exista en la base de datos

Si el código ya existe
    Mostrar "Ya existe un producto con ese código"
    Finalizar
Fin Si

Asignar estado "Activo"

Asignar fecha de alta

Asignar usuario que realiza el alta

Guardar producto en la base de datos

Registrar operación en auditoría

Mostrar "Producto agregado correctamente"

Fin
```

---

# 10. Implementación mejorada en C#

```csharp
public class ProductoService
{
    private ProductoRepository productoRepository;
    private AuditoriaService auditoriaService;

    public ProductoService()
    {
        productoRepository = new ProductoRepository();
        auditoriaService = new AuditoriaService();
    }

    public string AgregarProducto(Producto producto, Usuario usuarioActual)
    {
        if (usuarioActual == null)
        {
            return "Debe iniciar sesión para realizar esta acción.";
        }

        if (!usuarioActual.TienePermiso("AGREGAR_PRODUCTO"))
        {
            return "No posee permisos para realizar esta acción.";
        }

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
        producto.FechaAlta = DateTime.Now;
        producto.IdUsuarioAlta = usuarioActual.IdUsuario;

        productoRepository.Guardar(producto);

        auditoriaService.RegistrarAltaProducto(producto, usuarioActual);

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

# 11. Clase Producto mejorada

```csharp
public class Producto
{
    public int IdProducto { get; set; }
    public string CodigoProducto { get; set; }
    public string NombreProducto { get; set; }
    public string Descripcion { get; set; }
    public decimal Precio { get; set; }
    public int StockActual { get; set; }
    public int StockMinimo { get; set; }
    public string Estado { get; set; }
    public int IdCategoria { get; set; }
    public int IdProveedor { get; set; }
    public DateTime FechaAlta { get; set; }
    public int IdUsuarioAlta { get; set; }
}
```

---

# 12. Clase Usuario

```csharp
public class Usuario
{
    public int IdUsuario { get; set; }
    public string NombreUsuario { get; set; }
    public List<string> Permisos { get; set; }

    public bool TienePermiso(string permiso)
    {
        return Permisos.Contains(permiso);
    }
}
```

---

# 13. Servicio de auditoría

```csharp
public class AuditoriaService
{
    public void RegistrarAltaProducto(Producto producto, Usuario usuario)
    {
        Console.WriteLine("Alta de producto registrada");
        Console.WriteLine("Producto: " + producto.NombreProducto);
        Console.WriteLine("Usuario: " + usuario.NombreUsuario);
        Console.WriteLine("Fecha: " + DateTime.Now);
    }
}
```

---

# 14. Pruebas propuestas

Aplicando el Proceso Unificado, cada iteración debe finalizar con pruebas.

## Pruebas unitarias

| Caso                               | Resultado esperado      |
| ---------------------------------- | ----------------------- |
| Producto válido                    | Se guarda correctamente |
| Código vacío                       | Muestra error           |
| Nombre vacío                       | Muestra error           |
| Precio negativo                    | Muestra error           |
| Stock negativo                     | Muestra error           |
| Stock mínimo mayor al stock actual | Muestra error           |
| Código repetido                    | Muestra error           |
| Usuario sin permisos               | Muestra error           |

## Pruebas de integración

| Prueba                    | Componentes involucrados                                     |
| ------------------------- | ------------------------------------------------------------ |
| Alta correcta de producto | Pantalla, controlador, servicio, repositorio y base de datos |
| Alta con código repetido  | Servicio, repositorio y base de datos                        |
| Alta sin permisos         | Usuario, controlador y servicio                              |
| Registro de auditoría     | Servicio, auditoría y base de datos                          |

---

# 15. Mejoras realizadas respecto al ejercicio original

Las principales mejoras incorporadas son:

1. Se agregó control de permisos del usuario.
2. Se agregó registro de auditoría.
3. Se agregó fecha de alta del producto.
4. Se agregó usuario que realizó el alta.
5. Se mejoraron las reglas de negocio.
6. Se identificaron riesgos del caso de uso.
7. Se dividió el desarrollo en iteraciones.
8. Se mantuvo una arquitectura en capas.
9. Se agregaron pruebas por iteración.
10. Se aplicó el enfoque centrado en casos de uso.

---

# Conclusión

Al aplicar los conceptos del Proceso Unificado, la funcionalidad “Agregar un nuevo producto” queda mejor definida, más ordenada y más completa. Ya no se trata solamente de escribir código, sino de desarrollar una funcionalidad considerando análisis, diseño, arquitectura, riesgos, implementación y pruebas.

Además, al trabajar de forma iterativa e incremental, el sistema puede construirse por partes, permitiendo detectar errores temprano y mejorar la calidad del producto final.
