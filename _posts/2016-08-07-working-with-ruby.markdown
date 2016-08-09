---
layout: post
title: Working with the Ruby Programming Language
category: Ruby
description: Ruby is an open source language focused on simplicity. It provides syntax that is easy to read and compose. Ideal for web development using the Ruby on Rails web framework.
---

# Getting Started

For an indepth overview of Ruby, please visit the official [Ruby Website.](https://www.ruby-lang.org/en/) Tutorials on how to setup Ruby can also be found there. This will concentrate on code samples showing key Ruby concepts and syntax.


## Code Samples
<hr>


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

## Run the File in the Terminal
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

<p><strong>Operators &amp; Usage</strong></p>
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

## 8. Loops

<p><strong>Loop Do</strong></p>

```ruby
# print even numbers on the screen
# next is like continue

x = 1

loop do 
	x += 1

	# check if its an even number and print it
	next unless (x % 2) == 0
	puts x
	break if x >= 10
end
```

<p><strong>While</strong></p>

```ruby
## same as do, get even numbers and output

y = 1

while y <= 10
	y += 1
	next unless (y % 2) == 0
	puts y
end
```

<p><strong>Until</strong></p>

```ruby
# until - do something until condition is met

a = 1

until a >= 10
	a += 1
	next unless (a % 2) == 0
	puts a
end
```

<p><strong>Loop Through An Array</strong></p>

```ruby
numbers = [1,2,3,4,5]

for number in numbers
	puts "#{number}"
end
```

<p><strong>Cycle Through Numbers 0 to 5</strong></p>

```ruby
# loop from 0 to 5 and output the number
(0..5).each do |i|
	puts "# #{i}"
end
```

## 9. Functions

- Variables are passed by value, value cannot be changed inside function

```ruby
# function to add two numbers
def add_nums(num_1, num_2)
	return num_1.to_i + num_2.to_i
end

puts add_nums(3,4)

# function to change variable
# value to change inside a function will not affect the outside value
x = 1

def change_x(x)
	x = 4
end

change_x(x)

puts "x is equal to: #{x}"
```

## 10. Exceptions

```ruby
# get two numbers and divide them, catch an exception if division by zero

print "Enter a number: "

firstNum = gets.to_i

print "Enter another number: "

secondNum = gets.to_i

begin
	answer = firstNum / secondNum

rescue
	puts "You cant divide by zero"
	exit
end

puts "#{firstNum} / #{secondNum} = #{answer}"
```

<p><strong>Exceptions: Raise ArgumentError</strong></p>

```ruby
# throw exception with raise

age = 12

def check_age(age)
	raise ArgumentError, "Enter Positive Number" unless age > 0
end

begin
	check_age(-1)
rescue ArgumentError
	puts "That is an impossible age"
end
```

## 11. String Functions

```ruby
# double quotes - outputs correctly, including interpolation
puts "Add Them #{4+5} \n\n"

# single quotes - outputs as literal
puts 'Add Them #{4,5} \n\n'

# manipulate strings
firstName = "John"
lastName = "Smith"

fullName = firstName + lastName

middleName = "Joseph"

fullName = "#{firstName} #{middleName} #{lastName}"

puts fullName

# does it include this? True/False
puts fullName.include?("Joseph")

#output total size of string
puts fullName.size

# count how many vowels
puts "Vowels : " + fullName.count("aeiou").to_s

# count how many consonants (exclude aeiou)
puts "Consonants : " + fullName.count("^aeiou").to_s

# does the name start with this? True/False
puts fullName.start_with?("Joh")

# At what index pos does Smith start?
puts "Index : " + fullName.index("Smith").to_s

# tranform to uppercase
puts fullName.upcase

# tranform to lowercase
puts fullName.downcase

# tranform to varying case
puts fullName.swapcase

# strip whitespace left and right
fullName = "         " + fullName

# remove whitespace on the left
fullName = fullName.lstrip

#remove whitespace on the right
fullName = fullName.rstrip

#remove all whitespace left and right
fullName = fullName.strip

# adds dots before text. value is string total
puts fullName.rjust(20, '.')

# adds dots after text. value is string total
puts fullName.ljust(20, '.')

# adds dots l/r of text. value is string total
puts fullName.center(20, '.')

# chop off the last letter
puts fullName.chop

# chomp the last new line, with param remove the last letters 
puts fullName.chomp('th')

# delete specific letters
puts fullName.delete("o")

# split into array - split at every new character
nameArray = fullName.split(//)
puts nameArray

# split into array - split at every space
nameArray = fullName.split(/ /)
puts nameArray
```

## 12. HEREDOC

Outputs everything in same format including new lines

```ruby
multiline_string = <<EOM
This is a very long string
that contains
interpolation like #{4 + 5} \n\n
EOM

puts multiline_string
```

## 13. Data Conversions

```ruby
# to string
to_s

# to integer
to_i

# to float
to_f

# to symbol
to_sym
```

## 14. Escape Sequences
/\\ Backslash
/\' Single Quote
/\" Double Quote
/\a Bell
/\b Backspace
/\c Formfeed
/\n Newline
/\r Carriage
/\t Tab
/\v Vertical Tab

## 15. Objects

Everything is an object in ruby.
We model real world objects using classes.
Every object has attributes also called instance variables
Every object capibilities also called methods


