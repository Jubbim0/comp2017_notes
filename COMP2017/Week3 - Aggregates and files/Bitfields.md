- For some specialised applications where you need data fields that are smaller than a byte or are packed into several bytes
- You can specify a size, in bits, for elements in a structure
- eg for:
![](Screenshot%202024-01-06%20at%203.30.56%20pm.png)
```c
struct IOdev {
  unsigned R_W: 1;
  unsigned Dirn: 8;
  unsigned mode: 3;
  unsigned pad: 4;
}
```