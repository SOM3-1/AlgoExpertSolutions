## three number sum
find the index of three number sum

{
  "array": [12, 3, 1, 2, -6, 5, -8, 6],
  "targetSum": 0
}

o/p: [
  [-8, 2, 6],
  [-8, 3, 5],
  [-6, 1, 5]
]

First and foremost thing to do, sort the goddamn array always
Take the first index as first element, next take the second element as left and last index as right.
Apply two pinter technique

on finding sum we iterate left and right together to find  another set



```javascript
function threeNumberSum(array, targetSum) {
	array.sort((a,b) => (a-b));
	
	let finalArray = [];
	
	for ( let i =0;i<array.length-2;i++){
	let left = i+1;
	let right = array.length-1;
	while(left < right){
		let sum = array[i]+array[left]+array[right];
		if(targetSum === sum){
			finalArray.push([array[i],array[left],array[right]]);
			left++;
			right--;			
		}
		else if (targetSum > sum )
		left++;
		else if(targetSum<sum)
		right --;
		
		}
	}
	return finalArray;
	
}

```
