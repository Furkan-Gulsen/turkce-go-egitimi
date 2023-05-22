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