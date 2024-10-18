# Learning c++
[https://www.learncpp.com/](https://www.learncpp.com/) is the top recomended learning platform.


## VS code settings for c++

To run a c++ program we need a compiler, Mac already has clang++ and g++ via xcode-developer-tools

try typing clang++ in the terminal

```shell
$ clang++ --help
$ g++ --help
```


## Basic clang++ commands

### To compile the cpp file
Lets say you have a **hello-world.cpp** that prints hello-world

```cpp
// hello-world.cpp

#include <iostream>

int main()
{
    std::cout << "Hello, world!" << std::endl;
    return 0;
}
```

open the temnial <mark style="background:gray;">&nbsp;cmd + j&nbsp;</mark> then type 

```
$ clang++ hello-world.cpp
```

this will create a file **a.out** , this is the compiled code of **hello-world.cpp**

### Lets run our compiled program
type the compiled code filename and hit enter

```
$ ./a.out
Hello, world!
```
hurray! you just executed your fist program

### Naming the output file
a.out is not a bad name for the program. Lets change by adding -o and name of the file

```
$ clang++ hello-world.cpp -o hello-world.out
$ ./hello-world.out
Hello, world!
```

