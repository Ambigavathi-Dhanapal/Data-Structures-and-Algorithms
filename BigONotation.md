## Understanding Big-O Notations:</h2>
Understanding Big-O Notation is crucial for developers because it helps them write efficient code, optimize algorithms, and understand the potential bottlenecks in their applications as data grows. In this post, we'll break down different Big-O complexities with easy-to-understand examples.

<div class="separator" style="clear: both; text-align: center; padding: 1em 0;">
    <a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhZ90cIKfVcywRb5Wg4R4XHdWwAdC4w0ZtPLLPbEDvMQ0KrKkZC4UH1MMinTupz44gXpIQdEWXk5kBE1Jz8Z0p4enNhSrrCbkgyjx0OVplLvQSqURYgCKhDD21tJRMi8TPiHoGnpXhQeiwxSuQUbO-A13-itOfhfek_AdeGlclXpUGB1386gl49IVBhtlw/s1400/Bigonotation1.png" style="display: block;">
        <img alt="Big O Notation Example" border="0" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhZ90cIKfVcywRb5Wg4R4XHdWwAdC4w0ZtPLLPbEDvMQ0KrKkZC4UH1MMinTupz44gXpIQdEWXk5kBE1Jz8Z0p4enNhSrrCbkgyjx0OVplLvQSqURYgCKhDD21tJRMi8TPiHoGnpXhQeiwxSuQUbO-A13-itOfhfek_AdeGlclXpUGB1386gl49IVBhtlw/s1400/Bigonotation1.png" style="width: 100%; max-width: 800px; height: auto;" />
    </a>
</div>

## Why is Big-O Important?</h2>

- Predict Performance: It shows how an algorithm will perform as the input size grows.
- Optimize Code: Identifies areas where you can make algorithms more efficient.
- Compare Algorithms: Helps in choosing the best approach for a problem.           

## Different Big-O Notations
Here are the types of Big-O notations:</p>
* O(1) - Constant Time</li>
* O(log n) - Logarithmic Time</li>
* O(n) - Linear Time</li>
* O(n log n) - Linearithmic Time</li>
* O(n²) - Quadratic Time</li>
* O(n³) - Cubic Time</li>
* O(2ⁿ) - Exponential Time</li>
* O(n!) - Factorial Time</li>



### 1. O(1) - Constant Time

- An algorithm runs in constant time if it takes the same amount of time to execute regardless of the input size.
```python
import time
import sys
# Example: Function to get the first element of a list
def get_first_element(arr):
    return arr[0]
# Analyze performance (time and space complexity)
def analyze_performance():
    arr = [1, 2, 3, 4, 5]
    start_time = time.time()
    result = get_first_element(arr)
    end_time = time.time()
    time_taken = end_time - start_time
    space_taken = sys.getsizeof(arr) + sys.getsizeof(result)
    print("Time Complexity: O(1)")
    print("Space Complexity: O(1)")
    print(f"Time taken: {time_taken:.6f} seconds")
    print(f"Approximate space taken: {space_taken} bytes")
analyze_performance()
# Expected Output:
# Time Complexity: O(1)
# Space Complexity: O(1)
# Time taken: 0.000000 seconds (varies depending on system and input size)
# Approximate space taken: 148 bytes (varies depending on system and input size)
```
- Accessing the first element of a list takes the same amount of time, no matter the size of the list.
- Time Taken: Instant (~0 seconds) | Space Taken: 148 bytes.


### 2. O(log n) - Logarithmic Time

- An algorithm runs in logarithmic time if it reduces the problem size by half with each step. This is common in divide-and-conquer algorithms like binary search.
```python
import time
import sys
# Example: Binary search on a sorted list
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
# Calculate time and space complexity
def analyze_binary_search_performance():
    arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    target = 7
    # Measure time taken
    start_time = time.time()
    result = binary_search(arr, target)
    end_time = time.time()
    time_taken = end_time - start_time
    # Measure space taken
    space_taken = sys.getsizeof(arr) + sys.getsizeof(result)
    # Output results
    print("Time Complexity: O(log n)")
    print("Space Complexity: O(1)")
    print(f"Time taken: {time_taken:.6f} seconds")
    print(f"Approximate space taken: {space_taken} bytes")
# Run the performance analysis
analyze_binary_search_performance()
# Expected Output:
# Time Complexity: O(log n)
# Space Complexity: O(1)
# Time taken: 0.000001 seconds
# Approximate space taken: 180 bytes
```

- Efficiently halves the problem size at each step.
- Time Taken: Very fast (~0.000001 seconds) | Space Taken: 180 bytes.

### 3. O(n) - Linear Time
-  An algorithm runs in linear time if its runtime increases linearly with the size of the input. 

```python
import time
import sys
# Example: Finding the maximum element in a list
def find_max(arr):
    max_value = arr[0]
    for num in arr:
        if num > max_value:
            max_value = num
    return max_value
# Analyze performance (time and space complexity)
def analyze_performance():
    arr = [1, 3, 5, 2, 8, 4]
    start_time = time.time()
    result = find_max(arr)
    end_time = time.time()
    time_taken = end_time - start_time
    space_taken = sys.getsizeof(arr) + sys.getsizeof(result)
    print("Time Complexity: O(n)")
    print("Space Complexity: O(1)")
    print(f"Time taken: {time_taken:.6f} seconds")
    print(f"Approximate space taken: {space_taken} bytes")
analyze_performance()
# Expected Output:
# Time Complexity: O(n)
# Space Complexity: O(1)
# Time taken: 0.000001 seconds (varies depending on system and input size)
# Approximate space taken: 180 bytes (varies depending on system and input size)
```

- The function iterates through the entire list once, resulting in a linear time complexity of O(n).
- Scales proportionally with input size.
- Time Taken: Quick (~0.000001 seconds) | Space Taken: 180 bytes.


### 4. O(n log n) - Linearithmic Time

- This time complexity is typical for efficient sorting algorithms like mergesort and quicksort, which divide the problem and solve each part.

```python
import time
import sys
# Example: Merge sort algorithm
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)
def merge(left, right):
    result = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    result.extend(left[i:])
    result.extend(right[j:])
    return result
# Analyze performance (time and space complexity)
def analyze_performance():
    arr = [5, 3, 8, 4, 2, 7, 1, 6]
    start_time = time.time()
    result = merge_sort(arr)
    end_time = time.time()
    time_taken = end_time - start_time
    space_taken = sys.getsizeof(arr) + sys.getsizeof(result)
    print("Time Complexity: O(n log n)")
    print("Space Complexity: O(n)")
    print(f"Time taken: {time_taken:.6f} seconds")
    print(f"Approximate space taken: {space_taken} bytes")
analyze_performance()
# Expected Output:
# Time Complexity: O(n log n)
# Space Complexity: O(n)
# Time taken: 0.000010 seconds (varies depending on system and input size)
# Approximate space taken: 240 bytes (varies depending on system and input size)
```

- The array is repeatedly divided in half (log n), and each half is merged in linear time (n), resulting in O(n log n).
- Common in sorting algorithms; more complex than linear.
- Time Taken: Moderate (~0.000010 seconds) | Space Taken: 240 bytes.

### 5. O(n²) - Quadratic Time

- An algorithm runs in quadratic time if it uses nested loops over the input data. This is common in basic sorting algorithms like bubble sort.
```python
import time
import sys
# Example: Bubble sort
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
# Analyze performance (time and space complexity)
def analyze_performance():
    arr = [5, 3, 8, 4, 2, 7, 1, 6]
    start_time = time.time()
    bubble_sort(arr)
    end_time = time.time()
    time_taken = end_time - start_time
    space_taken = sys.getsizeof(arr)
    print("Time Complexity: O(n²)")
    print("Space Complexity: O(1)")
    print(f"Time taken: {time_taken:.6f} seconds")
    print(f"Approximate space taken: {space_taken} bytes")
analyze_performance()
# Expected Output:
# Time Complexity: O(n²)
# Space Complexity: O(1)
# Time taken: 0.000010 seconds (varies depending on system and input size)
# Approximate space taken: 120 bytes (varies depending on system and input size)
```

- The function compares each pair of elements in the array, leading to O(n²) complexity due to the nested loops.
- Increases rapidly with nested loops.
- Time Taken: Slower (~0.00010 seconds) | Space Taken: 120 bytes.


### 6. O(n³) - Cubic Time

- Algorithms with three nested loops run in cubic time. This is rare but can occur in some brute-force algorithms, such as matrix multiplication.
```python
import time
import sys
# Example: Matrix multiplication
def matrix_multiply(A, B):
    n = len(A)
    result = [[0] * n for _ in range(n)]
    for i in range(n):
        for j in range(n):
            for k in range(n):
                result[i][j] += A[i][k] * B[k][j]
    return result
# Analyze performance (time and space complexity)
def analyze_performance():
    A = [[1, 2], [3, 4]]
    B = [[5, 6], [7, 8]]
    start_time = time.time()
    result = matrix_multiply(A, B)
    end_time = time.time()
    time_taken = end_time - start_time
    space_taken = sys.getsizeof(A) + sys.getsizeof(B) + sys.getsizeof(result)
    print("Time Complexity: O(n³)")
    print("Space Complexity: O(n²)")
    print(f"Time taken: {time_taken:.6f} seconds")
    print(f"Approximate space taken: {space_taken} bytes")
analyze_performance()
# Expected Output:
# Time Complexity: O(n³)
# Space Complexity: O(n²)
# Time taken: 0.000007 seconds (varies depending on system and input size)
# Approximate space taken: 232 bytes (varies depending on system and input size)
```

- The algorithm has three nested loops for matrix multiplication, leading to O(n³) time complexity.
- Slower than quadratic; typical in triple nested loops.
- Time Taken: Noticeably slower (~0.000007 seconds) | Space Taken: 232 bytes.
 
### 7. O(2ⁿ) - Exponential Time
- An algorithm runs in exponential time if it doubles in runtime with each additional element in the input. This is common in recursive algorithms that solve subproblems repeatedly, like the naive recursive Fibonacci sequence.
```python
import time
import sys
# Example: Recursive Fibonacci sequence
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)
# Analyze performance (time and space complexity)
def analyze_performance():
    n = 10  # You can change this value to test with different inputs
    start_time = time.time()
    result = fibonacci(n)
    end_time = time.time()
    time_taken = end_time - start_time
    space_taken = sys.getsizeof(n) + sys.getsizeof(result)
    print("Time Complexity: O(2^n)")
    print("Space Complexity: O(n)")
    print(f"Time taken: {time_taken:.6f} seconds")
    print(f"Approximate space taken: {space_taken} bytes")
analyze_performance()
# Expected Output:
# Time Complexity: O(2^n)
# Space Complexity: O(n)
# Time taken: 0.000017 seconds (varies depending on system and n)
# Approximate space taken: 56 bytes (varies depending on system and n)
```

- Each call to fibonacci makes two additional recursive calls, leading to an exponential growth of 2ⁿ.
- Doubles time with each input, impractical for large sizes.
- Time Taken: Slow (~0.000017 seconds) | Space Taken: 56 bytes.

### 8. O(n!) - Factorial Time

- An algorithm with factorial time complexity tries all possible ways to solve a problem. This is typical for algorithms that generate permutations or combinations.
```python
import time
import sys
# Example: Generating all permutations of a list
def permutations(arr):
    if len(arr) == 0:
        return [[]]
    result = []
    for i, num in enumerate(arr):
        rest = arr[:i] + arr[i+1:]
        for p in permutations(rest):
            result.append([num] + p)
    return result
# Analyze performance (time and space complexity)
def analyze_performance():
    arr = [1, 2, 3]
    start_time = time.time()
    result = permutations(arr)
    end_time = time.time()
    time_taken = end_time - start_time
    space_taken = sys.getsizeof(arr) + sys.getsizeof(result)
    print("Time Complexity: O(n!)")
    print("Space Complexity: O(n!)")
    print(f"Time taken: {time_taken:.6f} seconds")
    print(f"Approximate space taken: {space_taken} bytes")
# Run performance analysis
analyze_performance()
# Expected Output:
# Time Complexity: O(n!)
# Space Complexity: O(n!)
# Time taken: 0.000013 seconds (varies based on system and input size)
# Approximate space taken: 240 bytes (varies based on system and input size)
```

- The function generates all permutations of the list, leading to O(n!) complexity due to the recursive calls and list construction.
- Extremely slow, as it explores all possibilities.
- Time Taken: Very slow (~0.000013 seconds) | Space Taken: 240 bytes.

## Comparision

<div class="separator" style="clear: both; text-align: center; padding: 1em 0;">
    <a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh0lf4B3MqmBlgNdBZlYakuoFTDsrtWeZMbsIvgKv59k9MeJmlZUvM1T2VjNo-VVcdZSE5_krEEDEmUxOvVD_nzHd6wLyn-3veFryKBn57atE4b1fgAo9PAbG2VzWFUuOTLJns0pPQdJCR_pMHfy76bAhNrdA3mhMSipqPCp-ke3dOqkpb7wzn6yrVsSpY/s1568/BigONotation-Comparision.png" style="display: block;">
        <img alt="Big O Notation Comparison" border="0" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh0lf4B3MqmBlgNdBZlYakuoFTDsrtWeZMbsIvgKv59k9MeJmlZUvM1T2VjNo-VVcdZSE5_krEEDEmUxOvVD_nzHd6wLyn-3veFryKBn57atE4b1fgAo9PAbG2VzWFUuOTLJns0pPQdJCR_pMHfy76bAhNrdA3mhMSipqPCp-ke3dOqkpb7wzn6yrVsSpY/s1568/BigONotation-Comparision.png" style="width: 100%; max-width: 800px; height: auto;" />
    </a>
</div>

<table border="1" style="width: 100%; border-collapse: collapse; text-align: left;">
    <thead>
        <tr>
            <th>#</th>
            <th>Notation</th>
            <th>Name</th>
            <th>Example</th>
            <th>Time Taken (Approx.)</th>
            <th>Space Taken (Approx.)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>O(1)</td>
            <td>Constant Time</td>
            <td>Accessing an element in a list</td>
            <td>~0.000000 seconds</td>
            <td>~148 bytes</td>
        </tr>
        <tr>
            <td>2</td>
            <td>O(log n)</td>
            <td>Logarithmic Time</td>
            <td>Binary search</td>
            <td>~0.000001 seconds</td>
            <td>~180 bytes</td>
        </tr>
        <tr>
            <td>3</td>
            <td>O(n)</td>
            <td>Linear Time</td>
            <td>Finding the max element in a list</td>
            <td>~0.000001 seconds</td>
            <td>~180 bytes</td>
        </tr>
        <tr>
            <td>4</td>
            <td>O(n log n)</td>
            <td>Linearithmic Time</td>
            <td>Merge sort</td>
            <td>~0.000010 seconds</td>
            <td>~240 bytes</td>
        </tr>
        <tr>
            <td>5</td>
            <td>O(n²)</td>
            <td>Quadratic Time</td>
            <td>Bubble sort</td>
            <td>~0.00010 seconds</td>
            <td>~120 bytes</td>
        </tr>
        <tr>
            <td>6</td>
            <td>O(n³)</td>
            <td>Cubic Time</td>
            <td>Matrix multiplication</td>
            <td>~0.000007 seconds</td>
            <td>~232 bytes</td>
        </tr>
        <tr>
            <td>7</td>
            <td>O(2ⁿ)</td>
            <td>Exponential Time</td>
            <td>Recursive Fibonacci sequence</td>
            <td>~0.000017 seconds</td>
            <td>56 bytes</td>
        </tr>
        <tr>
            <td>8</td>
            <td>O(n!)</td>
            <td>Factorial Time</td>
            <td>Generating all permutations of a list</td>
            <td>~0.000013 seconds</td>
            <td>240 bytes</td>
        </tr>
    </tbody>
</table>


</br>


## Summary

#### Efficient Algorithms: 
- O(1), O(log n), and O(n) are ideal for large datasets, offering quick runtimes and minimal memory usage.

#### Moderately Efficient: 
- O(n log n) is efficient for sorting algorithms, striking a balance with moderate time and space requirements.

#### Inefficient Algorithms: 
- O(n²), O(n³), O(2ⁿ), and O(n!) become impractical as input sizes grow, as they consume significant time and memory, making them suitable only for small datasets.

By understanding and choosing the right algorithm based on complexity, you can optimize your code for better performance and scalability. Practice analyzing and implementing various algorithms to gain a deeper understanding of how they behave with different input sizes.


[![GitHub Repo](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/Ambigavathi-Dhanapal/Data-Structures-and-Algorithms) [![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://github.com/Ambigavathi-Dhanapal/Data-Structures-and-Algorithms/blob/main/BigONotation.ipynb) 	 [![Blog](https://img.shields.io/badge/Blog-Visit-brightgreen)](https://learntocodewithambiga.blogspot.com/2024/10/big-o-notation-complete-guide.html)


<p>If you have any questions or want to share your experiences, feel free to comment below. I’d love to hear your thoughts!</p>


