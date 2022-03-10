# Package fmt verbs example

```
package main

import "fmt"

func main() {
	name := "Pablo"
	fmt.Println("Hello, Playground, my name is ", name)

	a, b := 4, 6
	fmt.Println("Sum:", a+b, "Mean Value: ", (a+b)/2)

	figure := "Circle"
	radius := 5
	pi := 3.14159

	_, _ = figure, pi

	fmt.Printf("Radius is %d\n", radius)
	fmt.Printf("Radius is %+d\n", radius)
	fmt.Printf("Pi constant is %f\n", pi)
	fmt.Printf("The diameter of a %s with a Radius of %d is %f\n", figure, radius, float64(radius)*2*pi)

	//%q for quoted string
	fmt.Printf("This is a %q", figure)

	//%v -> replaced by any type
	fmt.Printf("The diameter of a %v with a Radius of %v is %v\n", figure, radius, float64(radius)*2*pi)

	// %T -> type data //se usa T mayuscula si usas la minuscula si funciona pero da en parentesis el dato nuevamente.
	fmt.Printf("figure is of type %t\n ", figure)
	fmt.Printf("radius is of type %t\n ", radius)
	fmt.Printf("pi is of type %t\n ", pi)
	fmt.Println("pi is of type %t ", pi)
	
	// %t -> bool
	closed := trye
	fmt.Printf("File closed: %t\n", closed)
	
	// %b -> base 2
	fmt.Printf("%b \n", 55)
	
	// %b -> base 2 ip4
	fmt.Printf("%08b \n", 55)
}

```
