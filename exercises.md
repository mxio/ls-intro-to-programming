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
A few sources I like other than the official documentation for Ruby are https://apidock.com and https://rubydocs.org/.

On https://rubydocs.org/, I can easily select from a dropdown of documentation for various versions for Ruby. Then I can find or search for methods or classes on the left sidebar. The documentation page for a method shows what the method returns, for example: `str.downcase → new_str`. This shows that downcase returns a new string, which is really helpful in understanding your code.

Both apidock.com and rubydocs.org shows an example of how a method is used.

### 12. Given the following data structures. Write a program that moves the information from the array into the empty hash that applies to the correct person.

```
contact_data = [["joe@email.com", "123 Main st.", "555-123-4567"],
            ["sally@email.com", "404 Not Found Dr.", "123-234-3454"]]

contacts = {"Joe Smith" => {}, "Sally Johnson" => {}}

contacts["Joe Smith"][:email] = contact_data[0][0]
contacts["Joe Smith"][:address] = contact_data[0][1]
contacts["Joe Smith"][:phone] = contact_data[0][2]
contacts["Sally Johnson"][:email] = contact_data[1][0]
contacts["Sally Johnson"][:address] = contact_data[1][1]
contacts["Sally Johnson"][:phone] = contact_data[1][2]

contacts
```

### 13. Using the hash you created from the previous exercise, demonstrate how you would access Joe's email and Sally's phone number?

```
# Joe's email
contacts["Joe Smith"][:email]

# Sally's phone number
contacts["Sally Johnson"][:phone]
```

### 14. In exercise 12, we manually set the contacts hash values one by one. Now, programmatically loop or iterate over the contacts hash from exercise 12, and populate the associated data from the contact_data array. Hint: you will probably need to iterate over ([:email, :address, :phone]), and some helpful methods might be the Array shift and first methods.

Note that this exercise is only concerned with dealing with 1 entry in the contacts hash, like this:

```
contact_data = ["joe@email.com", "123 Main st.", "555-123-4567"]
contacts = {"Joe Smith" => {}}
```

```
contact_data = ["joe@email.com", "123 Main st.", "555-123-4567"]
contacts = {"Joe Smith" => {}}

def move_data(arr, hash)
  keys = [:email, :address, :phone]

  # first, put the keys into the empty hash, then assign array values to the keys

  # using [keys[index]] in the iterator creates each of the keys in the empty object
  keys.each_with_index do |val, index|
    hash["Joe Smith"][keys[index]] = arr[index]
  end

  hash
end

move_data(contact_data, contacts)
```

### 15. Use Ruby's Array method delete_if and String method start_with? to delete all of the words that begin with an "s" in the following array.

```
arr = ['snow', 'winter', 'ice', 'slippery', 'salted roads', 'white trees']
```

Then recreate the arr and get rid of all of the words that start with "s" or starts with "w".


Removing words beginning with "s":
```
arr = ['snow', 'winter', 'ice', 'slippery', 'salted roads', 'white trees']

arr.delete_if {|val| val.start_with?("s")}
```

Removing words beginning with "s" or "w":
```
arr = ['snow', 'winter', 'ice', 'slippery', 'salted roads', 'white trees']

arr.delete_if {|val| val.start_with?("s") || val.start_with?("w")}

# simpler answer
arr.delete_if { |word| word.start_with?("s", "w") }
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
It will output: "These hashes are the same!"
