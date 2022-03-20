# AlgoExpertSolutions

# minimum num of sum that cannt be created
if we have [1,2,5]  then we cannot create 4
Can be created, 1,2,3,6,7,8 (4 wasn't present or didnt get add up)

{
  "coins": [5, 7, 1, 1, 2, 3, 22]
}
o/p: 20


First sort it

# THERE IS A PATTERN , if the added sum+1 is less than next value then return added sum+1;

Lets take above example

[1,1,2,3,5,7,22]
lets start with 0
not of minChange+1 < coins[i] then add sum +coins[i]
           min+ coins[i]
0+1 > 1 => 0+1 = 1
1+1 > 1 => 1+1 = 2
2+1 > 2 = > 4
4+1 > 3 => 7
7+1 > 5 => 12
12+1 > 7 =>19
19+1 < 22 => retrun 19+1





```javascript
function nonConstructibleChange(coins) {
  // Write your code here.

	let minChange  = 0;	
	coins.sort((a,b) => a-b);
	for( let i = 0;i<coins.length;i++)
		{
			if( minChange+1 < coins[i])
				return minChange+1;
			minChange += coins[i];
		}
	return minChange+1;
}
```
