Programming Language: Go

Use print statements when you're stuck. so you can see the output. The print command is  fmt.Println() 
Find the set of inputs or a sequence that throws the error and use the print statements to trigger the bug
Use the devler debugger for Go.
Check your syntax and logic errors.

For example:

package main

import (
    "fmt"
)

func add(a, b int) int {
    fmt.Printf("Adding %d and %d\n", a, b)
    result := a + b
    fmt.Printf("Result is %d\n", result)
    return result
}

func main() {
    num1 := 5
    num2 := 3
    sum := add(num1, num2)
    fmt.Printf("Final sum: %d\n", sum)
}

In this example, we are using print functions to prin t the input before we call the add function to make sure our input is right.