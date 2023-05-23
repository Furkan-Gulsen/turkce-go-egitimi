# Closing Channels

Go dilinde, channel'ların kapatılması, mesajların gönderilmesi ve alınması işlemleri arasında senkronizasyon sağlayan bir yöntemdir. close fonksiyonu kullanılarak, bir channel kapatılabilir. Kapatılan bir channel'a mesaj gönderilemez ve bu channel'dan daha fazla mesaj alınamaz.

```golang
package main

import "fmt"

func main() {
	jobs := make(chan int, 5)
	done := make(chan bool)

	go func() {
		for {
			j, more := <-jobs
			if more {
				fmt.Println("received job", j)
			} else {
				fmt.Println("received all jobs")
				done <- true
				return
			}
		}
	}()

	for j := 1; j <= 3; j++ {
		jobs <- j
		fmt.Println("sent job", j)
	}

	close(jobs)
	fmt.Println("sent all jobs")

	<-done
}
```

Bu örnekte, jobs adlı bir channel ve done adlı bir channel oluşturulur. goroutine kullanarak, jobs channel'ından mesajların alınması işlemi gerçekleştirilir.

for döngüsü kullanarak, jobs channel'ına üç adet mesaj gönderilir. select anahtar kelimesi kullanarak, mesaj gönderildiği zaman, sent job mesajı ekrana yazdırılır.

Daha sonra, jobs channel'ı close fonksiyonu kullanılarak kapatılır. Bu işlem gerçekleştirildiği zaman, sent all jobs mesajı ekrana yazdırılır.

done channel'ı kullanılarak, gönderilen tüm mesajların alındığı kontrol edilir. done channel'ı, goroutine'un tamamlandığını gösterir.

Çıktı:

```
sent job 1
sent job 2
sent job 3
sent all jobs
received job 1
received job 2
received job 3
received all jobs
```

Bu örnekte, jobs channel'ına mesajlar gönderilir ve goroutine'un bu mesajları alması sağlanır. Daha sonra, jobs channel'ı close fonksiyonu kullanılarak kapatılır. Bu işlem gerçekleştirildiği zaman, goroutine'un alınması gereken tüm mesajları aldığı kontrol edilir.