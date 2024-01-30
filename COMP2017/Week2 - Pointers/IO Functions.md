# General / Both Input and Outout

## feof(stream)
For reading input files, eg. stdin the EOF is important
	- feof() tests the end of file indicator (return boolean)
	- EOF does not happen until trying to read beyond the end of the file eg.
```c
// while not at the end of file
while (!feof(stdin)) {
	int num;
	fscanf(stdin, "%d", &num); // take the next int in standard in, and store it at the address of num (num = stdin[position])
	fprintf(stdout, "num: %d\n", num); // print the value to standard out, EOL char between each entry.
}
```

## fflush
- Output stream: force writes all data 
- input stream: discard any unprocessed buffered data

# Input
## int getchar(void);
- Most basic form of input 
- Reads from standard input, the next character
- Returns -1 (defined as the symbol EOF)

## int scanf(const char \*format, ...)
- reads from stdin
- returns:
	- number of successfully read items
- Arguments:
	- First argument is a format string 
	- Followed by parameters stored as [pointers](Pointers.md)
eg.
```c
int x;  
float f;  
scanf(“%d %f”, &x, &f);
```

## char \*fgets(char \*str, int n, FILE \*stream)
- Reads a line from the specified stream and stores it to memory pointed to by \*str
	- use string processing functions to deal with returned data
- It stops when either:
	- It reaches (n-1) char is read
	- a new line character is encountered
	- EOF is encountered 
- Combine `fgets` and `feof` together to distinguish between read errors vs EOF
eg. read from stdin, for a max of 63 characters, print each line
```c
#include <stdio.h> #include <string.h>

#define BUFLEN (64)

int main(int argc, char **argv) { int len;

char buf[BUFLEN];  
while (fgets(buf, BUFLEN, stdin) != NULL) {

len = strlen(buf);

printf("%d\n", len); }

return 0; }
```
# Output
## void putchar(int c);
- Write a character (represented by an integer) to stdout
## int printf(const char \*format, ...)

- printf() writes to stdout:
	- Strings
	- Variables of a primitive type
- Returns:
	- Number of printed characters
- Arguments:
	- First argument is a format string 
	- Followed by an arbitrary number of parameters depending on format strings 
- Format string codes:
| Code       |                     Description                      |
| ---------- |:----------------------------------------------------:|
| %c         |                      Character                       |
| %d         |                       Integer                        |
| %u         |                   Unsigned Integer                   |
| %f, %g, %e |             double floating point number             |
| %x         |                     Hexadecimal                      |
| %ld        |                         Long                         |
| %.2f       | Print floating point numbers with two decimal points |
| %s         |                        String                        |
| %p         |                       Pointer                        |
|            |                       Print %                        |




eg. to take a temp (in ºF) and convert to ºC:
```c
int main(int argc, char **argv) {

int ftemp; /* the fahrenheit temperature */

printf("Please enter a fahrenheit temperature");

 scanf("%d", &ftemp);

printf("%d fahrenheit is %d centigrade", ftemp, (ftemp-32)*5/ 9);

return 0; }
```