# Arrays

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
