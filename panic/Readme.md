# Panic

panic, programın çalışması sırasında beklenmedik bir durumla karşılaştığında, programın çalışmasını durdurarak bir hata mesajı vermesini sağlayan bir Go dilindeki bir özelliktir.

panic bir hata olduğu için genellikle kullanılmamalıdır, ancak bir hata durumunda programın beklenmedik şekilde sonlanmaması için kullanılabilir. panic kullandığınızda, program çalışması durdurulur ve geriye kalan tüm kodların çalışması durdurulur.

panic kullanımı örneği:

```golang
package main

import "fmt"

func main() {
	defer func() {
		if err := recover(); err != nil {
			fmt.Println("Panic yakalandı:", err)
		}
	}()

	divideByZero()
	fmt.Println("Bu kod çalışacak mı?")
}

func divideByZero() {
	numerator := 10
	denominator := 0
	result := numerator / denominator
	fmt.Println("Sonuç:", result)
}

```

Bu örnekte, divideByZero adında bir fonksiyonumuz var. Bu fonksiyon içerisinde numerator'ı 10 ve denominator'ü 0 olarak ayarladıktan sonra, result değişkenine numerator'ı denominator'e böldürüyoruz. Ancak denominator'ün 0 olması durumunda, matematiksel olarak geçersiz bir işlem yapmaya çalışıyoruz. Bu durumda bir bölme sıfıra bölme hatası (division by zero error) oluşur ve bir panic durumu başlatılır.

Ana fonksiyonun içinde defer ifadesi kullanarak bir fonksiyonu erteleriz. Bu ertelediğimiz fonksiyon, recover() fonksiyonunu kullanarak bir panic durumunu yakalamak için kullanılır. Eğer bir panic durumu meydana gelirse, recover() fonksiyonu panic'in neden olduğu hatayı döndürür ve err değişkenine atar. Daha sonra, if err != nil kontrolüyle panic durumunun olup olmadığını kontrol ederiz.

Eğer divideByZero() fonksiyonunda bir panic durumu gerçekleşirse, recover() fonksiyonu tarafından yakalanacak ve err değişkenine atanacak. Ardından fmt.Println() ifadesiyle "Panic yakalandı: {hata}" şeklinde bir çıktı üretecektir. Bu sayede programın çalışması durmayacak ve devam edecektir.