# Guía mega exprés sobre LocalDate y LocalDateTime

Básicamente son clases nativas de Java 8, que sirven para representar momentos en el tiempo. Como hemos dicho en alguna otra oportunidad, en Kotlin se puede usar cualquier clase de Java, y por eso es que Kotlin no incluye una API propia para manejar fechas.

Con `LocalDate` podemos representar una fecha, y con `LocalDateTime` una fecha y una hora.

## Métodos que pueden ser de interés

``` kotlin
// Instancia de LocalDateTime con los valores de la fecha y hora actual del sistema.
val fechaActual = LocalDateTime.now()
>>> 2020-08-28T 03:16:08
  
// Instancia de LocalDate (sin hora) con valores que recibe por parámetro. 
// Notar que el orden es de mayor a menor: año, mes, día
val renunciaDeLaRua = LocalDate.of(2001, 12, 20) 
>>> 2001-12-20

// Devuelve un booleano indicando si la fecha es posterior a la que viene por parámetro.
fechaActual.isAfter(renunciaDeLaRua) 
>>> true

// Como arriba, pero al revés.
fechaActual.isBefore(renunciaDeLaRua)
>>> false
```

Esto es bien bien básico, pero suficiente para resolver el ejercicio de Servidor Web. Te dejamos la documentación oficial de [`LocalDateTime`](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDateTime.html) y la de [`LocalDate`](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDate.html) por si querés chusmear algo más. 
