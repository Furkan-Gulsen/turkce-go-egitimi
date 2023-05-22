# Errors

Go dilinde hata yönetimi, error adlı bir veri tipi kullanılarak yapılır. error veri tipi, hata mesajı veya nil değeri döndüren bir fonksiyondan dönen değerleri işlemek için kullanılır.

```golang
package main

import (
	"errors"
	"fmt"
)

func divide(x, y float64) (float64, error) {
	if y == 0 {
		return 0, errors.New("Cannot divide by zero")
	}
	return x / y, nil
}

func main() {
	result, err := divide(10, 2)
	if err != nil {
		fmt.Println(err)
	} else {
		fmt.Println(result)
	}

	result, err = divide(10, 0)
	if err != nil {
		fmt.Println(err)
	} else {
		fmt.Println(result)
	}
}
```

Bu örnekte, divide adlı bir fonksiyon tanımlanır ve iki sayıyı böler. Ancak, eğer ikinci sayı 0 ise bir hata döndürür.

main fonksiyonunda, divide fonksiyonu iki farklı parametreyle çağrılır. err adlı bir hata değişkeni kullanılarak her bir çağrı sonucu kontrol edilir. Eğer hata varsa hata mesajı ekrana yazdırılır. Aksi halde, sonuç ekrana yazdırılır.

Çıktı:
```
5 <nil>
Cannot divide by zero
```

Bu örnekte, error kullanarak hata yönetimi örneği yapılmıştır. divide fonksiyonu, ikinci parametresi 0 ise hata döndürür. main fonksiyonunda, err adlı bir hata değişkeni kullanılarak her çağrının sonucu kontrol edilir. Eğer hata varsa, hata mesajı ekrana yazdırılır. Aksi halde, sonuç ekrana yazdırılır.