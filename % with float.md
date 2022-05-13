``` go
package main

import (
	"fmt"
	"reflect"
	"time"
)

func main() {
	var (
		num1 float64	// 因为提前声明了float类型，导致不能用 % 运算
		num2 float64
		operator string
	)

	fmt.Println("输入算式，运算符与数字用空格隔开：")
	fmt.Scanln(&num1, &operator, &num2)

	if (reflect.TypeOf(num1) == int && reflect.TypeOf(num2) == int) {
		fmt.Println(Calculation_int(num1, num2, operator))
	} else {
		fmt.Println(Calculation(num1, num2, operator))
	}

	time.Sleep(5 * time.Second)
}

func Calculation(x float64, y float64, operator string) float64 {
	switch operator {
	case "+":
		return x + y
	case "-":
		return x - y
	case "*":
		return x * y
	case "/":
		return x / y
	default:
		fmt.Println("Error: Invalid operator")
		return 0
	}
}

func Calculation_int(x int, y int, operator string) int {
	switch operator {
	case "%":
		return x % y
	default:
		fmt.Println("Error: Invalid operator")
		return 0
	}
}


```
