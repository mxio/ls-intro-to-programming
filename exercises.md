# Exercises

### 1. Use the each method of Array to iterate over [1, 2, 3, 4, 5, 6, 7, 8, 9, 10], and print out each value.

```
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

arr.each do |x|
  puts x
end
```

### 2. Same as above, but only print out values greater than 5.
```
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

arr.each do |x|
  if x > 5
    puts x
  end
end
```

### 3. Now, using the same array from #2, use the select method to extract all odd numbers into a new array.
```
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
new_arr = []

arr.select do |x|
  # Don't need a conditional if statement, the expression will return only values in the new array that meets the requirement
  x % 2 != 0
end

#Simpler given solution 
new_array = arr.select do |number|
  number % 2 != 0
end
```

### 4. Append 11 to the end of the original array. Prepend 0 to the beginning.
```
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

arr.push(11)
arr.unshift(0)
```

### 5. Get rid of 11. And append a 3.
```
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

arr.push(11)
arr.unshift(0)

# Remove 11. Don't need to add the 11 in parenthesis. arr.pop returns 11 but removes the last item from the array already
arr.pop

# Append a 3
arr.push(3)
```

### 6. Get rid of duplicates without specifically removing any one value.

```
arr.uniq
```

### 7. What's the major difference between an Array and a Hash?
An array holds values at indexes whereas a hash holds key-value pairs.

### 8. Create a Hash using both Ruby syntax styles.
```
first_hash = {:a => 1}
second_hash = {a: 1}
```

### 9. Suppose you have a hash `h = {a:1, b:2, c:3, d:4}`
```
1. Get the value of key `:b`.
h[:b]

2. Add to this hash the key:value pair `{e:5}`
h[:e] = 5

3. Remove all key:value pairs whose value is less than 3.5
h.delete_if do |key, value|
  value < 3.5
end
```

### 10. Can hash values be arrays? Can you have an array of hashes? (give examples)
Yes, hash values can be arrays
```
hash = {
  a: 1,
  b: 2,
  c: [1, 2, 3]
}

hash[:c]
```
Arrays can have hashes too.
```
arr = [{a: 1, b: 2}, {c: 3, d: 4}]
```

### 11. Look at several Rails/Ruby online API sources and say which one you like best and why.

### 12. Given the following data structures. Write a program that moves the information from the array into the empty hash that applies to the correct person.

### 13. Using the hash you created from the previous exercise, demonstrate how you would access Joe's email and Sally's phone number?

### 14. In exercise 12, we manually set the contacts hash values one by one. Now, programmatically loop or iterate over the contacts hash from exercise 12, and populate the associated data from the contact_data array. Hint: you will probably need to iterate over ([:email, :address, :phone]), and some helpful methods might be the Array shift and first methods.

Note that this exercise is only concerned with dealing with 1 entry in the contacts hash, like this:

```
contact_data = ["joe@email.com", "123 Main st.", "555-123-4567"]
contacts = {"Joe Smith" => {}}
```

### 15. Use Ruby's Array method delete_if and String method start_with? to delete all of the words that begin with an "s" in the following array.

```
arr = ['snow', 'winter', 'ice', 'slippery', 'salted roads', 'white trees']
```

### 16. Take the following array:
```
a = ['white snow', 'winter wonderland', 'melting ice',
     'slippery sidewalk', 'salted roads', 'white trees']
```

and turn it into a new array that consists of strings containing one word. (ex. ["white snow", etc...] → ["white", "snow", etc...]. Look into using Array's map and flatten methods, as well as String's split method.

### 17. What will the following program output?
```
hash1 = {shoes: "nike", "hat" => "adidas", :hoodie => true}
hash2 = {"hat" => "adidas", :shoes => "nike", hoodie: true}

if hash1 == hash2
  puts "These hashes are the same!"
else
  puts "These hashes are not the same!"
end
```
