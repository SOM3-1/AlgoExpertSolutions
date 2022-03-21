# AlgoExpertSolutions
## product sum of special array


{
  "array": [5, 2, [7, -1], 3, [6, [-13, 8], 4]]
}
o/p 12

so 5+2 = 7
next we find an array
this is an arrray inside another array so dept will be 2
next our option would be to sum this and multiply by depth
i.e 7-1*2 and add it to next sum
i.e 12+17 
next 3=> add
20
next 6 that is not a number so depth will be 2 and next items inside that is an array, so depth willincrease to 3
do the above deeds
and returnthe sum

# I solved this using recursion
```javascript
function productSum(array, m=1) {
	let sum = 0;
	for (let i = 0;i<array.length;i++){
		if (typeof array[i]  == 'number'){
			sum += array[i];
		}
		else{
    //dept increase everytime a new array is encountered
			sum += productSum(array[i], m+1)
		}
	}
	return m*sum;
}
```
