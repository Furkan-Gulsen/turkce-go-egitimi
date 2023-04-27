# if/else

if ve else ifadeleri, Go programlama dilinde, belirli koşulların doğru veya yanlış olması durumunda farklı kod bloklarının çalışmasını sağlar.

```golang
if x > 0 {
    fmt.Println("Positive number")
} else if x < 0 {
    fmt.Println("Negative number")
} else {
    fmt.Println("Zero")
}
```

Bu örnekte, if ifadesi, x değişkeninin 0 dan büyük olması durumunda "Positive number" metnini yazdıracaktır. Eğer x değişkeni 0 dan büyük değilse, else if ifadesi kontrol edilecek ve x değişkeninin 0 dan küçük olması durumunda "Negative number" metnini yazdıracaktır. Eğer x değişkeni 0 dan büyük veya küçük değilse, else bloğu çalışacak ve "Zero" metnini yazdıracaktır.

```golang
if ve else ifadeleri, karmaşık koşulları kontrol etmek için de kullanılabilir.
if x > 10 && x < 20 {
    fmt.Println("x is between 10 and 20")
} else if x > 20 && x < 30 {
    fmt.Println("x is between 20 and 30")
} else {
    fmt.Println("x is not between 10 and 30")
}
```

Bu örnekte, if ifadesi, x değişkeninin 10 ve 20 arasında olması durumunda "x is between 10 and 20" metnini yazdıracaktır. Eğer x değişkeni 10 ve 20 arasında değilse, else if ifadesi kontrol edilecek ve x değişkeninin 20 ve 30 arasında olması durumunda "x is between 20 and 30" metnini yazdıracaktır. Eğer x değişkeni 10 ve 30 arasında değilse, else bloğu çalışacak ve "x is not between 10 and 30" metnini yazdıracaktır.