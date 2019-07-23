# Exercises

### 1. Given a hash of family members, with keys as the title and an array of names as the values, use Ruby's built-in select method to gather only immediate family members' names into a new array.

```
# Given

family = {  uncles: ["bob", "joe", "steve"],
            sisters: ["jane", "jill", "beth"],
            brothers: ["frank","rob","david"],
            aunts: ["mary","sally","susan"]
          }
```          

```
# make sure to create new array per the question
new_arr = family.select do |key, value| 
  key == sisters || key == brothers }
end

new_arr.flatten
puts new_arr
```

### 2. Look at Ruby's merge method. Notice that it has two versions. What is the difference between merge and merge!? Write a program that uses both and illustrate the differences.

`merge` returns a new hash whereas `merge!` replaces the values of duplicate keys in the hash with the other hash. 
Using `merge`:
```
hash_one = {1 => "a", 2 => "b", 3 => "c"}
hash_two = {1 => "d", 4 => "e"}

hash_one.merge(hash_two)
# {1=>"d", 2=>"b", 3=>"c", 4=>"e"}
puts hash_one
# {1=>"a", 2=>"b", 3=>"c"}
```


```
hash_one = {1 => "a", 2 => "b", 3 => "c"}
hash_two = {1 => "d", 4 => "e"}

hash_one.merge!(hash_two)
# {1=>"d", 2=>"b", 3=>"c", 4=>"e"}
puts hash_one
# {1=>"d", 2=>"b", 3=>"c", 4=>"e"}
```

### 3. Using some of Ruby's built-in Hash methods, write a program that loops through a hash and prints all of the keys. Then write a program that does the same thing except printing the values. Finally, write a program that prints both.

Loops through and prints all the keys
```
letter_hash = {1 => "a", 2 => "b", 3 => "c"}

letter_hash.each_key do |key|
  puts key
end
```

Loops through and prints all the keys 
```
letter_hash = {1 => "a", 2 => "b", 3 => "c"}

letter_hash.each_value do |value|
  puts value
end
```

Prints both keys and values
```
letter_hash = {1 => "a", 2 => "b", 3 => "c"}

letter_hash.each_pair do |key, value|
  puts "#{key}: #{value}"
end
```

### 4. Given the following expression, how would you access the name of the person?

`person = {name: 'Bob', occupation: 'web developer', hobbies: 'painting'`

person[:name]

### 5. What method could you use to find out if a Hash contains a specific value in it? Write a program to demonstrate this use.
You can use the `has_value?` method

```
letter_hash = {1 => "a", 2 => "b", 3 => "c"}

letter_hash.has_value?("c")
```

### 6. Given the array...
```
words =  ['demo', 'none', 'tied', 'evil', 'dome', 'mode', 'live',
          'fowl', 'veil', 'wolf', 'diet', 'vile', 'edit', 'tide',
          'flow', 'neon']
```

Write a program that prints out groups of words that are anagrams. Anagrams are words that have the same exact letters in them but in a different order. Your output should look something like this:

```
["demo", "dome", "mode"]
["neon", "none"]
(etc)
```

Solution
```
result = {}

words.each do |word|
  key = word.split('').sort.join
  # if there is already the key, then push the word into the array (this step happens after the else block)
  if result.has_key?(key)
    result[key].push(word)
  else
    # if there is no key yet, the key will have an array with the word in it, then when there is a key, the above statement will run
    result[key] = [word]
  end
end

result.each_value do |v|
  puts "------"
  p v
end
```

### 7. Given the following code...
```
x = "hi there"
my_hash = {x: "some value"}
my_hash2 = {x => "some value"}
```

my_hash uses a symbol for for the x key whereas my_hash2 uses the x variable as the key which stores the string "hi there".

### 8. If you see this error, what do you suspect is the most likely problem?

`NoMethodError: undefined method `keys' for Array`

A. We're missing keys in an array variable.
B. There is no method called keys for Array objects.
C. keys is an Array object, but it hasn't been defined yet.
D. There's an array of strings, and we're trying to get the string keys out of the array, but it doesn't exist.

My answer: B. There is no method called keys for Array objects.
