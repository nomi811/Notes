# Definitions

### [Arrays](#arrays)
### [Booleans](#booleans)
### [Hashes](#hashes)
### [Integers](#integers)
### [Objects](#objects)
### [Strings](#strings)
### [Symbols](#symbols)
### [Variables](#variables)

##### <a name="arrays">Arrays</a>

Arrays are ordered integer-indexed collection of objects.  They work like a pocket file folder.

`<<` append operator - adds to end of array

`.clear`      - to empty an array
`= []`        - to empty an array
`.inspect`    - returns back the array as a string
`.join`       - puts everything in array and smooshes together as a string
`.join(", ")` - separates with commas
`.split(',')` - splits the objects at the comma and makes each a separate string inside an array

`array.uniq`  - just shows a new array with only the unizue values but doesn't change array
`array.uniq!` - shows just unique values and changes array. Gets rid of duplicates
`array.delete_at(2)`  - deletes array value at the (2) position
`array.delete(4)` - will delete the number "4" from array
`array.push(4)` - will add "4" to end of array
`array.pop` - will delete the last value of array
`array.shift` - deletes first value of array
`array.unshift(1)`  - puts "1" at beginning of array
`array + [9,10,11,12]`  - adds onto the previous array. doesn't change original array

##### <a name="booleans">Booleans</a>

Booleans are true or false statements

##### <a name="hashes">Hashes</a>

Hashes are unordered, object-indexed collections of objects (or key-value pairs)

They are like hanging file folders that can be moved.  They have labels

Use hashes when labels matter

Uses {}

```
person = { 'first_name' => 'Kevin', 'last_name' => 'Smith' }

puts person['first_name']   # Kevin

puts person.index('Kevin')  # first_name

puts person.keys
  # first_name
  # last_name
puts person.values
  # Kevin
  # Smith
puts person.length
  # 2
puts person.size
  # 2
puts person.to_a
  # first_name
  # Kevin
  # last_name
  # Smith
puts person.clear
  # {}
puts person = {}
  # {}

person['gender'] = 'male'

puts person
  # {"gender"=>"male"}
```

##### <a name="integers">Integers</a>

  - Integers  whole numbers
  - Floats    decimal numbers

`**` exponential
`+=` adds and changes assignment of variable

`-200.abs`  # returns 200
`200.next`  # returns 201
`x.class`   # says what class integer is. Fixnum or Bignum

`.round` rounds up
`.to_i`   will round by cutting off decimal values
`.floor` will round down
`.ceil` will round up

##### <a name="objects">Objects</a>

Objects are an instance of a class.

##### <a name="strings">Strings</a>

Sequences of characters that are strung together.

##### <a name="symbols">Symbols</a>

Symbols are labels used to identify a piece of data. They are stored in memory one-time. (Strings are stored in memory each time)

`:test` makes test into a symbol

`hash = { :first_name => 'Kevin', :last_name => "Smith" }`

##### <a name="variables">Variables</a>

Variables are not objects.
  - allow us to keep track of objects
  - are undefined or act like an object
  - point to objects

Variables: scope indicators
```
  - Global    $variable
  - Class     @@variable
  - Instance  @variable
  - Local     variable
  - Block     variable
```
