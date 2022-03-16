# Unbufferd Channels



1. /////////////////////////////////
2. // Unbuffered Channels
3. // Go Playground: https://play.golang.org/p/\_44csjQDJvM
4. /////////////////////////////////
5. &#x20;
6. package main
7. &#x20;
8. import (
9. "fmt"
10. "time"
11. )
12. &#x20;
13. func main() {
14. c1 := make(chan int) //unbuffered channel
15. &#x20;
16. // Launching a goroutine
17. go func(c chan int) {
18. fmt.Println("func goroutine starts sending data into the channel")
19. c <- 10
20. fmt.Println("func goroutine after sending data into the channel")
21. }(c1) // calling the anonymous func and passing c1 as argument
22. &#x20;
23. fmt.Println("main goroutine sleeps for 2 seconds")
24. time.Sleep(time.Second \* 2)
25. &#x20;
26. fmt.Println("main goroutine starts receiving data")
27. d := <-c1
28. fmt.Println("main goroutine received data:", d)
29. &#x20;
30. // we sleep for a second to give time to the goroutine to finish
31. time.Sleep(time.Second)
32. &#x20;
33. // After running the program we notice that the sender (the func goroutine) blocks on the channel
34. // until the receiver (the main goroutine) receives the data from the channel.
35. }
36. &#x20;
37. //\*\* EXPECTED OUTPUT: \*\*//
38. // main goroutine sleeps for 2 seconds
39. // func goroutine starts sending data into the channel
40. // main goroutine starts receiving data
41. // main goroutine received data: 10
42. // func goroutine after sending data into the channel
