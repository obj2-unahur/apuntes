# Colecciones de Wollok a Kotlin
Cómo se menciona en el titulo lo que se busca con este trabajo es dar un primer acercamiento hacia lo que es Kotlin comparandolo directamente con
la herramienta que ya conocen que es Wollok.

Antes de empezar cabe destacar que a diferenca de Wollok dónde teniamos tres tipos de colecciones (Set,  Maps y Lists) en Kotlin existen, además  las listas:
 * **readOnly:** Cómo su nombre lo indica (sólo lectura) unicamente provee operaciones para acceder a los elemtos de la colección.
 * **mutables:** que permiten un mayor dinamismo sobre las colecciones permitiendo modificar los elementos de su interior (agregar, remover, actualizar).

## Cosas que se puenden hacer con las colecciones:
### Ejecutar una accion sobre todos los elementos de la colección: Por ejemplo cómo se viene el cumple de Pepita todas sus amigas aves tienen que ir hasta su casa.

En Wollok se hacía así te acordás?
```wollok
avesAmigas.forEach({ aveAmiga => aveAmiga.volarHataLoDePepita()}) 
```

En cambio en Kotlin...
``` kotlin
avesAmigas.forEach({ aveAmiga -> aveAmiga.volarHataLoDePepita()}) 
```
No hay mucha diferencia en vez de usar  **"=>"**  usa  **"->"**.


### Agregar un elemento: Por ejemplo Batman tiene que agarrar al Guasón que tiene su base en el pacifico y necesita un gadget indispensable.
``` wollok
var baticituron = new List["Batarang", "Batillaves del batimovil", "Bati celular"]
baticituron.add("Bati repelente contra tiburones")
```

``` kotlin
val baticituron = mutableListOf("Batarang", "Batillaves del batimovil", "Bati celular")
baticituron.add("Bati repelente contra tiburones")

[Batarang, Batillaves del batimovil, Bati celular, Bati repelente contra tiburones]
```

Ojo al tejo, tambien podes agregarlo donde quieras pasandole un posicion.
``` kotlin
baticituron.add(1, "Bati repelente contra tiburones")

[Batarang, Bati repelente contra tiburones, Batillaves del batimovil, Bati celular]
```

### Eliminar un elemento: Por ejemplo Ash se va a enfrentar al lider de gimnasio de piedra por lo qué Pikachu no va a ser eficaz.
``` wollok
equipo.remove(pikachu)
```

``` kotlin
equipo.remove(pikachu) 
```
o tambien si a Ash se le ocurre bochar al primer integrante de su equipo podemos hacer así :sunglasses: .. 
``` kotlin
equipo.removeAt(0) //Acordate que el indice de las listas siempre empieza en 0.
```

## Mensajes iguales: 
- ``clear()``  Para borrar todos elementos de la lista.
- ```size``` Devuelve el  tamaño de la lista.
- ```isEmpty()``` Pregunta si esta vacia.
- ```contains(element)``` Pregunta contiene un elemento por parametro.
- ```max()``` Devuelve el valor maximo. Por ende tambien ```min()``` que hace lo mismo pero al reves.
- ```sum()``` Suma valores de los elemntos.
- ```any({elemento -> elemento condicion})``` Pregunta si algun elemento de la coleccion cumple una condicion.
- ```all({elemento -> elemento condicion})``` Pregunta si todos elementos de la coleccion cumplen una condicion.
- ```find({elemento -> elemento condicion})``` Devulve un elemento que haya cumplido una condicion.
- ```first()``` Devuelve el primer elemento de una coleccion, contrario a esto ```last()``` devuelve el ultimo, peeero tambien se puede usar  ```get(posicion)``` y que devuelva el elemento en ese lugar












