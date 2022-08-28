### Zależności 

`implementation("org.jetbrains.kotlinx:kotlinx-coroutines-core:$.$.$")`

### Korutyna

Korutyna to kod wykonujący się asynchronicznie, jednocześnie nie będąc powiązanym z żadnym wątkiem.


### runBlocking

`runBlocking {...}` - pozwala na rozpoczęcie działania korutyny wewnątrz zwykłej funkcji, blokując przy tym główny wątek programu.
```
fun funkcja() {
  runBlocking {
    println("Hello")
    delay(5000L)
  }
  println("World")
}
```

### coroutineScope

`coroutineScope {...}` - odpala nową korutynę. Jeśli zagnieździmy `coroutineScope` jedna w drugiej, to ta zewnętrzna nie będzie kontynuować działania dopóki nie wykona się do końca ta wewnętrzna.

### launch

`launch {...}` wydziela część kodu, który ma się wykonać asynchronicznie z resztą kodu na zewnątrz.
* `runBlocking` - blokuje wątek główny
* `coroutineScope` - blokuje runBlocking oraz inne coroutineScope
* `launch` - nie blokuje niczego

### suspend

W Kotlinie nie występują słowa kluczowe `async` `await`, zamiast tego Kotlin używa funkcji ze słowem kluczowym `suspend`.
Wewnątrz funkcji `suspend` możemy używać funkcji korutyn, takich jak np. `delay`



