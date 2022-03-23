### BigO-Notation
> a way to estimate the efficiency of a program and the time taken to execute it
- an algorithm has the time complexity O(f(n)) if its number of operations grows bigger similar to (or slower than) the function f(n) when the input size n is a large number.
- it describes the upper bound for the function's growth rate.


### Input size
> is the measure of the size of input data
- the running time of an algorithm depends on the input data


### Common growth rates
+ O(1) (constant time). The algorithm performs a constant number of operations. Maybe one, two, twenty-six, or two hundred – it doesn't matter. What is important is that it doesn't depend on the input size. Typical algorithms of this class include calculating the answer using a direct formula, printing a couple of values, all letters of the English alphabet, etc.
+ O(n) (linear time). The time is proportional to the input size, i.e., the time grows linearly as the input size increases. Often, such algorithms are iterated only once. They occur quite frequently, because it is usually necessary to go through every input element before calculating the final answer. This makes the O(n)O(n) class one of the most effective classes in practice.
+ O(2^n) (exponential time). Just in case, let's mention that 2^n is the same as multiplying 22 by itself nn times. Again, maths states that the number of subsets of a set of nn elements is equal to 2^n, therefore, it is reasonable to expect that such algorithms scan all the subsets of the input elements. It is worth noting that this class is extremely inefficient in practice; even for small input sizes, the time taken by the algorithm will be remarkably high.
+ O(n^2) (quadratic time). Normally, such algorithms go through all pairs of input elements. Why? Well, mathematics is generous, it constantly provides us with important results: in this case, basic maths confirms that the number of unordered pairs in a set of nn elements is equal to \frac{n(n-1)}{2} 
2n(n−1), which, as we will learn later in this topic, is O(n^2). Quadratic time algorithms usually contain two nested loops.
+ O(log n) (logarithmic time). Perhaps a quick reminder on logarithms is necessary. We usually refer to logarithms of base 2; however, the base does not affect the class. By definition, \log_2n equals the number of times nn must be divided by 22 to get 11. That being said, it should not be difficult to guess that such algorithms divide the input size into halves at each step. They are relatively fast: if the size of the input is huge, say, 2^31
31 (programmers should know the importance of this number), the algorithm will perform approximately \log_2(2^{31}) = 31log
2(2 31)=31 operations, which is pretty effective.

#### less common complexity class
+ O(n) (square root time);
+ O(n log n) (log-linear time);
+ O(n^k) (polynomial time);
+ O(n!) (factorial time).
