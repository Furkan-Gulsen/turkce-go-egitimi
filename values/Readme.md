## Values

Değerler (values), Go programlama dilinde, değişkenlerin taşıdığı verilerdir. Değerler sabit veya değişken olabilirler ve farklı veri tiplerini ifade edebilirler.

Go dilinde temel veri tipleri şunlardır:

- Sayısal veri tipleri: int, float32, float64, complex64, complex128, byte, rune gibi veri tipleri, sayısal değerleri ifade etmek için kullanılır.
- Boolean veri tipi: bool veri tipi, yalnızca true veya false değerlerini alabilen bir veri tipidir.
- String veri tipi: string veri tipi, metin veya karakter dizisi değerlerini ifade etmek için kullanılır.
- Kompleks veri tipleri: struct, array, slice, map, channel gibi veri tipleri, birden fazla veri öğesini bir arada tutmak ve belirli bir amaca hizmet etmek için kullanılır.

Değerlerin türleri, Go dilinde statik olarak belirlenir. Bir değişkene bir değer atadığımızda, bu değişkenin türü belirlenir ve daha sonra bu türü değiştiremeyiz.

```golang
var age int
age = 32

age = "thirty-two" // compile error: cannot use "thirty-two" (type string) as type int in assignment
```

Bu örnekte, age değişkeni önce int türünde tanımlanır ve daha sonra age değişkenine 32 sayısı atanır. Daha sonra age değişkenine "thirty-two" stringi atanmaya çalışılır ve program hata verir. Çünkü, age değişkeni int türünde tanımlandığı için string türünde bir değer atanamaz.
Değerler, programların farklı amaçlar için kullanılmasını sağlar. Örneğin, bir sayısal işlem yapmak için bir int değeri kullanabiliriz veya bir metin işlemek için bir string değeri kullanabiliriz.