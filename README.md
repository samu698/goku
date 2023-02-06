# Array

In Go, un array è una raccolta ordinata e di lunghezza fissa di elementi dello stesso tipo. La dimensione di un array deve essere specificata quando viene dichiarata e, una volta impostata, non può essere modificata. La sintassi per dichiarare un array in Go è la seguente: 

```
func main() {
	var variableName [arraySize]type
}
```

Ad esempio, per dichiarare un array di 5 numeri interi:

```go
{
	var numbers [5]int
}
```

È possibile accedere agli elementi in un array utilizzando il loro indice, che inizia da 0.  Ad esempio:

```go
{
	numbers[0] = 10
	numbers[1] = 20
	...
}
```

Puoi anche utilizzare una sintassi abbreviata per dichiarare e inizializzare un array in una riga:

```go
{
numbers := [5]int{10, 20, 30, 40, 50}
}
```

---

In Go, è anche possibile utilizzare l'operatore di lunghezza ( **`len`**) per ottenere la dimensione di un array:

```go
	fmt.Println("Array length:", len(numbers))
```

È possibile utilizzare i cicli **`for`**per iterare attraverso gli elementi di un array:

```go
{
	for i := 0; i < len(numbers); i++ {
		fmt.Println("Element", i, "is", numbers[i])
	}
```

In Go, è anche possibile utilizzare la sintassi di "range" per iterare attraverso gli elementi di un array:

```go
for i, value := range numbers {
    fmt.Println("Element", i, "is", value)
}
```

Gli array in Go sono passati per valore, il che significa che quando si passa un array a una funzione, verrà creata una copia dell'array e non sarà possibile modificare l'originale. Se si desidera modificare l'array originale, è necessario passare un riferimento all'array, ad esempio utilizzando un puntatore o un sottoinsieme di slice.

# Slice

A **`slice`**in Go è un array dinamico che consente di memorizzare una sequenza di valori dello stesso tipo. A differenza di un array, la lunghezza di a **`slice`**può cambiare in fase di esecuzione, rendendola una struttura dati flessibile e potente per i programmi Go.

Ecco un esempio di come puoi creare un **`slice`**in Go:

```go
package main

import "fmt"

func main() {
	numbers := []int{1, 2, 3, 4, 5}
	fmt.Println(numbers)

} // [1 2 3 4 5]
```

In questo esempio, la **`[]int`**sintassi viene utilizzata per creare un array di numeri interi e l' **`:=`**operatore viene utilizzato per assegnare l'array a una **`slice`**variabile denominata **`numbers`**.

Puoi anche creare un vuoto **`slice`**usando la **`make`**funzione:

```go
package main

import "fmt"

func main() {
	numbers := make([]int, 0)
	fmt.Println(numbers)

} // []
```

In questo esempio, la **`make`**funzione viene utilizzata per creare un vuoto **`slice`**di numeri interi. Il primo argomento della **`make`**funzione è il tipo di **`slice`**e il secondo argomento è la lunghezza di **`slice`**.

Una volta che hai un **`slice`**, puoi usare varie funzioni integrate per manipolarlo. Ad esempio, puoi utilizzare la **`append`**funzione per aggiungere elementi alla fine di un **`slice`**:

```go
package main

import "fmt"

func main() {
	numbers := []int{1, 2, 3}
	numbers = append(numbers, 4, 5)
	fmt.Println(numbers)

} // [1 2 3 4 5]
```

In questo esempio, la **`append`**funzione viene utilizzata per aggiungere due nuovi elementi al file **`numbers`** **`slice`**.

Puoi anche utilizzare l'operatore di indicizzazione **`[]`**per accedere a singoli elementi in un **`slice`**:

```go
package main

import "fmt"

func main() {
	numbers := []int{1, 2, 3, 4, 5}
	fmt.Println(numbers[2])

} // 3
```

In questo esempio, la **`fmt.Println`**funzione viene utilizzata per stampare il valore del terzo elemento nel file **`numbers`** **`slice`**.

**`slices`**sono una parte fondamentale della programmazione Go e sono ampiamente utilizzati nei programmi Go. Che tu stia lavorando con matrici di numeri, stringhe o qualsiasi altro tipo, **`slices`**fornisci un modo semplice e flessibile per archiviare e manipolare sequenze di valori nei tuoi programmi Go.

Oltre alle operazioni di base descritte sopra, il **`slice`**tipo di Go fornisce anche molte altre funzioni e operazioni utili:

- Slicing: è possibile utilizzare la **`[start:end]sliceslice`** sintassi per estrarre un sub-**`slice`** da un file**`slice`.** Per esempio:
    
    ```go
    package main
    
    import "fmt"
    
    func main() {
    	numbers := []int{1, 2, 3, 4, 5}
    	fmt.Println(numbers[1:3])
    
    }
    ```
    
    In questo esempio, la **`[1:3]`**sintassi viene utilizzata per estrarre un sub- **`slice`**di **`numbers`** **`slice`**che include gli elementi all'indice 1 e 2.
    
    - Lunghezza e capacità: è possibile utilizzare la **`lenslicecap`**funzione integrata per ottenere la lunghezza di a e la funzione integrata per ottenere la sua capacità. Per esempio:
    
    ```go
    package main
    
    import "fmt"
    
    func main() {
    	numbers := []int{1, 2, 3, 4, 5}
    	fmt.Println("Length:", len(numbers))
    	fmt.Println("Capacity:", cap(numbers))
    
    }
    ```
    
    In questo esempio, la **`len`**funzione viene utilizzata per ottenere la lunghezza di **`numbers`** **`slice`**e la **`cap`**funzione viene utilizzata per ottenere la sua capacità.
    
    - Ciclo: è possibile utilizzare il **`forslice`**ciclo per scorrere gli elementi in un file **`slice`**. Per esempio:
        
        ```go
        package main
        
        import "fmt"
        
        func main() {
        	numbers := []int{1, 2, 3, 4, 5}
        	for i, number := range numbers {
        		fmt.Println(i, number)
        	}
        
        }
        ```
        
        In questo esempio, il **`for`**ciclo viene utilizzato per scorrere gli elementi in **`numbers`** **`slice`**e la **`range`**parola chiave viene utilizzata per ottenere sia l'indice che il valore di ciascun elemento.
        
        - Copia: è possibile utilizzare la **`copyslice`** funzione integrata per copiare gli elementi da uno  **`slice`al**l'altro. Per esempio:
        
        ```go
        package main
        
        import "fmt"
        
        func main() {
        	numbers1 := []int{1, 2, 3}
        	numbers2 := make([]int, 3)
        	copy(numbers2, numbers1)
        	fmt.Println(numbers2)
        
        }
        ```
        
        In questo esempio, la **`copy`**funzione viene utilizzata per copiare gli elementi da **`numbers1`** **`slice`**a **`numbers2`** **`slice`**.
        
        In conclusione, il **`slice`**tipo di Go fornisce un modo conveniente e flessibile per archiviare e manipolare sequenze di valori nei programmi Go. Sia che tu stia lavorando con matrici di numeri, stringhe o qualsiasi altro tipo, **`slices`**sono uno strumento essenziale da avere nel tuo toolkit Go.

# For range

Il **`for range`**ciclo è una funzionalità di Go che consente di eseguire iterazioni sugli elementi di una raccolta, ad esempio un array, una sezione, una stringa, una mappa o un canale. Il **`for range`**ciclo fornisce un modo conveniente per accedere a ciascun elemento della raccolta uno alla volta, senza la necessità di gestire manualmente un indice o una variabile contatore.

Ecco un esempio di utilizzo di un **`for range`**ciclo per iterare su una fetta di numeri interi:

```go
numbers := []int{1, 2, 3, 4, 5}

for i, number := range numbers {
    fmt.Println(i, number)
}
```

In questo esempio, il **`for range`**ciclo eseguirà un'iterazione su ciascun elemento nella **`numbers`**sezione e la **`i`**variabile verrà impostata sull'indice dell'elemento corrente, mentre la **`number`**variabile verrà impostata sul valore dell'elemento corrente.

È anche possibile omettere la variabile index utilizzando il **`_`**carattere:

```go
for _, number := range numbers {
    fmt.Println(number)
}
```

**`numbers`**In questo esempio, verrà stampato solo il valore di ciascun elemento nella sezione e la variabile index non è necessaria, quindi viene scartata utilizzando il **`_`**carattere.

Quando viene utilizzato con una stringa, il **`for range`**ciclo ripeterà ogni **`rune`**valore nella stringa. Ecco un esempio:

```go
text := "Hello, world!"

for i, r := range text {
	fmt.Println(i, string(r))
}
```

In questo esempio, il **`for range`**ciclo ripeterà ogni **`rune`**valore nella **`text`**stringa e la **`i`**variabile verrà impostata sull'indice di current **`rune`**, mentre la **`r`**variabile verrà impostata sul valore di current **`rune`**.

Il **`for range`**ciclo è una funzionalità molto utile in Go e può essere utilizzato per semplificare e rendere il codice più leggibile quando si lavora con raccolte e stringhe. Usando il **`for range`**ciclo, puoi concentrarti sulla logica di ciò che vuoi fare con ogni elemento, senza doversi preoccupare di gestire manualmente indici o contatori.

# Runa

A **`rune`**in Go è un tipo predefinito che rappresenta un punto di codice Unicode. È essenzialmente un alias per **`int32`**ed è usato per rappresentare un singolo carattere in una stringa.

In Go, le stringhe vengono archiviate come una sequenza di punti di codice Unicode e a **`rune`**può essere utilizzato per accedere e manipolare singoli caratteri all'interno di una stringa. Ecco un esempio di utilizzo di a **`rune`**per accedere al primo carattere in una stringa:

```go
package main

import "fmt"

func main() {
	text := "Hello, world!"

	firstRune := rune(text[0]) // prende il carattere nella posizione indicata all'interno di text[] della stringa text, 
														 // in questo caso prende H
	fmt.Println(firstRune, string(firstRune))

}
// Il programma restituisce: 72 H
```

In questo esempio, alla **`firstRune`**variabile viene assegnato il valore del primo carattere della **`text`**stringa. La **`string`**funzione viene quindi utilizzata per convertire il **`rune`**valore in una stringa in modo che possa essere stampato.

**`runes`**vengono utilizzati in Go quando è necessario manipolare le stringhe a livello di carattere, piuttosto che a livello di byte. Ciò è particolarmente importante quando si lavora con testo multilingue, in cui un singolo carattere può occupare più byte. Usando **`runes`**, puoi assicurarti di lavorare con il carattere corretto, piuttosto che con una sequenza di byte che potrebbe non rappresentare un carattere valido.

Nel complesso, **`runes`**sono una parte cruciale del linguaggio di programmazione Go e forniscono un modo potente e flessibile per lavorare con testo e stringhe nei tuoi programmi Go.

In Go, puoi usare la **`len`**funzione per ottenere la lunghezza di una stringa in rune, invece che in byte. Per esempio:

```go
package main

import "fmt"

func main() {
	text := "Hello, 世界!"

	fmt.Println("String length in runes:", len(text))
	fmt.Println("String length in bytes:", len([]byte(text)))

} // Restituisce: String length in runes: 14
							 // String length in bytes: 14
```

In questo esempio, la **`len`**funzione viene utilizzata due volte. La prima chiamata restituisce la lunghezza della **`text`**stringa in rune, mentre la seconda chiamata restituisce la lunghezza della stringa in byte.

È importante tenere presente che la lunghezza di una stringa in rune potrebbe non essere uguale alla sua lunghezza in byte. Questo perché alcuni caratteri in una stringa potrebbero occupare più byte in memoria, a seconda della codifica utilizzata.

Un'altra caratteristica utile delle rune è che possono essere utilizzate con il **`for`**ciclo per scorrere i caratteri in una stringa. Ecco un esempio:

```go
package main

import "fmt"

func main() {
	text := "Hello, 世界!"

	for i, r := range text {
		fmt.Printf("%d: %c\n", i, r)
	}

}
```

In questo esempio, il **`for`**ciclo utilizza la **`range`**parola chiave per scorrere la **`text`**stringa. La **`range`**parola chiave restituisce sia l'indice del carattere corrente che il valore del carattere corrente, rappresentato come **`rune`**.

La **`fmt.Printf`**funzione viene quindi utilizzata per stampare l'indice del carattere corrente e il carattere stesso.

In conclusione, **`runes`**in Go fornisce un modo conveniente ed efficiente per lavorare con i caratteri nelle stringhe. Sia che tu stia contando i caratteri, ripetendo i caratteri o manipolando i singoli caratteri, **`runes`**sono uno strumento essenziale da avere nel tuo toolkit Go.
