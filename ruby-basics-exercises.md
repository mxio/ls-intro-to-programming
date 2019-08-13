### 2. Locate the description of the while loop in the ruby documentation.
It is in Control Expressions which can be found in Table of Content in Pages at ruby-lang.org or can be in the left-hand sidebar after selecting a version of Ruby on ruby-lang.org

### 5. Using the ruby documentation, determine how you can write large numbers in a way that makes them easier to read.
Use literals to write large numbers with underscores replacing commas or any way you'd like to make it readable.

# Reading Documentation 2
### 3. Assume you have the following code:
```
s = 'abc def ghi,jkl mno pqr,stu vwx yz'
puts s.split.inspect
puts s.split(',').inspect
puts s.split(',', 2).inspect
```

What will each of the 3 puts statements print?
Solution

```
# puts s.split.inspect
["abc", "def", "ghi,jkl", "mno", "pqr,stu", "vwx", "yz"]

# puts s.split(',').inspect
["abc def ghi", "jkl mno pqr", "stu vwx yz"]


# puts s.split(',', 2).inspect
["abc def ghi", "jkl mno pqr,stu vwx yz"]
# only the first two. The second returns the full string even with the third comma
```
