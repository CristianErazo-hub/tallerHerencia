# Taller Herencia - Ejercicio 1

Implementación en Java con Maven del ejercicio de cuentas bancarias usando herencia.

## Estructura del proyecto

- `Cuenta`: clase base con operaciones comunes para manejo de saldo, consignaciones, retiros, interés y extracto mensual.
- `CuentaAhorros`: hereda de `Cuenta` y controla el estado activo/inactivo según el saldo.
- `CuentaCorriente`: hereda de `Cuenta` y permite manejo de sobregiro.
- `App`: clase principal con un ejemplo de uso.

## Diagrama de clases

```mermaid
classDiagram
    class Cuenta {
        #float saldo
        #int numeroConsignaciones
        #int numeroRetiros
        #float tasaAnual
        #float comisionMensual
        +Cuenta(float saldo, float tasaAnual)
        +consignar(float cantidad) void
        +retirar(float cantidad) void
        +calcularInteres() void
        +extractoMensual() void
        +imprimir() void
    }

    class CuentaAhorros {
        -boolean activa
        +CuentaAhorros(float saldo, float tasaAnual)
        +consignar(float cantidad) void
        +retirar(float cantidad) void
        +extractoMensual() void
        +imprimir() void
    }

    class CuentaCorriente {
        -float sobregiro
        +CuentaCorriente(float saldo, float tasaAnual)
        +consignar(float cantidad) void
        +retirar(float cantidad) void
        +extractoMensual() void
        +imprimir() void
    }

    CuentaAhorros --|> Cuenta
    CuentaCorriente --|> Cuenta
```

## Requisitos

- Java 17 o superior.
- Maven 3.9 o superior.

## Compilación y ejecución

```bash
mvn package
java -cp target/taller-herencia-1.0-SNAPSHOT.jar com.taller.herencia.App
```
