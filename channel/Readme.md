# Channel

Go dilinde channel, goroutines arasında veri iletişimi yapmak için kullanılan bir veri yapısıdır. Channel, make anahtar kelimesi kullanılarak oluşturulur ve <- operatörü kullanılarak veri gönderme ve alma işlemleri yapılır.

```golang
package main

import "fmt"

func main() {
	messages := make(chan string)

	go func() { messages <- "Hello" }()

	msg := <-messages
	fmt.Println(msg)
}
```

Bu örnekte, messages adlı bir channel oluşturulur.

go anahtar kelimesi kullanılarak, bir goroutine oluşturulur ve bu goroutine, messages channel'ına bir Hello mesajı gönderir.

main fonksiyonunda, msg adlı bir değişkene messages channel'ından bir mesaj alınır ve ekrana yazdırılır.

Çıktı:
```
Hello
```

Bu örnekte, channel kullanarak, bir goroutine'dan ana iş parçacığına bir mesaj gönderildi. Bu nedenle, goroutine işlemi tamamlandıktan sonra ana iş parçacığı channel'dan mesajı alır ve sonucu ekrana yazdırır.

Kanallar, Golang'de birçok durumda kullanılabilir, örneğin:

1. Goroutineler arasında veri alışverişi yapmak için
2. Senkronizasyon işlemleri için
3. Uygulamanızın performansını artırmak için (paralel işlem yapmak)
4. Goroutineler arasında veri yarışmalarını önlemek için
5. Görevlerin koordinasyonu ve senkronizasyonu için

## Nedir bu Paralel işlemler?

Paralel işlemler, bir uygulamanın aynı anda birden fazla işlemi eşzamanlı olarak yapabilmesine olanak tanıyan bir tekniktir. Bu teknik, özellikle büyük veri işleme, hesaplama yoğunluğu yüksek işlemler ve çoklu kullanıcı desteği gerektiren uygulamalar gibi durumlarda önemlidir.

Golang, paralel işlem yapmak için goroutine'leri kullanır. Goroutine'ler, hafif iş parçacıklarıdır ve işlemci çekirdeklerindeki boş zamanları kullanarak uygulamanızı paralel ve yüksek performanslı hale getirirler. Goroutine'ler, uygulamanızın işlemesi için gerekli olan kaynakları daha verimli bir şekilde kullanmanıza olanak tanır ve uygulamanızın daha hızlı çalışmasını sağlar.

Örneğin, bir uygulama bir web sitesindeki birden fazla kullanıcının verilerini eşzamanlı olarak işlemek isteyebilir. Paralel işlem yaparak, bu verileri aynı anda işleyebilir ve daha kısa sürede sonuçlar elde edebilirsiniz. Buna ek olarak, paralel işlem yapmak aynı zamanda uygulamanızın daha fazla kullanıcı desteğine sahip olmasına da yardımcı olur.

Golang'daki paralel işlem yapma yeteneği, özellikle büyük ölçekli, hesaplama yoğunluğu yüksek ve çoklu kullanıcı desteği gerektiren uygulamalarda oldukça faydalıdır.

- **Veri işleme:** Bir uygulama, büyük veri kümelerini işlemek için paralel işlem yapabilir. Örneğin, bir uygulama bir veritabanındaki milyonlarca kaydı okuyabilir ve bu kayıtlardan farklı bir algoritma ile analizler yapabilir.
- **Hesaplama yoğunluğu yüksek işlemler:** Bir uygulama, yüksek hesaplama yoğunluğu gerektiren işlemleri paralel işlem yaparak daha hızlı bir şekilde tamamlayabilir. Örneğin, bir uygulama karmaşık matematiksel hesaplamalar yapabilir veya büyük dosyaların şifrelemesini yapabilir.
- **Çoklu kullanıcı desteği:** Bir uygulama, aynı anda birden fazla kullanıcının erişimine izin vermek için paralel işlem yapabilir. Örneğin, bir web uygulaması birden fazla kullanıcının aynı anda istek göndermesini sağlayabilir ve bu istekleri paralel olarak işleyebilir. 
- **Çoklu işlemci çekirdeği:** Birden fazla işlemci çekirdeğine sahip sistemlerde, paralel işlem yaparak uygulamanızın daha verimli bir şekilde çalışmasını sağlayabilirsiniz. Örneğin, bir uygulama, birden fazla işlemci çekirdeğini kullanarak daha hızlı veri işleme ve hesaplama yapabilir.

Bu örnekler, paralel işlemlerin ne gibi durumlarda kullanılabileceğine dair bir fikir vermektedir. Golang'daki goroutine'ler sayesinde, bu tür işlemleri daha hızlı ve verimli bir şekilde gerçekleştirebilirsiniz.

## Buffering

Go dilinde channel'ların boyutu, belirli bir kapasiteyle sınırlandırılabilir. Bu, channel'ların belirli sayıda veri almasını sağlar. Bu özellik, channel buffering olarak adlandırılır.

```golang
package main

import "fmt"

func main() {
	messages := make(chan string, 2)

	messages <- "Hello"
	messages <- "World"

	fmt.Println(<-messages)
	fmt.Println(<-messages)
}
```

Bu örnekte, messages adlı bir channel oluşturulur ve boyutu 2 olarak belirlenir.

Hello ve World mesajları, messages channel'ına gönderilir.

<-messages kullanılarak, messages channel'ından mesajlar alınır ve ekrana yazdırılır.

Çıktı:

```
Hello
World
```

Bu örnekte, channel buffering kullanarak, messages channel'ı boyutu 2 olarak tanımlandı. Böylece, Hello ve World mesajları channel'a gönderildi ve channel'da depolandı. <-messages kullanılarak, mesajlar sırayla channel'dan alındı ve ekrana yazdırıldı.

## Channel Synchronization

Go dilinde, channel'lar ayrıca, farklı goroutines arasında senkronizasyon için de kullanılabilir. Bu, bir goroutine'un, diğer bir goroutine'un işlemi tamamlamasını beklemesi gerektiği durumlarda kullanışlıdır.

```golang
package main

import (
	"fmt"
	"time"
)

func worker(done chan bool) {
	fmt.Print("working...")
	time.Sleep(time.Second)
	fmt.Println("done")

	done <- true
}

func main() {
	done := make(chan bool, 1)
	go worker(done)

	<-done
}
```

Bu örnekte, worker adlı bir fonksiyon tanımlanır ve done adlı bir channel parametresi alır.

worker fonksiyonu, working... mesajını ekrana yazdırır, bir saniyelik bir bekleme süresi ekler ve done mesajını ekrana yazdırır.

main fonksiyonunda, done adlı bir channel oluşturulur ve boyutu 1 olarak belirlenir. go anahtar kelimesi kullanılarak, worker fonksiyonu bir goroutine olarak çağrılır. <-done kullanılarak, worker fonksiyonu tamamlandığında main fonksiyonuna bir mesaj gönderilir ve ana iş parçacığı bu mesajı alır.

Çıktı:
```
working...done
```

Bu örnekte, channel senkronizasyonu kullanarak, worker fonksiyonu bir goroutine olarak çağrıldı. worker fonksiyonu, done channel'ına bir mesaj gönderir ve işlemi tamamlanır. main fonksiyonu, <-done kullanılarak, worker fonksiyonunun işlemi tamamlamasını bekler. Sonuç olarak, working...done mesajları sırayla ekrana yazdırılır.

## Channel Directions

Go dilinde, channel'ların yönü, gönderme (send) veya alma (receive) işlemleri için belirlenebilir. Bu nedenle, channel'ların kullanımı, farklı goroutines arasındaki iletişimi ve veri aktarımını kolaylaştırır.

```golang
package main

import "fmt"

func ping(pings chan<- string, msg string) {
	pings <- msg
}

func pong(pings <-chan string, pongs chan<- string) {
	msg := <-pings
	pongs <- msg
}

func main() {
	pings := make(chan string, 1)
	pongs := make(chan string, 1)

	ping(pings, "Hello")
	pong(pings, pongs)

	fmt.Println(<-pongs)
}
```

Bu örnekte, ping ve pong adlı iki fonksiyon tanımlanır ve channel'larının yönleri belirlenir.

ping fonksiyonu, bir chan<- operatörü ile, sadece bir mesaj göndermek için kullanılabilen bir pings channel'ı parametresi alır.

pong fonksiyonu, bir <-chan operatörü ile, sadece mesaj almak için kullanılabilen bir pings channel'ı parametresi ve bir chan<- operatörü ile, sadece mesaj göndermek için kullanılabilen bir pongs channel'ı parametresi alır.

main fonksiyonunda, pings ve pongs channel'ları oluşturulur. ping fonksiyonu kullanılarak, pings channel'ına bir Hello mesajı gönderilir. pong fonksiyonu, pings channel'ından mesajı alır ve pongs channel'ına gönderir. Son olarak, <-pongs kullanılarak, pongs channel'ından mesaj alınır ve ekrana yazdırılır.

Çıktı:

```
Hello
```

Bu örnekte, channel directions kullanarak, ping ve pong fonksiyonları, farklı yönlerdeki channel'ları kullanarak mesaj gönderme ve alma işlemlerini gerçekleştirir. ping fonksiyonu, sadece mesaj göndermek için kullanılan pings channel'ını kullanarak mesaj gönderir. pong fonksiyonu, pings channel'ından mesajı alır ve pongs channel'ına gönderir. Son olarak, <-pongs kullanılarak, pongs channel'ından mesaj alınır ve ekrana yazdırılır.
