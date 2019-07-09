# Exercises

### 1. Write a program called name.rb that asks the user to type in their name and then prints out a greeting message with their name included.

// inside name.rb
puts "Enter your name"
name = gets.chomp
puts "Hello " + name

### 2. Write a program called age.rb that asks a user how old they are and then tells them how old they will be in 10, 20, 30 and 40 years. Below is the output for someone 20 years old.

// inside age.rb
puts "How old are you?"
current_age = gets.chomp.to_i

puts "In 10 years you will be:"
puts current_age + 10

puts "In 20 years you will be:"
puts current_age + 10

puts "In 30 years you will be:"
puts current_age + 10

puts "In 40 years you will be:"
puts current_age + 10

### 3. Add another section onto name.rb that prints the name of the user 10 times. You must do this without explicitly writing the puts method 10 times in a row. Hint: you can use the times method to do something repeatedly.

puts "Enter your name"  
name = gets.chomp  

10.times do
    puts name  
end

### 4. Modify name.rb again so that it first asks the user for their first name, saves it into a variable, and then does the same for the last name. Then outputs their full name all at once.

puts "What is your first name?"  
first_name = gets.chomp  
puts "What is your last name?"  
last_name = gets.chomp

puts first_name + " " + last_name

### 5. 

```
x = 0
3.times do
  x += 1
end
puts x
```
Output: 3

```
y = 0
3.times do
  y += 1
  x = y
end
puts x
```
Output: x is not accessible because it is in the inner scope
