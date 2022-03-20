# AlgoExpertSolutions

There will be competion happening against two teams
one is home and another is away, winner will get 3 points and it'll be round robin
determine which got the highest point and return it

{
  "competitions": [
    ["HTML", "C#"],
    ["C#", "Python"],
    ["Python", "HTML"]
  ],
  "results": [0, 0, 1]
}
reults give us which team won
if its 0 then away team i.e 2nd index

# I CREATED THIS SOLUTION


First create an empt object
find out who won,
if the team is not found then add it to object and assign the points
Next competition if same team wins then add the pooints, at the end keep track which team has highest points and return the key value

```javascript
function tournamentWinner(competitions, results) {
  // Write your code here.
  let tempObject  = {};
	let  i =0;
	let maxValue = 0;
	let winner = '';
	
	for (const x of competitions){
		let z = results[i]===1?x[0]:x[1];
		if(!(z in tempObject))
			tempObject[z] = 3;
		else 
			tempObject[z] = tempObject[z] + 3;
		
		if( maxValue <= tempObject[z])
			{
				maxValue = tempObject[z];
				winner = z;
			}
		i++;
	}
  return winner;
}



// Do not edit the line below.
exports.tournamentWinner = tournamentWinner;


/// my reference to reduce the obejct to find out largets value
Object.keys(tempObject).reduce((a, b) => tempObject[a] > tempObject[b] ? a : b);

```
