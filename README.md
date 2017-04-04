# REST-API-for-Scholarships
REST API that takes in the nxn matrix of scholarships given and returns your selections. 

You can only pick sequential scholarships and the product of all scholarships you pick is how much money you'll be awarded! (this school is very cheap, so you only need a few dollars... scholarships are in the range 0-100).

Scholarships can appear on the same row
...
... 1 2 3 4 5 6 ...
...

Or same column
...
1
2
3
4
5
...

Or on a diagonal
...
... 1 2 3 ...
... 1 3 5 ...
... 1 2 5 ...
...

The number of scholarships n is such that n >= 100.
An example request is outlined below.

Example (can only pick 3 scholarships) (n=5)
1 2 3 4 5    
1 1 2 3 5   
3 4 5 5 5    
3 4 5 9 5    
1 1 5 5 25    
Answer: 5 * 9 * 25 = 1125 (this is not wrong, figure out where this pattern is...)

API Specs:
POST /max_scholarship
'Content-Type: application/json'

Sample json:

{"data": [[1,2,3,4,5], [1,1,2,3,5], [3,4,5,5,5], [3,4,5,9,5], [1,1,5,5,25]]}
Response:

{"sequence": [5,9,25], "total": 1125}
