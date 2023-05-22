# Non-Blocking Channel Operations

Go dilinde, channel'lar, blocking özelliklerine sahiptir. Yani, bir goroutine, bir channel'a mesaj göndermek ya da mesaj almak istediğinde, ilgili işlem tamamlanana kadar engellenir. Ancak, select anahtar kelimesi kullanılarak, channel'ların non-blocking işlemleri de gerçekleştirilebilir.

```golang
package main

import "fmt"

func main() {
	messages := make(chan string)
	signals := make(chan bool)

	select {
	case msg := <-messages:
		fmt.Println("received message", msg)
	default:
		fmt.Println("no message received")
	}

	msg := "hello"
	select {
	case messages <- msg:
		fmt.Println("sent message", msg)
	default:
		fmt.Println("no message sent")
	}

	select {
	case msg := <-messages:
		fmt.Println("received message", msg)
	default:
		fmt.Println("no message received")
	}

	select {
	case sig := <-signals:
		fmt.Println("received signal", sig)
	default:
		fmt.Println("no signal received")
	}

	signal := true
	select {
	case signals <- signal:
		fmt.Println("sent signal", signal)
	default:
		fmt.Println("no signal sent")
	}

	select {
	case sig := <-signals:
		fmt.Println("received signal", sig)
	default:
		fmt.Println("no signal received")
	}
}
```


Bu örnekte, messages adlı bir channel oluşturulur ve bir mesaj gönderilmeden önce select anahtar kelimesi kullanılarak, no message received mesajı ekrana yazdırılır.

Daha sonra, bir mesaj oluşturulur ve messages channel'ına gönderilir. select anahtar kelimesi kullanılarak, sent message hello mesajı ekrana yazdırılır.

Ardından, select anahtar kelimesi kullanılarak, messages channel'ından bir mesaj alınır. Ancak, herhangi bir mesaj gönderilmeden önce bu işlem gerçekleştirildiği için, no message received mesajı ekrana yazdırılır.

Bu örnekte, signals adlı bir channel oluşturulur ve bir sinyal gönderilmeden önce select anahtar kelimesi kullanılarak, no signal received mesajı ekrana yazdırılır.
Daha sonra, bir sinyal oluşturulur ve signals channel'ına gönderilir. select anahtar kelimesi kullanılarak, sent signal true mesajı ekrana yazdırılır.

Son olarak, select anahtar kelimesi kullanılarak, signals channel'ından bir sinyal alınır. Ancak, herhangi bir sinyal gönderilmeden önce bu işlem gerçekleştirildiği için, no signal received mesajı ekrana yazdırılır.

Çıktı:

```
no message received
sent message hello
no message received
no signal received
sent signal true
received signal true
```

Bu örnekte, select anahtar kelimesi kullanarak, non-blocking işlemli yapılabilir ve channel'ların engellenmesi önlenebilir. Bu, birden fazla channel'ın dinlenmesi gereken durumlarda yararlı olabilir.