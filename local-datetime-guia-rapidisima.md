# Guía mega exprés sobre LocalDate y LocalDateTime

Básicamente son objetos que sirven para represtar una hora y/o fecha respectivamente (Date sólo para fechas y DateTime para fecha y hora).

## Métodos que pueden ser de interés

``` kotlin
// Instancia de LocalDateTime con los valores de la fecha y hora actual del sistema.
val fechaActual = LocalDateTime.now()
// >>> 2020-08-28T 03:16:08
  
// Instancia de LocalDate (sin hora) con valores que recibe por parámetro.
val renunciaDeLaRua = LocalDate.of(2001, 12, 20) 
// >>> 2001-12-20

// Devuelve un booleano indicando si la fecha es posterior a la que viene por parámetro.
fechaActual.isAfter(renunciaDeLaRua) 
// >>> true

// Como arriba, pero al revés.
fechaActual.isBefore(renunciaDeLaRua)
// >>> false
```

Con esto ya estarías para hacer el trabajo de la semana 3, igual acá te dejamos la [documentación oficial](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDateTime.html) por si querés chusmear algo más. 
