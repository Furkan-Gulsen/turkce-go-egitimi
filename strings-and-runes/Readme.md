# Strings and Runes

Strings, Go programlama dilinde, Unicode karakterlerinin birleştirilerek oluşturduğu bir karakter dizisidir. Her bir karakter, 1-4 byte arasında değişen boyutlarda olabilir.

```golang
str := "hello"
fmt.Println(str)
fmt.Println(str[0])
fmt.Println(str[1:3])
```

Bu örnekte, str adlı bir string değişkeni tanımlanır ve "hello" değeri atanır. str değişkeni ekrana yazdırılır, ardından str[0] ifadesi kullanılarak, dizinin ilk karakteri olan "h" ekrana yazdırılır. str[1:3] ifadesi kullanılarak, dizinin ikinci ve üçüncü karakterleri olan "el" ekrana yazdırılır.

```golang
for i, r := range "hello" {
    fmt.Printf("%d: %s\n", i, string(r))
}
```

Bu örnekte, for döngüsü kullanarak range fonksiyonu ile "hello" stringinin her bir karakterine erişilir. Her karakterin pozisyonu ve değeri ekrana yazdırılır.
Runes, Go programlama dilinde, bir Unicode karakterinin birleşimini ifade eden bir veri türüdür. Runes, 1-4 byte arasında değişen boyutlarda olabilen karakterleri temsil etmek için kullanılır.

```golang
str := "こんにちは"
for i, r := range str {
    fmt.Printf("%d: %c\n", i, r)
}
```

Bu örnekte, str adlı bir string değişkeni tanımlanır ve "こんにちは" değeri atanır. for döngüsü kullanarak range fonksiyonu ile her bir karakterine erişilir ve karakterin pozisyonu ve değeri ekrana yazdırılır.