# Topics

### [Loops and Iterators](#loops_iterators)
* [.each iterator](#each_iterator)
* [.times iterator](#times_iterator)
* [while loop](#while_loop)
* [until loop](#until_loop)
* [for loop](#for_loop)
* [arrays](#arrays)
* [hashes](#hashes)
  - [literal notation](#literal_notation)

### [Histogram](#histogram)
### [Methods](#methods)
### [Splat Arguments](#splat_arguments)
### [Return](#return)

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

#### <a name="loops_iterators">Loops & Iterators</a>

Repeat an action using an **iterator**. Iterator invokes a block of code.  The code block is just the bit that contains the instructions to be repeated. When you loop over an array or a hash, you say that you *iterate* over it.

```
i = 0
loop do
  i += 1
  print "#{i}"
  break if i > 5
end
```

Prints just odd numbers
```
for i in 1..5
  next if i % 2 == 0
  print i
end
```
Prints just even numbers
```
for i in 1..5
  next if i % 2 != 0
  print i
end
```

##### <a name="each_iterator">.each iterator</a>
```
array = [1,2,3,4,5]

array.each do |x|
  x += 10
  print "#{x}"
end

// 1112131415
```

##### <a name="times_iterator">.times iterator</a>
```
10.times {print "Chunky bacon!"}

OR

10.times do
  print "Chunky bacon!"
end

// Will print Chunky bacon! 10 times with no spaces after exclamation point.
```

##### <a name="while_loop">while loop</a>

```
i = 3

while i > 0 do
  print i
  i -= 1
end

// 321
```

##### <a name="until_loop">until loop</a>

```
i = 3

until i == 0 do
  print i
  i -= 1
end

// 321
```

##### <a name="for_loop">for loop</a>

```
for k in 1..3
  print k
end

// 123
```

##### <a name="arrays">arrays</a>

```
[1,2,3,4,5]
 0 1 2 3 4 index numbers

```
```
array = [1,2,3,4,5]

print array[2]

// 3
```

 string array `["hello", "car", "dog"]`
 2 dimensional array - array of arrays - multidimensional `[[0,0,0,0], [0,0,0,0,], [0,0,0,0], [0,0,0,0]]`
```
multi_d_array = [[1,2,3,4], [5,6,7,8], [9,10,11,12]]

multi_d_array.each { |x| puts "#{x}\n"}

//  [1, 2, 3, 4]
    [5, 6, 7, 8]
    [9, 10, 11, 12]

print multi_d_array[1][3]

// 8
```

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

##### <a name="hashes">hashes</a>

a hash is a collection of key-value pairs

```
hash = {
  key1 = value1,
  key2 = value2,
  key3 = value3
}
```
###### <a name="literal_notation">literal notation</a>
```
my_hash = { "name"    => "Eric",
            "age"     => 26,
            "hungry?" => true
}

puts my_hash["name"]    // Eric
puts my_hash["age"]     // 26
puts my_hash["hungry?"] // true
```

`Hash.new` makes a new, empty hash
```
sounds = Hash.new
sounds["dog"] = "woof"
sounds["cat"] = "meow"

puts sounds["dog"]    // woof

OR

prices = {
  "apple" => 0.52,
  "banana" => 0.23,
  "kiwi" => 1.42
}
```

```
friends = ["Milhouse", "Ralph", "Nelson", "Otto"]

family = {
  "Homer" => "dad",
  "Marge" => 'mom',
  'Lisa' => 'sister',
  'Maggie' => 'sister',
  'Abe' => 'grandpa',
  "Santa's Little Helper" => 'dog'
}

friends.each { |name| puts name }
// Milhouse
// Ralph
// Nelson
// Otto

friends.each { |x| puts "#{x}" }
// Milhouse
// Ralph
// Nelson
// Otto

family.each { |x, y| puts "#{x}: #{y}" }
// Homer: dad
// Marge: mom
// Lisa: sister
// Maggie: sister
// Abe: grandpa
// Santa's Little Helper: dog
```
```
restaurant_menu = {
  'noodles' => 4,
  'soup' => 3,
  'salad' => 2
}

restaurant_menu.each do |item, price|
  puts "#{item}: #{price}"
end

// noodles: 4
// soup: 3
// salad: 2

restaurant_menu = Hash.new
restaurant_menu ['noodles'] = 4
restaurant_menu ['soup'] = 3
restaurant_menu ['salad'] = 2

restaurant_menu.each do |item, price|
  puts "#{item}: #{price}"
end

// noodles: 4
// soup: 3
// salad: 2

restaurant_menu.each { |item, price| puts price }

// 4
// 3
// 2
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

##### <a name="methods">Methods</a>

```
def prime(n)
  puts "That's not an integer." unless n.is_a? Integer
  is_prime = true
  for i in 2..n - 1
    if n % i == 0
      is_prime = false
    end
  end

  if is_prime
    puts "#{n} is prime!"
  else
    puts "#{n} is not prime."
  end
end

prime(2)
prime(9)
prime(11)
prime(51)
prime(97)
prime(18)

// 2 is prime!
// 9 is not prime.
// 11 is prime!
// 51 is not prime.
// 97 is prime!
// 18 is not prime.
```
```
def array_of_10
  puts (1..10).to_a
end

array_of_10

// 1
// 2
// 3
// 4
// 5
// 6
// 7
// 8
// 9
// 10
```
```
def square(n)
  puts n ** 2
end

square(12)
square(3)
square(8)

// 144
// 9
// 64
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
```
def greeter(name)
  return "Hello, " + name + "!"
end

output = greeter("Nomi")
puts output

// Hello, Nomi!
```
```
def by_three?(number)
  return number % 3 == 0
end

output = by_three?(9)
puts output

output = by_three?(7)
puts output

// true
// false
```
