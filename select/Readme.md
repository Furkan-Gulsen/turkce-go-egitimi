# Select

Go dilinde, select anahtar kelimesi, birden fazla channel'ı dinleyerek, hangi channel'ın mesaj gönderdiğini belirleyebilir. Bu özellik, channel'ların senkronizasyonunu kolaylaştırır ve farklı goroutines arasındaki mesajlaşmayı yönetir.

```golang
package main

import (
	"fmt"
	"time"
)

func main() {
	c1 := make(chan string)
	c2 := make(chan string)

	go func() {
		time.Sleep(time.Second * 1)
		c1 <- "one"
	}()

	go func() {
		time.Sleep(time.Second * 2)
		c2 <- "two"
	}()

	for i := 0; i < 2; i++ {
		select {
		case msg1 := <-c1:
			fmt.Println("received", msg1)
		case msg2 := <-c2:
			fmt.Println("received", msg2)
		}
	}
}
```

Bu örnekte, c1 ve c2 adlı iki channel oluşturulur ve mesaj gönderme işlemi için goroutine'lar oluşturulur.

main fonksiyonunda, select anahtar kelimesi kullanılarak, c1 ve c2 channel'ları dinlenir. İlk olarak, goroutine'lar arasındaki bekleme süresi nedeniyle, c1 channel'ından bir mesaj alınır ve ekrana yazdırılır. Daha sonra, c2 channel'ından bir mesaj alınır ve ekrana yazdırılır.

Çıktı:
```
received one
received two
```

Bu örnekte, select anahtar kelimesi kullanarak, c1 ve c2 channel'larını dinleyen bir for döngüsü oluşturuldu. Bu, mesaj alım süresine bağlı olarak farklı channel'ların dinlenmesini sağlar. Sonuç olarak, goroutine'lar arasındaki mesajlaşma, belirli bir sıraya göre gerçekleştirilir ve select anahtar kelimesi kullanarak senkronizasyon sağlanır.