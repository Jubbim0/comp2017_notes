## Definition
- More formal example: \<Llist> ::== Nothing | element \<Llist>
- A link list is an ordered collection of [Data Types](Data%20Types.md), where the next element in the list is accessed via a pointer to the data instead of continuously stores like an array
	- Linked lists may use multiple links to link elements according to interpretations of order BUT the most common implementation is a `singly linked list` where one element maps to one pointer to another element 
## Datatype Implementation Diagram 
![](Screenshot%202024-01-09%20at%202.12.48%20pm.png)
- Each element has two components:
	- the `data` component (anything you want)
	- the `link` component (a pointer)
	![](Screenshot%202024-01-09%20at%202.14.57%20pm.png)
	(NULL depicts the end of list)
- Adding an element to the front:
![](Screenshot%202024-01-09%20at%202.18.34%20pm.png)
(before any changes)
![](Screenshot%202024-01-09%20at%202.20.00%20pm.png)
(set the starting pointer to the new element, and the new elements pointer to what was the old first element)
- However, if the starting pointer was changed first you lose access to the pointer to the location of the original first element
	- one pointer can point to one thing; everytime we draw a new arrow we effectively erase any existing pointer 
- Adding an element elsewhere in the list:
![](Screenshot%202024-01-13%20at%203.22.28%20pm.png)
![](Screenshot%202024-01-13%20at%203.22.39%20pm.png)


## Linked List: Internals
- The dynamic nature of the linked list data structure means we must allocate and free memory on demand
	- Most higher level languages deal with this automatically for the programmer, but not in C 

1.  Represent each datapoint as a node. This is a structure which contains a pointer to its data (initialised as a void pointer) and a pointer to the next node structure in the dataset:
```c
struct node {
	void *data;
	struct node *next;
}
```
2. make the first node, with next=NULL (one element linked list):
```c
struct node n;
n.data = 0;
n.next = NULL;
```


# Characteristics
What is the worst case situation for altering the n-th element of:
- An array 
	- Altering an element anywhere in the array has the same cost. As array's elements are reffered to by their address offset, their cost is `O(1)` or constant time
- A linked list 
	- Altering an element at the end of the linked list requires traversal of the whole data structure, the cost is `O(n)` or linear time
## Advantages
- Dynamic nature of the data strucuture
- Flexible structure 
	- Singly linked list 
	- Doubly linked 
	- Circular list 
	- etc.
## Disadvantages
- Linear worst-case cost of access 
- The absence of a Linked List implementation in standard C (have to DIY)

# Programatic Implementation 
As a linked list is dynamically sized, we must allocate and free memory manually, to do so use:
- malloc()
	- to allocate and free memory when we add an element 
- free()
	- to de-allocate memory when it goes out of scope / is removed

1. Declare the data structure 
```c
struct LinkedList {
	char *content; // pointer to String in memory
	Struct LinkedList *next; // pointer to the next element of the LL
}
```
2. Add an element to the front 
```c
// returns a pointer to the linked List, has attributes of the current data structure and the point to insert
struct LinkedList *addToFront(struct LinkedList *listp, struct LinkedList *newp) {
	newp->next = listp;
	return newp;
}
```
3. Adding to the end
```c
struct LinkedList *addToEnd(struct LinkedList *listp, struct LinkedList *newp) {
	struct LinkedList *p; // holds pointer to not lose ref to struct 
	// if it is an empty linked list
	if (listp == NULL)
		return newp;
	// Start from listP, setting p to the next pointer, then transverse through the LL till the end (next == NULL)
	for(p=listp; p->next != NULL; p=p->next)
		; // NULL STATEMENT
	// once at the end of the data structure set the NULL next to the new data
	p->next = newp;
	return listp;
}
```
4. Deallocating all in a list 
```c
void freeAll(List *listp){
	struct List *p;
	for(; listp != NULL; listp=p) {
		p = listp->next;
		free(listp->content);
		free(listp);
		
	}
}

```
6. Delete the first element in a list
```c
struct List deleteFirstElement(List *listp){
	struct List *p
	if (listp != null) {
		p=listp->next
		free(listp->content);
		free(listp);
	}
	return p;
}
```
7. Count the length of the linked list
```c
int count(struct List *listp) {
	int counter = 0;
	for( ; listp!=NULL; counter++)
		listp = listp->next;
	return counter;
}
```