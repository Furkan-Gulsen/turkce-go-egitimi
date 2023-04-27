# Arrays

Dizi (array), Go programlama dilinde, aynı tipte birden fazla değişkeni tek bir değişkende tutmamızı sağlayan bir veri yapısıdır. Bir dizi, önceden belirlenmiş bir boyuta ve belirli bir veri tipine sahiptir.

```golang
var a [5]int
a[0] = 1
a[1] = 2
a[2] = 3
a[3] = 4
a[4] = 5
fmt.Println(a)
```

Bu örnekte, a adlı bir dizi tanımlanır ve boyutu 5 olarak belirtilir. Dizinin elemanlarına a[index] söz dizimi ile erişilir ve elemanlar tek tek atanabilir. Bu örnekte, dizi elemanlarına sırasıyla 1, 2, 3, 4 ve 5 değerleri atanır ve fmt.Println(a) ifadesi kullanılarak tüm dizinin elemanları ekrana yazdırılır.

Dizilerin boyutu, bir kere tanımlandıktan sonra değiştirilemez. Ancak, Go dilindeki dil özellikleri ile dizi boyutları değiştirilebilir. Bu özellik, Go dilinde slice adı verilen bir veri yapısı ile gerçekleştirilir.

```golang
a := [5]int{1, 2, 3, 4, 5}
fmt.Println(a)
```

Bu örnekte, a adlı bir dizi tanımlanır ve elemanları {1, 2, 3, 4, 5} olarak atanır. Dizinin boyutu, elemanların sayısına eşit olmalıdır. Bu örnekte, a adlı dizi, {1, 2, 3, 4, 5} değerleri ile başlatılır ve tüm elemanları ekrana yazdırılır.