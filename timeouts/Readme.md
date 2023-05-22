# Timeouts

Go dilinde, timeout işlemleri, özellikle ağ işlemleri sırasında önemlidir. time paketi kullanılarak, belirli bir süre beklenmesi sağlanabilir. Eğer süre aşılırsa, timeout hatası oluşur.

```golang
package main

import (
	"fmt"
	"time"
)

func main() {
	c1 := make(chan string, 1)

	go func() {
		time.Sleep(time.Second * 2)
		c1 <- "result 1"
	}()

	select {
	case res := <-c1:
		fmt.Println(res)
	case <-time.After(time.Second * 1):
		fmt.Println("timeout 1")
	}

	c2 := make(chan string, 1)

	go func() {
		time.Sleep(time.Second * 2)
		c2 <- "result 2"
	}()

	select {
	case res := <-c2:
		fmt.Println(res)
	case <-time.After(time.Second * 3):
		fmt.Println("timeout 2")
	}
}
```

Bu örnekte, c1 ve c2 adlı iki channel oluşturulur ve mesaj gönderme işlemleri için goroutine'lar oluşturulur.

İlk olarak, select anahtar kelimesi kullanılarak, c1 channel'ından bir mesaj beklenir. Ancak, time.After kullanılarak, c1 channel'ından bir mesaj alınmadan önce, bir saniye beklenir. Eğer bir saniyeden daha uzun bir süre geçerse, timeout hatası oluşur ve timeout 1 mesajı ekrana yazdırılır.

Daha sonra, select anahtar kelimesi kullanılarak, c2 channel'ından bir mesaj beklenir. Ancak, time.After kullanılarak, c2 channel'ından bir mesaj alınmadan önce, üç saniye beklenir.

Çıktı:
```
timeout 1
result 2
```

Bu örnekte, time.After kullanarak timeout işlemleri gerçekleştirildi. İlk olarak, c1 channel'ına bir saniyeden önce bir mesaj gönderilmediği için timeout hatası oluşur. Daha sonra, c2 channel'ına iki saniyeden önce bir mesaj gönderildiği için mesaj alınır ve ekrana yazdırılır.