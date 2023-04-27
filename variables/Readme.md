## Variables

Değişkenler (variables), Go programlama dilinde veri saklamak için kullanılan temel yapı taşlarından biridir. Bir değişkene bir değer atayarak, o değişkenin tuttuğu değeri programda kullanabiliriz.

Değişkenlerin tanımlanması, var anahtar kelimesi ile yapılır. Tanımlanacak değişkenin adı ve veri tipi belirtilir. İlk değer verilmediğinde, Go dilinde değişkenlerin varsayılan bir değeri vardır.

```golang
var name string
name = "John Doe"
```

Bu örnekte, name adında bir değişken tanımlanır ve bu değişkenin tipi string olarak belirlenir. Daha sonra, name değişkenine "John Doe" stringi atanır.
Değişkenlerin değeri değiştirilebilir ve farklı veri tiplerinde olabilirler.

```golang
var age int
age = 32

age = "thirty-two" // compile error: cannot use "thirty-two" (type string) as type int in assignment
````

Bu örnekte, önce age adında bir değişken tanımlanır ve bu değişkenin tipi int olarak belirlenir. Daha sonra, age değişkenine 32 sayısı atanır.

Sonrasında age değişkenine "thirty-two" stringi atanmaya çalışılır ve program hata verir. Çünkü, age değişkeni int tipinde tanımlandığı için string tipinde bir değer atanamaz.

Değişkenler, programlarda belirli bir amaca hizmet etmek için kullanılırlar. Örneğin, bir kullanıcının ismi, yaşı veya bir dizi sayısal değer saklanabilir.