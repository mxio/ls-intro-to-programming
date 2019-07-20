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
puts hash_one

# outputs: {1=>"a", 2=>"b", 3=>"c"}
```
hash_one remains unchanged. `hash_one.merge(hash_two)` evaluates to `{1=>"d", 2=>"b", 3=>"c", 4=>"e"}`.

```
hash_one = {1 => "a", 2 => "b", 3 => "c"}
hash_two = {1 => "d", 4 => "e"}

hash_one.merge!(hash_two)
puts hash_one
```

Using `merge!`, the `merge!` expression returns `{1=>"d", 2=>"b", 3=>"c", 4=>"e"}` and hash_one is updated to `{1=>"d", 2=>"b", 3=>"c", 4=>"e"}`.

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
