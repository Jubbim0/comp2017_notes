Common Types:
- [Enums](Enums.md)
- [Structure](Structure.md)
- [Union](Union.md)
Dynamic Data Structures:
- [Linked Lists](Linked%20Lists.md)
# Sizes
All datatypes have a specific amount of memory that they occupy (found by the sizeOf(Obj) function), these are defined in the file <limits.h>
- Int does not have a standard number of bytes in C
- The type **char** is defined in <limits.h>
	- `#define UCHAR_MAX 255    // max value for an unsigned char`
	- `#define CHAR_MAX 127    // max value for a char`
	- `#define CHAR_MIN (-128)    // min value for a char`

# Floating Point Types
- Exact bit representation unknown, usually IEEE 754
- Generally, floating point number **x** is defined as:
![](Screenshot%202023-11-20%20at%204.05.49%20pm.png)
Where:
- s - sign (+/-)
- b - base of exponent (eg. 2, 10, 16)
- e - exponent
- p - precision
- fk - non negative integer less then b
	- +0, -0, +ve/0 = +infinite, 
# Variable Keywords
- Most C implementations default types as signed values, but do NOT assume this
	- Using the keywords *signed* and *unsigned* helps mitigate this

- **const** makes the value immutable
	- It can be used to help avoid arbitrary changes to memory
- You can **cast** if you know the memory is writable
	- eg.
```c
char fileheader[] = {'P', '1'}; // writable
const char *dataptr = (char*)fileheader;
char *p = (char*)dataptr;
p[1] = '3';
```


