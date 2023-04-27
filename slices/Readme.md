# Slices

Dilin temel veri yapılarından biri olan dilimler (slices), Go programlama dilinde, boyutu değiştirilebilen, esnek bir dizi veri yapısıdır. Dilimler, dizilerin bir alt kümesi olarak düşünülebilir ve Go dilinde sıkça kullanılır.

```golang
a := []int{1, 2, 3, 4, 5}
fmt.Println(a)
```

Bu örnekte, a adlı bir dilim tanımlanır ve elemanları {1, 2, 3, 4, 5} olarak atanır. Dizilerden farklı olarak, dilimlerin boyutu tanımlama aşamasında belirtilmez. Dilimler, boş da tanımlanabilir.

```golang
var a []int
a = append(a, 1)
a = append(a, 2, 3, 4, 5)
fmt.Println(a)
```

Bu örnekte, a adlı bir dilim tanımlanır ve append() fonksiyonu ile elemanlarına sırasıyla 1, 2, 3, 4 ve 5 değerleri eklenir. append() fonksiyonu, bir dilime bir veya birden fazla eleman eklemek için kullanılır.

Dilimler, dizilerden farklı olarak, bir alt küme olarak da tanımlanabilir.

```golang
a := []int{1, 2, 3, 4, 5}
b := a[1:4]
fmt.Println(b)
```

Bu örnekte, a adlı bir dilim tanımlanır ve elemanlarına {1, 2, 3, 4, 5} değerleri atanır. b adlı bir dilim de a diliminin 1 indeksinden 4 indeksine kadar olan alt kısmını içerir. b dilimindeki elemanlar {2, 3, 4} olarak çıktı olarak verilir.