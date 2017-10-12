# Topics

### [Loops and Iterators](#loops_iterators)
* [.each iterator](#each_iterator)
* [.times iterator](#times_iterator)
* [while loop](#while_loop)
* [until loop](#until_loop)
* [for loop](#for_loop)

### [Arrays](#arrays)
  - [array.sort](#array.sort)

### [Hashes](#hashes)
  - [literal notation](#literal_notation)

### [Histogram](#histogram)
### [Methods](#methods)
### [Splat Arguments](#splat_arguments)
### [Return](#return)
### [Operators](#operators)
  - [Compair Operators](#compair_operators)
  - [Conditional Assignment](#conditional_assignment)

```
print "Integer please: "
user_num = Integer(gets.chomp)

if user_num < 0
  puts "You picked a negative integer!"
elsif user_num > 0
  puts "You picked a positive integer!"
else
  puts "You picked zero!"
end
```
```
print "Thtring, pleathe!: "
user_input = gets.chomp
user_input.downcase!

if user_input.include? "s"
  user_input.gsub!(/s/, "th")
else
  puts "nothing to do here!"
end

puts "Your string is: #{user_input}"
```
```
counter = 1
while counter < 11
  puts counter
  counter = counter + 1
end

OR

counter = 1
until counter > 10
  puts counter
  counter += 1
end
```
`+=` assignment operator. Add 1 to counter, then assign the new value back to counter

When you know exact number of loops
```
for num in 1...10
  puts num
end
```
`...` - don't include highest number in range
`..` - include highest number in range




##### Hiding information

```
puts "Text to search through: "
text = gets.chomp
puts "Word to redact: "
redact = gets.chomp

words = text.split(" ")

words.each do |word|
  if word != redact
    print word + " "
  else
    print "REDACTED"
  end
end
```



##### <a name="histogram">Histogram</a>
```
puts "Text please: "
text = gets.chomp

words = text.split(" ")

frequencies = Hash.new(0)

words.each { |word| frequencies[word] += 1 }

frequencies = frequencies.sort_by { |a, b| b }

frequencies.reverse!

frequencies.each { |word, frequency| puts word + " " + frequency.to_s }

// Text please:
// sit in the car and sit in the house
// the 2
// in 2
// sit 2
// house 1
// and 1
// car 1
```



##### <a name="splat_arguments">Splat Arguments</a>

`*` splat signals to Ruby that we don't know how many there are going to be, but it could be more than one.
```
def friend(*name)
  puts "My friend is " + name.to_s + "."
end

friend("Bob", "Sammy", "Eric", "Ralph")

// My friend is ["Bob", "Sammy", "Eric", "Ralph"].

def what_up(greeting, *bros)
  bros.each { |bro| puts "#{greeting}", "#{bro}!" }
end

what_up("What up", "Justin", "Ben", "Kevin Sorbo")

// What up
// Justin!
// What up
// Ben!
// What up
// Kevin Sorbo!
```
Only one greeting `"What up"`, multiple names `"Justin", "Ben", "Kevin Sorbo"`


##### <a name="return">Return</a>

```
def double(n)
  return n * 2
end

output = double(6)
output += 2
puts output

// 14
```
