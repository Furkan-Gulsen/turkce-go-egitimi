<h1 align="center">
  <img alt="logo" src="https://miro.medium.com/v2/resize:fit:1200/0*DWuaFZuGhnXDKCds.png" width="224px"/><br/>Türkçe Go Eğitimi
</h1>



Bu repo, Go dilini hızlı bir şekilde öğrenmek isteyenler için hazırlanmış bir eğitim serisidir. Toplamda 40 konuyu, örnekler üzerinden anlatarak dilin temel yapılarını kapsar. Aynı zamanda bu eğitim serisi, Go dilini öğrenmek isteyenlere düzenli bir kaynak sunmayı amaçlar. Her bir konu, açıklayıcı ve anlaşılır bir şekilde ele alınmıştır, böylece okuyucuların Go dilini kolayca ve hızlıca öğrenmeleri hedeflenir. Bu eğitim serisini aynı zamanda [https://docs.furkangulsen.com/golang-dokumani](https://docs.furkangulsen.com/golang-dokumani) web sitesinden de takip edebilirsiniz.

Repoyu beğenirseniz daha fazla kişiye ulaşması için yıldız atabilir ve sosyal medya hesaplarınızda paylaşabilirsiniz  ⭐️


<br>

# Nedir bu Go?

Go, basit, hızlı ve güvenilir yazılım geliştirmek için tasarlanmış açık kaynak bir programlama dilidir. Go dili, hızlı bir derleme süreci, hafif syntax yapısı ve etkili bir garbage collection sistemine sahip olmasıyla öne çıkar.

Go dilinin kullanımı, çeşitli geliştirme araçları, paketleri ve modülleri içerir. Geliştiriciler, Go diliyle birçok farklı uygulama türünü geliştirebilirler, örneğin web uygulamaları, API'ler, veritabanı sistemleri, ağ yazılımı ve daha pek çok şey.

Go dilinin temel özelliklerinden biri, hızlı bir derleme sürecidir. Go, C diline benzer syntax yapısı ve C++ gibi dillerdeki nesne yönelimli özellikleri kullanır. Go dilinde garbage collection, hafif iş parçacıkları, kapsüllü tip sistemleri, ve dinamik bellek yönetimi gibi özellikler de mevcuttur.

Go dilinin bir diğer önemli özelliği, etkili paket yönetimi sistemidir. Go dilinde, modüller ve paketler, yazılım geliştiricilerinin kodlarını düzenli bir şekilde organize etmelerine ve geliştirmelerine olanak tanır. Bu sayede, geliştiriciler kolayca tekrar kullanılabilir kodlar yazabilirler.

Sonuç olarak, Go dilinin temel özellikleri arasında hızlı derleme süreci, hafif syntax yapısı, etkili paket yönetimi, garbage collection, ve kapsüllü tip sistemleri gibi özellikler bulunur. Go dilinde geliştirme yapmak, birçok uygulama türü için uygun bir seçenektir ve yazılım geliştirme sürecini hızlandırmaya yardımcı olabilir.

<br>

# İçerik:

- [Values](#values)
- [Variables](#variables)
- [Constants](#constants)
- [For](#for)
- [If-Else](#if-else)
- [Switch](#switch)
- [Arrays](#arrays)
- [Slices](#slices)
- [Maps](#maps)
- [Range](#range)
- [Functions](#functions)
- [Variadic Functions](#variadic-functions)
- [Closures](#closures)
- [Recursion](#recursion)
- [Pointers](#pointers)
- [String Functions](#string-functions)
- [Structs](#structs)
- [Methods](#methods)
- [Interfaces](#interfaces)
- [Struct Embedding](#struct-embedding)
- [Errors](#errors)
- [Goroutines](#goroutines)
- [Channel](#channel)
- [Select](#select)
- [Timeouts](#timeouts)
- [Non-Blocking Channel](#non-blocking-channel)
- [Closing Channels](#closing-channels)
- [Range over Channels](#range-over-channels)
- [Timers](#timers)
- [Tickers](#tickers)
- [Worker Pools](#worker-pools)
- [Wait Groups](#wait-groups)
- [Rate Limiting](#rate-limiting)
- [Atomic Counters](#atomic-counters)
- [Sorting](#sorting)
- [Panic](#panic)
- [Defer](#defer)
- [Recover](#recover)
- [Strings and Runes](#strings-and-runes)
- [Text Templates](#text-templates)
- [JSON](#json)


---

<br>

# Values

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

<br>

---

<br>

<br><br>

# Variables

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


<br><br>


# Constants

Sabitler (constants), Go programlama dilinde, programın herhangi bir yerinde değiştirilemeyen, sabit değerlerdir. Sabitler, bir kere tanımlanır ve daha sonra programın herhangi bir yerinde kullanılabilirler.

Sabitler, const anahtar kelimesi ile tanımlanır ve veri tipleri belirtilir. Sabitlere ilk değer verilmesi zorunludur ve daha sonra değiştirilemezler.

```golang
const pi = 3.14159
const welcomeMessage = "Welcome to Go programming"
````

Bu örnekte, pi sabiti float64 türünde tanımlanır ve ilk değeri 3.14159 olarak atanır. Daha sonra, welcomeMessage sabiti string türünde tanımlanır ve ilk değeri "Welcome to Go programming" olarak atanır.

Sabitler, programların belirli bir amaç için kullanılacak sabit değerlerini tutmak için kullanılırlar. Örneğin, pi sayısı veya belirli bir mesaj veya hata kodu gibi. Sabitler, programların daha okunaklı ve bakımı kolay hale getirilmesine yardımcı olur ve aynı sabitin programda farklı yerlerinde birden fazla kez kullanılmasını kolaylaştırır.

Sabitler, programın herhangi bir yerinde kullanılabildiğinden, farklı dosyalar arasında da paylaşılabilirler. Ayrıca, sabitlerin değiştirilemez olması, program hatalarını azaltır ve güvenliği artırır.




<br><br>

# For

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





<br><br>

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




<br><br>

# Switch

switch ifadesi, Go programlama dilinde, belirli koşullara göre farklı işlemler yapmak için kullanılır:

```golang
day := "sunday"
​
switch day {
case "monday":
    fmt.Println("Today is Monday")
case "tuesday":
    fmt.Println("Today is Tuesday")
case "wednesday":
    fmt.Println("Today is Wednesday")
case "thursday":
    fmt.Println("Today is Thursday")
case "friday":
    fmt.Println("Today is Friday")
case "saturday":
    fmt.Println("Today is Saturday")
case "sunday":
    fmt.Println("Today is Sunday")
default:
    fmt.Println("Invalid day")
}
```

Bu örnekte, switch ifadesi, day değişkeninin değerine göre farklı işlemler yapar. Eğer day değişkeni "monday" ise "Today is Monday" metnini yazdırır. Eğer day değişkeni "tuesday" ise "Today is Tuesday" metnini yazdırır. Bu şekilde, day değişkeninin değerine göre farklı kod blokları çalıştırılabilir.

default ifadesi, tüm koşulların doğru olmadığı durumlarda çalışacak olan bir kod bloğunu ifade eder.

```golang
switch x {
case 1:
    fmt.Println("x is 1")
case 2:
    fmt.Println("x is 2")
case 3:
    fmt.Println("x is 3")
default:
    fmt.Println("x is not 1, 2 or 3")
}
```

Bu örnekte, switch ifadesi, x değişkeninin değerine göre farklı işlemler yapar. Eğer x değişkeni 1 ise "x is 1" metnini yazdırır. Eğer x değişkeni 2 ise "x is 2" metnini yazdırır. Eğer x değişkeni 3 ise "x is 3" metnini yazdırır. Eğer x değişkeni 1, 2 veya 3 değilse, default bloğu çalışacak ve "x is not 1, 2 or 3" metnini yazdıracaktır.




<br><br>

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



<br><br>

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



<br><br>

# Maps

Map, Go programlama dilinde, bir anahtar-değer çiftleri koleksiyonudur. Map veri yapısı, diğer programlama dillerindeki dictionary, hash table veya associative array gibi veri yapılarına benzer. Bir Map veri yapısı, belirli bir anahtar için bir değer saklar.

```golang
var colors map[string]string
colors = make(map[string]string)
colors["red"] = "#FF0000"
colors["green"] = "#00FF00"
colors["blue"] = "#0000FF"
fmt.Println(colors)
```

Bu örnekte, colors adlı bir Map tanımlanır ve make() fonksiyonu ile oluşturulur. colors veri yapısına red, green ve blue anahtarlarına sahip renk kodları eklenir ve fmt.Println(colors) ifadesi kullanılarak Map veri yapısındaki tüm anahtar-değer çiftleri ekrana yazdırılır.

Map veri yapısı, diğer programlama dillerindeki veri yapılarından farklı olarak, anahtarlar için belirli bir veri tipi ve değerler için belirli bir veri tipi belirtmek zorunda değildir. Anahtarlar ve değerler farklı veri tiplerinde olabilir.

```golang
ages := map[string]int{
    "Alice": 25,
    "Bob":   30,
    "Carol": 35,
}
fmt.Println(ages)
```

Bu örnekte, ages adlı bir Map tanımlanır ve string türünde anahtarlar ve int türünde değerlerle ilgili çiftler atanır. Map veri yapısının oluşturulması ve eleman eklenmesi make() fonksiyonu ile birleştirilerek de yapılabilir.




<br><br>

# Range

range ifadesi, Go programlama dilinde, belirli bir dizi, dilim veya harita üzerinde döngü oluşturmak için kullanılır. range ifadesi, veri yapısındaki tüm elemanları tek tek ele almak için kullanılır.

```golang
numbers := []int{1, 2, 3, 4, 5}
for i, num := range numbers {
    fmt.Println("index:", i, "number:", num)
}
```

Bu örnekte, numbers adlı bir dilim tanımlanır ve elemanlarına {1, 2, 3, 4, 5} değerleri atanır. range ifadesi kullanılarak, numbers dilimindeki tüm elemanlar tek tek alınır ve for döngüsü içinde kullanılır. i değişkeni, döngünün sırasıdaki indeks değerini, num değişkeni ise indeksteki elemanı temsil eder. Bu örnekte, indeksler ve elemanlar birlikte yazdırılır.

```golang
colors := map[string]string{
    "red":   "#FF0000",
    "green": "#00FF00",
    "blue":  "#0000FF",
}
for color, code := range colors {
    fmt.Println("color:", color, "code:", code)
}
```

Bu örnekte, colors adlı bir Map tanımlanır ve red, green ve blue anahtarlarına sahip renk kodları atanır. range ifadesi kullanılarak, colors haritasındaki tüm anahtar-değer çiftleri tek tek alınır ve for döngüsü içinde kullanılır. color değişkeni, anahtarı temsil eder ve code değişkeni, anahtara karşılık gelen değeri temsil eder. Bu örnekte, renkler ve kodları birlikte yazdırılır.



<br><br>

# Functions

Function, Go programlama dilinde, belirli bir işlevi yerine getiren kod bloklarını ifade eder. Bir fonksiyon, bir veya birden fazla parametre alabilir, bir işlem gerçekleştirebilir ve bir veya birden fazla sonuç döndürebilir.

```golang
func add(a int, b int) int {
    return a + b
}
​
result := add(5, 10)
fmt.Println(result)
```

Bu örnekte, add adlı bir fonksiyon tanımlanır. Fonksiyon, a ve b adlı iki int tipinde parametre alır ve bu parametreler toplanarak toplam sonucu int tipinde geri döndürür. add fonksiyonu, 5 ve 10 parametreleri ile çağrılır ve sonuç fmt.Println(result) ifadesi ile yazdırılır.

```golang
func swap(a, b string) (string, string) {
    return b, a
}
​
x, y := swap("hello", "world")
fmt.Println(x, y)
```

Bu örnekte, swap adlı bir fonksiyon tanımlanır. Fonksiyon, a ve b adlı iki string tipinde parametre alır ve bu parametreleri birbirleriyle yer değiştirerek geri döndürür. swap fonksiyonu, "hello" ve "world" parametreleri ile çağrılır ve geri döndürülen sonuçlar x ve y değişkenleri tarafından alınır. Sonuçlar, fmt.Println(x, y) ifadesi ile yazdırılır.




<br><br>

# Variadic Functions

Variadic Functions, Go programlama dilinde, değişken sayıda argüman alan fonksiyonlardır. Bu fonksiyonlar, bir veya birden fazla argüman alabilir ve değişken sayıda argüman alabilir.

```golang
func sum(nums ...int) int {
    total := 0
    for _, num := range nums {
        total += num
    }
    return total
}

fmt.Println(sum(1, 2, 3, 4, 5))
fmt.Println(sum(2, 4, 6))
```

Bu örnekte, sum adlı bir fonksiyon tanımlanır. Fonksiyon, nums adlı bir int türünde değişken sayıda parametre alır ve toplamını geri döndürür. Fonksiyon içinde, for döngüsü kullanarak nums dizisindeki tüm elemanların toplamı hesaplanır. Fonksiyon, sum(1, 2, 3, 4, 5) ve sum(2, 4, 6) şeklinde çağrılır ve sonuçlar ekrana yazdırılır.

```golang
func concatenate(sep string, strs ...string) string {
    result := ""
    for i, str := range strs {
        if i > 0 {
            result += sep
        }
        result += str
    }
    return result
}

fmt.Println(concatenate(", ", "foo", "bar", "baz"))
fmt.Println(concatenate("-", "hello", "world"))
```

Bu örnekte, concatenate adlı bir fonksiyon tanımlanır. Fonksiyon, sep adlı bir string türünde ve değişken sayıda strs adlı string türünde parametre alır. Fonksiyon içinde, for döngüsü kullanarak strs dizisindeki tüm elemanların birleştirilmesi ve sep ayraç karakteri ile birleştirilmesi sağlanır. Fonksiyon, concatenate(", ", "foo", "bar", "baz") ve concatenate("-", "hello", "world") şeklinde çağrılır ve sonuçlar ekrana yazdırılır.






<br><br>

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




<br><br>

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




<br><br>

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



<br><br>

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




<br><br>

# Structs

Structs, Go programlama dilinde, farklı veri türlerini içeren bir veri yapısıdır. Bu yapıda, farklı veri türlerine sahip verileri bir arada tutabilir ve bu veriler üzerinde işlemler yapabilirsiniz.

```golang
type Person struct {
    Name string
    Age  int
}

var p Person
p.Name = "John Doe"
p.Age = 42
fmt.Println(p)
fmt.Printf("Name: %s, Age: %d\n", p.Name, p.Age)
```

Bu örnekte, Person adlı bir struct oluşturulur ve Name adlı bir string türünde ve Age adlı bir int türünde iki adet özellik tanımlanır. var anahtar kelimesi ile p adlı bir Person türünde değişken tanımlanır. p değişkeninin Name ve Age özellikleri, p.Name ve p.Age ifadeleri kullanılarak atama işlemi yapılır ve fmt.Println() fonksiyonu ile p değişkeni ekrana yazdırılır. Ayrıca p.Name ve p.Age ifadeleri kullanılarak, Name ve Age özellikleri ayrı ayrı ekrana yazdırılır.

```golang
type Rectangle struct {
    width  float64
    height float64
}

func (r Rectangle) area() float64 {
    return r.width * r.height
}

r := Rectangle{width: 3.0, height: 4.0}
fmt.Println(r.area())
````

Bu örnekte, Rectangle adlı bir struct oluşturulur ve width adlı bir float64 türünde ve height adlı bir float64 türünde iki adet özellik tanımlanır. area adlı bir fonksiyon, Rectangle türünde bir parametre alır ve dikdörtgenin alanını hesaplar. Fonksiyonun döndürdüğü sonuç, dikdörtgenin alanıdır. r adlı bir Rectangle değişkeni oluşturulur ve width ve height özelliklerine 3.0 ve 4.0 değerleri atanır. r.area() ifadesi kullanılarak, dikdörtgenin alanı hesaplanır ve sonuç ekrana yazdırılır.




<br><br>

# Methods

Methods, Go programlama dilinde, bir veri yapısına özgü işlemleri gerçekleştirmek için kullanılan bir fonksiyon türüdür. Bu işlemler, veri yapısının özellikleri üzerinde çalışarak sonuç üretirler.

```golang
type Rectangle struct {
    width  float64
    height float64
}

func (r Rectangle) area() float64 {
    return r.width * r.height
}

func (r Rectangle) perimeter() float64 {
    return 2 * (r.width + r.height)
}

r := Rectangle{width: 3.0, height: 4.0}
fmt.Println(r.area())
fmt.Println(r.perimeter())
```

Bu örnekte, Rectangle adlı bir struct oluşturulur ve width adlı bir float64 türünde ve height adlı bir float64 türünde iki adet özellik tanımlanır. area adlı bir fonksiyon, Rectangle türünde bir parametre alır ve dikdörtgenin alanını hesaplar. Fonksiyonun döndürdüğü sonuç, dikdörtgenin alanıdır. perimeter adlı bir fonksiyon, Rectangle türünde bir parametre alır ve dikdörtgenin çevresini hesaplar. Fonksiyonun döndürdüğü sonuç, dikdörtgenin çevresidir. r adlı bir Rectangle değişkeni oluşturulur ve width ve height özelliklerine 3.0 ve 4.0 değerleri atanır. r.area() ve r.perimeter() ifadeleri kullanılarak, dikdörtgenin alanı ve çevresi hesaplanır ve sonuçlar ekrana yazdırılır.

```golang
type Person struct {
    Name string
    Age  int
}

func (p *Person) setName(name string) {
    p.Name = name
}

func (p *Person) setAge(age int) {
    p.Age = age
}

func (p Person) getName() string {
    return p.Name
}

func (p Person) getAge() int {
    return p.Age
}

p := Person{Name: "John Doe", Age: 42}
p.setName("Jane Doe")
p.setAge(35)
fmt.Printf("Name: %s, Age: %d\n", p.getName(), p.getAge())
```

Bu örnekte, Person adlı bir struct oluşturulur ve Name adlı bir string türünde ve Age adlı bir int türünde iki adet özellik tanımlanır. setName adlı bir fonksiyon, Person türünde bir pointer (*Person) parametre alır ve kişinin ismini değiştirir. setAge adlı bir fonksiyon, Person türünde bir pointer (*Person) parametre alır ve kişinin yaşını değiştirir. getName adlı bir fonksiyon, Person türünde bir parametre alır ve kişinin adını döndürür. getAge adlı bir fonksiyon, Person





<br><br>

# Interfaces

Go dilinde interface, bir veya birden fazla metodun belirli bir imza setini tanımlayan bir veri tipidir. Bu imza seti, bir veri tipinin hangi metodları uygulaması gerektiğini belirtir. Bu nedenle, interface'ler, bir veri tipinin hangi özelliklere sahip olduğunu tanımlamak için kullanılır.

Örneğin, bir şeklin alanını hesaplamak için area adlı bir fonksiyon tanımlamış olsunuz. Kare, daire ve dikdörtgen gibi farklı şekiller, area fonksiyonunu farklı şekillerde uygular. Bu durumda, her bir şeklin alanını hesaplamak için ayrı ayrı fonksiyonlar tanımlamak yerine, interface kullanarak hepsini aynı türdeki bir veri tipinde toplayabilirsiniz.

```golang
package main

import (
	"fmt"
	"math"
)

type Shape interface {
	area() float64
}

type Circle struct {
	radius float64
}

type Rectangle struct {
	width, height float64
}

type Square struct {
	side float64
}

func (c Circle) area() float64 {
	return math.Pi * c.radius * c.radius
}

func (r Rectangle) area() float64 {
	return r.width * r.height
}

func (s Square) area() float64 {
	return s.side * s.side
}

func getArea(shape Shape) float64 {
	return shape.area()
}

func main() {
	circle := Circle{radius: 5}
	rectangle := Rectangle{width: 5, height: 10}
	square := Square{side: 5}

	fmt.Printf("Circle area: %f\n", getArea(circle))
	fmt.Printf("Rectangle area: %f\n", getArea(rectangle))
	fmt.Printf("Square area: %f\n", getArea(square))
}
```

Bu örnekte, Shape adlı bir interface tanımlanır ve area adlı bir fonksiyon imzası belirtilir. Circle, Rectangle ve Square adlı üç farklı yapı tanımlanır ve her biri area adlı bir fonksiyona sahiptir.
getArea adlı bir fonksiyon tanımlanır ve parametresi Shape türündedir. Bu fonksiyon, alanı hesaplanacak şekil verisini alır ve area fonksiyonu çağrılarak şeklin alanını hesaplar.
main fonksiyonunda, örnek olarak circle, rectangle ve square adlı üç farklı değişken oluşturulur. Bu değişkenlerin her biri getArea fonksiyonuna parametre olarak verilir ve her bir şeklin alanı hesaplanarak ekrana yazdırılır.

Çıktı:

```
Circle area: 78.539816
Rectangle area: 50.000000
Square area: 25.000000
``` 




<br><br>

# Struct Embedding

Go dilinde struct embedding, bir struct'ın başka bir struct içinde yerleştirilmesi anlamına gelir. Böylece, iç içe geçmiş yapılar oluşturulabilir ve kod tekrarı azaltılabilir.

```golang
package main

import "fmt"

type Person struct {
	Name string
	Age  int
}

func (p Person) SayHello() {
	fmt.Printf("Hello, my name is %s and I'm %d years old\n", p.Name, p.Age)
}

type Employee struct {
	Person
	Company string
}

func main() {
	emp := Employee{
		Person: Person{
			Name: "John",
			Age:  30,
		},
		Company: "ABC Inc.",
	}

	emp.SayHello()
}
```

Bu örnekte, Person adlı bir struct tanımlanır ve Name ve Age adlı iki özelliği vardır. Ayrıca SayHello adlı bir fonksiyonu da bulunur.

Employee adlı bir struct tanımlanır ve Person adlı bir struct içinde yerleştirilir. Employee'nin kendine ait bir Company adlı bir özelliği de vardır.
main fonksiyonunda, emp adlı bir Employee değişkeni oluşturulur. Bu değişkenin Person özelliğine bir Person türünden veri atanır. SayHello fonksiyonu, emp değişkeni üzerinden çağrılır ve sonuç ekrana yazdırılır.

Çıktı:

```
Hello, my name is John and I'm 30 years old
```

Bu örnekte, Employee adlı bir yapı, Person yapısını içerir. Bu, Employee yapısına Person yapısının tüm özelliklerini ekler. Böylece, Employee yapısını kullanarak hem Employee hem de Person verilerine erişilebilir. Bu özellik, kod tekrarını azaltır ve yapıları daha modüler hale getirir.



<br><br>

# Errors

Go dilinde hata yönetimi, error adlı bir veri tipi kullanılarak yapılır. error veri tipi, hata mesajı veya nil değeri döndüren bir fonksiyondan dönen değerleri işlemek için kullanılır.

```golang
package main

import (
	"errors"
	"fmt"
)

func divide(x, y float64) (float64, error) {
	if y == 0 {
		return 0, errors.New("Cannot divide by zero")
	}
	return x / y, nil
}

func main() {
	result, err := divide(10, 2)
	if err != nil {
		fmt.Println(err)
	} else {
		fmt.Println(result)
	}

	result, err = divide(10, 0)
	if err != nil {
		fmt.Println(err)
	} else {
		fmt.Println(result)
	}
}
```

Bu örnekte, divide adlı bir fonksiyon tanımlanır ve iki sayıyı böler. Ancak, eğer ikinci sayı 0 ise bir hata döndürür.

main fonksiyonunda, divide fonksiyonu iki farklı parametreyle çağrılır. err adlı bir hata değişkeni kullanılarak her bir çağrı sonucu kontrol edilir. Eğer hata varsa hata mesajı ekrana yazdırılır. Aksi halde, sonuç ekrana yazdırılır.

Çıktı:
```
5 <nil>
Cannot divide by zero
```

Bu örnekte, error kullanarak hata yönetimi örneği yapılmıştır. divide fonksiyonu, ikinci parametresi 0 ise hata döndürür. main fonksiyonunda, err adlı bir hata değişkeni kullanılarak her çağrının sonucu kontrol edilir. Eğer hata varsa, hata mesajı ekrana yazdırılır. Aksi halde, sonuç ekrana yazdırılır.





<br><br>

# Goroutines

Goroutines, Go dilinde eşzamanlı olarak çalışan işlemlerdir. Goroutines, go anahtar kelimesi kullanılarak oluşturulur ve farklı işlemleri eşzamanlı olarak gerçekleştirmek için kullanılır.

```golang
package main

import (
	"fmt"
	"time"
)

func sayHello() {
	fmt.Println("Hello")
}

func main() {
	go sayHello() // goroutine
	time.Sleep(time.Second)
	fmt.Println("World")
}
```

Bu örnekte, sayHello adlı bir fonksiyon tanımlanır ve Hello adlı bir mesajı ekrana yazdırır.

main fonksiyonunda, sayHello fonksiyonu bir goroutine olarak çağrılır. Bu nedenle, sayHello fonksiyonunun çalışması diğer işlemlerden bağımsız olarak gerçekleşir. time.Sleep fonksiyonu, bir saniyelik bir bekleme süresi ekler. Son olarak, World adlı bir mesaj ekrana yazdırılır.

Çıktı:
```
Hello
World
```

Bu örnekte, goroutine kullanarak, sayHello fonksiyonu eşzamanlı olarak çalıştırıldı. sayHello fonksiyonu, goroutine olarak çağrıldığı için, diğer işlemlerden bağımsız olarak çalıştı ve sonuç olarak ekrana Heşşp mesajı yazdırıldıktan sonra World mesajı yazdırıldı.




<br><br>

# Channel

Go dilinde channel, goroutines arasında veri iletişimi yapmak için kullanılan bir veri yapısıdır. Channel, make anahtar kelimesi kullanılarak oluşturulur ve <- operatörü kullanılarak veri gönderme ve alma işlemleri yapılır.

```golang
package main

import "fmt"

func main() {
	messages := make(chan string)

	go func() { messages <- "Hello" }()

	msg := <-messages
	fmt.Println(msg)
}
```

Bu örnekte, messages adlı bir channel oluşturulur.

go anahtar kelimesi kullanılarak, bir goroutine oluşturulur ve bu goroutine, messages channel'ına bir Hello mesajı gönderir.

main fonksiyonunda, msg adlı bir değişkene messages channel'ından bir mesaj alınır ve ekrana yazdırılır.

Çıktı:
```
Hello
```

Bu örnekte, channel kullanarak, bir goroutine'dan ana iş parçacığına bir mesaj gönderildi. Bu nedenle, goroutine işlemi tamamlandıktan sonra ana iş parçacığı channel'dan mesajı alır ve sonucu ekrana yazdırır.

Kanallar, Golang'de birçok durumda kullanılabilir, örneğin:

1. Goroutineler arasında veri alışverişi yapmak için
2. Senkronizasyon işlemleri için
3. Uygulamanızın performansını artırmak için (paralel işlem yapmak)
4. Goroutineler arasında veri yarışmalarını önlemek için
5. Görevlerin koordinasyonu ve senkronizasyonu için

<br><br>

# Nedir bu Paralel işlemler?

Paralel işlemler, bir uygulamanın aynı anda birden fazla işlemi eşzamanlı olarak yapabilmesine olanak tanıyan bir tekniktir. Bu teknik, özellikle büyük veri işleme, hesaplama yoğunluğu yüksek işlemler ve çoklu kullanıcı desteği gerektiren uygulamalar gibi durumlarda önemlidir.

Golang, paralel işlem yapmak için goroutine'leri kullanır. Goroutine'ler, hafif iş parçacıklarıdır ve işlemci çekirdeklerindeki boş zamanları kullanarak uygulamanızı paralel ve yüksek performanslı hale getirirler. Goroutine'ler, uygulamanızın işlemesi için gerekli olan kaynakları daha verimli bir şekilde kullanmanıza olanak tanır ve uygulamanızın daha hızlı çalışmasını sağlar.

Örneğin, bir uygulama bir web sitesindeki birden fazla kullanıcının verilerini eşzamanlı olarak işlemek isteyebilir. Paralel işlem yaparak, bu verileri aynı anda işleyebilir ve daha kısa sürede sonuçlar elde edebilirsiniz. Buna ek olarak, paralel işlem yapmak aynı zamanda uygulamanızın daha fazla kullanıcı desteğine sahip olmasına da yardımcı olur.

Golang'daki paralel işlem yapma yeteneği, özellikle büyük ölçekli, hesaplama yoğunluğu yüksek ve çoklu kullanıcı desteği gerektiren uygulamalarda oldukça faydalıdır.

- **Veri işleme:** Bir uygulama, büyük veri kümelerini işlemek için paralel işlem yapabilir. Örneğin, bir uygulama bir veritabanındaki milyonlarca kaydı okuyabilir ve bu kayıtlardan farklı bir algoritma ile analizler yapabilir.
- **Hesaplama yoğunluğu yüksek işlemler:** Bir uygulama, yüksek hesaplama yoğunluğu gerektiren işlemleri paralel işlem yaparak daha hızlı bir şekilde tamamlayabilir. Örneğin, bir uygulama karmaşık matematiksel hesaplamalar yapabilir veya büyük dosyaların şifrelemesini yapabilir.
- **Çoklu kullanıcı desteği:** Bir uygulama, aynı anda birden fazla kullanıcının erişimine izin vermek için paralel işlem yapabilir. Örneğin, bir web uygulaması birden fazla kullanıcının aynı anda istek göndermesini sağlayabilir ve bu istekleri paralel olarak işleyebilir. 
- **Çoklu işlemci çekirdeği:** Birden fazla işlemci çekirdeğine sahip sistemlerde, paralel işlem yaparak uygulamanızın daha verimli bir şekilde çalışmasını sağlayabilirsiniz. Örneğin, bir uygulama, birden fazla işlemci çekirdeğini kullanarak daha hızlı veri işleme ve hesaplama yapabilir.

Bu örnekler, paralel işlemlerin ne gibi durumlarda kullanılabileceğine dair bir fikir vermektedir. Golang'daki goroutine'ler sayesinde, bu tür işlemleri daha hızlı ve verimli bir şekilde gerçekleştirebilirsiniz.

<br><br>

# Buffering

Go dilinde channel'ların boyutu, belirli bir kapasiteyle sınırlandırılabilir. Bu, channel'ların belirli sayıda veri almasını sağlar. Bu özellik, channel buffering olarak adlandırılır.

```golang
package main

import "fmt"

func main() {
	messages := make(chan string, 2)

	messages <- "Hello"
	messages <- "World"

	fmt.Println(<-messages)
	fmt.Println(<-messages)
}
```

Bu örnekte, messages adlı bir channel oluşturulur ve boyutu 2 olarak belirlenir.

Hello ve World mesajları, messages channel'ına gönderilir.

<-messages kullanılarak, messages channel'ından mesajlar alınır ve ekrana yazdırılır.

Çıktı:

```
Hello
World
```

Bu örnekte, channel buffering kullanarak, messages channel'ı boyutu 2 olarak tanımlandı. Böylece, Hello ve World mesajları channel'a gönderildi ve channel'da depolandı. <-messages kullanılarak, mesajlar sırayla channel'dan alındı ve ekrana yazdırıldı.

<br><br>

# Channel Synchronization

Go dilinde, channel'lar ayrıca, farklı goroutines arasında senkronizasyon için de kullanılabilir. Bu, bir goroutine'un, diğer bir goroutine'un işlemi tamamlamasını beklemesi gerektiği durumlarda kullanışlıdır.

```golang
package main

import (
	"fmt"
	"time"
)

func worker(done chan bool) {
	fmt.Print("working...")
	time.Sleep(time.Second)
	fmt.Println("done")

	done <- true
}

func main() {
	done := make(chan bool, 1)
	go worker(done)

	<-done
}
```

Bu örnekte, worker adlı bir fonksiyon tanımlanır ve done adlı bir channel parametresi alır.

worker fonksiyonu, working... mesajını ekrana yazdırır, bir saniyelik bir bekleme süresi ekler ve done mesajını ekrana yazdırır.

main fonksiyonunda, done adlı bir channel oluşturulur ve boyutu 1 olarak belirlenir. go anahtar kelimesi kullanılarak, worker fonksiyonu bir goroutine olarak çağrılır. <-done kullanılarak, worker fonksiyonu tamamlandığında main fonksiyonuna bir mesaj gönderilir ve ana iş parçacığı bu mesajı alır.

Çıktı:
```
working...done
```

Bu örnekte, channel senkronizasyonu kullanarak, worker fonksiyonu bir goroutine olarak çağrıldı. worker fonksiyonu, done channel'ına bir mesaj gönderir ve işlemi tamamlanır. main fonksiyonu, <-done kullanılarak, worker fonksiyonunun işlemi tamamlamasını bekler. Sonuç olarak, working...done mesajları sırayla ekrana yazdırılır.

<br><br>

# Channel Directions

Go dilinde, channel'ların yönü, gönderme (send) veya alma (receive) işlemleri için belirlenebilir. Bu nedenle, channel'ların kullanımı, farklı goroutines arasındaki iletişimi ve veri aktarımını kolaylaştırır.

```golang
package main

import "fmt"

func ping(pings chan<- string, msg string) {
	pings <- msg
}

func pong(pings <-chan string, pongs chan<- string) {
	msg := <-pings
	pongs <- msg
}

func main() {
	pings := make(chan string, 1)
	pongs := make(chan string, 1)

	ping(pings, "Hello")
	pong(pings, pongs)

	fmt.Println(<-pongs)
}
```

Bu örnekte, ping ve pong adlı iki fonksiyon tanımlanır ve channel'larının yönleri belirlenir.

ping fonksiyonu, bir chan<- operatörü ile, sadece bir mesaj göndermek için kullanılabilen bir pings channel'ı parametresi alır.

pong fonksiyonu, bir <-chan operatörü ile, sadece mesaj almak için kullanılabilen bir pings channel'ı parametresi ve bir chan<- operatörü ile, sadece mesaj göndermek için kullanılabilen bir pongs channel'ı parametresi alır.

main fonksiyonunda, pings ve pongs channel'ları oluşturulur. ping fonksiyonu kullanılarak, pings channel'ına bir Hello mesajı gönderilir. pong fonksiyonu, pings channel'ından mesajı alır ve pongs channel'ına gönderir. Son olarak, <-pongs kullanılarak, pongs channel'ından mesaj alınır ve ekrana yazdırılır.

Çıktı:

```
Hello
```

Bu örnekte, channel directions kullanarak, ping ve pong fonksiyonları, farklı yönlerdeki channel'ları kullanarak mesaj gönderme ve alma işlemlerini gerçekleştirir. ping fonksiyonu, sadece mesaj göndermek için kullanılan pings channel'ını kullanarak mesaj gönderir. pong fonksiyonu, pings channel'ından mesajı alır ve pongs channel'ına gönderir. Son olarak, <-pongs kullanılarak, pongs channel'ından mesaj alınır ve ekrana yazdırılır.





<br><br>

# Select

Go dilinde, select anahtar kelimesi, birden fazla channel'ı dinleyerek, hangi channel'ın mesaj gönderdiğini belirleyebilir. Bu özellik, channel'ların senkronizasyonunu kolaylaştırır ve farklı goroutines arasındaki mesajlaşmayı yönetir.

```golang
package main

import (
	"fmt"
	"time"
)

func main() {
	c1 := make(chan string)
	c2 := make(chan string)

	go func() {
		time.Sleep(time.Second * 1)
		c1 <- "one"
	}()

	go func() {
		time.Sleep(time.Second * 2)
		c2 <- "two"
	}()

	for i := 0; i < 2; i++ {
		select {
		case msg1 := <-c1:
			fmt.Println("received", msg1)
		case msg2 := <-c2:
			fmt.Println("received", msg2)
		}
	}
}
```

Bu örnekte, c1 ve c2 adlı iki channel oluşturulur ve mesaj gönderme işlemi için goroutine'lar oluşturulur.

main fonksiyonunda, select anahtar kelimesi kullanılarak, c1 ve c2 channel'ları dinlenir. İlk olarak, goroutine'lar arasındaki bekleme süresi nedeniyle, c1 channel'ından bir mesaj alınır ve ekrana yazdırılır. Daha sonra, c2 channel'ından bir mesaj alınır ve ekrana yazdırılır.

Çıktı:
```
received one
received two
```

Bu örnekte, select anahtar kelimesi kullanarak, c1 ve c2 channel'larını dinleyen bir for döngüsü oluşturuldu. Bu, mesaj alım süresine bağlı olarak farklı channel'ların dinlenmesini sağlar. Sonuç olarak, goroutine'lar arasındaki mesajlaşma, belirli bir sıraya göre gerçekleştirilir ve select anahtar kelimesi kullanarak senkronizasyon sağlanır.




<br><br>

# Timeouts

Go dilinde, timeout işlemleri, özellikle ağ işlemleri sırasında önemlidir. time paketi kullanılarak, belirli bir süre beklenmesi sağlanabilir. Eğer süre aşılırsa, timeout hatası oluşur.

```golang
package main

import (
	"fmt"
	"time"
)

func main() {
	c1 := make(chan string, 1)

	go func() {
		time.Sleep(time.Second * 2)
		c1 <- "result 1"
	}()

	select {
	case res := <-c1:
		fmt.Println(res)
	case <-time.After(time.Second * 1):
		fmt.Println("timeout 1")
	}

	c2 := make(chan string, 1)

	go func() {
		time.Sleep(time.Second * 2)
		c2 <- "result 2"
	}()

	select {
	case res := <-c2:
		fmt.Println(res)
	case <-time.After(time.Second * 3):
		fmt.Println("timeout 2")
	}
}
```

Bu örnekte, c1 ve c2 adlı iki channel oluşturulur ve mesaj gönderme işlemleri için goroutine'lar oluşturulur.

İlk olarak, select anahtar kelimesi kullanılarak, c1 channel'ından bir mesaj beklenir. Ancak, time.After kullanılarak, c1 channel'ından bir mesaj alınmadan önce, bir saniye beklenir. Eğer bir saniyeden daha uzun bir süre geçerse, timeout hatası oluşur ve timeout 1 mesajı ekrana yazdırılır.

Daha sonra, select anahtar kelimesi kullanılarak, c2 channel'ından bir mesaj beklenir. Ancak, time.After kullanılarak, c2 channel'ından bir mesaj alınmadan önce, üç saniye beklenir.

Çıktı:
```
timeout 1
result 2
```

Bu örnekte, time.After kullanarak timeout işlemleri gerçekleştirildi. İlk olarak, c1 channel'ına bir saniyeden önce bir mesaj gönderilmediği için timeout hatası oluşur. Daha sonra, c2 channel'ına iki saniyeden önce bir mesaj gönderildiği için mesaj alınır ve ekrana yazdırılır.




<br><br>

# Non-Blocking Channel Operations

Go dilinde, channel'lar, blocking özelliklerine sahiptir. Yani, bir goroutine, bir channel'a mesaj göndermek ya da mesaj almak istediğinde, ilgili işlem tamamlanana kadar engellenir. Ancak, select anahtar kelimesi kullanılarak, channel'ların non-blocking işlemleri de gerçekleştirilebilir.

```golang
package main

import "fmt"

func main() {
	messages := make(chan string)
	signals := make(chan bool)

	select {
	case msg := <-messages:
		fmt.Println("received message", msg)
	default:
		fmt.Println("no message received")
	}

	msg := "hello"
	select {
	case messages <- msg:
		fmt.Println("sent message", msg)
	default:
		fmt.Println("no message sent")
	}

	select {
	case msg := <-messages:
		fmt.Println("received message", msg)
	default:
		fmt.Println("no message received")
	}

	select {
	case sig := <-signals:
		fmt.Println("received signal", sig)
	default:
		fmt.Println("no signal received")
	}

	signal := true
	select {
	case signals <- signal:
		fmt.Println("sent signal", signal)
	default:
		fmt.Println("no signal sent")
	}

	select {
	case sig := <-signals:
		fmt.Println("received signal", sig)
	default:
		fmt.Println("no signal received")
	}
}
```


Bu örnekte, messages adlı bir channel oluşturulur ve bir mesaj gönderilmeden önce select anahtar kelimesi kullanılarak, no message received mesajı ekrana yazdırılır.

Daha sonra, bir mesaj oluşturulur ve messages channel'ına gönderilir. select anahtar kelimesi kullanılarak, sent message hello mesajı ekrana yazdırılır.

Ardından, select anahtar kelimesi kullanılarak, messages channel'ından bir mesaj alınır. Ancak, herhangi bir mesaj gönderilmeden önce bu işlem gerçekleştirildiği için, no message received mesajı ekrana yazdırılır.

Bu örnekte, signals adlı bir channel oluşturulur ve bir sinyal gönderilmeden önce select anahtar kelimesi kullanılarak, no signal received mesajı ekrana yazdırılır.
Daha sonra, bir sinyal oluşturulur ve signals channel'ına gönderilir. select anahtar kelimesi kullanılarak, sent signal true mesajı ekrana yazdırılır.

Son olarak, select anahtar kelimesi kullanılarak, signals channel'ından bir sinyal alınır. Ancak, herhangi bir sinyal gönderilmeden önce bu işlem gerçekleştirildiği için, no signal received mesajı ekrana yazdırılır.

Çıktı:

```
no message received
sent message hello
no message received
no signal received
sent signal true
received signal true
```

Bu örnekte, select anahtar kelimesi kullanarak, non-blocking işlemli yapılabilir ve channel'ların engellenmesi önlenebilir. Bu, birden fazla channel'ın dinlenmesi gereken durumlarda yararlı olabilir.





<br><br>

# Closing Channels

Go dilinde, channel'ların kapatılması, mesajların gönderilmesi ve alınması işlemleri arasında senkronizasyon sağlayan bir yöntemdir. close fonksiyonu kullanılarak, bir channel kapatılabilir. Kapatılan bir channel'a mesaj gönderilemez ve bu channel'dan daha fazla mesaj alınamaz.

```golang
package main

import "fmt"

func main() {
	jobs := make(chan int, 5)
	done := make(chan bool)

	go func() {
		for {
			j, more := <-jobs
			if more {
				fmt.Println("received job", j)
			} else {
				fmt.Println("received all jobs")
				done <- true
				return
			}
		}
	}()

	for j := 1; j <= 3; j++ {
		jobs <- j
		fmt.Println("sent job", j)
	}

	close(jobs)
	fmt.Println("sent all jobs")

	<-done
}
```

Bu örnekte, jobs adlı bir channel ve done adlı bir channel oluşturulur. goroutine kullanarak, jobs channel'ından mesajların alınması işlemi gerçekleştirilir.

for döngüsü kullanarak, jobs channel'ına üç adet mesaj gönderilir. select anahtar kelimesi kullanarak, mesaj gönderildiği zaman, sent job mesajı ekrana yazdırılır.

Daha sonra, jobs channel'ı close fonksiyonu kullanılarak kapatılır. Bu işlem gerçekleştirildiği zaman, sent all jobs mesajı ekrana yazdırılır.

done channel'ı kullanılarak, gönderilen tüm mesajların alındığı kontrol edilir. done channel'ı, goroutine'un tamamlandığını gösterir.

Çıktı:

```
sent job 1
sent job 2
sent job 3
sent all jobs
received job 1
received job 2
received job 3
received all jobs
```

Bu örnekte, jobs channel'ına mesajlar gönderilir ve goroutine'un bu mesajları alması sağlanır. Daha sonra, jobs channel'ı close fonksiyonu kullanılarak kapatılır. Bu işlem gerçekleştirildiği zaman, goroutine'un alınması gereken tüm mesajları aldığı kontrol edilir.






<br><br>

# Range over Channels

Go dilinde, range anahtar kelimesi, channel'lar üzerinde döngü işlemlerinin gerçekleştirilmesini sağlar. Bu yöntemle, channel'ın kapatılması beklenmeden, tüm mesajlar for döngüsü kullanılarak alınabilir.

```golang
package main

import "fmt"

func main() {
	queue := make(chan string, 2)
	queue <- "one"
	queue <- "two"
	close(queue)

	for elem := range queue {
		fmt.Println(elem)
	}
}
```

Bu örnekte, queue adlı bir channel oluşturulur. for döngüsü kullanarak, queue channel'ına iki adet mesaj gönderilir.

close fonksiyonu kullanılarak, queue channel'ı kapatılır. Daha sonra, for döngüsü kullanılarak, queue channel'ının mesajları range anahtar kelimesi kullanılarak alınır.

Çıktı:

```golang
one
two
```

Bu örnekte, range anahtar kelimesi kullanarak, queue channel'ına gönderilen mesajlar alınır. close fonksiyonu kullanılarak, queue channel'ı kapatılır. Ancak, range anahtar kelimesi kullanılarak, tüm mesajlar alınır.





<br><br>

# Timers

Go dilinde, timerlar, bir işlemin belirli bir süre sonra gerçekleştirilmesini sağlamak için kullanılır. time paketi içerisinde yer alan NewTimer fonksiyonu kullanılarak, bir timer oluşturulabilir.

```golang
package main

import (
	"fmt"
	"time"
)

func main() {
	timer1 := time.NewTimer(2 * time.Second)

	<-timer1.C
	fmt.Println("Timer 1 expired")

	timer2 := time.NewTimer(time.Second)

	go func() {
		<-timer2.C
		fmt.Println("Timer 2 expired")
	}()

	stop2 := timer2.Stop()
	if stop2 {
		fmt.Println("Timer 2 stopped")
	}
}
```

Bu örnekte, NewTimer fonksiyonu kullanarak, iki adet timer oluşturulur.

İlk timer (timer1), iki saniye sonra sona erecek şekilde ayarlanır. Bu işlem gerçekleştirildiği zaman, <-timer1.C kullanılarak, timer1 süresinin dolması beklenir ve Timer 1 expired mesajı ekrana yazdırılır.

İkinci timer (timer2), bir saniye sonra sona erecek şekilde ayarlanır. goroutine kullanılarak, timer2 süresinin dolması beklenir ve Timer 2 expired mesajının ekrana yazılması beklenir, fakat 1 saniye bekledikten sonra timer2 stop edildiği için timer Timer 2 expired ekrana yazılmaz. Stop fonksiyonu kullanılarak, timer2 durdurulur ve Timer 2 stopped mesajı ekrana yazdırılır.

Çıktı:

```golang
Timer 1 expired
Timer 2 stopped
```

Bu örnekte, NewTimer fonksiyonu kullanarak, iki adet timer oluşturulur. İlk timer beklenen süre dolana kadar goroutine'un durmasını sağlayarak bir işlem gerçekleştirirken, ikinci timer için goroutine kullanarak, belirtilen süre dolana kadar beklenir. Stop fonksiyonu kullanılarak, timer2 durdurulur.





<br><br>

# Tickers

Go dilinde, tickerlar, belirli bir süre boyunca belirli aralıklarla bir işlemin gerçekleştirilmesini sağlamak için kullanılır. time paketi içerisinde yer alan NewTicker fonksiyonu kullanılarak, bir ticker oluşturulabilir.

```golang
package main

import (
	"fmt"
	"time"
)

func main() {
	ticker := time.NewTicker(500 * time.Millisecond)
	done := make(chan bool)

	go func() {
		for {
			select {
			case <-done:
				return
			case t := <-ticker.C:
				fmt.Println("Tick at", t)
			}
		}
	}()

	time.Sleep(1600 * time.Millisecond)
	ticker.Stop()
	done <- true
	fmt.Println("Ticker stopped")
}
```

Bu örnekte, NewTicker fonksiyonu kullanarak, bir ticker oluşturulur ve 500 milisaniyede bir bir işlem gerçekleştirilmesi sağlanır.

goroutine kullanılarak, select anahtar kelimesi kullanılarak, ticker'ın oluşturulduğu zaman aralığına bağlı olarak belirli aralıklarla bir işlem gerçekleştirilir. done adlı channel'a mesaj gönderilerek, goroutine durdurulur ve Ticker stopped mesajı ekrana yazdırılır.

Çıktı:

```
Tick at 2022-11-27 16:37:14.750915 +0300 MSK m=+0.501356162
Tick at 2022-11-27 16:37:15.249568 +0300 MSK m=+1.000018689
Tick at 2022-11-27 16:37:15.751064 +0300 MSK m=+1.501505306
Ticker stopped
```





<br><br>

# Worker Pools

Go dilinde, worker poollar, belirli bir işlemi yapmak üzere ayrılmış bir işçi grubudur. İşler bir channel'a gönderilir ve bu işçiler tarafından işlenir. Bu sayede, işlemler belirli bir sıra ile işçilere dağıtılarak, iş yükü paylaştırılmış olur.

```golang
package main

import (
	"fmt"
	"time"
)

func worker(id int, jobs <-chan int, results chan<- int) {
	for j := range jobs {
		fmt.Println("Worker", id, "started job", j)
		time.Sleep(time.Second)
		fmt.Println("Worker", id, "finished job", j)
		results <- j * 2
	}
}

func main() {
	jobs := make(chan int, 100)
	results := make(chan int, 100)

	for w := 1; w <= 3; w++ {
		go worker(w, jobs, results)
	}

	for j := 1; j <= 5; j++ {
		jobs <- j
	}
	close(jobs)

	for a := 1; a <= 5; a++ {
		<-results
	}
}
```

Bu örnekte, worker adlı bir fonksiyon oluşturulur. Bu fonksiyon, işçiler tarafından gerçekleştirilecek işlemleri alır ve işlemlerin sonuçlarını results channel'ına yazar.

jobs adlı bir channel oluşturulur ve 100 adet iş yüküne kadar bu channel'a mesaj gönderilebilir. results adlı bir channel oluşturulur ve 100 adet sonuç için bu channel'a mesaj gönderilebilir.

for döngüsü kullanılarak, işçiler için bir goroutine oluşturulur. İşçiler, worker fonksiyonuna gönderilen id, jobs ve results değişkenlerini kullanarak çalışır.

Bir sonraki for döngüsü kullanılarak, 5 adet iş yükü oluşturulur ve jobs channel'ına gönderilir. close fonksiyonu kullanılarak, jobs channel'ı kapatılır.

Son olarak, for döngüsü kullanılarak, sonuçlar results channel'ından alınır.

Çıktı:

```
Worker 3 started job 1
Worker 2 started job 2
Worker 1 started job 3
Worker 3 finished job 1
Worker 3 started job 4
Worker 2 finished job 2
Worker 1 finished job 3
Worker 1 started job 5
Worker 2 started job 6
Worker 3 finished job 4
Worker 2 finished job 6
Worker 1 finished job 5
```





<br><br>

# WaitGroups

WaitGroup yapısı, Go dilinde, goroutine'lar arasında senkronizasyon sağlamak için kullanılan bir mekanizmadır. WaitGroup yapısı, Go'nun sync paketi içinde bulunur.

WaitGroup yapısı, programcıların çalışacak işlemlerin sayısını önceden belirtmelerine ve bu işlemlerin tamamlanmasını beklemelerine olanak tanır. Her goroutine, işlemin tamamlandığını bildirmek için WaitGroup yapısındaki Done() fonksiyonunu çağırır. WaitGroup yapısındaki Wait() fonksiyonu, tüm işlemlerin tamamlanmasını bekler.

Aşağıdaki örnek, WaitGroup yapısının kullanımını göstermektedir:

```golang
package main

import (
    "fmt"
    "sync"
    "time"
)

func worker(id int, wg *sync.WaitGroup) {
    defer wg.Done()

    fmt.Printf("Worker %d starting\n", id)
    time.Sleep(time.Second)
    fmt.Printf("Worker %d done\n", id)
}

func main() {
    var wg sync.WaitGroup

    for i := 1; i <= 5; i++ {
        wg.Add(1)
        go worker(i, &wg)
    }

    wg.Wait()

    fmt.Println("All workers done")
}
```

Bu örnekte, 5 adet iş yapan işçi fonksiyonu worker() çalıştırılır. WaitGroup yapısı, her işçi fonksiyonu başlamadan önce Add() fonksiyonu ile bekleyen işlem sayısını arttırır. Her işçi fonksiyonu tamamlandığında, Done() fonksiyonu ile bir işlem tamamlandığı bildirilir. Wait() fonksiyonu, tüm işlemlerin tamamlandığını beklemek için kullanılır. Sonuç olarak, tüm işçi fonksiyonları tamamlandıktan sonra, main() fonksiyonu "All workers done" mesajını yazdırır.

```
Worker 5 starting
Worker 3 starting
Worker 4 starting
Worker 1 starting
Worker 2 starting
Worker 5 done
Worker 3 done
Worker 2 done
Worker 1 done
Worker 4 done
All workers done
```





<br><br>

# Rate Limiting

Rate Limiting, bir API veya bir servisin, bir kullanıcının belli bir süre içinde yapabileceği istek sayısını sınırlandırmak için kullanılan bir yöntemdir. Bu yöntem, bir uygulamanın veya hizmetin aşırı yüklenmesini önlemek için kullanılabilir.

Go dilinde, Rate Limiting yapmak için time paketi kullanılabilir. Bu paket, belirli bir zaman aralığı boyunca belirli bir eylemde bulunmak için beklenmesi gereken süreyi hesaplamak için kullanılır.

Aşağıdaki örnekte, time.Ticker ve time.Sleep kullanarak bir Rate Limiting örneği gösterilmektedir:

```golang
package main

import (
    "fmt"
    "time"
)

func main() {
    requests := make(chan int, 5)

    for i := 1; i <= 5; i++ {
        requests <- i
    }
    close(requests)

    limiter := time.Tick(200 * time.Millisecond)

    for req := range requests {
        <-limiter
        fmt.Println("request", req, time.Now())
    }
}
```

Bu örnekte, requests adlı bir channel oluşturulur ve içine 5 adet sayı eklenir. Daha sonra, limiter adlı bir time.Ticker oluşturulur ve 200 milisaniyelik bir süreyle sınırlandırılır.

Daha sonra, requests channel'ındaki her bir istek için bir goroutine başlatılır ve her bir istek önce limiter channel üzerinden bekletilir. Bu sayede, aynı anda en fazla 1 istek işlenebilir.

Örneğin, eğer requests channel'ındaki 5 isteğin arasında hiç bekleme yapmadan hemen işlem yapılırsa, tüm istekler hızlı bir şekilde işlenecektir. Ancak, limiter channel'ın sağladığı sınırlama nedeniyle, her bir istek arasında 200 milisaniye beklenmesi sağlanır.

```
request 1 2023-05-23 15:56:01.46705 +0300 +03 m=+0.201167209
request 2 2023-05-23 15:56:01.667008 +0300 +03 m=+0.401132584
request 3 2023-05-23 15:56:01.867014 +0300 +03 m=+0.601146918
request 4 2023-05-23 15:56:02.067052 +0300 +03 m=+0.801193043
request 5 2023-05-23 15:56:02.267025 +0300 +03 m=+1.001173793
```

Bu şekilde, Rate Limiting yaparak isteklerin belli bir hızda işlenmesi sağlanır.






<br><br>

# Atomic Counters

Atomic Counters konusu, Go dilinde eşzamanlılık işlemlerinde kullanılan bir konudur. Birçok Go programı, birden fazla goroutine tarafından paylaşılan verileri kullandığı için, bu verilerin aynı anda birden fazla goroutine tarafından değiştirilmesi kaçınılmazdır. Bu değişikliklerin uygun bir şekilde kontrol edilmemesi, programın beklenmeyen şekillerde çalışmasına neden olabilir.

Bir Atomic Counter, Go'nun sync/atomic paketinde bulunan bir veri yapısıdır. Bu veri yapısı, AddInt64, CompareAndSwapInt64, SwapInt64, LoadInt64 ve StoreInt64 gibi bir dizi yönteme sahiptir. Bu yöntemler, birden fazla goroutine tarafından aynı anda erişilebilecek bir değişkenin güvenli bir şekilde değiştirilmesini sağlar.

Aşağıdaki örnek, Atomic Counter kullanarak, 10 adet goroutine tarafından ortak kullanılan bir sayaç değişkeninin güvenli bir şekilde artırılmasını gösterir:

```golang
package main

import (
    "fmt"
    "sync"
    "sync/atomic"
)

func main() {
    var counter int64 = 0
    var wg sync.WaitGroup
    for i := 0; i < 10; i++ {
        wg.Add(1)
        go func() {
            defer wg.Done()
            atomic.AddInt64(&counter, 1)
        }()
    }
    wg.Wait()
    fmt.Println("Counter:", counter)
}
```

Bu örnekte, counter değişkeni, int64 türünden bir Atomic Counter olarak tanımlanır ve başlangıçta 0 değeri atanır. Daha sonra, 10 adet goroutine oluşturulur ve her biri, atomic.AddInt64 yöntemi kullanılarak counter değişkenini arttırır. Bu yöntem, &counter adresini alarak, counter değişkenine atomik bir şekilde 1 ekler.

Sonuç olarak, Atomic Counter veri yapısı, birden fazla goroutine tarafından paylaşılan değişkenlerin güvenli bir şekilde değiştirilmesini sağlar ve eşzamanlılık işlemlerinde kullanılan önemli bir konudur.





<br><br>

# Sorting

Golang'da sıralama işlemi için sort paketi kullanılır. Bu paket içinde çeşitli veri türlerine özgü sıralama işlemleri yapmak için fonksiyonlar yer alır.

En yaygın kullanılan iki sıralama fonksiyonu sort.Ints() ve sort.Strings() fonksiyonlarıdır. sort.Ints() fonksiyonu, bir int türünde slice'ı küçükten büyüğe doğru sıralar. sort.Strings() fonksiyonu ise, bir string türünde slice'ı alfabetik olarak sıralar.

Bunların yanı sıra, sort paketi içinde sort.Float64s() fonksiyonu da mevcuttur ve float64 türünde slice'ı küçükten büyüğe doğru sıralar.

Ayrıca, sort.Slice() fonksiyonu ile özel sıralama işlemleri de gerçekleştirilebilir. Bu yöntem, bir slice ve bir Less fonksiyonu alır. Less fonksiyonu, iki slice elemanını karşılaştırmak için kullanılır ve sonucuna göre elemanların sıralanmasına karar verilir. Bu fonksiyon, slice elemanlarına göre özel sıralama işlemleri yapmak için kullanılabilir.

Örneğin, aşağıdaki örnekte sort.Slice() fonksiyonu kullanılarak özel bir sıralama işlemi gerçekleştirilir:

```golang
package main

import (
	"fmt"
	"sort"
)

type Person struct {
	Name string
	Age  int
}

func main() {
	people := []Person{
		{"Alice", 25},
		{"Bob", 30},
		{"Charlie", 20},
	}

	sort.Slice(people, func(i, j int) bool {
		return people[i].Age < people[j].Age
	})

	fmt.Println(people)
}
```

Bu örnekte, Person tipinde bir slice tanımlanır ve sort.Slice() fonksiyonu kullanılarak Age alanına göre küçükten büyüğe doğru sıralama yapılır.

Çıktı:

```
[{Charlie 20} {Alice 25} {Bob 30}]
```

<br><br>

# Diğer Örnekler

İlk örnekte, sort.Ints() fonksiyonu kullanılarak ints adlı bir slice küçükten büyüğe doğru sıralanır ve sonuç ekrana yazdırılır:

```golang
package main

import (
	"fmt"
	"sort"
)

func main() {
	ints := []int{5, 2, 7, 1, 9, 3, 8, 6, 4}
	sort.Ints(ints)
	fmt.Println(ints)

	if sort.IntsAreSorted(ints) {
		fmt.Println("Slice is sorted.")
	} else {
		fmt.Println("Slice is not sorted.")
	}
}
```

Çıktı:

```
[1 2 3 4 5 6 7 8 9]
Slice is sorted.
```

İkinci örnekte ise sort.Strings() fonksiyonu kullanılarak strings adlı bir slice alfabetik olarak sıralanır ve sonuç ekrana yazdırılır:

```golang
package main

import (
	"fmt"
	"sort"
)

func main() {
	strings := []string{"apple", "banana", "cherry", "date", "elderberry", "fig"}
	sort.Strings(strings)
	fmt.Println(strings)

	if sort.StringsAreSorted(strings) {
		fmt.Println("Slice is sorted.")
	} else {
		fmt.Println("Slice is not sorted.")
	}
}
```

Çıktı:

```
[apple banana cherry date elderberry fig]
Slice is sorted.
```



<br><br>

# Panic

panic, programın çalışması sırasında beklenmedik bir durumla karşılaştığında, programın çalışmasını durdurarak bir hata mesajı vermesini sağlayan bir Go dilindeki bir özelliktir.

panic bir hata olduğu için genellikle kullanılmamalıdır, ancak bir hata durumunda programın beklenmedik şekilde sonlanmaması için kullanılabilir. panic kullandığınızda, program çalışması durdurulur ve geriye kalan tüm kodların çalışması durdurulur.

panic kullanımı örneği:

```golang
package main

import "fmt"

func main() {
	defer func() {
		if err := recover(); err != nil {
			fmt.Println("Panic yakalandı:", err)
		}
	}()

	divideByZero()
	fmt.Println("Bu kod çalışacak mı?")
}

func divideByZero() {
	numerator := 10
	denominator := 0
	result := numerator / denominator
	fmt.Println("Sonuç:", result)
}

```

Bu örnekte, divideByZero adında bir fonksiyonumuz var. Bu fonksiyon içerisinde numerator'ı 10 ve denominator'ü 0 olarak ayarladıktan sonra, result değişkenine numerator'ı denominator'e böldürüyoruz. Ancak denominator'ün 0 olması durumunda, matematiksel olarak geçersiz bir işlem yapmaya çalışıyoruz. Bu durumda bir bölme sıfıra bölme hatası (division by zero error) oluşur ve bir panic durumu başlatılır.

Ana fonksiyonun içinde defer ifadesi kullanarak bir fonksiyonu erteleriz. Bu ertelediğimiz fonksiyon, recover() fonksiyonunu kullanarak bir panic durumunu yakalamak için kullanılır. Eğer bir panic durumu meydana gelirse, recover() fonksiyonu panic'in neden olduğu hatayı döndürür ve err değişkenine atar. Daha sonra, if err != nil kontrolüyle panic durumunun olup olmadığını kontrol ederiz.

Eğer divideByZero() fonksiyonunda bir panic durumu gerçekleşirse, recover() fonksiyonu tarafından yakalanacak ve err değişkenine atanacak. Ardından fmt.Println() ifadesiyle "Panic yakalandı: {hata}" şeklinde bir çıktı üretecektir. Bu sayede programın çalışması durmayacak ve devam edecektir.






<br><br>

# Defer

defer, Go dilindeki özel bir anahtar sözcüktür ve belirli bir işlevin çalışmasının sonunda çalıştırılacak işlevleri veya ifadeleri belirtmek için kullanılır. Defer ifadeleri, işlevin sonunda ne olursa olsun, yani o fonksiyonun herhangi bir nedenle sona ermesi durumunda bile çalıştırılacaktır.

Defer ifadeleri kullanarak, bir işlevin sonunda açılan dosyaları, kapatılmayan veritabanı bağlantılarını, ağ bağlantılarını vb. hızlı ve güvenli bir şekilde kapatmak mümkündür.

Örnek olarak, bir dosya açılır ve defer ile fonksiyon sonunda dosya kapatılır:

```golang
package main

import (
	"fmt"
	"os"
)

func main() {
	// dosya açma
	f, err := os.Open("example.txt")
	if err != nil {
		fmt.Println(err)
		return
	}

	// dosya kapatma
	defer f.Close()

	// dosyayı okuma
	b := make([]byte, 1024)
	n, err := f.Read(b)
	if err != nil {
		fmt.Println(err)
		return
	}

	// dosya içeriğini yazdırma
	fmt.Println(string(b[:n]))
}
```

Bu örnekte, os.Open fonksiyonu kullanılarak "example.txt" dosyası açılır. defer ifadesi kullanılarak dosya kapatma işlemi, işlevin sonunda çalıştırılacak şekilde planlanır. Daha sonra, Read fonksiyonu kullanılarak dosya içeriği okunur ve ekrana yazdırılır.

Burada dikkat edilmesi gereken önemli bir nokta, defer ifadesinin en sona yazılmamasıdır. defer ifadesinin kapatılacak olan dosyayı açan ifade ile aynı blokta olması gerekmektedir. Aksi takdirde, defer ifadesi, işlevin sonuna kadar beklemeye devam edecektir.





<br><br>

# String Functions

Golang, string verileri üzerinde işlemler yapmak için birçok hazır fonksiyon sunar. Bu fonksiyonlar, string verileri parçalama, birleştirme, karşılaştırma, arama, değiştirme ve daha birçok işlem yapmak için kullanılabilir.

Bazı yaygın kullanılan string fonksiyonları şunlardır:

- len(s string) int: Verilen string'in uzunluğunu döndürür.
- s[i] byte: Verilen string'deki belirtilen indeks numarasındaki karakteri döndürür.
- s + t: İki string'i birleştirir.
- strings.Split(s, sep string) []string: Verilen string'i, belirtilen ayırıcı karakterlere göre parçalar ve bir diziye dönüştürür.
- strings.Join(a []string, sep string) string: Verilen string dizisini, belirtilen ayırıcı karakterle birleştirir ve tek bir string olarak döndürür.
- strings.Contains(s, substr string) bool: Verilen string içinde, belirtilen alt string'in olup olmadığını kontrol eder.
- strings.HasPrefix(s, prefix string) bool: Verilen string'in, belirtilen ön ek ile başlayıp başlamadığını kontrol eder.
- strings.HasSuffix(s, suffix string) bool: Verilen string'in, belirtilen son ek ile bitip bitmediğini kontrol eder.
- strings.Replace(s, old, new string, n int) string: Verilen string'de, belirtilen eski string'i, belirtilen yeni string ile değiştirir. İsteğe bağlı olarak, belirtilen sayıda değiştirme yapar.

Örnek olarak, bir string içinde belirli bir karakter dizisinin kaç kez geçtiğini bulmak için strings.Count fonksiyonu kullanılabilir:

```golang
package main

import (
    "fmt"
    s "strings"
)

var p = fmt.Println

func main() {

    p("Contains:  ", s.Contains("test", "es"))
    p("Count:     ", s.Count("test", "t"))
    p("HasPrefix: ", s.HasPrefix("test", "te"))
    p("HasSuffix: ", s.HasSuffix("test", "st"))
    p("Index:     ", s.Index("test", "e"))
    p("Join:      ", s.Join([]string{"a", "b"}, "-"))
    p("Repeat:    ", s.Repeat("a", 5))
    p("Replace:   ", s.Replace("foo", "o", "0", -1))
    p("Replace:   ", s.Replace("foo", "o", "0", 1))
    p("Split:     ", s.Split("a-b-c-d-e", "-"))
    p("ToLower:   ", s.ToLower("TEST"))
    p("ToUpper:   ", s.ToUpper("test"))
}
```

Çıktı:

```
Contains:   true
Count:      2
HasPrefix:  true
HasSuffix:  true
Index:      1
Join:       a-b
Repeat:     aaaaa
Replace:    f00
Replace:    f0o
Split:      [a b c d e]
ToLower:    test
ToUpper:    TEST
```



<br><br>

# Text Templates

Template (şablon) dosyaları, Go'da metin tabanlı verileri biçimlendirmek için kullanılır. Bir şablon dosyası, bir metin belgesi içindeki verilerin bir kısmını yer tutucular veya ifadeler ile değiştirerek oluşturulur. Bu işlem, bir şablon dosyasını bir veri yapısıyla birleştirerek gerçekleştirilir.

Örneğin, bir e-posta gönderimi sırasında, bir şablon dosyası kullanarak mesajın içeriği belirli bir formatta oluşturulabilir. Şablon dosyasında, değişkenler ve fonksiyonlar kullanarak yer tutucular ve ifadeler tanımlanabilir. Daha sonra, bu değişkenler ve fonksiyonlar gerçek veri yapısıyla birleştirilir ve sonuç olarak tamamlanmış metin belgesi oluşturulur.

Go'da, şablon dosyaları text/template ve html/template paketleriyle oluşturulur. Bu paketler, şablon dosyalarının oluşturulmasını ve işlenmesini sağlayan birçok fonksiyon sağlarlar.

```golang
package main

import (
    "fmt"
    "os"
    "text/template"
)

type Person struct {
    Name    string
    Age     int
    Country string
}

func main() {
    person := Person{
        Name:    "John",
        Age:     30,
        Country: "USA",
    }

    tpl := "My name is {{.Name}} and I am {{.Age}} years old. I live in {{.Country}}.\n"
    t := template.Must(template.New("person").Parse(tpl))

    err := t.Execute(os.Stdout, person)
    if err != nil {
        fmt.Println("Error executing template:", err)
    }
}
```

Bu örnekte, Person adında bir veri yapısı tanımlanmıştır. Ardından, tpl değişkeninde, şablonun bir metni yer alır. Şablon içinde kullanılacak olan değişkenler, {{.}} işaretleri arasına yazılır. Bu değişkenlere, veri yapısındaki alanlar atanacaktır.

Daha sonra, template.Must() fonksiyonu kullanılarak yeni bir Template nesnesi oluşturulur ve şablon metni Parse() fonksiyonu ile bu nesneye atanır. Ardından, Execute() fonksiyonu kullanılarak, Template nesnesi, veri yapısı ve os.Stdout (standart çıktı) yazıcısı kullanılarak işlenir ve sonuç, ekrana yazdırılır.

Programın çıktısı şöyle olacaktır:

```
My name is John and I am 30 years old. I live in USA.
```




<br><br>

# JSON

JSON (JavaScript Object Notation), hafif bir veri değişim formatıdır ve insanlar tarafından okunması ve yazılması kolaydır. Go dilinde, encoding/json paketi, JSON verileri ile işlem yapmak için kullanılabilir.

JSON verileri, anahtar/değer çiftleri veya dizilerden oluşur. Anahtarlar bir string, değerler ise bir JSON verisi olabilir. JSON verileri, {} (süslü parantezler) ile belirtilen nesneler şeklinde de olabilir.

Örnek bir JSON verisi şöyle görünebilir:

```json
{
    "name": "John Doe",
    "age": 30,
    "city": "New York"
}
```

Bu veri, name, age ve city olmak üzere üç anahtar taşır. name anahtarı bir string değeri, age anahtarı bir sayısal değer ve city anahtarı da yine bir string değeridir.

Go dilinde, JSON verileri için struct yapısı kullanılabilir. struct yapısındaki alanlar, JSON verisindeki anahtarlarla eşleştirilebilir. Ardından, encoding/json paketinde yer alan Marshal() ve Unmarshal() fonksiyonları kullanılarak, Go nesnesi ve JSON verisi arasında dönüşüm yapılabilir.

Örneğin, bir Person struct'ı tanımlayalım ve bu struct'ı JSON verisiyle eşleştirelim:

```golang
type Person struct {
    Name string `json:"name"`
    Age  int    `json:"age"`
    City string `json:"city"`
}
```

Burada, Person struct'ının alanları, JSON verisindeki anahtarlarla eşleştirilmiştir. Name alanı için name, Age alanı için age, City alanı için ise city anahtarları kullanılmıştır.

Bu struct'ı JSON verisine dönüştürmek için, json.Marshal() fonksiyonu kullanılabilir:

```golang
person := Person{Name: "John Doe", Age: 30, City: "New York"}
jsonData, err := json.Marshal(person)
if err != nil {
    fmt.Println("Error encoding JSON:", err)
}
fmt.Println(string(jsonData)) // {"name":"John Doe","age":30,"city":"New York"}
```

Burada, Person struct'ı bir person değişkeni olarak tanımlanır ve json.Marshal() fonksiyonu kullanılarak person nesnesi JSON verisine dönüştürülür. Elde edilen JSON verisi, string() fonksiyonu kullanılarak string türüne dönüştürülür ve ekrana yazdırılır.

Bir başka örnek de, JSON verilerini Go veri yapılarına dönüştürmek ve tersi işlemi yapmak için json.Marshal() ve json.Unmarshal() fonksiyonlarını kullanmaktır. Örneğin:

```golang
package main

import (
    "encoding/json"
    "fmt"
)

type Person struct {
    Name string
    Age  int
}

func main() {
    // Go veri yapısını JSON formatına dönüştürme
    p1 := Person{"Alice", 30}
    jsonStr, err := json.Marshal(p1)
    if err != nil {
        panic(err)
    }
    fmt.Println(string(jsonStr))

    // JSON verisini Go veri yapısına dönüştürme
    var p2 Person
    jsonStr = []byte(`{"Name":"Bob","Age":40}`)
    err = json.Unmarshal(jsonStr, &p2)
    if err != nil {
        panic(err)
    }
    fmt.Println(p2)
}
```

Bu örnekte, Person adlı bir yapı tanımlanır ve json.Marshal() ve json.Unmarshal() fonksiyonları kullanılarak bu yapı JSON verisi olarak kodlanır ve çözümlenir.

```
{"Name":"Alice","Age":30}
{Bob 40}
```
