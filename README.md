
# In an arry find the target sum
May be sorted or not (if not then sort it

{
  "array": [3, 5, -4, 8, 11, 1, -1, 6],
  "targetSum": 10
}


sort the input array;
[-4,-1,1,3,5,6,8,11

Use two pointer , add first and last 
-4+11 = 7
7<10
so we need higher value to get the value
so increment the first pointer
 do tis itertaively
 
 ```javascript
 function twoNumberSum(array, targetSum) {
   let left = 0;
    let right = array.length - 1;
	array.sort((a,b) => a-b);

    while (left < right) {
        let sum = array[left] + array[right];
        if (sum === targetSum) {
            return [array[left],array[right]];
        } else if (sum > targetSum) {
            right--;
        } else {
            left++;
        }
    }
	return [];
}
```
## One more solution without sorting 
Using objects/hash map in js
We get the tget value right?
we have the first index/pointer value  too
so get the value that we need to make the sum complete
Initialise an empty object


sum = target - first index value;
sum = 10-3 => 7

if the sum is not found in object then add the index 
obj = {3}
iterate to next index
sum =10-5 = 5
obj = {3, 5}
sum = 10 - (-4) = 14
obj = {3, 5, -4}
sum=10-8 =2
obj = {3, 5, -4, 8}
sum = 10-11 = -1
obj = {3, 5, -4, 8, 11}
sum = 10-1= 9
obj = {3, 5, -4, 8, 11, 1}
sum = 10+1 = 11
11 found in the object so return it



```javascript
function twoNumberSum(array, targetSum) {
  // Write your code here.
	let sum ;
	const table = {};
	
	for(const num of array){
		sum = targetSum - num;
		if(sum in table)
			return [num, sum];
		else
			table[num]=true;	
	}
	return [];
}
```


