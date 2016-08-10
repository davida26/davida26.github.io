---
layout: post
title: 22 Ruby Programming Language Examples
category: Ruby
description: Ruby is an open source language focused on simplicity. It provides syntax that is easy to read and compose. 22 Ruby Examples to cover everything you need to get started with Ruby.
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
```ruby
# \\ Backslash
# \' Single Quote
# \" Double Quote
# \a Bell
# \b Backspace
# \c Formfeed
# \n Newline
# \r Carriage
# \t Tab
# \v Vertical Tab
```

## 15. Objects

Everything is an object in ruby.
We model real world objects using classes.
Every object has attributes also called instance variables
Every object capabilities also called methods

```ruby
# initialize with setters and getters (long way)

class Animal
	def initialize
		puts "Creating a new animal"
	end

	def set_name(new_name)
		#instence var @
		@name = new_name
	end

	#getter
	def get_name
		@name
	end

	# get a value
	def name
		@name
	end

	# another way to do a setter method
	def name=(new_name)
		if new_name.is_a?(Numeric)
			puts "Name cant be a number"
		else
			@name = new_name
		end
	end
end

# create a new animal

cat = Animal.new

# set the name - method 1
cat.set_name ("Fluffy")

# get the name - method 1
puts cat.get_name

# way to get name - method 2
puts cat.name

# set the name - method 2
cat.name = "Fluffy"
puts cat.name




#--------------------------
# improved animal class

class Dog
	# attr_accessor creates all the getters and setters
	attr_accessor :name, :height, :weight

	def bark
		return "woof"
	end
end

rover = Dog.new
rover.name = "Rex"

puts rover.name


# inherit from Dog
class GermanShepard < Dog
	# override method
	def bark
		return "loud bark"
	end
end

# create new german shepard
max = GermanShepard.new
max.name = "Max"

# formatted printing
printf "%s goes %s \n", max.name, max.bark()

# %s for string
# %d for integers
# %f for floats
# %.3f would print float with 3 decimals
```

# 16. Modules

- Made up of methods and instance variables
- Cant be instantiated, in other words cant turn them into an object
- Used to add functionality to a class
- Classes can only inherit one class but they <strong>can</strong>
inherit multiple modules
- Modules should be in their own files include with:

```ruby
require_relative file
```

<p><strong>Sample Module 1 - Human.rb</strong></p>
``ruby
# module name human
module Human
	# create getters and setters
	attr_accessor :name, :height, :weight

	# create a method
	def run
		puts self.name + "runs"
	end
end
```

<p><strong>Sample Module 2 - Smart.rb</strong></p>

```ruby
module Smart
	def act_smart
		return "E = MC2"
	end
end
```

<p><strong>Main File with Modules Included</strong></p>

```ruby
require_relative "prg1"
require_relative "prg2"

# create another module to show in different places
# recommended is to add in diff files
module Animal
	def make_sound
		puts "woof"
	end
end

# new class dog that includes the animal module
class Dog
	include Animal
end

rover = Dog.new

rover.make_sound
```

<p><strong>Main File with New Class Added - Uses Prepend</strong></p>

```ruby
#--------------------------------
# create a new class, include the modules

class Scientist
	include Human
	# prepend supercedes all other modules
	prepend Smart

	# example module, overriden by prepend
	def act_smart
		return "e = mc^2"
	end
end

einstein = Scientist.new

einstein.name = "Albert"

puts einstein.name

# run the method
einstein.run

printf "%s says %s", einstein.name, einstein.act_smart()
```

## 17. Polymorphism

- Ruby relies less on the type (class) of an object and more on its capabilities.
- If it walks like a duck and talks like a duck, then Ruby treats it as a duck.
- Statically typed languages use duck typing to achieve polymorphism

```ruby
# We create a class called Bird with a generic method to perform the tweet
class Bird
	def tweet(bird_type)
		bird_type.tweet
	end
end

# Cardinal is created and inherits Bird, tweets
class Cardinal < Bird
	def tweet
		puts "Tweet"
	end
end

# Owl is created and inherits Bird, Hoots
class Owl < Bird
	def tweet
		puts "Hoot Hoot"
	end
end

# now we create the bird
new_bird = Bird.new

# and we pass the type to the tweet method to output the correct sound
# again we create a new bird of each type
new_bird.tweet(Cardinal.new)
new_bird.tweet(Owl.new)
```

## 18. Symbols

- Symbols are strings that cannot be changed
- Useful for string comparison and to conserve memory
- Useful to pass data if the string value doesn't change or requires access to string methods
- Occur as keys in hashes

```ruby
# symbol
:david

# output to see what it looks like
puts :david

# convert to a string
puts :david.to_s

# what type is it? Symbol
puts :david.class

# get the object id
puts :david.object_id
```

## 19. Arrays

```ruby
# Creating arrays
 
array_1 = Array.new
array_2 = Array.new(5) # Gets nil as default
array_3 = Array.new(5, "empty")
array_4 = [1,"two",3,5.5] # You can store multiple object types
 
puts array_1
puts array_2
puts array_3
puts array_4
 
# Indexes start at 0
puts array_4[2]
 
# Return 2 values starting at the 2nd index
puts array_4[2,2].join(", ")
 
# Return values in index 0, 1 and 3
puts array_4.values_at(0,1,3).join(", ")
 
# Add 0 at the beginning of the array
array_4.unshift(0)
puts array_4.join(", ")
 
# Remove the first item in the array
array_4.shift()
puts array_4.join(", ")
 
# Add 100 and 200 to the end of the array
array_4.push(100, 200)
puts array_4.join(", ")
 
# Remove item at the end of the array
array_4.pop
puts array_4.join(", ")
 
# Add one array to the end of another
array_4.concat([10,20,30])
puts array_4.join(", ")
 
# Array Methods
 
puts "Array Size : " + array_4.size().to_s
puts "Array Contains 100 : " + array_4.include?(100).to_s
puts "How Many 100s : " + array_4.count(100).to_s
puts "Array Empty : " + array_4.empty?.to_s
 
# Convert an array into a string
puts array_4.join(", ")
 
# Print and Inspect the array
p array_4
 
# Output array in loop
array_4.each do |value|
  puts value
end
```

## 20. Hashes

- Collection of key value pairs

```ruby
# create key / value pair
number_hash = { "PI" => 3.14,
				"Golden" => 1.619, 
				 "e" => 2.718 }

#output the value of the hash called PI
puts number_hash["PI"]

# Based on the order 
superheroes = Hash["Clark Kent", "Superman", "Bruce Wayne", "Batman"]
puts superheroes["Clark Kent"]

# Add to a hash
superheroes["Barry Allen"] = "Flash"
puts superheroes["Barry Allen"]
 
# Set a default key value
samp_hash = Hash.new("No Such Key")
puts samp_hash["Dog"]
 
superheroines = Hash["Lisa Morel", "Aquagirl", "Betty Kane", "Batgirl"]
 
# Combine 2 hashes in a destructive way with update or with no overwriting
# with merge
 
superheroes.update(superheroines)
 
# Print out each key and value
 
superheroes.each do |key, value|
  puts key.to_s + ' : ' + value
end
 
puts "Has Key Lisa Morel : " + superheroes.has_key?("Lisa Morel").to_s
puts "Has Value Batman : " + superheroes.has_value?("Batman").to_s
puts "Is Hash Empty : " + superheroes.empty?.to_s
puts "Size of Hash : " + superheroes.size.to_s
 
# Delete a key value
 
superheroes.delete("Barry Allen")
 
puts "Size of Hash : " + superheroes.size.to_s
```

## 21. Enumerable

- Allows a class to gains collection capabilities like hashes
- Must include a function called each

```ruby
class Menu
  include Enumerable
 
  # Each provides items one at a time
 
  def each
    yield "pizza"
    yield "spaghetti"
    yield "salad"
    yield "bread"
    yield "water"
  end
end
 
menu_options = Menu.new
 
# We can cycle through all the options
 
menu_options.each do |item|
  puts "Would you like : #{item}"
end
 
# Check to see if we have pizza
p menu_options.find {|item| item == "pizza"}
 
# Return items 5 letters in length
p menu_options.select {|item| item.size <= 5}
 
# Reject items that meet the criteria
p menu_options.reject {|item| item.size <= 5}
 
# Return the first item
p menu_options.first
 
# Return the first 2
p menu_options.take(2)
 
# Return the everything except the first 2
p menu_options.drop(2)
 
# Return the minimum item
p menu_options.min
 
# Return the maximum item
p menu_options.max
 
# Sort the items
p menu_options.sort
 
# Return each item in reverse order
menu_options.reverse_each {|item| puts item}
```

## 22. File Input / Output

```ruby
# Create a file for writing
file = File.new("authors.out", "w")
 
# Add lines
file.puts "William Shakespeare"
file.puts "Agatha Christie"
file.puts "Barbara Cartland"
 
# Close file
file.close
 
# Output everything in the file
puts File.read("authors.out")
 
# Open file for appending
file = File.new("authors.out", "a")
file.puts "Danielle Steel"
file.close
puts File.read("authors.out")
 
# Create another file containing data separated by commas
file = File.new("author_info.out", "w")
file.puts "William Shakespeare,English,plays and poetry,4 billion"
file.puts "Agatha Christie,English,who done its,4 billion"
file.puts "Barbara Cartland,English,romance novels,1 billion"
file.puts "Danielle Steel,English,romance novels,800 million"
file.close
 
# Cycle through the data to write a sentence
File.open("author_info.out") do |record|
  record.each do |item|
 
    # Split each line into 4 parts based on commas
    name, lang, specialty, sales = item.chomp.split(',')
    puts "#{name} was an #{lang} author that specialized in #{specialty}. They sold over #{sales} books."
  end
end
```
