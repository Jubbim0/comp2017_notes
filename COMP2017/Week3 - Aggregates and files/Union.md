- Union allows you to declare variables that occupy the same memory, allows you to not consume extra memory 

# Example 
- For example, to make a library catalogue that contains information about books and films. Where book store: author and ISBN. And for films store: director, producer

## Solution 1 - Without Union 
```c
enum holding_type {book, film}
struct catalog {
  char * title;
  enum holding_type type;
  
  // book:
  struct {
	char * author;
	char * ISBN;
  } book_info;

  // film:
  struct {
	char * director;
	char * producer;
  } film_info;
};
```
- Only one of the structures book_info or film_info is used at any one time, major waste of memory 
- instead use a union to indicate that each variant occupies the *same* memory area
## Solution 2
```c
enum holding_type {book, film}
struct catalog {
  char * title;
  enum holding_type type;
  union {
	  // book:
	  struct {
		char * author;
		char * ISBN;
	  } book_info;
	
	  // film:
	  struct {
		char * director;
		char * producer;
	  } film_info;
  } info;
};
```