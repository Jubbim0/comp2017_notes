# Simple Variables
- C has a number of simple types
	- float, int, char, etc
	- each implies an interpretation of the bit pattern stored in the memory

- *Declarations* label and reserve memory 
	- eg. reserve memory for an integer and call it "counter"
```c
int counter;
```
- *Initialisation* or assignment specifies content:
```c
int counter = 0;
counter = 0;
```

In memory this would look like
![](Screenshot%202023-11-17%20at%207.11.18%20pm.png)
![](Screenshot%202023-11-17%20at%207.11.27%20pm.png)
![](Screenshot%202023-11-17%20at%207.11.37%20pm.png)

# Arrays 
- Arrays are indexed collections of the same types 
- declared with:
	- `<type> <variablename>[size]`
eg.
```c
int  counters[MAX];
char alphabet[26];
```
# Strings
- Strings are represented by "array-like" notation
- An array of characters
eg.
```c
char myHobby[] = ”rowing”;
```
- All strings are NULL-terminated
	- NULL is the binary value 0 (denoted as '\0'), not the ASCII 0
	- eg. the above array would have the char: \['r', 'o', 'w', 'i', 'n', 'g', '\\0']
# Memory & Pointers
- Memory begins as random values at addresses
 ![](Screenshot%202023-11-18%20at%203.08.51%20pm.png)
 - A pointer is essentially a memory addresses 
 - We can find out the address of a variable using the & operator
![](Screenshot%202023-11-18%20at%203.10.36%20pm.png)![](Screenshot%202023-11-18%20at%203.11.09%20pm.png)

# Pointer Operators
## Indirection Operator "\*"
- Indirection operator, '\*'
	- The indirection operator, '\*' is used in a variable declaration to declare a "pointer to a variable of the specified type"
![](Screenshot%202023-11-18%20at%203.12.32%20pm.png)

Two examples:
```c
float * amt;
```
- A pointer (labeled amt) to a float 
```c
float ** tricky;
```
- A pointer (labelled tricky) to a pointer to an int 

- The indirection operator '\*' is used to "unravel" the indirection
## Address Operator "\&"
- & is used to access the address of a variable 
- A pointer can be assigned to the address of a variable by:
```c
int *countp = &count;
```
- This declares a pointer to an integer, the integer being the address when viewed as hexidecimal 
- eg. use of pointer notation to manipulate arrays:
```c
char msg[] = "Hello!";
char *str = &msg[0]
```
	- This creates a pointer to the address of the first char of the string

## Dereferencing, Also "\*"
- if the /* is on the right hand side of the expression, before a variable of type pointer, it evaluates the memory assigned at that location
- eg:
```c
int x = 4; // assigns the value of 4 to x at some location in memory
int * px = &x; // assigns a pointer px to the address of x eg. 0x100
int y = *px // dereferences px, to find the value of 4 stored earlier
```
# Shortcuts
- Pointer notation leads to some shortcuts as apart of C:
	- eg. moving through a string 
```c
while (*str != '\0')
  str++
```
	- As C treats '0' as false this can become:
```c
while (*str)
  str++;
```


# Pointer Arithmetic
```c
int *p = NULL;
int x[4];
p = x;
```
![](Screenshot%202023-11-20%20at%203.40.41%20pm.png)
- Seeking to the nth byte from a starting address?
```c
void *get_address(someType *data, int n){
  unsigned char *ptr = (unsigned char*) data;
  return (void*)(ptr + n);
}
```

[Data Types](Data%20Types.md)
