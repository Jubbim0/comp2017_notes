- Primitive version of classes
- Allows storing multiple values in a key-value map, containing differently typed values 
- eg making a structure:
```c
struct date // name of structure 
{
// fields of structure:
enum day_name day;
int day_num;
enum month_name month;
int year;
};
```
- After this is done, you may initialise an instance of the structure:
```c
Big_day // structure declaration
{
Mon, 7, Jan, 1980 // structure initialisation
};

// OR:
struct date moonlanding; // declaring NULL filled struct 
struct date deadline = {day_undef, 1, Jan, 2000}
```
- More generally:
```c
struct [tag]
{
  [member-declarations]
} [identifier-list];
// once defined, can declare with:
struct [tag] [identifier-list];
// set elements with:
[identifier].[field] = [new-value];
// access elements with
[dataType] [variable] = [identifier].[field]
```
- if a pointer to the struct is used, then the -> operator indicates the element required, eg:
```c
struct date bigday;
struct date* mydate;
int theyear;

mydate = &bigday
theyear = mydate->year
```

# Type Def
- Removes the necessity to put "struct \[tag]", instead gives a short hand typed 
- eg.
```c
typedef struct date{

enum day_name int  
enum month_name int

} Date;

Date Big_day = {Mon,  
Date moonlanding;  
Date dopday = {day_undef, 1, Jan, 2000}; Date *completion;
```

# Included Structures in C 
- There are a number of files that contain structures to use in your programming:
	- stdio.h
	- time.h
	- stat.h
	- pwd.h

## stdio.h
- Used to work with [Files in C](Files%20in%20C.md)
- FILE is a struct in this file
- To open a file, use [IO Functions](IO%20Functions.md):
	- eg. use - `FILE *fopen(const char *path, const char *mode` - to open a file `turtles.txt` in write mode
```c
#include <stdio.h>
FILE * myfile = fopen("turtles.txt", "w")
```
(path can be relative eg `turtles.txt` or absolute eg. `/home/ssta7171/turtles.txt`
- modes for fopen have the first character being
	- "r" - open file for reading
	- "w" - truncate to zero length, or create a text file for writing
	- "a" - append; open or create text file for writing at EOF
- With just the above character, it is the default mode. A second char can be added to change  the functionality:
	- "b" - works with binary files instead of text eg. 
		- "rb" - open binary file for reading
		- "wb" - truncate to zero length or create binary fie for writing 
		- "ab" - append; open or create binary file for writing at EOF
	- "+" - updating the file 
		- "r+" - open file for updating (reading and writing)
		- "w+" - truncate to zero length, or create a text file for update
		- "a+" - "a" - append; open or create text file for update at EOF


## time.h

## stat.h

## pwd.h

# Memory Alignment
