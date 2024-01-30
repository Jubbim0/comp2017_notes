- Memory allocation functions return a void pointer (no scalar value)
## malloc(size_t size);
1. Request size number of bytes of memory
2. Returns a pointer:
	- If successful, points to new memory
	- If unsuccessful, is null
- size_t is typically defined as an unsigned int
	- It replaces the use of more specific types to allow the implementation to be system-specific
	- The `sizeof()` operator is of type size_t
- Eg:
```C
int * ptr;
ptr = (int *)malloc(sizeof(int)*20)
/* 1. initialise the pointer you will use
 * 2. Size of an int is 4 bytes,  will resolve to 80 bytes
 * 3. Cast result pointer to an int pointer
 */
```

## void \*calloc(size_t num, size_t size)
- Has two arguments:
	- num specifies the number of 'blocks' of contiguous memory
	- Size specifies the size of each block
- The allocated memory is cleared (set to 0)

## void free (void \*ptr)
- The argument is the pointer to the section of memory you wish to unallocate
- eg:
```C
int * ptr;
ptr = (int *)malloc(sizeof(int)*20);
free((void *)ptr);
Ptr = NULL;
```
