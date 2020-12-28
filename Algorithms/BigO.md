<img src="https://github.com/vaquarkhan/Notes-for-FAANG/blob/master/Algorithms/Resources/BigO1.PNG">



Big-O | Name | Description
------| ---- | -----------
**O(1)** | constant | **This is the best.** The algorithm always takes the same amount of time, regardless of how much data there is. Example: looking up an element of an array by its index.
**O(log n)** | logarithmic | **Pretty great.** These kinds of algorithms halve the amount of data with each iteration. If you have 100 items, it takes about 7 steps to find the answer. With 1,000 items, it takes 10 steps. And 1,000,000 items only take 20 steps. This is super fast even for large amounts of data. Example: binary search.
**O(n)** | linear | **Good performance.** If you have 100 items, this does 100 units of work. Doubling the number of items makes the algorithm take exactly twice as long (200 units of work). Example: sequential search.
**O(n log n)** | "linearithmic" | **Decent performance.** This is slightly worse than linear but not too bad. Example: the fastest general-purpose sorting algorithms.
**O(n^2)** | quadratic | **Kinda slow.** If you have 100 items, this does 100^2 = 10,000 units of work. Doubling the number of items makes it four times slower (because 2 squared equals 4). Example: algorithms using nested loops, such as insertion sort.
**O(n^3)** | cubic | **Poor performance.** If you have 100 items, this does 100^3 = 1,000,000 units of work. Doubling the input size makes it eight times slower. Example: matrix multiplication.
**O(2^n)** | exponential | **Very poor performance.** You want to avoid these kinds of algorithms, but sometimes you have no choice. Adding just one bit to the input doubles the running time. Example: traveling salesperson problem.
**O(n!)** | factorial | **Intolerably slow.** It literally takes a million years to do anything.  



<img  src="https://github.com/vaquarkhan/Notes-for-FAANG/blob/master/Algorithms/Resources/BigO2.PNG">


<img  src="https://github.com/vaquarkhan/Notes-for-FAANG/blob/master/Algorithms/Resources/BigO3.PNG">


### O(1)

       public boolean isFirstNumberEqualToOne(List&lt;Integer&gt; numbers) {
           return numbers.get(0) == 1;
        }

O(1) represents a function that always takes the same take regardless of input size.

### O(n)

     public boolean containsNumber(List&lt;Integer&gt; numbers, int comparisonNumber) {
        for(Integer number : numbers) {
          if(number == comparisonNumber) {
            return true;
          }
        }
        return false;
      }

O(n) represents the complexity of a function that increases linearly and in direct proportion to the number of inputs. This is a good example of how Big O Notation describes the worst case scenario as the function could return the true after reading the first element or false after reading all n elements.

### O(n2)

      public static boolean containsDuplicates(List&lt;String&gt; input) {
        for (int outer = 0; outer &lt; input.size(); outer++) {
          for (int inner = 0; inner &lt; input.size(); inner++) {
            if (outer != inner &amp;&amp; input.get(outer).equals(input.get(inner))) {
              return true;
            }
          }
        }
        return false;
      }

O(n2) represents a function whose complexity is directly proportional to the square of the input size. Adding more nested iterations through the input will increase the complexity which could then represent O(n3) with 3 total iterations and O(n4) with 4 total iterations.

### O(2n)

    public int fibonacci(int number) {
      if (number &lt;= 1) {
        return number;
      } else {
        return fibonacci(number - 1) + fibonacci(number - 2);
      }
    }

O(2n) represents a function whose performance doubles for every element in the input. This example is the recursive calculation of Fibonacci numbers. The function falls under O(2n) as the function recursively calls itself twice for each input number until the number is less than or equal to one.

### O(log n)
      public boolean containsNumber(List&lt;Integer&gt; numbers, int comparisonNumber) {
        int low = 0;
        int high = numbers.size() - 1;
        while (low &lt;= high) {
          int middle = low + (high - low) / 2;
          if (comparisonNumber &lt; numbers.get(middle)) {
            high = middle - 1;
          } else if (comparisonNumber &gt; numbers.get(middle)) {
            low = middle + 1;
          } else {
           return true;
          }
        }
        return false;
      }

O(log n) represents a function whose complexity increases logarithmically as the input size increases. This makes O(log n) functions scale very well so that the handling of larger inputs is much less likely to cause performance problems.



<img src="https://github.com/vaquarkhan/Notes-for-FAANG/blob/master/Algorithms/Resources/BigO4.png">


- https://www.bigocheatsheet.com/
- https://github.com/raywenderlich/swift-algorithm-club/edit/master/Big-O%20Notation.markdown
- https://dzone.com/articles/learning-big-o-notation-with-on-complexity
