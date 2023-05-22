# Goroutines

Goroutines, Go dilinde eşzamanlı olarak çalışan işlemlerdir. Goroutines, go anahtar kelimesi kullanılarak oluşturulur ve farklı işlemleri eşzamanlı olarak gerçekleştirmek için kullanılır.

```golang
package main

import (
	"fmt"
	"time"
)

func sayHello() {
	fmt.Println("Hello")
}

func main() {
	go sayHello() // goroutine
	time.Sleep(time.Second)
	fmt.Println("World")
}
```

Bu örnekte, sayHello adlı bir fonksiyon tanımlanır ve Hello adlı bir mesajı ekrana yazdırır.

main fonksiyonunda, sayHello fonksiyonu bir goroutine olarak çağrılır. Bu nedenle, sayHello fonksiyonunun çalışması diğer işlemlerden bağımsız olarak gerçekleşir. time.Sleep fonksiyonu, bir saniyelik bir bekleme süresi ekler. Son olarak, World adlı bir mesaj ekrana yazdırılır.

Çıktı:
```
Hello
World
```

Bu örnekte, goroutine kullanarak, sayHello fonksiyonu eşzamanlı olarak çalıştırıldı. sayHello fonksiyonu, goroutine olarak çağrıldığı için, diğer işlemlerden bağımsız olarak çalıştı ve sonuç olarak ekrana Heşşp mesajı yazdırıldıktan sonra World mesajı yazdırıldı.