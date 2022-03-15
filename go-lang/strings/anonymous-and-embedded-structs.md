# Anonymous and Embedded Structs



1. /////////////////////////////////
2. // Anonymous and Embedded Structs
3. // Go Playground: https://play.golang.org/p/NtH6I30gtxb
4. /////////////////////////////////
5. &#x20;
6. package main
7. &#x20;
8. import (
9. &#x20;   "fmt"
10. &#x20;   "strings"
11. )
12. &#x20;
13. func main() {
14. &#x20;
15. &#x20;   // an anonymous struct is a struct with no explicitly defined struct type alias.
16. &#x20;   diana := struct {
17. &#x20;       firstName, lastName string
18. &#x20;       age                 int
19. &#x20;   }{
20. &#x20;       firstName: "Diana",
21. &#x20;       lastName:  "Muller",
22. &#x20;       age:       30,
23. &#x20;   }
24. &#x20;
25. &#x20;   fmt.Printf("%#v\n", diana)
26. &#x20;   // =>struct { firstName string; lastName string; age int }{firstName:"Diana", lastName:"Muller", age:30
27. &#x20;
28. &#x20;   //\*\* ANONYMOUS FIELDS \*\*//
29. &#x20;
30. &#x20;   // fields type becomes fields name.
31. &#x20;   type Book struct {
32. &#x20;       string
33. &#x20;       float64
34. &#x20;       bool
35. &#x20;   }
36. &#x20;
37. &#x20;   b1 := Book{"1984 by George Orwell", 10.2, false}
38. &#x20;   fmt.Printf("%#v\n", b1) // => main.Book{string:"1984 by George Orwell", float64:10.2, bool:false}
39. &#x20;
40. &#x20;   fmt.Println(b1.string) // => 1984 by George Orwell
41. &#x20;
42. &#x20;   // mixing anonymous with named fields:
43. &#x20;   type Employee1 struct {
44. &#x20;       name   string
45. &#x20;       salary int
46. &#x20;       bool
47. &#x20;   }
48. &#x20;
49. &#x20;   e := Employee1{"John", 40000, false}
50. &#x20;   fmt.Printf("%#v\n", e) // => main.Employee1{name:"John", salary:40000, bool:false}
51. &#x20;   e.bool = true          // changing a field
52. &#x20;
53. &#x20;   fmt.Println(strings.Repeat("#", 10))
54. &#x20;
55. &#x20;   //\*\* EMBEDDED STRUCTS \*\*//
56. &#x20;   // An embedded struct is just a struct that acts like a field inside another struct.
57. &#x20;
58. &#x20;   // define a new struct type
59. &#x20;   type Contact struct {
60. &#x20;       email, address string
61. &#x20;       phone          int
62. &#x20;   }
63. &#x20;
64. &#x20;   // define a struct type that contains another struct as a field
65. &#x20;   type Employee struct {
66. &#x20;       name        string
67. &#x20;       salary      int
68. &#x20;       contactInfo Contact
69. &#x20;   }
70. &#x20;
71. &#x20;   // declaring a value of type Employee
72. &#x20;   john := Employee{
73. &#x20;       name:   "John Keller",
74. &#x20;       salary: 3000,
75. &#x20;       contactInfo: Contact{
76. &#x20;           email:   "jkeller@company.com",
77. &#x20;           address: "Street 20, London",
78. &#x20;           phone:   042324234,
79. &#x20;       },
80. &#x20;   }
81. &#x20;
82. &#x20;   fmt.Printf("%+v\n", john)
83. &#x20;   // => {name:John Keller salary:3000 contactInfo:{email:jkeller@company.com address:Street 20, London phone:295619381404\}}
84. &#x20;
85. &#x20;   // accessing a field
86. &#x20;   fmt.Printf("Employee's salary: %d\n", john.salary)
87. &#x20;
88. &#x20;   // accessing a field from the embedded struct
89. &#x20;   fmt.Printf("Employee's email:%s\n", john.contactInfo.email) // => Employee's email:jkeller@company.com
90. &#x20;
91. &#x20;   // updating a field
92. &#x20;   john.contactInfo.email = "new\_email@thecompany.com"
93. &#x20;   fmt.Printf("Employee's new email address:%s\n", john.contactInfo.email)
94. &#x20;   // =>  Employee's new email address:new\_email@thecompany.com
95. }
