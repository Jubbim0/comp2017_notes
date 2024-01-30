- To do math on binary, bitwise operators must be used
- These include:
	- shift right: >>
	- shift left: >>
	- bitwise AND: &
	- bitwise OR: |
	- bitwise XOR: ^
	- bitwise NOT: ~
## shift right: >>

## shift left: >>
- Move each bit to the left by the second number times, losing everything to the left
eg. 5 >> 2 = 00000101 >> 2 = 00010100 = 20
	
## bitwise AND: &
- Does a comparison between each bit in the two numbers,
	- if both 1 then output is 1
	- otherwise output is 0
- Truth Table:

| x   | y   | &   |
| --- | --- | --- |
| 1   | 1   | 1   |
| 1   | 0   | 0   |
| 0   | 1   | 0   |
| 0   | 0   | 0   |
- eg. 100110 & 011111 = 000110
## bitwise OR: |
- Does a comparison between each
- Truth Table:

| x   | y   | |   |
| --- | --- | --- |
| 1   | 1   | 1   |
| 1   | 0   | 1   |
| 0   | 1   | 1   |
| 0   | 0   | 0   |


## bitwise XOR: ^
- Truth Table:

| x   | y   | ^   |
| --- | --- | --- |
| 1   | 1   | 0   |
| 1   | 0   | 1   |
| 0   | 1   | 1   |
| 0   | 0   | 0   |


## bitwise NOT: ~
- Flips every bit 
- Truth Table:

| x   | ~   |
| --- | --- |
| 1   |    0 |
| 0    |   1  |
