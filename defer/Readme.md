# Defer

defer, Go dilindeki özel bir anahtar sözcüktür ve belirli bir işlevin çalışmasının sonunda çalıştırılacak işlevleri veya ifadeleri belirtmek için kullanılır. Defer ifadeleri, işlevin sonunda ne olursa olsun, yani o fonksiyonun herhangi bir nedenle sona ermesi durumunda bile çalıştırılacaktır.

Defer ifadeleri kullanarak, bir işlevin sonunda açılan dosyaları, kapatılmayan veritabanı bağlantılarını, ağ bağlantılarını vb. hızlı ve güvenli bir şekilde kapatmak mümkündür.

Örnek olarak, bir dosya açılır ve defer ile fonksiyon sonunda dosya kapatılır:

```golang
package main

import (
	"fmt"
	"os"
)

func main() {
	// dosya açma
	f, err := os.Open("example.txt")
	if err != nil {
		fmt.Println(err)
		return
	}

	// dosya kapatma
	defer f.Close()

	// dosyayı okuma
	b := make([]byte, 1024)
	n, err := f.Read(b)
	if err != nil {
		fmt.Println(err)
		return
	}

	// dosya içeriğini yazdırma
	fmt.Println(string(b[:n]))
}
```

Bu örnekte, os.Open fonksiyonu kullanılarak "example.txt" dosyası açılır. defer ifadesi kullanılarak dosya kapatma işlemi, işlevin sonunda çalıştırılacak şekilde planlanır. Daha sonra, Read fonksiyonu kullanılarak dosya içeriği okunur ve ekrana yazdırılır.

Burada dikkat edilmesi gereken önemli bir nokta, defer ifadesinin en sona yazılmamasıdır. defer ifadesinin kapatılacak olan dosyayı açan ifade ile aynı blokta olması gerekmektedir. Aksi takdirde, defer ifadesi, işlevin sonuna kadar beklemeye devam edecektir.