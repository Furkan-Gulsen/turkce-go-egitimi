# WaitGroups

WaitGroup yapısı, Go dilinde, goroutine'lar arasında senkronizasyon sağlamak için kullanılan bir mekanizmadır. WaitGroup yapısı, Go'nun sync paketi içinde bulunur.

WaitGroup yapısı, programcıların çalışacak işlemlerin sayısını önceden belirtmelerine ve bu işlemlerin tamamlanmasını beklemelerine olanak tanır. Her goroutine, işlemin tamamlandığını bildirmek için WaitGroup yapısındaki Done() fonksiyonunu çağırır. WaitGroup yapısındaki Wait() fonksiyonu, tüm işlemlerin tamamlanmasını bekler.

Aşağıdaki örnek, WaitGroup yapısının kullanımını göstermektedir:

```golang
package main

import (
    "fmt"
    "sync"
    "time"
)

func worker(id int, wg *sync.WaitGroup) {
    defer wg.Done()

    fmt.Printf("Worker %d starting\n", id)
    time.Sleep(time.Second)
    fmt.Printf("Worker %d done\n", id)
}

func main() {
    var wg sync.WaitGroup

    for i := 1; i <= 5; i++ {
        wg.Add(1)
        go worker(i, &wg)
    }

    wg.Wait()

    fmt.Println("All workers done")
}
```

Bu örnekte, 5 adet iş yapan işçi fonksiyonu worker() çalıştırılır. WaitGroup yapısı, her işçi fonksiyonu başlamadan önce Add() fonksiyonu ile bekleyen işlem sayısını arttırır. Her işçi fonksiyonu tamamlandığında, Done() fonksiyonu ile bir işlem tamamlandığı bildirilir. Wait() fonksiyonu, tüm işlemlerin tamamlandığını beklemek için kullanılır. Sonuç olarak, tüm işçi fonksiyonları tamamlandıktan sonra, main() fonksiyonu "All workers done" mesajını yazdırır.

```
Worker 5 starting
Worker 3 starting
Worker 4 starting
Worker 1 starting
Worker 2 starting
Worker 5 done
Worker 3 done
Worker 2 done
Worker 1 done
Worker 4 done
All workers done
```