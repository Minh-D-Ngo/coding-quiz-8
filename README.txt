- Staircase
	- Time complexity: The time complexity of this code is O(n^2), where 'n' 
is the input parameter. The outer loop runs 'n' times (from 1 to 'n'). Within each 
iteration of the loop, creating the string stair involves two repeat operations. 
The repeat operation itself takes linear time proportional to the length of the 
resulting string. So for each iteration, you're performing repeat operations for 
'n' times ('n - i' spaces and 'i' hashtags). As a result, the total number of 
repeat operations sums up to n + (n - 1) + (n - 2) + ... + 1, which is proportional 
to n^2. Therefore, the overall time complexity is O(n^2).

	- Space complexity: The space complexity of this code is O(n^2) as well.
Within each iteration of the loop, two strings are created: one for spaces and 
another for hashtags, each with a length proportional to 'n'. However, as the code 
doesn't store these strings but rather prints them directly, the space complexity 
for strings doesn't accumulate over iterations.

- Alternating Characters (Recursive)
	- Time complexity: The time complexity of this code is O(n), where 'n' is 
the length of the input string s. This is because the function makes a single pass 
through the string, evaluating each character once.

	- Space complexity: The space complexity is O(n), where 'n' is the length 
of the input string s. This is due to the recursive calls and the space taken up 
by the call stack. In the worst case, the function can make 'n' recursive calls, 
consuming space on the stack proportional to the length of the string.

	- Recursive Definition:
1. Function alternatingCharacters(String s):
	- Entry point for the user. Calls the helper recursive function countDeletions 
and passes the input string s and an initial index of 0.
	- Returns the result of the countDeletions function.

2.Function countDeletions(String s, int index):
	- Parameters: s is the input string, and index is the current index being evaluated.
	- Base case: If the current index index is greater than or equal to the length of 
the string minus 1 (s.length() - 1), return 0. This signifies reaching the end of the string.
	- Recursive steps:
		- Retrieve the characters at the current index index and the next index index + 1.
		- If these characters are the same (currentChar == nextChar), increment the count 
by 1 and recursively call countDeletions with the next index (index + 1).
		- If the characters are different, recursively call countDeletions with the next 
index (index + 1) without incrementing the count.
	- The recursion continues until it reaches the end of the string. At each step, 
it checks if the current character is the same as the next character. If they're the same, 
it counts one deletion and moves to the next character.
=> The function works by examining each character and checking if it is the same as the next 
character. If they are the same, it counts a deletion and moves to the next character for evaluation. 
The recursion continues until it reaches the end of the string, and the total count of deletions 
needed to make the string have alternating characters is returned.

*Note*: One of the test case for alternating characters had a runtime error as the
code is written recursively