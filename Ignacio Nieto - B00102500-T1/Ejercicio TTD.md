# Ejercicio 13 - Desarrollo de una aplicación bancaria usando TDD

## Enunciado

Se debe desarrollar una aplicación informática utilizando la técnica **TDD** para gestionar cuentas bancarias.
El sistema debe permitir:

* Abrir una cuenta bancaria.
* Consultar el saldo inicial.
* Realizar depósitos.
* Realizar retiros.
* Transferir fondos entre cuentas.
* Validar situaciones excepcionales.

La técnica **TDD**, o **Test Driven Development**, propone escribir primero las pruebas y luego implementar el código necesario para que esas pruebas pasen.

---

# Etapa 1: Especificación y prueba inicial

## 1. Requisitos básicos del sistema

## Requisitos funcionales

### RF1 - Abrir cuenta bancaria

El sistema debe permitir crear una cuenta bancaria con un número de cuenta, titular y saldo inicial.

### RF2 - Consultar saldo

El sistema debe permitir consultar el saldo disponible de una cuenta.

### RF3 - Depositar fondos

El sistema debe permitir realizar depósitos en una cuenta bancaria.

### RF4 - Retirar fondos

El sistema debe permitir retirar dinero de una cuenta, siempre que haya saldo suficiente.

### RF5 - Transferir fondos

El sistema debe permitir transferir dinero desde una cuenta origen hacia una cuenta destino.

### RF6 - Validar operaciones inválidas

El sistema debe evitar:

* Depósitos negativos o iguales a cero.
* Retiros negativos o iguales a cero.
* Retiros mayores al saldo disponible.
* Transferencias a cuentas inexistentes.
* Transferencias con saldo insuficiente.

---

## Requisitos no funcionales

### RNF1 - Confiabilidad

El sistema debe mantener correctamente el saldo de las cuentas.

### RNF2 - Seguridad

El sistema no debe permitir operaciones inválidas.

### RNF3 - Mantenibilidad

El código debe estar ordenado para poder agregar nuevas funcionalidades.

### RNF4 - Claridad

Los mensajes de error deben ser claros.

### RNF5 - Testeabilidad

Todas las funcionalidades principales deben estar cubiertas por pruebas automatizadas.

---

## 2. Prueba inicial: crear cuenta y obtener saldo inicial

Siguiendo TDD, primero se escribe una prueba que inicialmente fallará porque todavía no existe la implementación.

```csharp
[TestClass]
public class CuentaBancariaTests
{
    [TestMethod]
    public void CrearCuenta_DeberiaTenerSaldoInicial()
    {
        // Arrange
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

        // Act
        decimal saldo = cuenta.ObtenerSaldo();

        // Assert
        Assert.AreEqual(1000, saldo);
    }
}
```

---

# Etapa 2: Desarrollo de las funcionalidades básicas

## 3. Implementar la funcionalidad para abrir una cuenta bancaria

Después de escribir la prueba inicial, se implementa el código mínimo para que la prueba pase.

```csharp
public class CuentaBancaria
{
    public string NumeroCuenta { get; private set; }
    public string Titular { get; private set; }
    private decimal saldo;

    public CuentaBancaria(string numeroCuenta, string titular, decimal saldoInicial)
    {
        NumeroCuenta = numeroCuenta;
        Titular = titular;
        saldo = saldoInicial;
    }

    public decimal ObtenerSaldo()
    {
        return saldo;
    }
}
```

---

## 4. Implementar la funcionalidad de depósito

Primero se escribe la prueba.

```csharp
[TestMethod]
public void Depositar_MontoValido_DeberiaAumentarSaldo()
{
    // Arrange
    CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

    // Act
    cuenta.Depositar(500);

    // Assert
    Assert.AreEqual(1500, cuenta.ObtenerSaldo());
}
```

Ahora se implementa el método `Depositar`.

```csharp
public void Depositar(decimal monto)
{
    if (monto <= 0)
    {
        throw new ArgumentException("El monto a depositar debe ser mayor a cero.");
    }

    saldo += monto;
}
```

---

## 5. Implementar la funcionalidad de retiro

Primero se escribe la prueba.

```csharp
[TestMethod]
public void Retirar_MontoValido_DeberiaDisminuirSaldo()
{
    // Arrange
    CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

    // Act
    cuenta.Retirar(300);

    // Assert
    Assert.AreEqual(700, cuenta.ObtenerSaldo());
}
```

Ahora se implementa el método `Retirar`.

```csharp
public void Retirar(decimal monto)
{
    if (monto <= 0)
    {
        throw new ArgumentException("El monto a retirar debe ser mayor a cero.");
    }

    if (monto > saldo)
    {
        throw new InvalidOperationException("Saldo insuficiente.");
    }

    saldo -= monto;
}
```

---

## 6. Implementar la funcionalidad de transferencia

Primero se escribe la prueba.

```csharp
[TestMethod]
public void Transferir_MontoValido_DeberiaDescontarYAgregarSaldo()
{
    // Arrange
    CuentaBancaria cuentaOrigen = new CuentaBancaria("001", "Ignacio", 1000);
    CuentaBancaria cuentaDestino = new CuentaBancaria("002", "Juan", 500);

    // Act
    cuentaOrigen.Transferir(cuentaDestino, 300);

    // Assert
    Assert.AreEqual(700, cuentaOrigen.ObtenerSaldo());
    Assert.AreEqual(800, cuentaDestino.ObtenerSaldo());
}
```

Ahora se implementa el método `Transferir`.

```csharp
public void Transferir(CuentaBancaria cuentaDestino, decimal monto)
{
    if (cuentaDestino == null)
    {
        throw new ArgumentException("La cuenta destino no existe.");
    }

    Retirar(monto);
    cuentaDestino.Depositar(monto);
}
```

---

# Etapa 3: Pruebas adicionales y mejoras

## 7. Pruebas adicionales para casos específicos

Además de probar los casos correctos, se deben probar situaciones excepcionales.

---

## Prueba: no permitir depósito negativo

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentException))]
public void Depositar_MontoNegativo_DeberiaLanzarExcepcion()
{
    // Arrange
    CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

    // Act
    cuenta.Depositar(-100);
}
```

---

## Prueba: no permitir depósito igual a cero

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentException))]
public void Depositar_MontoCero_DeberiaLanzarExcepcion()
{
    // Arrange
    CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

    // Act
    cuenta.Depositar(0);
}
```

---

## Prueba: no permitir retiro mayor al saldo disponible

```csharp
[TestMethod]
[ExpectedException(typeof(InvalidOperationException))]
public void Retirar_MontoMayorAlSaldo_DeberiaLanzarExcepcion()
{
    // Arrange
    CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

    // Act
    cuenta.Retirar(1500);
}
```

---

## Prueba: no permitir retiro negativo

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentException))]
public void Retirar_MontoNegativo_DeberiaLanzarExcepcion()
{
    // Arrange
    CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

    // Act
    cuenta.Retirar(-200);
}
```

---

## Prueba: no permitir transferencia con saldo insuficiente

```csharp
[TestMethod]
[ExpectedException(typeof(InvalidOperationException))]
public void Transferir_SaldoInsuficiente_DeberiaLanzarExcepcion()
{
    // Arrange
    CuentaBancaria cuentaOrigen = new CuentaBancaria("001", "Ignacio", 500);
    CuentaBancaria cuentaDestino = new CuentaBancaria("002", "Juan", 100);

    // Act
    cuentaOrigen.Transferir(cuentaDestino, 1000);
}
```

---

## Prueba: no permitir transferencia a cuenta inexistente

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentException))]
public void Transferir_CuentaDestinoInexistente_DeberiaLanzarExcepcion()
{
    // Arrange
    CuentaBancaria cuentaOrigen = new CuentaBancaria("001", "Ignacio", 1000);

    // Act
    cuentaOrigen.Transferir(null, 300);
}
```

---

# 8. Ejecución de todas las pruebas

Luego de implementar cada funcionalidad, se ejecutan todas las pruebas para verificar que el sistema funcione correctamente.

Las pruebas esperadas son:

| Prueba                            | Resultado esperado           |
| --------------------------------- | ---------------------------- |
| Crear cuenta con saldo inicial    | Pasa                         |
| Depositar monto válido            | Pasa                         |
| Retirar monto válido              | Pasa                         |
| Transferir monto válido           | Pasa                         |
| Depositar monto negativo          | Pasa, porque lanza excepción |
| Depositar monto cero              | Pasa, porque lanza excepción |
| Retirar más dinero del disponible | Pasa, porque lanza excepción |
| Retirar monto negativo            | Pasa, porque lanza excepción |
| Transferir con saldo insuficiente | Pasa, porque lanza excepción |
| Transferir a cuenta inexistente   | Pasa, porque lanza excepción |

---

# 9. Refactorización del código

Después de verificar que las pruebas pasan, se puede mejorar el código para hacerlo más claro.

Una mejora posible es crear un método privado para validar montos.

```csharp
private void ValidarMonto(decimal monto, string operacion)
{
    if (monto <= 0)
    {
        throw new ArgumentException($"El monto a {operacion} debe ser mayor a cero.");
    }
}
```

Código refactorizado:

```csharp
public class CuentaBancaria
{
    public string NumeroCuenta { get; private set; }
    public string Titular { get; private set; }
    private decimal saldo;

    public CuentaBancaria(string numeroCuenta, string titular, decimal saldoInicial)
    {
        if (string.IsNullOrWhiteSpace(numeroCuenta))
        {
            throw new ArgumentException("El número de cuenta es obligatorio.");
        }

        if (string.IsNullOrWhiteSpace(titular))
        {
            throw new ArgumentException("El titular es obligatorio.");
        }

        if (saldoInicial < 0)
        {
            throw new ArgumentException("El saldo inicial no puede ser negativo.");
        }

        NumeroCuenta = numeroCuenta;
        Titular = titular;
        saldo = saldoInicial;
    }

    public decimal ObtenerSaldo()
    {
        return saldo;
    }

    public void Depositar(decimal monto)
    {
        ValidarMonto(monto, "depositar");
        saldo += monto;
    }

    public void Retirar(decimal monto)
    {
        ValidarMonto(monto, "retirar");

        if (monto > saldo)
        {
            throw new InvalidOperationException("Saldo insuficiente.");
        }

        saldo -= monto;
    }

    public void Transferir(CuentaBancaria cuentaDestino, decimal monto)
    {
        if (cuentaDestino == null)
        {
            throw new ArgumentException("La cuenta destino no existe.");
        }

        Retirar(monto);
        cuentaDestino.Depositar(monto);
    }

    private void ValidarMonto(decimal monto, string operacion)
    {
        if (monto <= 0)
        {
            throw new ArgumentException($"El monto a {operacion} debe ser mayor a cero.");
        }
    }
}
```

---

# 10. Ejecución de pruebas después de refactorizar

Después de la refactorización, se ejecutan nuevamente todas las pruebas.

El objetivo es comprobar que los cambios internos del código no hayan roto ninguna funcionalidad.

Resultado esperado:

```text
Todas las pruebas pasan correctamente.
```

Esto confirma que la refactorización mejoró el código sin modificar el comportamiento esperado del sistema.

---

# Etapa 4: Cobertura completa de pruebas

## 11. Funcionalidades cubiertas por pruebas automatizadas

| Funcionalidad                      | ¿Tiene prueba? |
| ---------------------------------- | -------------- |
| Crear cuenta bancaria              | Sí             |
| Consultar saldo inicial            | Sí             |
| Depositar fondos                   | Sí             |
| Retirar fondos                     | Sí             |
| Transferir fondos                  | Sí             |
| Validar depósito inválido          | Sí             |
| Validar retiro inválido            | Sí             |
| Validar transferencia inválida     | Sí             |
| Validar saldo insuficiente         | Sí             |
| Validar cuenta destino inexistente | Sí             |

---

## 12. Casos límite y situaciones excepcionales

### Caso límite 1: saldo inicial negativo

El sistema no debe permitir crear una cuenta con saldo inicial negativo.

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentException))]
public void CrearCuenta_SaldoInicialNegativo_DeberiaLanzarExcepcion()
{
    CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", -100);
}
```

---

### Caso límite 2: número de cuenta vacío

El sistema no debe permitir crear una cuenta sin número.

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentException))]
public void CrearCuenta_NumeroVacio_DeberiaLanzarExcepcion()
{
    CuentaBancaria cuenta = new CuentaBancaria("", "Ignacio", 1000);
}
```

---

### Caso límite 3: titular vacío

El sistema no debe permitir crear una cuenta sin titular.

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentException))]
public void CrearCuenta_TitularVacio_DeberiaLanzarExcepcion()
{
    CuentaBancaria cuenta = new CuentaBancaria("001", "", 1000);
}
```

---

## 13. Resultado final de las pruebas

Luego de ejecutar todas las pruebas, el sistema cumple con los requisitos establecidos.

```text
Resultado final:
Todas las pruebas fueron ejecutadas correctamente.
El sistema permite abrir cuentas, consultar saldo, depositar, retirar y transferir fondos.
También controla errores como saldos negativos, montos inválidos, saldo insuficiente y cuentas inexistentes.
```

---

# Código final completo

## Clase CuentaBancaria

```csharp
public class CuentaBancaria
{
    public string NumeroCuenta { get; private set; }
    public string Titular { get; private set; }
    private decimal saldo;

    public CuentaBancaria(string numeroCuenta, string titular, decimal saldoInicial)
    {
        if (string.IsNullOrWhiteSpace(numeroCuenta))
        {
            throw new ArgumentException("El número de cuenta es obligatorio.");
        }

        if (string.IsNullOrWhiteSpace(titular))
        {
            throw new ArgumentException("El titular es obligatorio.");
        }

        if (saldoInicial < 0)
        {
            throw new ArgumentException("El saldo inicial no puede ser negativo.");
        }

        NumeroCuenta = numeroCuenta;
        Titular = titular;
        saldo = saldoInicial;
    }

    public decimal ObtenerSaldo()
    {
        return saldo;
    }

    public void Depositar(decimal monto)
    {
        ValidarMonto(monto, "depositar");
        saldo += monto;
    }

    public void Retirar(decimal monto)
    {
        ValidarMonto(monto, "retirar");

        if (monto > saldo)
        {
            throw new InvalidOperationException("Saldo insuficiente.");
        }

        saldo -= monto;
    }

    public void Transferir(CuentaBancaria cuentaDestino, decimal monto)
    {
        if (cuentaDestino == null)
        {
            throw new ArgumentException("La cuenta destino no existe.");
        }

        Retirar(monto);
        cuentaDestino.Depositar(monto);
    }

    private void ValidarMonto(decimal monto, string operacion)
    {
        if (monto <= 0)
        {
            throw new ArgumentException($"El monto a {operacion} debe ser mayor a cero.");
        }
    }
}
```

---

## Clase de pruebas completa

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using System;

[TestClass]
public class CuentaBancariaTests
{
    [TestMethod]
    public void CrearCuenta_DeberiaTenerSaldoInicial()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

        decimal saldo = cuenta.ObtenerSaldo();

        Assert.AreEqual(1000, saldo);
    }

    [TestMethod]
    public void Depositar_MontoValido_DeberiaAumentarSaldo()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

        cuenta.Depositar(500);

        Assert.AreEqual(1500, cuenta.ObtenerSaldo());
    }

    [TestMethod]
    public void Retirar_MontoValido_DeberiaDisminuirSaldo()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

        cuenta.Retirar(300);

        Assert.AreEqual(700, cuenta.ObtenerSaldo());
    }

    [TestMethod]
    public void Transferir_MontoValido_DeberiaDescontarYAgregarSaldo()
    {
        CuentaBancaria cuentaOrigen = new CuentaBancaria("001", "Ignacio", 1000);
        CuentaBancaria cuentaDestino = new CuentaBancaria("002", "Juan", 500);

        cuentaOrigen.Transferir(cuentaDestino, 300);

        Assert.AreEqual(700, cuentaOrigen.ObtenerSaldo());
        Assert.AreEqual(800, cuentaDestino.ObtenerSaldo());
    }

    [TestMethod]
    [ExpectedException(typeof(ArgumentException))]
    public void Depositar_MontoNegativo_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

        cuenta.Depositar(-100);
    }

    [TestMethod]
    [ExpectedException(typeof(ArgumentException))]
    public void Depositar_MontoCero_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

        cuenta.Depositar(0);
    }

    [TestMethod]
    [ExpectedException(typeof(InvalidOperationException))]
    public void Retirar_MontoMayorAlSaldo_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

        cuenta.Retirar(1500);
    }

    [TestMethod]
    [ExpectedException(typeof(ArgumentException))]
    public void Retirar_MontoNegativo_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", 1000);

        cuenta.Retirar(-200);
    }

    [TestMethod]
    [ExpectedException(typeof(InvalidOperationException))]
    public void Transferir_SaldoInsuficiente_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuentaOrigen = new CuentaBancaria("001", "Ignacio", 500);
        CuentaBancaria cuentaDestino = new CuentaBancaria("002", "Juan", 100);

        cuentaOrigen.Transferir(cuentaDestino, 1000);
    }

    [TestMethod]
    [ExpectedException(typeof(ArgumentException))]
    public void Transferir_CuentaDestinoInexistente_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuentaOrigen = new CuentaBancaria("001", "Ignacio", 1000);

        cuentaOrigen.Transferir(null, 300);
    }

    [TestMethod]
    [ExpectedException(typeof(ArgumentException))]
    public void CrearCuenta_SaldoInicialNegativo_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "Ignacio", -100);
    }

    [TestMethod]
    [ExpectedException(typeof(ArgumentException))]
    public void CrearCuenta_NumeroVacio_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuenta = new CuentaBancaria("", "Ignacio", 1000);
    }

    [TestMethod]
    [ExpectedException(typeof(ArgumentException))]
    public void CrearCuenta_TitularVacio_DeberiaLanzarExcepcion()
    {
        CuentaBancaria cuenta = new CuentaBancaria("001", "", 1000);
    }
}
```

---

# Conclusión

Aplicando TDD, el desarrollo de la aplicación bancaria se realizó siguiendo el ciclo:

```text
Prueba → Código → Refactorización
```

Primero se definieron los requisitos y se escribieron las pruebas. Luego se implementó el código necesario para que las pruebas pasaran. Finalmente, se refactorizó el código para mejorar su estructura sin modificar su comportamiento.

Gracias a este enfoque, el sistema queda más confiable, mantenible y preparado para futuras mejoras.
