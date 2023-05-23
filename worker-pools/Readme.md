# Worker Pools

Go dilinde, worker poollar, belirli bir işlemi yapmak üzere ayrılmış bir işçi grubudur. İşler bir channel'a gönderilir ve bu işçiler tarafından işlenir. Bu sayede, işlemler belirli bir sıra ile işçilere dağıtılarak, iş yükü paylaştırılmış olur.

```golang
package main

import (
	"fmt"
	"time"
)

func worker(id int, jobs <-chan int, results chan<- int) {
	for j := range jobs {
		fmt.Println("Worker", id, "started job", j)
		time.Sleep(time.Second)
		fmt.Println("Worker", id, "finished job", j)
		results <- j * 2
	}
}

func main() {
	jobs := make(chan int, 100)
	results := make(chan int, 100)

	for w := 1; w <= 3; w++ {
		go worker(w, jobs, results)
	}

	for j := 1; j <= 5; j++ {
		jobs <- j
	}
	close(jobs)

	for a := 1; a <= 5; a++ {
		<-results
	}
}
```

Bu örnekte, worker adlı bir fonksiyon oluşturulur. Bu fonksiyon, işçiler tarafından gerçekleştirilecek işlemleri alır ve işlemlerin sonuçlarını results channel'ına yazar.

jobs adlı bir channel oluşturulur ve 100 adet iş yüküne kadar bu channel'a mesaj gönderilebilir. results adlı bir channel oluşturulur ve 100 adet sonuç için bu channel'a mesaj gönderilebilir.

for döngüsü kullanılarak, işçiler için bir goroutine oluşturulur. İşçiler, worker fonksiyonuna gönderilen id, jobs ve results değişkenlerini kullanarak çalışır.

Bir sonraki for döngüsü kullanılarak, 5 adet iş yükü oluşturulur ve jobs channel'ına gönderilir. close fonksiyonu kullanılarak, jobs channel'ı kapatılır.

Son olarak, for döngüsü kullanılarak, sonuçlar results channel'ından alınır.

Çıktı:

```
Worker 3 started job 1
Worker 2 started job 2
Worker 1 started job 3
Worker 3 finished job 1
Worker 3 started job 4
Worker 2 finished job 2
Worker 1 finished job 3
Worker 1 started job 5
Worker 2 started job 6
Worker 3 finished job 4
Worker 2 finished job 6
Worker 1 finished job 5
```