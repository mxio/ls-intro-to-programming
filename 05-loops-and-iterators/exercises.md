# Exercises

### 1. What does the each method in the following program return after it is finished executing?

```
x = [1, 2, 3, 4, 5]
x.each do |a|
  a + 1
end
```
[1, 2, 3, 4, 5]

### 2. Write a while loop that takes input from the user, performs an action, and only stops when the user types "STOP". Each loop can get info from the user.

```
input = ""

while input != "STOP"
  puts "Enter anything"
  input = gets.chomp
 end
```

### 3. Use the each_with_index method to iterate through an array of your creation that prints each index and value of the array.

```
arr = ["bee", "mouse", "cat", "dog"]
arr.each_with_index do |animal, index|
  puts "#{index}: #{animal}"
  index += 1
end
```

### 4. Write a method that counts down to zero using recursion.
```
def countdown(num)
  if num <= 0
    puts num
  else 
    puts num
    countdown(num - 1)
  end
end
```
