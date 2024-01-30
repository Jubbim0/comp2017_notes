- Is a very low level language
	- Used for: systems software, and software that requires hardware interaction
	- Does not have features such as objects/classes/templates/operator overloading

- C-Programs consist of two language components: Preprocessing language and C-Language
- Differences from java are numerous:
	- Same control flow
	- References are called [pointers](Pointers.md)
	- No garbage collection
	- No classes or objects 
	- C is procedural while Java is object-orientated
- A C-Program consists of:
	- Global variables
	- Function definitions (main is envoked at start of runtime)
	- Functions have local variables

Hello world in C:
```c
#include <stdio.h>

int main (int argc, char **argv) {

printf("Hello World!\n");

return 0; }
}
```
- prints "hello world" to stdout 
- No standard input
- `int argc` stores number of arguments,
- `char **argv` stores the [pointers](Pointers.md) to the arguments 

# Running C Code 
- Put your code into a file with the ext `".c"`
- Compile the program using gcc
	- gcc hello.c –o hello  
	- gcc hello.c
- When you compile, compile flags may be used, for example from above:
	- `-o <name>`
- Run the program by typing the name of the program (default is a.out)
	- ./hello 
	- ./a.out

# Programming in C 
- [Functions](Functions%20in%20C.md) may be used
- There are ways to get [IO Functions](IO%20Functions.md)