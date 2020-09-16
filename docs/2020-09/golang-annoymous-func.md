原文地址：[Link](https://haicoder.net/golang/golang-anonymous-func.html)
截取其中关键部分
# GO语言匿名函数
## 概念
就是只有函数体没有函数名的函数
## 用处
Go 语言的匿名函数可以直接赋值给变量，也可以作为函数的参数，传递给函数。
### 匿名函数做参数
1. 定义
```
func walk(lis []int, callback func(int)){
   
}
```
首先定义了一个函数walk，该函数的第一个参数是一个切片，第二个参数是一个参数为int类型的匿名函数
2. 案例
2.1 匿名函数赋值给变量
```
package main

import (
	"fmt"
)

func main() {
	fmt.Println("嗨客网(www.haicoder.net)")

	//Go语言的匿名函数可以赋值给变量
	f := func(num1, num2 int){
		fmt.Println(num1, " + ", num2, " = ", num1+num2)
	}

	f(10, 20)
}
```
2.2 匿名函数做参数
```
package main

import (
	"fmt"
)

func walk(lis []int, callback func(int)){
	for _, i := range lis{
		callback(i)
	}
}


func main() {
	fmt.Println("嗨客网(www.haicoder.net)")

	//Go语言匿名函数做参数，一般是用作回调函数
	slice := []int{1, 2, 3, 4}
	walk(slice, func(i int) {
		fmt.Println("Num =", i)
	})
}
```
