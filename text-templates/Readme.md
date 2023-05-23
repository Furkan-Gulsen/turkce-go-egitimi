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