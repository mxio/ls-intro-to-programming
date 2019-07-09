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
puts "Hello " + name

10.times do |n|
puts name
end
