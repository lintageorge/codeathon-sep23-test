# Program 4: Sort a linear Array

Write a program to sort the given array of numbers in ascending order. Return the sorted array. Initial array size will be a maximum of 500 elements.

### samples
Input | output
------|-------
[100,180,260,310,40,535,695] | [40,100,180,260,310,535,695]
[1,2,3,4,5,6,7,8,9,10] | [1,2,3,4,5,6,7,8,9,10]
[10,9,8,7,6,5,4,3,2,1] | [1,2,3,4,5,6,7,8,9,10]

### Tasks
- Develop the program using your choice of programming language
- Create test script covering all scenarios (min 5 test cases)
- varify the performance of the program for an array of 50000 elements
- Improve the performance of the program for an array of 50000 elements

def quick_sort(arr):
    if len(arr) <= 1:
        return arr

    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]

    return quick_sort(left) + middle + quick_sort(right)

# Example usage:
input_array = [12, 4, 5, 6, 7, 3, 1, 15, 2, 10]
sorted_array = quick_sort(input_array)
print(sorted_array)
