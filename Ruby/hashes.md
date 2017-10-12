# <a name="top">Hashes</a>

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

:point_up:[top](#top)
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

:point_up:[top](#top)
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

:point_up:[top](#top)
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

:point_up:[top](#top)
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
###### <a name="literal_notation">literal notation</a> :point_up:[top](#top)

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

:point_up:[top](#top)
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

:point_up:[top](#top)
