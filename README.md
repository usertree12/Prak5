# Выполнил студент группы ЭФМО-01-24 Кирпиченков Дмитрий Дмитриевич
---
### Язык GO. 4 практическая
---

**1) Сумма цифр числа. Напишите программу, которая принимает целое число и вычисляет сумму 
его цифр.
Вход: `1234`
Выход: `10` (1 + 2 + 3 + 4)**
```
package main

import (
	"fmt"
	"os"
)

func main() {
	var number int
	var sum int
	fmt.Println("Введите четырёхзначное число: ")
	fmt.Fscan(os.Stdin, &number)
	sum = sum + (number % 10)
	number = number / 10
	sum = sum + (number % 10)
	number = number / 10
	sum = sum + (number % 10)
	number = number / 10
	sum = sum + (number % 10)
	number = number / 10
	fmt.Println("Сумма чисел равна: ", sum)
}
```
**2) Преобразование температуры. Напишите программу, которая преобразует температуру из градусов 
Цельсия в Фаренгейты и обратно. 
Вход: `25 (Celsius)`
Выход: `77 (Fahrenheit)`**
```
package main

import (
	"fmt"
	"os"
)

func fahrenheit(c_num float32) float32 {
	var fahrenheit_num = (1.8 * c_num) + 32
	return fahrenheit_num
}
func celsius(fahrenheit_num float32) float32 {
	var c_num = (0.5556 * (fahrenheit_num - 32))
	return c_num
}

func main() {
	var c_grad float32
	var fahrenheit_grad float32
	fmt.Println("Введите число градусов по Цельсию: ")
	fmt.Fscan(os.Stdin, &c_grad)
	fmt.Println("Это ", fahrenheit(c_grad), "градусов по Фаренгейту")
	fmt.Println("Введите число градусов по Фаренгейту: ")
	fmt.Fscan(os.Stdin, &fahrenheit_grad)
	fmt.Println(Это ", celsius(fahrenheit_grad), "градусов по Цельсию")
}
```
**3) Удвоение каждого элемента массива. Удвоение каждого элемента массива:
   Напишите программу, которая принимает массив чисел и возвращает 
новый массив, где каждое число удвоено.
Вход: `[1, 2, 3, 4]`
Выход: `[2, 4, 6, 8]`**
```
package main

import (
	"fmt"
	"os"
)

func main() {
	var numbers [3]int
	fmt.Println("Введите первый элемент: ")
	fmt.Fscan(os.Stdin, &numbers[0])
	numbers[0] = numbers[0] * 2
	fmt.Println("Введите второй элемент трёхмерного массива: ")
	fmt.Fscan(os.Stdin, &numbers[1])
	numbers[1] = numbers[1] * 2
	fmt.Println("Введите третий элемент трёхмерного массива: ")
	fmt.Fscan(os.Stdin, &numbers[2])
	numbers[2] = numbers[2] * 2
	fmt.Println("Преобразованный массив: ", numbers)
}
```
**4) Объединение строк. Напишите программу, которая принимает несколько строк и объединяет их 
в одну строку через пробел.
Вход: `["Hello", "world"]`
Выход: `Hello world`**
```
package main

import (
	"fmt"
	"os"
)

func main() {
	var lines [3]string
	fmt.Println("Введите первую строку: ")
	fmt.Fscan(os.Stdin, &lines[0])
	fmt.Println("Введите вторую строку: ")
	fmt.Fscan(os.Stdin, &lines[1])
	fmt.Println("Введите третью строку: ")
	fmt.Fscan(os.Stdin, &lines[2])
	fmt.Println(lines[0], lines[1], lines[2])
}
```
**5) Расчет расстояния между двумя точками. Напишите программу, которая вычисляет расстояние между двумя точками 
в 2D пространстве.
Вход: `(x1=1, y1=1), (x2=4, y2=5)`
Выход: `5.0`**
```
package main

import (
	"fmt"
	"math"
	"os"
)

func main() {
	var x1 float64
	var y1 float64
	var x2 float64
	var y2 float64
	var res float64
	fmt.Println("Введите координату x первой точки: ")
	fmt.Fscan(os.Stdin, &x1)
	fmt.Println("Введите координату y первой точки: ")
	fmt.Fscan(os.Stdin, &y1)
	fmt.Println("Введите координату x второй точки: ")
	fmt.Fscan(os.Stdin, &x2)
	fmt.Println("Введите координату y второй точки: ")
	fmt.Fscan(os.Stdin, &y2)
	var a1 = x2 - x1
	var a2 = y2 - y1
	res = (a1 * a1) + (a2 * a2)
	fmt.Println("Расстояние = ", (math.Sqrt(res)))
}
```
### 2. Задачи с условным оператором

**1) Проверка на четность/нечетность**
```
package main

import (
	"fmt"
	"os"
)

func main() {
	var number int
	fmt.Println("Введите любое целое число: ")
	fmt.Fscan(os.Stdin, &number)
	if number%2 == 1 {
		fmt.Println("Число нечётное")
	} else {
		fmt.Println("Число чётное")
	}
}
```
**2) Проверка высокосного года**
```
package main

import (
	"fmt"
)

func WhatYear(year int) bool {
		if (year%4 == 0 && year%100 != 0) || (year%400 == 0) {
		return true
	}
	return false
}

func main() {
	var year int
	fmt.Print("Введите год: ")
	_, err := fmt.Scan(&year)
	if err != nil {
		fmt.Println("Ошибка ввода:", err)
		return
	}

	if WhatYear(year) {
		fmt.Println("Високосный")
	} else {
		fmt.Println("Не високосный")
	}
}

```
**3) Определение наибольшего из трех чисел**
```
package main

import (
	"fmt"
	"os"
)

func main() {
	var number1 float32
	var number2 float32
	var number3 float32
	fmt.Println("Введите первый номер: ")
	fmt.Fscan(os.Stdin, &number1)
	fmt.Println("Введите второй номер: ")
	fmt.Fscan(os.Stdin, &number2)
	fmt.Println("Введите третий номер: ")
	fmt.Fscan(os.Stdin, &number3)
	if num1 > num && num1 > num3 {
		fmt.Println(number1)
	} else if num2 > num3 {
		fmt.Println(number2)
	} else {
		fmt.Println(number3)
	}
}
```
**4) Категория возраста**
```
package main

import (
	"fmt"
	"os"
)

// Категории
// Ребёнок: 0 - 11
// Подросток: 12 - 17
// Взрослый: 18 - 60
// Пожилой: 61 - 100

func main() {
	var age int
	fmt.Println("Введите возраст: ")
	fmt.Fscan(os.Stdin, &age)
	if age >= 0 && age <= 11 {
		fmt.Println("Ребёнок")
	}
	if age >= 12 && age <= 17 {
		fmt.Println("Подросток")
	}
	if age >= 18 && age <= 60 {
		fmt.Println("Взрослый")
	}
	if age >= 61 && age < 100 {
		fmt.Println("Пожилой")
	}
}
```
**5) Проверка делимости на 3 и 5**
```
package main

import (
	"fmt"
	"os"
)

func main() {
	var number int
	fmt.Println("Введите любое целое число: ")
	fmt.Fscan(os.Stdin, &number)
	if number%5 == 0 && number%3 == 0 {
		fmt.Println("Данное число делится одновременно на 3 и 5")
	} else {
		fmt.Println("Данное число не делится одновременно на 3 и 5")
	}
}
```
### 3. Задачи на циклы

**1) Факториал числа**
```
package main

import (
	"fmt"
)

func factorial(n int) int {
	if n == 0 {
		return 1 
	}
	result := 1
	for i := 1; i <= n; i++ {
		result *= i
	}
	return result
}

func main() {
	var number int
	fmt.Print("Введите число: ")
	fmt.Scan(&number)

	result := factorial(number)
	fmt.Printf("Факториал %d! = %d\n", number, result)
}

```
**2) Числа Фибоначчи**
```
package main

import (
	"fmt"
)

func fibonacci(n int) []int {
	fibSeries := make([]int, n)
	if n > 0 {
		fibSeries[0] = 0
	}
	if n > 1 {
		fibSeries[1] = 1
	}
	for i := 2; i < n; i++ {
		fibSeries[i] = fibSeries[i-1] + fibSeries[i-2]
	}
	return fibSeries
}

func main() {
	var n int
	fmt.Print("Введите число: ")
	fmt.Scan(&n)
	fibNumbers := fibonacci(n)
	fmt.Println(fibNumbers)
}

```
**3) Реверс массива**
```
package main

import (
    "fmt"
)

func reverseArray(arr []int) []int {
    reversed := make([]int, len(arr))
    for i, v := range arr {
        reversed[len(arr)-1-i] = v
    }
    
    return reversed
}

func main() {
    arr := []int{1, 2, 3, 4, 5}
    reversedArr := reverseArray(arr)
    fmt.Println(reversedArr)
}

```
**4) Поиск простых чисел**
```
package main

import (
	"fmt"
)

func isPrime(num int) bool {
	if num < 2 {
		return false
	}
	for i := 2; i*i <= num; i++ {
		if num%i == 0 {
			return false
		}
	}
	return true
}

func main() {
	var n int
	fmt.Print("Введите число: ")
	fmt.Scan(&n)
	primes := []int{}

	for i := 2; i <= n; i++ {
		if isPrime(i) {
			primes = append(primes, i)
		}
	}

	fmt.Println(primes)
}

```
**5) Сумма чисел в массиве**
```
package main

import (
	"fmt"
)

func main() {
	numbers := []int{1, 2, 3, 4, 5}

	sum := 0
	for _, number := range numbers {
		sum += number
	}

	fmt.Println("Сумма чисел в массиве:", sum)
}

```
