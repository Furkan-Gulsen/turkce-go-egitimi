# Functions

Function, Go programlama dilinde, belirli bir işlevi yerine getiren kod bloklarını ifade eder. Bir fonksiyon, bir veya birden fazla parametre alabilir, bir işlem gerçekleştirebilir ve bir veya birden fazla sonuç döndürebilir.

```golang
func add(a int, b int) int {
    return a + b
}
​
result := add(5, 10)
fmt.Println(result)
```

Bu örnekte, add adlı bir fonksiyon tanımlanır. Fonksiyon, a ve b adlı iki int tipinde parametre alır ve bu parametreler toplanarak toplam sonucu int tipinde geri döndürür. add fonksiyonu, 5 ve 10 parametreleri ile çağrılır ve sonuç fmt.Println(result) ifadesi ile yazdırılır.

```golang
func swap(a, b string) (string, string) {
    return b, a
}
​
x, y := swap("hello", "world")
fmt.Println(x, y)
```

Bu örnekte, swap adlı bir fonksiyon tanımlanır. Fonksiyon, a ve b adlı iki string tipinde parametre alır ve bu parametreleri birbirleriyle yer değiştirerek geri döndürür. swap fonksiyonu, "hello" ve "world" parametreleri ile çağrılır ve geri döndürülen sonuçlar x ve y değişkenleri tarafından alınır. Sonuçlar, fmt.Println(x, y) ifadesi ile yazdırılır.