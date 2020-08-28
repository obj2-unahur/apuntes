# Guía mega exprés sobre Local Date y LocalDateTime
Básicamente son objetos que sirven para represtar una hora y/o fecha respectivamente (Date sólo para fechas y DateTime para fecha y hora).
## Métodos que pueden ser de interes
``` kotlin
val fechaActual = LocalDateTime.now() //Instancia de LocalDateTime con los valores de la fecha y hora actual del sistema.
>>> 2020-08-28T 03:16:08
  
val declaracionDeIndependencia = LocalDateTime.of(1816,7,9, 11, 30) //Instancia de LocalDateTime con valores que recibe por parametro.
>>> 1986-07-09T 11:30

fechaActual.isAfter(declaracionDeIndependencia) //Devuelve un booleano comparando si una fecha viene despues que otra.
>>> true

fechaActual.isBefore(declaracionDeIndependencia)  //Cómo arriba pero esto pregunta si fue antes.
>>>false
```
Con esto ya estarías para hacer el trabajo de esta semana, igual acá te dejo la [documentación oficial](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDateTime.html) por si querés chusmear algo más. 
