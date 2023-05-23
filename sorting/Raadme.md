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

## Diğer Örnekler

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