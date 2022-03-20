# AlgoExpertSolutions
## check if the 2nd array is subsequent 

{
  "array": [5, 1, 22, 25, 6, -1, 8, 10],
  "sequence": [1, 6, -1, 10]
}

They are need not to be adjacent but need to be in sequence 

Hint: if 1 from 2nd array is not matched then we do not need to continue,next when 1 is found in first array thn we do not need to check the previous elements again because it has to be sequence. Once elements are found, push it to a new array, if the sub and new array length match the return true;


```javascript
function isValidSubsequence(array, sequence) {
	
	let arrayIndex = 0;
	let sequenceIndex = 0;
	while(arrayIndex < array.length && sequenceIndex < sequence.length){
		if(array[arrayIndex] === sequence[sequenceIndex])
			sequenceIndex++;
		arrayIndex++;
	}
	return sequenceIndex === sequence.length;
}
```
