# Maps

Map, Go programlama dilinde, bir anahtar-değer çiftleri koleksiyonudur. Map veri yapısı, diğer programlama dillerindeki dictionary, hash table veya associative array gibi veri yapılarına benzer. Bir Map veri yapısı, belirli bir anahtar için bir değer saklar.

```golang
var colors map[string]string
colors = make(map[string]string)
colors["red"] = "#FF0000"
colors["green"] = "#00FF00"
colors["blue"] = "#0000FF"
fmt.Println(colors)
```

Bu örnekte, colors adlı bir Map tanımlanır ve make() fonksiyonu ile oluşturulur. colors veri yapısına red, green ve blue anahtarlarına sahip renk kodları eklenir ve fmt.Println(colors) ifadesi kullanılarak Map veri yapısındaki tüm anahtar-değer çiftleri ekrana yazdırılır.

Map veri yapısı, diğer programlama dillerindeki veri yapılarından farklı olarak, anahtarlar için belirli bir veri tipi ve değerler için belirli bir veri tipi belirtmek zorunda değildir. Anahtarlar ve değerler farklı veri tiplerinde olabilir.

```golang
ages := map[string]int{
    "Alice": 25,
    "Bob":   30,
    "Carol": 35,
}
fmt.Println(ages)
```

Bu örnekte, ages adlı bir Map tanımlanır ve string türünde anahtarlar ve int türünde değerlerle ilgili çiftler atanır. Map veri yapısının oluşturulması ve eleman eklenmesi make() fonksiyonu ile birleştirilerek de yapılabilir.