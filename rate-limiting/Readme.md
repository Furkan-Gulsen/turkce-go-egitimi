# Rate Limiting

Rate Limiting, bir API veya bir servisin, bir kullanıcının belli bir süre içinde yapabileceği istek sayısını sınırlandırmak için kullanılan bir yöntemdir. Bu yöntem, bir uygulamanın veya hizmetin aşırı yüklenmesini önlemek için kullanılabilir.

Go dilinde, Rate Limiting yapmak için time paketi kullanılabilir. Bu paket, belirli bir zaman aralığı boyunca belirli bir eylemde bulunmak için beklenmesi gereken süreyi hesaplamak için kullanılır.

Aşağıdaki örnekte, time.Ticker ve time.Sleep kullanarak bir Rate Limiting örneği gösterilmektedir:

```golang
package main

import (
    "fmt"
    "time"
)

func main() {
    requests := make(chan int, 5)

    for i := 1; i <= 5; i++ {
        requests <- i
    }
    close(requests)

    limiter := time.Tick(200 * time.Millisecond)

    for req := range requests {
        <-limiter
        fmt.Println("request", req, time.Now())
    }
}
```

Bu örnekte, requests adlı bir channel oluşturulur ve içine 5 adet sayı eklenir. Daha sonra, limiter adlı bir time.Ticker oluşturulur ve 200 milisaniyelik bir süreyle sınırlandırılır.

Daha sonra, requests channel'ındaki her bir istek için bir goroutine başlatılır ve her bir istek önce limiter channel üzerinden bekletilir. Bu sayede, aynı anda en fazla 1 istek işlenebilir.

Örneğin, eğer requests channel'ındaki 5 isteğin arasında hiç bekleme yapmadan hemen işlem yapılırsa, tüm istekler hızlı bir şekilde işlenecektir. Ancak, limiter channel'ın sağladığı sınırlama nedeniyle, her bir istek arasında 200 milisaniye beklenmesi sağlanır.

```
request 1 2023-05-23 15:56:01.46705 +0300 +03 m=+0.201167209
request 2 2023-05-23 15:56:01.667008 +0300 +03 m=+0.401132584
request 3 2023-05-23 15:56:01.867014 +0300 +03 m=+0.601146918
request 4 2023-05-23 15:56:02.067052 +0300 +03 m=+0.801193043
request 5 2023-05-23 15:56:02.267025 +0300 +03 m=+1.001173793
```

Bu şekilde, Rate Limiting yaparak isteklerin belli bir hızda işlenmesi sağlanır.