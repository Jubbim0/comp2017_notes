- Programs consist of "modules"
	- A module is a file
- Modules consist of:
	- [Functions](Functions%20in%20C.md) declarations
	- Function definitions
	- Global Variables

- Symbols can only be *defined* in one module 

- Data structures definitions, and declarations, macro definitions and external function declarations are found in modules.
	- These are commonly found in header files
eg.
`foo.c`
```c
int foo() {
printf ("hello from foo\n");
return 0;
}
```
`foo.h`
```c
extern int foo();
```
`sample.c`
```c
#include “foo.h”

int main(int argc, char **argv) {

foo();

return 0; }
```
# Global Variables 
- A module can refer to global variables and  [Functions](Functions%20in%20C.md) of other modules. 
	- Use the extern qualifier for global variables 