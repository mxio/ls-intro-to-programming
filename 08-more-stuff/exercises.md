# Exercises

### 1. Write a program that checks if the sequence of characters "lab" exists in the following strings. If it does exist, print out the word.

```
def check_for_lab(word)
  if word =~ /lab/
    puts "#{word} has 'lab' in it!"
  else
    puts "#{word} doesn't have 'lab' in it"
  end
end

check_for_lab("laboratory")
check_for_lab("experiment")
check_for_lab("Pans Labyrinth")
check_for_lab("elaborate")
check_for_lab("polar bear") 
```

### 2. What will the following program print to the screen? What will it return?

```
def execute(&block)
  block
end

execute { puts "Hello from inside the execute method!" }
```
It won't execute anything because there is no .call method for the block. (The solution says it returns a Proc object instead).

### 3. What is exception handling and what problem does it solve?
Exception handling is used to indicate errors when an error occurs. This allows the code following the error to run instead of being stuck on the error or exiting.

### 4. Modify the code in exercise 2 to make the block execute properly.

```

def execute(&block)
  block.call
end

execute { puts "Hello from inside the execute method!" }
```

### 5. Why does the following code...

```
def execute(block)
  block.call
end

execute { puts "Hello from inside the execute method!" }
```
Give us the following error when we run it?

```
block.rb1:in `execute': wrong number of arguments (0 for 1) (ArgumentError)
from test.rb:5:in `<main>'
```

There is no & before 'block' to indicate that a block is being passed.
