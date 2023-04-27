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