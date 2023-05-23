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