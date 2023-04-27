# Range

range ifadesi, Go programlama dilinde, belirli bir dizi, dilim veya harita üzerinde döngü oluşturmak için kullanılır. range ifadesi, veri yapısındaki tüm elemanları tek tek ele almak için kullanılır.

```golang
numbers := []int{1, 2, 3, 4, 5}
for i, num := range numbers {
    fmt.Println("index:", i, "number:", num)
}
```

Bu örnekte, numbers adlı bir dilim tanımlanır ve elemanlarına {1, 2, 3, 4, 5} değerleri atanır. range ifadesi kullanılarak, numbers dilimindeki tüm elemanlar tek tek alınır ve for döngüsü içinde kullanılır. i değişkeni, döngünün sırasıdaki indeks değerini, num değişkeni ise indeksteki elemanı temsil eder. Bu örnekte, indeksler ve elemanlar birlikte yazdırılır.

```golang
colors := map[string]string{
    "red":   "#FF0000",
    "green": "#00FF00",
    "blue":  "#0000FF",
}
for color, code := range colors {
    fmt.Println("color:", color, "code:", code)
}
```

Bu örnekte, colors adlı bir Map tanımlanır ve red, green ve blue anahtarlarına sahip renk kodları atanır. range ifadesi kullanılarak, colors haritasındaki tüm anahtar-değer çiftleri tek tek alınır ve for döngüsü içinde kullanılır. color değişkeni, anahtarı temsil eder ve code değişkeni, anahtara karşılık gelen değeri temsil eder. Bu örnekte, renkler ve kodları birlikte yazdırılır.