# Pointers

Pointers, Go programlama dilinde, bir değişkenin bellek adresini tutan bir veri türüdür. Bellek adresi, değişkenin tutulduğu bellek bölgesinin başlangıç adresidir.

```golang
func zeroVal(val int) {
    val = 0
}
​
func zeroPtr(ptr *int) {
    *ptr = 0
}
​
x := 5
zeroVal(x)
fmt.Println(x)
​
y := 5
zeroPtr(&y)
fmt.Println(y)
```

Bu örnekte, zeroVal adlı bir fonksiyon tanımlanır. Fonksiyon, bir int türünde parametre alır ve val adlı değişkenin değerini 0 olarak değiştirir. zeroPtr adlı bir fonksiyon tanımlanır. Fonksiyon, bir int türünde bir pointer (*int) parametre alır ve pointer ile gösterilen değişkenin değerini 0 olarak değiştirir. x adlı bir değişkene 5 değeri atanır ve zeroVal(x) fonksiyonu çağrılır. Fonksiyon çağrıldıktan sonra, x'in değeri 0 olarak değişmez. y adlı bir değişkene 5 değeri atanır ve zeroPtr(&y) fonksiyonu çağrılır. Fonksiyon çağrıldıktan sonra, y'nin değeri 0 olarak değişir.

```golang
func swap(a, b *int) {
    temp := *a
    *a = *b
    *b = temp
}
​
x := 5
y := 10
swap(&x, &y)
fmt.Println(x, y)
```

Bu örnekte, swap adlı bir fonksiyon tanımlanır. Fonksiyon, iki adet pointer (*int) parametre alır ve bu parametreler ile gösterilen iki değişkenin değerlerini birbirleriyle değiştirir. x adlı bir değişkene 5 değeri atanır ve y adlı bir değişkene 10 değeri atanır. swap(&x, &y) fonksiyonu çağrılır ve bu fonksiyon çağrıldıktan sonra x'in değeri 10, y'nin değeri ise 5 olarak değişir.