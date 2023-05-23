# Tickers

Go dilinde, tickerlar, belirli bir süre boyunca belirli aralıklarla bir işlemin gerçekleştirilmesini sağlamak için kullanılır. time paketi içerisinde yer alan NewTicker fonksiyonu kullanılarak, bir ticker oluşturulabilir.

```golang
package main

import (
	"fmt"
	"time"
)

func main() {
	ticker := time.NewTicker(500 * time.Millisecond)
	done := make(chan bool)

	go func() {
		for {
			select {
			case <-done:
				return
			case t := <-ticker.C:
				fmt.Println("Tick at", t)
			}
		}
	}()

	time.Sleep(1600 * time.Millisecond)
	ticker.Stop()
	done <- true
	fmt.Println("Ticker stopped")
}
```

Bu örnekte, NewTicker fonksiyonu kullanarak, bir ticker oluşturulur ve 500 milisaniyede bir bir işlem gerçekleştirilmesi sağlanır.

goroutine kullanılarak, select anahtar kelimesi kullanılarak, ticker'ın oluşturulduğu zaman aralığına bağlı olarak belirli aralıklarla bir işlem gerçekleştirilir. done adlı channel'a mesaj gönderilerek, goroutine durdurulur ve Ticker stopped mesajı ekrana yazdırılır.

Çıktı:

```
Tick at 2022-11-27 16:37:14.750915 +0300 MSK m=+0.501356162
Tick at 2022-11-27 16:37:15.249568 +0300 MSK m=+1.000018689
Tick at 2022-11-27 16:37:15.751064 +0300 MSK m=+1.501505306
Ticker stopped
```