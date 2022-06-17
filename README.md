# Time Complexity and Tree 1
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
## Self Test
* Get the big-) of the follows:
  - ```
    for (i = 0; i < n; i++)
      for (j = 0; j<n; j++)
         k++
    ```
  - O(n^2)
  - ```
    int x = 0;
    for (int i = 0; i < n*n; i++)
      x += i;
    ```
  - O(n^2)
  - ```
    int x = 0;
    for (int i = 1; i < n; i++)
      for (int j = i; j< 100; j++)
         x += i + j;
    ```
  - O(n)
  - ```
    int x = 0;
    for (int i = 1; i < n * n; i++)
      for (int j = 1; j < i; j++)
        x += i + j;
    ```
  - O(n^4)
  - ```
    int i = 0, j = 0;
    for (; i < n; i++)
      while (j < n && arr[i] < arr[j])
        j++
    ```
  - O(n)
## Time Complexity on Recursion
* Recursively call the same function
  - Solve the subproblems
    - The size of the input will be reduced
  - Merge the results from subproblem
* Example: factorial
  - <img width="539" alt="Screen Shot 2022-06-16 at 6 16 58 PM" src="https://user-images.githubusercontent.com/89602311/174193514-cbcd3eb7-8d40-46ab-b40e-46a54b68a75f.png">
  - the time complexity of factorial(n) is: 
  - <img width="314" alt="Screen Shot 2022-06-16 at 6 17 36 PM" src="https://user-images.githubusercontent.com/89602311/174193568-28fb774c-a8e7-41d9-8f94-57eab2fb36a8.png">
  - T(n) is an arithmetic sequence with the common difference 4 of successive members and T(0) equals 2
  - <img width="312" alt="Screen Shot 2022-06-16 at 6 17 59 PM" src="https://user-images.githubusercontent.com/89602311/174193594-b4c504bf-1578-4a3b-a07d-b7df6b28622a.png">
  - The time complexity of factorial is O(n)
* Example: fibonacci number
  - <img width="476" alt="Screen Shot 2022-06-16 at 6 19 11 PM" src="https://user-images.githubusercontent.com/89602311/174193700-43093a5f-1588-4a61-b700-2b3798ba86a8.png">
  - <img width="536" alt="Screen Shot 2022-06-16 at 6 19 30 PM" src="https://user-images.githubusercontent.com/89602311/174193720-7381318e-41c2-4c3e-bdb3-1f516aa1a586.png">
  - <img width="556" alt="Screen Shot 2022-06-16 at 6 19 45 PM" src="https://user-images.githubusercontent.com/89602311/174193750-8523a334-27f0-4589-a261-cb40f9c09816.png">
## Tree Terms
* Binary Tree: a tree in which a node has at most two children
* Full binary tree: a binary tree of heigh h every node other than the leaf nodes has two child nodes
* Complete binary tree: a binary tree of height h that is full to level h-1 and has the level h filled in from left to right
* Binary Search tree: a binary tree with a key ordering property that supports search of a key
* Balanced binary tree: in next CS class
## Binary Tree
* Definition
  - Recursive definiton:
    - Basic step: root (parent node)
    - Recursive step: two optional subtrees (child nodes: root.left, root.right)
* Implementation
  - Linked implementation is natural
  - Other implementation is also possible
  - <img width="595" alt="Screen Shot 2022-06-16 at 6 40 55 PM" src="https://user-images.githubusercontent.com/89602311/174195510-45b74aae-1e9c-4843-b56b-957d910967bb.png">




