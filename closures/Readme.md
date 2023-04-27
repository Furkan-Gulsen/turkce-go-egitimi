# Closures

Closures, Go programlama dilinde, bir fonksiyonun bir iç fonksiyon tarafından kullanılmasıyla oluşan bir yapıdır. Bu yapı, bir fonksiyonun içindeki başka bir fonksiyona referans vererek, bir fonksiyonun çalıştığı bağlamın dışındaki değişkenlere erişim sağlar.

```golang
func outer() func() int {
    count := 0
    return func() int {
        count++
        return count
    }
}
​
increment := outer()
fmt.Println(increment())
fmt.Println(increment())
fmt.Println(increment())
````

Bu örnekte, outer adlı bir fonksiyon tanımlanır. Fonksiyon, bir iç fonksiyon döndürür ve iç fonksiyon, count adlı bir değişkene erişim sağlar. increment adlı bir değişkene outer() fonksiyonu atanır ve bu değişken ile iç fonksiyon çalıştırılır. count değişkeni, increment() çağrıldıkça artar ve her seferinde artışı ekrana yazdırılır.

```golang
func adder(a int) func(int) int {
    return func(b int) int {
        return a + b
    }
}
​
addFive := adder(5)
fmt.Println(addFive(2))
fmt.Println(addFive(3))
```

Bu örnekte, adder adlı bir fonksiyon tanımlanır. Fonksiyon, a adlı bir int türünde parametre alır ve bir iç fonksiyon döndürür. İç fonksiyon, b adlı bir int türünde parametre alır ve a ile b parametrelerinin toplamını geri döndürür. addFive adlı bir değişkene adder(5) fonksiyonu atanır ve bu değişken ile iç fonksiyon çalıştırılır. addFive(2) ve addFive(3) çağrıldıkça sonuçlar ekrana yazdırılır.