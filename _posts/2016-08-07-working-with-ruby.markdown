---
layout: post
title: Working with the Ruby Programming Language
category: Ruby
description: Ruby is an open source language focused on simplicity. It provides syntax that is easy to read and compose. Ideal for web development using the Ruby on Rails web framework.
---

# Getting Started

For an indepth overview at what ruby is please visit the official [Ruby Website](https://www.ruby-lang.org/en/)


## Code Samples

Designed to show an introduction to key concepts.


### 1. Variables, Output & Calculations

Prompt the user to enter 2 numbers, store it in variables and perform calculation.

Print - does not output to a new line
Puts  - creates a new line

<h3>Code</h3>
```ruby
# prints the text
print "Enter a Value: "

# gets the user input
# to_i converts to an integer
first_num = gets.to_i

print "Enter Another Value: "

second_num = gets.to_i

# to_s converts back to string
puts first_num.to_s + " + " + second_num.to_s + " = " + 
(first_num + second_num).to_s
```

# Run the File in the Terminal
```bash
ruby myNumber.rb
```

### 2. Float Arithmetic

Always slightly off after 14 digits

```ruby
big_float = 1.12345678901234

puts ( big_float + 0.0000000000005).to_s
```

Will be slightly off at the end.

### 3. Check type of data

Everything inside Ruby is an object. Can be proved by:

```ruby
puts 1.class
puts 1.234.class
puts "MYString".class
```


### 4. Writing to a File, Reading and Outputting Content

```ruby
# Create a new file if it doesnt exist and write to it
write_handler = File.new("myTextFile.out", "w")

# Add content to the file and convert to string
write_handler.puts("My Content").to_s

# Close the file after editing
write_handler.close

# Read the file and store the contents to a var
data_from_file = File.read("myTextFile.out")

# Output what is stored
puts "Data From File:" + data_from_file
```

### 5. Execute code from a file

```ruby
load "prg1.rb"
```

### 6. Comments

```ruby
=begin
Multiline
Comment
=end
```

### 7. Conditional Operations

```ruby
puts "Enter Your Age: "

myAge = gets.to_i

if (myAge >= 5) && (myAge <= 6)
	puts "Youre in Kindergarten"
elsif (myAge >= 7) && (myAge <= 13)
	puts "Youre in Middle School"
	puts "Yeah"
else
	puts "Stay Home"
end
```

<p><strong>Operator &amp; Usage</strong></p>
<p>Comparison: == != < > <= >=</p>
<p>Logical: && || ! and or not</p>

```ruby
puts "true && false = " + (true && false).to_s
puts "true || false = " + (true || false).to_s
puts "!false = " + (!false).to_s

# Comparison
=begin
returns 0 if equal
1 if first is greater
-1 if first is less than
=end
puts "5 <=> 10 = " + (5 <=> 10).to_s


age = 12

# unless age is different from greater than 4
# executes first line only if age is less than 4
unless age > 4
	puts "no school"
else
	puts "go to school"
end

puts "You're Young" if age < 30
```

<p><strong>Case Statements</strong></p>

```ruby
age = 12

print "Enter a Greeting"

# chomp removes the new line added
greeting = gets.chomp

case greeting
when "French", "french"
	puts " Bonjour"
	exit
when "Spanish", "spanish"
	puts "Hola"
	exit
else
	puts "Hello"
end
```

<p><strong>Ternary Operator</strong></p>

```ruby
age = 12

# if age is greater than or equal to 50
# return old if true
# otherwise if false return young
puts (age >= 50) ? "Old" : "Young"
```