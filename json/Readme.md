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