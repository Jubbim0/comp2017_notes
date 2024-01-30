- Memory is a long array of 8 bit pieces called bytes
- This array is indexed from 0 to the number of bytes in the memory
- Each index is a memory address

# Memory Areas
- [The Stack](The%20Stack.md): local variables, function arguments, return addresses, temporary stoage
- [The Heap](The%20Heap.md): dynamically allocated memory
- Global/Static: global variables, static variables
- Code: programmatic instructions
![](Screenshot%202024-01-20%20at%203.46.02%20pm.png)
# [Memory Allocation Functions](Memory%20Allocation%20Functions.md)
 - To allocate dynamic memory from the heap use:
	 - malloc(size_t size)
	 - calloc(size_t num, size_t size)