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

### 3. How do you return the word "example" from the following array?

```
arr = [["test", "hello", "world"],["example", "mem"]]
```

`arr.last.first` or `arr.last[0]` 

### 4. What does each method return in the following example?

```
arr = [15, 7, 18, 5, 12, 8, 5, 1]

1. arr.index(5)

2. arr.index[5]

3. arr[5]
```

1. 3 (this is the index of the number 5)
2. Enumerator
3. 8

### 5. What is the value of a, b, and c in the following program?

```
string = "Welcome to America!"
a = string[6]
b = string[11]
c = string[19]
```

a = "e"
b = "A"
c = nil

### 6. You run the following code...
```
names = ['bob', 'joe', 'susan', 'margaret']
names['margaret'] = 'jody'
```

...and get the following error message:

```
TypeError: no implicit conversion of String into Integer
  from (irb):2:in `[]='
  from (irb):2
  from /Users/username/.rvm/rubies/ruby-2.0.0-p353/bin/irb:12:in `<main>'
```
What is the problem and how can it be fixed?

Setting the value of an index with a string is not possible. Instead, use the numerical index to set the new value:
`names[3] = 'jody'`

### 7. Write a program that iterates over an array and builds a new array that is the result of incrementing each value in the original array by a value of 2. You should have two arrays at the end of this program, The original array and the new array you've created. Print both arrays to the screen using the p method instead of puts.

```
arr = [1, 2, 3]
new_arr = []

arr.each do |x|
   new_arr.push(x + 2)
end

p arr
p new_arr
```
