Created: 1503250830

Type: [[lesson]]

Tags: [[swift]], [[documentation]], [[programming]]

##### Goal: Create a constant with an explicit type of `Float` and a value of `4`.

Solution: `let constType: Float = 4`


Example: ``` let individualScores = [75, 43, 103, 87, 12]
var teamScore = 0
for score in individualScores {
 if score > 50 {
 teamScore += 3
 } else {
 teamScore += 1
 }
}
print(teamScore)
// Prints "11" ```

Explanation: Declares a constant with an array of the scores of individual teams members, then declares a variable of the team score. It then creates a if-else function, which adds 3 to the team score if the team member has a score above 50, and adds 1 if they score below 50. It then declares a print call to show the new value of the teamScore variable. 