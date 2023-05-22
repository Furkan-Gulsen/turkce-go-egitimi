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