# Range over Channels

Go dilinde, range anahtar kelimesi, channel'lar üzerinde döngü işlemlerinin gerçekleştirilmesini sağlar. Bu yöntemle, channel'ın kapatılması beklenmeden, tüm mesajlar for döngüsü kullanılarak alınabilir.

```golang
package main

import "fmt"

func main() {
	queue := make(chan string, 2)
	queue <- "one"
	queue <- "two"
	close(queue)

	for elem := range queue {
		fmt.Println(elem)
	}
}
```

Bu örnekte, queue adlı bir channel oluşturulur. for döngüsü kullanarak, queue channel'ına iki adet mesaj gönderilir.

close fonksiyonu kullanılarak, queue channel'ı kapatılır. Daha sonra, for döngüsü kullanılarak, queue channel'ının mesajları range anahtar kelimesi kullanılarak alınır.

Çıktı:

```golang
one
two
```

Bu örnekte, range anahtar kelimesi kullanarak, queue channel'ına gönderilen mesajlar alınır. close fonksiyonu kullanılarak, queue channel'ı kapatılır. Ancak, range anahtar kelimesi kullanılarak, tüm mesajlar alınır.