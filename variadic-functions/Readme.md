## Variadic Functions

Variadic Functions, Go programlama dilinde, değişken sayıda argüman alan fonksiyonlardır. Bu fonksiyonlar, bir veya birden fazla argüman alabilir ve değişken sayıda argüman alabilir.

```golang
func sum(nums ...int) int {
    total := 0
    for _, num := range nums {
        total += num
    }
    return total
}

fmt.Println(sum(1, 2, 3, 4, 5))
fmt.Println(sum(2, 4, 6))
```

Bu örnekte, sum adlı bir fonksiyon tanımlanır. Fonksiyon, nums adlı bir int türünde değişken sayıda parametre alır ve toplamını geri döndürür. Fonksiyon içinde, for döngüsü kullanarak nums dizisindeki tüm elemanların toplamı hesaplanır. Fonksiyon, sum(1, 2, 3, 4, 5) ve sum(2, 4, 6) şeklinde çağrılır ve sonuçlar ekrana yazdırılır.

```golang
func concatenate(sep string, strs ...string) string {
    result := ""
    for i, str := range strs {
        if i > 0 {
            result += sep
        }
        result += str
    }
    return result
}

fmt.Println(concatenate(", ", "foo", "bar", "baz"))
fmt.Println(concatenate("-", "hello", "world"))
```

Bu örnekte, concatenate adlı bir fonksiyon tanımlanır. Fonksiyon, sep adlı bir string türünde ve değişken sayıda strs adlı string türünde parametre alır. Fonksiyon içinde, for döngüsü kullanarak strs dizisindeki tüm elemanların birleştirilmesi ve sep ayraç karakteri ile birleştirilmesi sağlanır. Fonksiyon, concatenate(", ", "foo", "bar", "baz") ve concatenate("-", "hello", "world") şeklinde çağrılır ve sonuçlar ekrana yazdırılır.