# De Wollok a Kotlin

Cómo se menciona en el titulo con el presente, lo que se busca es dar un primer acercamiento hacia lo que es Kotlin comparándolo directamente con
la herramienta que ya conocen que es Wollok.

Antes de empezar cabe destacar que a diferencia de Wollok dónde teníamos tres tipos de colecciones (Set,  Maps y Lists) en Kotlin si bien son las mismas tienen una diferencia:

* **readOnly:** Cómo su nombre lo indica (sólo lectura) únicamente provee operaciones para acceder a los elementos de la colección y se definen así: listOf, setOf y mapOf.

* **mutables:** Que permiten un mayor dinamismo sobre las colecciones permitiendo modificar los elementos de su interior (agregar, sacar, actualizar).
y se definen así : mutableListOf, mutableSetOf y mutableMapOf.

Podés pensar esto como algo similar a lo que en Wollok hacías con ```const``` y con ```var``` usando una para un valor fijo y la otra para uno que podía cambiar.

## Cosas que se pueden hacer con las colecciones: 

### Ejecutar una acción sobre todos los elementos de la colección: Por ejemplo, cómo se viene el cumple de Pepita (y como la cuarentena no rige para las aves) todas sus amigas están planeando ir hasta su casa.

En Wollok se hacía así ¿Te acordás?
```wollok
avesAmigas.forEach({ aveAmiga => aveAmiga.volarHastaLoDePepita()}) 
```

En cambio, en Kotlin...

``` kotlin
avesAmigas.forEach({ aveAmiga -> aveAmiga.volarHastaLoDePepita()}) 
```
No hay mucha diferencia como te darás cuenta en vez de usar ```=>``` en Kotlin se usa ```->```. Peeero si usamos la forma cheta de Kotlin quedaría así:
``` kotlin
avesAmigas.forEach(it.volarHastaLoDePepita()) 
```
Como ves, existe una palabra reservada ```it``` que nos quita la necesidad de hacer lambdas



### Agregar un elemento: Cómo pepita es un ser muy social siempre está haciendo amigos.
**Wollok**
``` wollok
avesAmigas.add(nuevoAmigo)
```

**Kotlin**
``` kotlin
avesAmigas.add(nuevoAmigo)
```


### Eliminar un elemento: Si bien la idea era que todos vayan a la fiesta hubo aves que no pudieron asistir y como pepita es bastante particular dijo (en idioma pepita claro) "El que no vino a mi cumpleaños es porque no es mi amigo".

**Wollok**
``` wollok
avesAmigas.remove(exAmigo)
```

**Kotlin**
``` kotlin
avesAmigas.remove(exAmigo)
```


### Cómo te habrás dado cuenta los mensajes entre ambos lenguajes son muy similares (por no decir iguales) acá podés chusmear algunos:
- ``clear()``  Para borrar todos elementos de la lista.
- ```size``` Devuelve el tamaño de la lista.
- ```isEmpty()``` Pregunta si está vacía.
- ```contains(element)``` Pregunta contiene un elemento por parámetro.
- ```max()``` Devuelve el valor máximo. Por ende también ```min()``` que hace lo mismo pero al revés.
- ```sum()``` Suma valores de los elementos.
- ```any({elemento -> elemento condición})``` Pregunta si algún elemento de la colección cumple una condición.
- ```all({elemento -> elemento condición})``` Pregunta si todos elementos de la colección cumplen una condición.
- ```find({elemento -> elemento condición})``` Devuelve un elemento que haya cumplido una condición.
- ```first()``` Devuelve el primer elemento de una colección, contrario a esto ```last()``` devuelve el ultimo, peeero también se puede usar  ```get(posición)``` y que devuelva el elemento en ese lugar.


## Pero no todo en la vida son colecciones. Veamos cómo se declaran los objetos que nosotros armamos.
Siempre que quieras definir un objeto, aunque solo sea uno, se tiene que definir como clase, generalmente no se da que los objetos sean uno solo como en Wollok, sino que sean instancias de una clase.

```kotlin
class Ave(var edad:Int, var direccion:String) { 
    var amiguis = mutableListOf<Ave>()
} 
```
Esta es una clase simple que tiene 3 atributos ```edad```, ```direccion``` y ```amiguis``` al definirlos como ```var``` es cómo en Wollok pero las ```const``` acá son ```val``` 
al pasarlos por paramatero no es necesario definirlo despues, solo con cuando se instancia.
```kotlin
var pepita = Ave(5, "Wallaby 42, Sidney")
```

y si quisiéramos agregar amigos para nuestra ave deberíamos hacer algo similar a esto
```kotlin
fun agregarAmigo(nuevoAmigo: Ave) { //en vez de escribir `method` usamos `fun` y se tiene que especificar el tipo de dato del parámetro.
    amiguis.add(nuevoAmigo)
}
```
por último si quisiéramos saber la cantidad de amigos que nuestro compañero ovíparo hizo sería algo como esto...
```kotlin
fun cuantosAmigosTiene():MutableList<Ave> { //Atenti a que se tiene que especificar el tipo de dato que devuelve la funcion
    return amiguis
}
```
