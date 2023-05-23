# Timers

Go dilinde, timerlar, bir işlemin belirli bir süre sonra gerçekleştirilmesini sağlamak için kullanılır. time paketi içerisinde yer alan NewTimer fonksiyonu kullanılarak, bir timer oluşturulabilir.

```golang
package main

import (
	"fmt"
	"time"
)

func main() {
	timer1 := time.NewTimer(2 * time.Second)

	<-timer1.C
	fmt.Println("Timer 1 expired")

	timer2 := time.NewTimer(time.Second)

	go func() {
		<-timer2.C
		fmt.Println("Timer 2 expired")
	}()

	stop2 := timer2.Stop()
	if stop2 {
		fmt.Println("Timer 2 stopped")
	}
}
```

Bu örnekte, NewTimer fonksiyonu kullanarak, iki adet timer oluşturulur.

İlk timer (timer1), iki saniye sonra sona erecek şekilde ayarlanır. Bu işlem gerçekleştirildiği zaman, <-timer1.C kullanılarak, timer1 süresinin dolması beklenir ve Timer 1 expired mesajı ekrana yazdırılır.

İkinci timer (timer2), bir saniye sonra sona erecek şekilde ayarlanır. goroutine kullanılarak, timer2 süresinin dolması beklenir ve Timer 2 expired mesajının ekrana yazılması beklenir, fakat 1 saniye bekledikten sonra timer2 stop edildiği için timer Timer 2 expired ekrana yazılmaz. Stop fonksiyonu kullanılarak, timer2 durdurulur ve Timer 2 stopped mesajı ekrana yazdırılır.

Çıktı:

```golang
Timer 1 expired
Timer 2 stopped
```

Bu örnekte, NewTimer fonksiyonu kullanarak, iki adet timer oluşturulur. İlk timer beklenen süre dolana kadar goroutine'un durmasını sağlayarak bir işlem gerçekleştirirken, ikinci timer için goroutine kullanarak, belirtilen süre dolana kadar beklenir. Stop fonksiyonu kullanılarak, timer2 durdurulur.