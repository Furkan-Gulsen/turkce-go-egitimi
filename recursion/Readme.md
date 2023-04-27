# Recursion

Recursion, Go programlama dilinde, bir fonksiyonun kendisini çağırmasıdır. Bu yapı, belirli bir koşul sağlanana kadar tekrarlanarak işlem yapar.

```golang
func factorial(n int) int {
    if n == 0 {
        return 1
    }
    return n * factorial(n-1)
}
​
fmt.Println(factorial(5))
```

Bu örnekte, factorial adlı bir fonksiyon tanımlanır. Fonksiyon, n adlı bir int türünde parametre alır ve faktöriyel hesaplar. Fonksiyon içinde, if koşulu kullanarak n değerinin 0 olup olmadığını kontrol eder. Eğer n 0 ise, 1 değeri döndürülür. Eğer n 0 değilse, fonksiyon kendini tekrar çağırarak faktöriyel hesaplar. factorial(5) çağrıldıkça sonuçlar ekrana yazdırılır.

```golang
func fibonacci(n int) int {
    if n < 2 {
        return n
    }
    return fibonacci(n-1) + fibonacci(n-2)
}
​
fmt.Println(fibonacci(10))
```

Bu örnekte, fibonacci adlı bir fonksiyon tanımlanır. Fonksiyon, n adlı bir int türünde parametre alır ve Fibonacci sayısını hesaplar. Fonksiyon içinde, if koşulu kullanarak n değerinin 2'den küçük olup olmadığını kontrol eder. Eğer n 2'den küçük ise, n değeri döndürülür. Eğer n 2'den büyük ise, fonksiyon kendini tekrar çağırarak Fibonacci sayısını hesaplar. fibonacci(10) çağrıldıkça sonuçlar ekrana yazdırılır.