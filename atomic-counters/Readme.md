# Atomic Counters

Atomic Counters konusu, Go dilinde eşzamanlılık işlemlerinde kullanılan bir konudur. Birçok Go programı, birden fazla goroutine tarafından paylaşılan verileri kullandığı için, bu verilerin aynı anda birden fazla goroutine tarafından değiştirilmesi kaçınılmazdır. Bu değişikliklerin uygun bir şekilde kontrol edilmemesi, programın beklenmeyen şekillerde çalışmasına neden olabilir.

Bir Atomic Counter, Go'nun sync/atomic paketinde bulunan bir veri yapısıdır. Bu veri yapısı, AddInt64, CompareAndSwapInt64, SwapInt64, LoadInt64 ve StoreInt64 gibi bir dizi yönteme sahiptir. Bu yöntemler, birden fazla goroutine tarafından aynı anda erişilebilecek bir değişkenin güvenli bir şekilde değiştirilmesini sağlar.

Aşağıdaki örnek, Atomic Counter kullanarak, 10 adet goroutine tarafından ortak kullanılan bir sayaç değişkeninin güvenli bir şekilde artırılmasını gösterir:

```golang
package main

import (
    "fmt"
    "sync"
    "sync/atomic"
)

func main() {
    var counter int64 = 0
    var wg sync.WaitGroup
    for i := 0; i < 10; i++ {
        wg.Add(1)
        go func() {
            defer wg.Done()
            atomic.AddInt64(&counter, 1)
        }()
    }
    wg.Wait()
    fmt.Println("Counter:", counter)
}
```

Bu örnekte, counter değişkeni, int64 türünden bir Atomic Counter olarak tanımlanır ve başlangıçta 0 değeri atanır. Daha sonra, 10 adet goroutine oluşturulur ve her biri, atomic.AddInt64 yöntemi kullanılarak counter değişkenini arttırır. Bu yöntem, &counter adresini alarak, counter değişkenine atomik bir şekilde 1 ekler.

Sonuç olarak, Atomic Counter veri yapısı, birden fazla goroutine tarafından paylaşılan değişkenlerin güvenli bir şekilde değiştirilmesini sağlar ve eşzamanlılık işlemlerinde kullanılan önemli bir konudur.