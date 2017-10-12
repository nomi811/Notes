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



##### <a name="arrays">Arrays</a>

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

Adds the numbers of an array together.
```
numbers = [5, 2, 8]
sum = 0

numbers.each do |n|
  sum += n
end

puts sum

// 15
```

capitalizes each string in an array
```
['ryan', 'jane'].each { |string| puts "#{string[0].upcase}#{string[1..-1]}" }

// Ryan
// Jane
```

The block, `{ |i| puts i }`, is passed the current array item each time it is evaluated.  This block prints the item multiplied by 5.

```
[1,2,3,4,5].each { |i| puts i * 5 }

// 5
// 10
// 15
// 20
// 25
```

This block prints the number 5 for each item. (It chooses to ignore the passed item, which is allowed.)
```
[1,2,3,4,5].each { |i| puts 5 }

// 5
// 5
// 5
// 5
// 5
```

##### <a name="array.sort">array.sort</a>

Sorts the numbers in order starting with 1.
```
my_array = [3,4,8,7,1,6,5,9,2]
puts my_array
puts
my_array.sort!
puts my_array
```

Sorts the words in alphabetical order starting with "A"
```
my_array = ["sara", 'benny', 'ralph', 'eric', 'albert']
puts my_array
puts
my_array.sort!
puts my_array

// sara
// benny
// ralph
// eric
// albert

// albert
// benny
// eric
// ralph
// sara
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

##### <a name="hashes">Hashes</a>

a hash is a collection of key-value pairs

```
hash = {
  key1 = value1,
  key2 = value2,
  key3 = value3
}
```
hash literal notation
```
new_hash = { "one " => 1 }
```

hash constructor notation
```
new_hash = Hash.new

OR

new_hash = Hash.new("goofy goober")  # puts what's in the parenthesis into the hash
```

iterating over a hash
```
my_hash.each do |key, value|
  puts key, my_hash[key]
end
```
```
matz = {"First name" => "Yukihiro",
        "Last name" => "Matsumoto",
        "Age" => 47,
        "Nationality" => "Japanese",
        "Nickname" => "Mate"
}

matz.each do |key, value|
  puts value        # gives only the value
end

// Yukihiro
// Matsumoto
// 47
// Japanese
// Mate
```
```
menagerie = {
  :foxes => 2,
  :weezards => 17,
  :elves => 1,
  :canaries => 4,
  :ham => 1
}

puts "string".object_id   # 70304701738880
puts "string".object_id   # 70304701737680
puts :symbol.object_id    # 807708
puts :symbol.object_id    # 807708
```
```
strings = ["one", "two", "three", "four"]
symbols = []
strings.each do |s|
  symbols.push(s.to_sym)  # or .intern to internalize the string into a symbol
end

print symbols

// [:one, :two, :three, :four]
```
```
:hello.to_s       # "hello"
"hello".to_sym    # :hello
```
```
symbol_hash = {
  :one    => 1,
  :two    => 2,
  :three  => 3
}

SAME AS
NEW SYNTAX

new_hash = {
  one:    1,
  two:    2,
  three:  3
}
```
```
grades = {
  alice:  100,
  bob:    92,
  chris:  95,
  dave:   97
}

puts grades.select { |name, grade| grade < 97 }   // {:bob=>92, :chris=>95}

puts grades.select { |k, v| k == :alice }   // {:alice=>100}
```
```
require 'benchmark'

string_AZ = Hash[("a".."z").to_a.zip((1..26).to_a)]
symbol_AZ = Hash[(:a..:z).to_a.zip((1..26).to_a)]

string_time = Benchmark.realtime do
  100_000.times { string_AZ["r"] }
end

symbol_time = Benchmark.realtime do
  100_000.times { symbol_AZ[:r] }
end

puts "String time: #{string_time} seconds."
puts "Symbol time: #{symbol_time} seconds."

// String time: 0.0121277219732292 seconds.
// Symbol time: 0.00839714301400818 seconds.
```
```
movie_ratings = {
  memento:      3,
  primer:       3.5,
  the_matrix:   5,
  truman_show:  4,
  red_dawn:     1.5,
  skyfall:      4,
  alex_cross:   2,
  uhf:          1,
  lion_king:    3.5
}

good_movies = movie_ratings.select { |k, v| v > 3 }
puts good_movies

// {:primer=>3.5, :the_matrix=>5, :truman_show=>4, :skyfall=>4, :lion_king=>3.5}

movie_ratings.each_key { |k| puts k, " " }    # just prints keys

movie_ratings.each_value { |v| puts v, " " }  # just prints values
```
A Program to keep track of movies and ratings
```
movies = {
  Memento:  3,
  Primer:   4,
  Ishtar:   1
}

puts "What would you like to do?"
puts "-- Type 'add' to add a movie."
puts "-- Type 'update' to update a movie."
puts "-- Type 'display' to display all movies."
puts "-- Type 'delete' to delete a movie."

choice = gets.chomp.downcase
case choice
when 'add'
  puts "What movie do you want to add?"
  title = gets.chomp
  if movies[title.to_sym].nil?
    puts "What's the rating? (Type a number 0 to 4.)"
    rating = gets.chomp
    movies[title.to_sym] = rating.to_i
    puts "#{title} has been added with a rating of #{rating}."
  else
    puts "That movie already exists! It's rating is #{movies[title.to_sym]}."
  end
when 'update'
  puts "What movie do you want to update?"
  title = gets.chomp
  if movies[title.to_sym].nil?
    puts "Movie not found."
  else
    puts "What's the new rating? (Type a number 0 to 4.)"
    rating = gets.chomp
    movies[title.to_sym] = rating.to_i
    puts "#{title} has been updated with new rating of #{rating}."
  end
when 'display'
  movies.each do |movie, rating|
    puts "#{movie}: #{rating}"
  end
when 'delete'
  puts "What movie do you want to delete?"
  title = gets.chomp
  if movies[title.to_sym].nil?
    puts "Movie not found!"
  else
    movies.delete(title.to_sym)
    puts "#{title} has been removed."
  end
else
  puts "Sorry, I didn't understand you."
end

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

Method checks to see if an integer is prime. Runs through the numbers 2 through the number minus 1 and divides the number by them. If any of the answers has no remainder, it says it is not prime.  If any have all remainders, it says it is prime.
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

Method that squares a number that is put in.
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

Method that capitalizes a word
```
def capitalize(string)
  puts "#{string[0].upcase}#{string[1..-1]}"
end

capitalize('ryan')      // Ryan
capitalize('jane')      // Jane
capitalize('michAel')   // MichAel
```

###### <a name="compair_operators">Compair Operators</a>
`<=>` compairs two objects numerically or alphabetically

shows `0` if they are equal
shows `-1` if first is less than second
shows `1` if first is greater than second

```
def alphabetize(arr, rev=false)
  if rev
    arr.sort { |item1, item2| item2 <=> item1 }   # decending order
  else
    arr.sort { |item1, item2| item1 <=> item2 }   # acending order
  end
end

books = ['Pride and Prejudice', 'Sense and Sensibility', 'Emma', 'Mansfield Park']

puts "A-Z: #{alphabetize(books)}"
puts "Z-A: #{alphabetize books, true}"

// A-Z: ["Emma", "Mansfield Park", "Pride and Prejudice", "Sense and Sensibility"]
// Z-A: ["Sense and Sensibility", "Pride and Prejudice", "Mansfield Park", "Emma"]
```

To put numbers in order from smallest to largest
```
def alphabetize(arr, rev=false)
  arr.sort!
end

numbers = [5,6,2,4]

puts alphabetize(numbers)

// 2
// 4
// 5
// 6
```
```
def alphabetize(arr, rev=false)
  arr.sort!
  if rev
    arr.reverse!
  else
    arr.sort!
  end
end

numbers = [5,1,3,8]

puts alphabetize(numbers)

// 1
// 3
// 5
// 8
```
```
def alphabetize(arr, rev=false)
  arr.sort!
  if rev
    arr.reverse!
  else
    arr.sort!
  end
end

numbers = [5,1,3,8]

puts alphabetize(numbers, true)

// 8
// 5
// 3
// 1
```
