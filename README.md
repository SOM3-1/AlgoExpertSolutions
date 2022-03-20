## Search in sorted 2 dimensiona array
{
  "matrix": [
    [1, 4, 7, 12, 15, 1000],
    [2, 5, 19, 31, 32, 1001],
    [3, 8, 24, 33, 35, 1002],
    [40, 41, 42, 44, 45, 1003],
    [99, 100, 103, 106, 128, 1004]
  ],
  "target": 44
}

o/p [3,3]

## Use two pinter to identify the target
First we eliminate the row then move to column
first we choose the element in top right corner, if the target  is less than 0th row last eleemnt then move to the previous column. If the target is greater than current 2d index then change row.

For example we will take 1000 as our column value in 0th row to check with target
1000 > 44
so col--
now col = 15
44>15, row++
so now we check in 1st row
32<44
row++
35<44
row++
45>44, so col--
44 match, return index value


```javascript
function searchInSortedMatrix(matrix, target) {
	let finalArray = [-1, -1];
	let row = 0;
	let col = matrix[0].length-1;
	while (row<matrix.length && col>=0){
		if(target === matrix[row][col])
			return [row,col];
		else if(target < matrix[row][col])
			col--;
		else
			row++
	}return finalArray;
  // Write your code here.
	
}
```
