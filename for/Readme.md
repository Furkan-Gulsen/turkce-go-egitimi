## For

for döngüsü, Go programlama dilinde, belirli bir koşul doğru olduğu sürece tekrarlanan kod bloklarını ifade etmek için kullanılır. for döngüsü, bir başlangıç durumu, bir koşul ve bir adım sayısı içerir.

```golang
for i := 0; i < 5; i++ {
    fmt.Println(i)
}
```

Bu örnekte, for döngüsü, i değişkeninin 0 değerinden başlayarak, i değişkeni < 5 koşulunu sağladığı sürece tekrarlanan bir döngüdür. Döngüdeki her adımda i değişkeni 1 artırılır ve sonuçta i değeri 4 olur.

for döngüsü, koşul kısmı sağlanana kadar tekrarlanır. Koşul kısmı doğru olmadığında, döngü sona erer. Ayrıca, for döngüsü break veya continue ifadeleri ile de kontrol edilebilir.

```golang
for i := 0; i < 10; i++ {
    if i == 3 {
        break
    }
    if i%2 == 0 {
        continue
    }
    fmt.Println(i)
}
```

Bu örnekte, for döngüsü, i değişkeninin 0 değerinden başlayarak, i değişkeni < 10 koşulunu sağladığı sürece tekrarlanan bir döngüdür. Döngüdeki her adımda, i değişkeni 1 artırılır.

Döngü, if koşulu ile kesilir ve break ifadesi çalıştırılır. Ayrıca, i değeri 3 olduğunda da döngü sona erer.

Döngü içindeki diğer if koşulu ise, eğer i değeri çift sayı ise bir sonraki adıma geçerek i değerini yazdırmaz. Bu koşulun nedeni, sadece tek sayıları yazdırmak istememizdir.