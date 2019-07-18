# Exercises

### 1. Below we have given you an array and a number. Write a program that checks to see if the number appears in the array.

```
arr = [1, 3, 5, 7, 9, 11]
number = 3
```

arr.include?(number)

### 2. What will the following programs return? What is value of arr after each?

```
1. arr = ["b", "a"]
   arr = arr.product(Array(1..3))
   arr.first.delete(arr.first.last)

2. arr = ["b", "a"]
   arr = arr.product([Array(1..3)])
   arr.first.delete(arr.first.last)
```

```
1. 
[["b", 1], ["b", 2], ["b", 3], ["a", 1], ["a", 2], ["a", 3]]
["b", 1] -> ["b"]
The program will return 1. The value of arr will be [["b"], ["b", 2], ["b", 3], ["a", 1], ["a", 2], ["a", 3]]

2. [["b", [1, 2, 3]], ["a", [1, 2, 3]]]
["b", [1, 3, 3]] -> ["b"]
The program will return [1,2,3]. The value of arr will be [["b"], ["a", [1, 2, 3]]]
```
