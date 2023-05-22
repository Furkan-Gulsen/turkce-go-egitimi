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