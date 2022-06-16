# Time Complexity and Tree
## Lecture plan
* Time complexity
* growth of functions
* time complexity on recursion
* binary tree
* binary search tree
## Time Complexity
* Theoretical approach
  - Characterizes the running time of an algorithm as a function of the input size, n
  - Allows us to evaluate the speed of an algorithm independent of the hardware or software environment
  -  <img width="438" alt="Screen Shot 2022-06-16 at 4 45 35 PM" src="https://user-images.githubusercontent.com/89602311/174171332-6ab63925-bbd8-4f61-a959-45334f2b0227.png">
* Low-Level Algorithm Analysis
  - Assign a value to a variable = 1 operation
  - Make an arithmetic operation = 1 operation
  - Calling a method = 1 operation
  - Returning from a method = 1 operation
  - Index in an array = 1 operation
  - Comparison = 1 operation etc.
* Low-Level Algorithm Analysis on the example
  - <img width="823" alt="Screen Shot 2022-06-16 at 4 48 24 PM" src="https://user-images.githubusercontent.com/89602311/174171627-518aafde-9ea5-4dc8-980f-6802bcc746d3.png">
* An exact step count is usually unnecessary
  - Too dependent on programming languages and programmer’s style
  - Asymptotic approach
* Focus on the fundamental method
  - If the number of operations is proportional to n, then double n will double the running time
  - If the number of operations is proportional to 2^n, doubling n will square the number of operations
* f(n) = O(g(n)) means that the growth rate of f(n) is no more than the growth rate of g(n) (The growth of the evaluation function)
## Growth of Function 
* Common Order of Growth
* <img width="579" alt="Screen Shot 2022-06-16 at 4 50 23 PM" src="https://user-images.githubusercontent.com/89602311/174171831-698d8511-2f4d-4c63-a23a-0d86ee5d82a5.png">
* <img width="832" alt="Screen Shot 2022-06-16 at 4 56 51 PM" src="https://user-images.githubusercontent.com/89602311/174175519-59239017-d2a4-4a8b-88fa-8b18ca19f016.png">
* For most algorithm analysis, only a short list of functions is needed
  - 1 (constant), log n (logarithmic), n (linear), n2 (quadratic), n3 (cubic), 2^n (exponential)
  - They are in strictly increasing order of magnitude
* About nlogn
  - n log n has strictly greater order of magnitude than n
  - n log n has strictly smaller order of magnitude than any power n^r for any r > 1 (polynomial)
* <img width="411" alt="Screen Shot 2022-06-16 at 4 56 03 PM" src="https://user-images.githubusercontent.com/89602311/174174471-4b1fec1e-5237-4448-89d8-0e65e680fdfa.png">
* Big-O Rules for Polynomial
  - ignore a constant factor
    - n, 3n, and 4n have the same growth rate O(n)
  - ignore low-order terms
    - n^2 + n and n^2 have the same growth rate O(n^2)
* Example:
  - If f f(n) is a polynomial of degree d, then f(n) is O(n^d)
    - E.g. f(n) = 4n^5 + 8n^4 + 3n^2+ 12n + 30 = O(n^5)
    - Drop lower-order terms
    - Drop constant factors
* Big-O rules for logarithm 
  - The order of magnitude of a logarithm does not depend on the base for the logarithms, where a ≠ b
  - <img width="370" alt="Screen Shot 2022-06-16 at 5 14 24 PM" src="https://user-images.githubusercontent.com/89602311/174185576-9bf8d76c-b6f5-47a0-9607-ef9a79d1699d.png">
  - Since the base for logarithms makes no difference to the order-of-growth, we generally write log without a base
  - log n is asymptotically smaller than n^r for any r > 0 , i.e. log n = o(n^r). 
* Optional 
* L'Hopitals Rule
  - <img width="498" alt="Screen Shot 2022-06-16 at 5 15 44 PM" src="https://user-images.githubusercontent.com/89602311/174185710-822dbba0-61d6-4464-87fc-1fd747ba9b53.png">
* Use L'Hopitals rule
  - <img width="463" alt="Screen Shot 2022-06-16 at 5 16 25 PM" src="https://user-images.githubusercontent.com/89602311/174185775-3300a1c4-e0a3-4ac0-bb4c-049c1db4efb9.png">
  - log n has strictly smaller order of magnitude than any positive power n^r of n, r > 0.
* <img width="553" alt="Screen Shot 2022-06-16 at 5 17 17 PM" src="https://user-images.githubusercontent.com/89602311/174185885-fc441c4c-ba0d-41bf-9861-601c1a161839.png">
* <img width="491" alt="Screen Shot 2022-06-16 at 5 17 32 PM" src="https://user-images.githubusercontent.com/89602311/174185917-ceed65dc-f657-4ee6-b62c-9c9ac9143b07.png">
  - These notations are pronounced “Big Oh”, “Big Theta”, and “Big Omega”, respectively.
  - The big-O notation gives an upper bound on the growth rate of a function, which is our focus
* <img width="559" alt="Screen Shot 2022-06-16 at 5 18 05 PM" src="https://user-images.githubusercontent.com/89602311/174186124-4b2a4fb8-0eb1-4d59-bd0a-a6ddb86d7dce.png">

