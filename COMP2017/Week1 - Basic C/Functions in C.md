A function consists of:
- A function declaration
	- Name of function,
	- return type of function,
	- Parameter list and their types
	- Of the form `<functionType> <name>(<variableType> <variable>, ...)`
	- eg.
```c
int foo(float f1, char f2)
```
- Followed by a function body
	- Contains local variables and control followed 
	- Surrounded by braces {}
	- eg.
```c
{
int x = 0;
return x;
}
```
- If it does not return, put the return type as `void`
- If there are no parameters use `(void)`
- Functions with arbitrary number of parameters are possible (use a `*` ) 
	- A special interface is required for querying values of parameters (**va_args**)
	- 
	- eg.
```C
int printf(const char *format, ...)
```

# External or Forward Functions 
- Do not have a function body, just a semicolon 
- Parameter types are specified without variable names
- eg. `int foo(float, char);` or `extern int foo(float, char);`


# Basic Functions 
- [IO Functions](IO%20Functions.md)