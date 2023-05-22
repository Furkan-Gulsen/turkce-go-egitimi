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